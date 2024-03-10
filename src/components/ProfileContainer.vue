<script lang="ts">
	import { defineComponent } from "vue";
	import BarSocials from "./BarSocials.vue";
	export default defineComponent({ components: { BarSocials } });
</script>

<template>
	<section class="profile-section">
		<div class="profile-section-text">
			<h1 class="h1">
				<br /><em class="profile-hi">Hi!</em>
				<span class="profile-iam">I'm</span>
				<br />
				<p class="profile-name">Leonardo Bazán Márquez</p>
				<strong class="profile-profession"> FullStack Web Developer </strong
				><br />
			</h1>
		</div>
		<BarSocials />
	</section>
</template>
<style scoped>
	.profile-section {
		margin: auto;
		min-height: 100dvh;
		padding-top: 5rem;
		flex-flow: column nowrap;
		justify-content: space-around;
		align-items: center;
		padding: 2rem;
		text-align: start;
		text-wrap: balance;
		color: var(--color-primary);

		.profile-section-text {
			display: flex;
			flex-flow: column wrap;
			justify-content: space-around;
			align-items: center;
			.h1 {
				font-size: 1rem;
				
				line-height: 100%;
				position: relative;

				&::before,
				&::after {
					font-size: 3em;
					line-height: 100%;
					color: var(--color-palette--cuaternary);
				}

				&::before {
					content: "{ ";
					position: absolute;
					top: -1em;
				}
				&::after {
					content: "}";
					position: absolute;
					bottom: -1em;
				}

				.profile-hi {
					padding-left: 1rem;
					line-height: 100%;
					font-size: 2em;
					font-weight: 300;
					color: var(--color-palette--tertiary);

					&::before,
					&::after {
						font-size: 1em;
						line-height: 100%;
						color: var(--color-palette--tertiary);
					}

					&::before {
						content: "";
					}
					&::after {
						content: "";
					}
				}
				.profile-iam {
					line-height: 100%;
					padding-left: 1rem;
					font-size: 1.2em;
					font-weight: 200;

					&::before,
					&::after {
						font-size: 1em;
						line-height: 100%;
						color: var(--color-palette--tertiary);
					}

					&::before {
						content: "";
					}
					&::after {
						content: "";
					}
				}
				.profile-name {
					line-height: 100%;
					padding-left: 2rem;
					font-size: 2em;
					line-height: 100%;
					font-weight: normal;

					&::before,
					&::after {
						font-size: 1em;
						line-height: 100%;
						color: var(--color-palette--tertiary);
					}

					&::before {
						content: "";
					}
					&::after {
						content: "";
					}
				}
				.profile-profession {
					line-height: 100%;
					font-size: 1.7em;
					padding-left: 3rem;
					font-weight: bold;

					&::before,
					&::after {
						font-size: 1em;
						line-height: 100%;

						color: var(--color-palette--tertiary);
					}

					&::before {
						content: "<";
					}
					&::after {
						content: "/>";
					}
				}
			}
		}
	}
</style>
