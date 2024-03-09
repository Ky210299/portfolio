<script lang="ts">
	import { defineComponent } from "vue";
	import BarSocials from "./BarSocials.vue";
	export default defineComponent({ components: { BarSocials } });
</script>

<template>
	<section class="profile-section" id="home">
		<div class="profile-section-text">
			<h2 class="h2">Hi! I'm Leonardo Bazan Marquez</h2>
			<h3 class="h3">
				<strong>FullStack Developer</strong>
			</h3>
			<BarSocials />
		</div>
	</section>
</template>

<style scoped>
	.profile-section {
		margin: auto;
		gap: 2rem;
		flex-flow: column nowrap;
		justify-content: space-between;
		align-items: center;

		.profile-section-text {
			display: flex;
			flex-flow: column wrap;
			justify-content: center;
			align-items: center;

			.h2 {
				max-width: 40rem;
				color: var(--color-primary);
				font-size: 3rem;
				margin-bottom: 2rem;
				text-align: center;
				text-wrap: balance;
				padding-bottom: 1rem;
				border-bottom: 2px solid var(--color-palette--secondary);
				line-height: 100%;
				&::first-letter {
					font-size: 1.2em;
				}
			}

			.h3 {
				font-size: 2rem;
				text-align: center;
				margin-bottom: 3rem;
				line-height: 100%;
				&::first-letter {
					font-size: 1.2em;
				}
			}
		}
	}
</style>
