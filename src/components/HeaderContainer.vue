<script lang="ts">
	import { defineComponent } from "vue";
	import MenuDeployed from "./MenuDeployed.vue";
	import IconDeployerMenu from "./icons/IconDeployerMenu.vue";
	export default defineComponent({
		setup() {},
		components: { MenuDeployed, IconDeployerMenu },
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<header class="header">
		<h1 class="h1"><a href="#home" class="a">LBM</a></h1>
		<nav class="nav">
			<ul class="ul">
				<li class="i"><a href="#home" title="Home" class="a">Home</a></li>
				<li class="i"><a href="#projects" title="Projects" class="a">Projects</a></li>
				<li class="i"><a href="#about" title="About" class="a">About</a></li>
			</ul>
		</nav>
	</header>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	
</style>
