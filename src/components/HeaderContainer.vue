<script lang="ts">

import { defineComponent } from 'vue'
import MenuDeployed from './MenuDeployed.vue';
import IconDeployerMenu from './icons/IconDeployerMenu.vue';
export default defineComponent({
  setup() {
  },
  components: { MenuDeployed, IconDeployerMenu}
})

</script>
 
 ««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
  <div class="container-header-bar nav-top">
  <header >
   <div class="container-left">
    <svg width="40" height="40" >
      <circle cx="20" cy="20" r="20" fill="green"></circle>
    </svg>
    <em>Leonardo Bazan Marquez</em>
   </div> 
   </header>
   <div class="container-right">
    <IconDeployerMenu/>
    <MenuDeployed/>
    
   </div>
  </div>
</template>

 
 ««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
.container-left{
justify-self: flex-end;
justify-content: space-between;
display: flex;
flex-flow: row nowrap;
gap: .5rem;
 svg{
  flex-shrink: 0;
 }

}
.container-right{
 justify-self: flex-start;
 display: flex;
 flex-flow: row-reverse nowrap;
 justify-content: space-between;
}

.nav-top{
display: flex;
flex-flow: row nowrap;
justify-content: space-around;
}

</style>

