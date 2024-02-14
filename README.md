# Vue 3 + TypeScript + Vite

This template should help get you started developing with Vue 3 and TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Type Support For `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin) to make the TypeScript language service aware of `.vue` types.

If the standalone TypeScript plugin doesn't feel fast enough to you, Volar has also implemented a [Take Over Mode](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669) that is more performant. You can enable it by the following steps:

1. Disable the built-in TypeScript Extension
   1. Run `Extensions: Show Built-in Extensions` from VSCode's command palette
   2. Find `TypeScript and JavaScript Language Features`, right click and select `Disable (Workspace)`
2. Reload the VSCode window by running `Developer: Reload Window` from the command palette.

## Project style reference

### User component names should always be multi-word, except for root App

components. This prevents conflicts with existing and future HTML elements, since all HTML elements are a single word.

### Use detailed prop definitions​

In committed code, prop definitions should always be as detailed as possible, specifying at least type(s).

#### Bad

// This is only OK when prototyping
const props = defineProps(['status'])

#### Nice
```
const props = defineProps({
  status: String
})
```
##### Even better

```
const props = defineProps({
  status: {
    type: String,
    required: true,

    validator: (value) => {
      return ['syncing', 'synced', 'version-conflict', 'error'].includes(
        value
      )
    }
  }
})
```

## Use keyed v-for

key with v-for is always required on components, in order to maintain internal component state down the subtree. Even for elements though, it's a good practice to maintain predictable behavior, such as object constancy in animations.

## Avoid v-if with v-for​

Never use v-if on the same element as v-for.

There are two common cases where this can be tempting:

To filter items in a list (e.g. v-for="user in users" v-if="user.isActive"). In these cases, replace users with a new computed property that returns your filtered list (e.g. activeUsers).

To avoid rendering a list if it should be hidden (e.g. v-for="user in users" v-if="shouldShowUsers"). In these cases, move the v-if to a container element (e.g. ul, ol).

use scoped or modules styles

## Filenames of Single-File Components should either be always PascalCase

components/
|- AppButton.vue
|- AppTable.vue
|- AppIcon.vue

## Tightly coupled component names

components/
|- TodoList.vue
|- TodoListItem.vue
|- TodoListItemButton.vue

## Order of words in component names

Component names should start with the highest-level (often most general) words and end with descriptive modifying words.

components/
|- SearchButtonClear.vue
|- SearchButtonRun.vue
|- SearchInputExcludeGlob.vue
|- SearchInputQuery.vue
|- SettingsCheckboxLaunchOnStartup.vue
|- SettingsCheckboxTerms.vue

## Component name casing in templates
```
   <!-- In Single-File Components and string templates -->

   <MyComponent/>
```
template
```
<!-- In in-DOM templates -->
<my-component></my-component>
```
OR

template
```
<!-- Everywhere -->
<my-component></my-component>
```
## Component names should prefer full words over abbreviations

## Prop name casing​

Prop names should always use camelCase during declaration. When used inside in-DOM templates, props should be kebab-cased.

### Bad
```
const props = defineProps({
  'greeting-text': String
})
```
template
```
// for in-DOM templates
<welcome-message greetingText="hi"></welcome-message>
```
### Good
```
const props = defineProps({
  greetingText: String
})
```
template
```
// for SFC - please make sure your casing is consistent throughout the project
// you can use either convention but we don't recommend mixing two different casing styles
<WelcomeMessage greeting-text="hi"/>
// or
<WelcomeMessage greetingText="hi"/>
```
template
```
// for in-DOM templates
<welcome-message greeting-text="hi"></welcome-message>
```
## Multi-attribute elements​

Elements with multiple attributes should span multiple lines, with one attribute per line.

### Bad
```
template
<img src="https://vuejs.org/images/logo.png" alt="Vue Logo">
template
<MyComponent foo="a" bar="b" baz="c"/>
```
### Good

template
```
<img
  src="https://vuejs.org/images/logo.png"
  alt="Vue Logo"
>
```
template
```
<MyComponent
  foo="a"
  bar="b"
  baz="c"
/>
```
## Simple expressions in templates​

Component templates should only include simple expressions, with more complex expressions refactored into computed properties or methods.

### Bad
```
template
{{
  fullName.split(' ').map((word) => {
    return word[0].toUpperCase() + word.slice(1)
  }).join(' ')
}}
```
### Good

template
``` 
<!-- In a template -->
{{ normalizedFullName }}
```
js
```
// The complex expression has been moved to a computed property
const normalizedFullName = computed(() =>
  fullName.value
    .split(' ')
    .map((word) => word[0].toUpperCase() + word.slice(1))
    .join(' ')
)
``` 
## Simple computed properties​

Complex computed properties should be split into as many simpler properties as possible.

### Bad

js
const price = computed(() => {
  const basePrice = manufactureCost.value / (1 - profitMargin.value)
  return basePrice - basePrice * (discountPercent.value || 0)
})

### Good

js
const basePrice = computed(
  () => manufactureCost.value / (1 - profitMargin.value)
)

const discount = computed(
  () => basePrice.value * (discountPercent.value || 0)
)

const finalPrice = computed(() => basePrice.value - discount.value)

## Quoted attribute values​

Non-empty HTML attribute values should always be inside quotes (single or double, whichever is not used in JS).

### Bad

template
<input type=text>
template
<AppSidebar :style={width:sidebarWidth+'px'}>

### Good

template
<input type="text">
template
<AppSidebar :style="{ width: sidebarWidth + 'px' }">

## Directive shorthands​

Directive shorthands (: for v-bind:, @ for v-on: and # for v-slot) should be used always or never.

## Single-File Components should always order <script>, <template>, and <style> tags consistently

## Prefer class selectors over element selectors in scoped

## Element attribute order​

The attributes of elements (including components) should be ordered consistently.

This is the default order we recommend for component options. They're split into categories, so you'll know where to add custom attributes and directives.

### Definition (provides the component options)

is

### List Rendering (creates multiple variations of the same element)

v-for

### Conditionals (whether the element is rendered/shown)

v-if
v-else-if
v-else
v-show
v-cloak

### Render Modifiers (changes the way the element renders)

v-pre
v-once

### Global Awareness (requires knowledge beyond the component)

id

### Unique Attributes (attributes that require unique values)

ref
key

### Two-Way Binding (combining binding and events)

v-model

### Other Attributes (all unspecified bound & unbound attributes)

### Events (component event listeners)

v-on

### Content (overrides the content of the element)

v-html
v-text

## Empty lines in component/instance options
