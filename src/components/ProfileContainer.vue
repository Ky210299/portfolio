<script lang="ts">
	import { defineComponent } from "vue";
	import BarSocials from "./BarSocials.vue";
	export default defineComponent({ components: { BarSocials } });
</script>

<template>
	<section class="profile-section" id="home">
		<div class="profile-section-text">
			<h1 class="h1">
				<em>Hi!</em>  <br />
				I'm Leonardo Bazan Marquez 
			</h1>
			<h2 class="h2">
				<strong> < FullStack Developer /></strong>
			</h2>
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

			.h1 {
				max-width: 40rem;
				font-size: 3rem;
				color: var(--color-primary);
				&::first-letter {
					font-size: 1.2em;
				}
			}

			.h2 {
				font-size: 2rem;
				&::first-letter {
					font-size: 1.2em;
				}
			}
		}
	}
</style>
