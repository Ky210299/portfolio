<script lang="ts">
	import { defineComponent } from "vue";
	import IconLinkedin from "./icons/IconLinkedin.vue";
	import IconGithub from "./icons/IconGithub.vue";
	export default defineComponent({
		components: { IconLinkedin, IconGithub },
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<li class="li">
		<a href="#" class="a" title="name" target="_blank" rel="noopener noreferer">
			<svg class="svg" width="25" height="25" view-box=" 0 0 25 25" >
				<rect width="25" height="25" fill="white"/>
			</svg>
		</a>
		<a href="#" class="a" title="name" target="_blank" rel="noopener noreferer">
			<svg class="svg" width="25" height="25" view-box=" 0 0 25 25" >
				<rect width="25" height="25" fill="white"/>
			</svg>
		</a>
		<a href="#" class="a" title="name" target="_blank" rel="noopener noreferer">
			<svg class="svg" width="25" height="25" view-box=" 0 0 25 25" >
				<rect width="25" height="25" fill="white"/>
			</svg>
		</a>
	</li>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.li {
		display: flex;
		flex-flow: row nowrap;
		justify-content: center;
		align-items: center;
		gap: 1rem;
		width: 100%;
		& .a {
			
		}
	}
</style>
