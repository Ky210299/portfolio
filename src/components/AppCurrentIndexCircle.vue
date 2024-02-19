<script lang="ts">
	import { defineComponent } from "vue";
	export default defineComponent({});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<svg width="20" height="20">
		<defs>
			<radialGradient id="enabled">
				<stop offset="1%" stop-color="white" />
				<stop offset="100%" stop-color="green" />
			</radialGradient>
		</defs>
		<defs>
			<radialGradient id="disabled">
				<stop offset="1%" stop-color="#363" />
				<stop offset="100%" stop-color="gray" />
			</radialGradient>
		</defs>
		<circle
			cx="10"
			cy="10"
			r="8"
			fill="url(#disabled)"
			class="svg__index-circle"
		/>
	</svg>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.enabled {
		r: 10;
		fill: url("#enabled");
	}
</style>
