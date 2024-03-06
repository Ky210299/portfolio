<script lang="ts">
	import { defineComponent } from "vue";
	export default defineComponent({});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<footer class="footer">
		<ul class="ul">
			<div class="tag">HTML</div>
			<div class="tag">CSS</div>
			<div class="tag">JavaScript</div>
			<div class="tag">Vuejs</div>
			<div class="tag">MongoDB</div>
			<div class="tag">PostgreSQL</div>
			<div class="tag">Julia</div>
		</ul>
	</footer>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.footer {
		overflow: hidden;
		background-color: var(--color-palette--primary);
		display: flex;
		flex-flow: row nowrap;
		justify-content: center;
		align-items: center;
		padding: 1.5rem;
		.ul {
			display: flex;
			flex-flow: row nowrap;
			justify-content: space-around;
			align-items: center;
			gap: 1rem;

			.tag {
				transition: all ease-in-out 0.3s;
				font-size: 0.8rem;
				text-align: center;
				background: transparent;
				color: var(--color-primary);
				filter: grayscale(0.6) brightness(1);
				box-shadow: inset 0 0 2px var(--color-primary);
				padding-inline: .5rem;
				border-radius: 1rem;
				
				&:hover {
					transform: scale(1.2);
					filter: grayscale(0) brightness(2);
					box-shadow: inset 0 0 3px var(--color-primary)
				}
			}
		}
	}
</style>
