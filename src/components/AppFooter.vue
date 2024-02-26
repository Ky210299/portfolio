<script lang="ts">
	import { defineComponent } from "vue";
	export default defineComponent({});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<footer class="footer">
		<span class="span"> Leonardo Bazan Marquez</span>
	</footer>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.footer {
		background-color: var(--color-palette--secondary);
		display: flex;
		flex-flow: row nowrap;
		justify-content: center;
		align-items: center;
		.span {
            color: var(--color-primary);
			text-shadow: 0px 0px 2px var(--color-secondary), 0px 0px 5px var(--color-secondary) ;
		}
	}
</style>
