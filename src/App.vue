<template>
	<div ref="test"  class="scroll">
		<HeaderContainer  />
		<Home id="home" />
		<main class="main" id="projects">
			<Projects  />
		</main>
		<Contact/>
		<About />	
	</div>
</template>

<script lang="ts" setup>
	
	import HeaderContainer from "./components/HeaderContainer.vue";
	import Home from "./views/Home.vue";
	import Projects from "./views/Projects.vue";
	import Contact from "./views/Contact.vue";
	import About from "./views/About.vue";


	
</script>
<style scoped>
	
</style>
