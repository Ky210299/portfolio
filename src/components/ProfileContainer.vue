<script lang="ts">
	import { defineComponent } from "vue";
	import BarSocials from "./BarSocials.vue";
	export default defineComponent({ components: { BarSocials } });
</script>

<template>
	<section class="profile-section" id="home">
		<div class="profile-section-text">
			<h1 class="h1">
				<em class="profile-hi">Hi!</em> <span class="profile-iam">I'm</span>
				<br />
				<p class="profile-name">Leonardo Bazan Marquez</p>
				<strong class="profile-profession">
					<span class="profession-tags"><</span> FullStack Developer
					<span class="profession-tags">/></span>
				</strong>
			</h1>
		</div>
		<BarSocials />
	</section>
</template>

<style scoped>
	.profile-section {
		margin: auto;
		flex-flow: column nowrap;
		justify-content: space-around;
		align-items: center;

		color: var(--color-primary);

		.profile-section-text {
			display: flex;
			flex-flow: column wrap;

			.h1 {
				font-size: 4rem;
				line-height: 100%;
			}
			.profile-hi {
				font-size: 1.5em;
				line-height: 100%;

				position: relative;
				font-weight: 500;
			}
			.profile-iam {
				padding-left: 1rem;
				font-size: 1em;
				line-height: 100%;

				font-weight: 200;
			}
			.profile-name {
				padding-left: 4rem;
				font-size: 1.2em;
				line-height: 100%;
				font-weight: normal;
			}
			.profile-profession {
				font-size: 1.5em;
				padding-left: 8rem;
				line-height: 100%;

				text-wrap: nowrap;
				font-weight: bolder;

				.profession-tags {
					font-size: 1.2em;
					font-weight: 300;
				}
			}
		}
	}
</style>
