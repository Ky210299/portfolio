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
				<strong class="profile-profession"> Frontend Web Developer </strong
				><br />
			</h1>
		</div>
		<BarSocials />
	</section>
</template>
<style scoped>
	.profile-section {
		flex-flow: column nowrap;
		justify-content: space-evenly;
		align-items: center;
		text-align: start;
		text-wrap: balance;
		color: var(--color-primary);
		

		.profile-section-text {
			
		
			display: flex;
			flex-flow: column wrap;
			justify-content: space-around;
			align-items: center;
			margin-bottom: 4rem;
			padding-top: 7rem;
			.h1 {
				flex: 1;
				font-size: 1rem;
				
				line-height: 1em;
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
					font-size: 1.7em;
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
					font-size: 1.15em;
					font-weight: 300;

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
					padding-left: 1.3rem;
					font-size: 1.3em;
					line-height: 2em;
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
					font-size: 1.3em;
					padding-left: 1.6rem;
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
