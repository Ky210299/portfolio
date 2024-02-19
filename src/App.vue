<template>
	<HeaderContainer />
	<ProfileContainer />
	<main class="main">
		<Projects />
	</main>
</template>

<script lang="ts" setup>
	import HeaderContainer from "./components/HeaderContainer.vue";
	import ProfileContainer from "./components/ProfileContainer.vue";
	import Projects from "./views/Projects.vue";
</script>

<style></style>
