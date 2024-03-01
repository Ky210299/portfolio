<script lang="ts">
	import { defineComponent } from "vue";
	export default defineComponent({});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<section id="about" class="about-section">
		<div class="text">
			<h2 class="h2">About me</h2>
			<p class="p">
				Front-end and data science developer with an electrical engineering
				background.
			</p>
			<p class="p">
				I love setting myself new challenges that solve problems or optimize
				results.
			</p>
			<p class="p">
				I enjoy teamwork and I believe it is the best way to achieve great
				things.
			</p>
		</div>
		<div class="picture">sssss</div>
	</section>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.about-section {
		font-family: var(--font-family-primary);
		display: flex;
		flex-flow: row wrap-reverse;
		justify-content: space-around;
		align-items: center;
		gap: 2rem;
		.text {
			width: 40vw;
			min-width: 20rem;
			.h2 {
				font-family: var(--font-family-secondary);
				font-size: 2rem;
				font-weight: bold;
				margin-bottom: 1rem;
				border-bottom: 1px solid var(--color-palette--secondary);
				padding-bottom: 1rem;
				&::first-letter {
					font-size: 3rem;
					color: var(--color-palette--opposite);
				}
			}
			.p {
				font-style: var(--font-family--secondary);

				text-wrap: pretty;
				padding: 0rem 1rem;
				margin-bottom: 1rem;
			}
		}
		.picture {
			outline: 1px solid white;
			min-width: 20vw;
			height: 4rem;
			padding: 2rem;
		}
	}
</style>
