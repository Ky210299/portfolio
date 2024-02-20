<template>
	<HeaderContainer />
	<ProfileContainer />
	<main class="main">
		<About/>
		<Projects />
	</main>
	<AppFooter/>
	
</template>

<script lang="ts" setup>
	import HeaderContainer from "./components/HeaderContainer.vue";
	import ProfileContainer from "./components/ProfileContainer.vue";
	import Projects from "./views/Projects.vue";
	import About from "./views/About.vue"
	import AppFooter from "./components/AppFooter.vue";
	// import Background from "./components/Background.vue";
</script>

<style scoped>
</style>
