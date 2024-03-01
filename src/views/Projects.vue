<script lang="ts">
	import { defineComponent } from "vue";
	import BarProjectFilter from "../components/BarProjectFilter.vue";
	import BarIndex from "../components/BarIndex.vue";
	import CardProjectContainer from "../components/CardProjectContainer.vue";
	export default defineComponent({
		components: { BarProjectFilter, BarIndex, CardProjectContainer },
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<div class="project-view">
		<h2 class="h2">Projects</h2>
		<!-- <aside class="aside">
			<h3 class="h3">Filter</h3>
			<div class="filters">
				<select name="technologies" id="technologies-filter">
					Tech
				</select>
				<select name="languages" id="technologies-filter">
					Lang
				</select>
				<select name="date" id="technologies-filter">
					Date
				</select>
			</div>
		</aside> -->
		<section class="projects-section" id="projects">
			<div class="grid">
				<article class="article">
					<div class="picture-container">
						<img
							src="../../public/descarga.jpeg"
							alt="Imagen"
							class="img"
							loading="lazy"
						/>
						<div class="description">
							<a href="#" class="a" title="Project Title">
								<h4 class="h4">Project Name</h4>
							</a>
							<ul class="technologies">
								<li class="tech">XgUK3</li>
								<li class="tech">XgUK3</li>
								<li class="tech">XgUK3</li>
							</ul>
						</div>
					</div>
					<p class="p">
						Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet.
					</p>
				</article>
			</div>
		</section>
	</div>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.project-view {
		display: flex;
		flex-flow: column wrap;
		width: 100%;

		.h2 {
			padding: 1rem 1rem;
			margin-bottom: 2rem;
			font-family: var(--font-family-secondary);
			font-size: 3rem;
			border-bottom: 1px solid var(--color-palette--secondary);

			&::first-letter {
				font-size: 4rem;
				color: var(--color-palette--opposite);
			}
		}
		/* .aside {
			display: flex;
			flex-flow: row nowrap;
			justify-content: space-around;
			align-items: center;
			gap: 2rem;
			padding: 1rem;
			margin-bottom: 2rem;
			.h3 {
				font-family: var(--font-family-secondary);
				font-size: 1.2rem;

				&::first-letter {
					font-size: 1.6rem;
					color: var(--color-palette--opposite);
				}
			}
			.filters {
				display: flex;
				flex-flow: row nowrap;
				justify-content: center;
				align-items: center;
				gap: 4rem;

        select{
          padding: 
        }
			}
		} */
		.projects-section {
			.grid {
				display: grid;
				gap: 2rem;
				grid-template-columns: repeat(auto-fit, minmax(16rem, 32rem));
				grid-auto-flow: row;
				width: 45vw;
				.article {
					transition: all ease 0.3s;
					position: relative;
					display: flex;
					flex-flow: column nowrap;
					justify-content: center;
					align-items: center;
					height: fit-content;

					.picture-container {
						position: relative;
						display: flex;
						justify-content: center;
						align-items: center;
						width: 100%;
						height: 100%;

						.img {
							transition: all ease 0.5s;
							box-shadow: 0 2rem 2rem -2rem var(--color-palette--primary);
							border-radius: 1rem;
							object-fit: contain;
						}
						.description {
							transition: all ease 0.3s;
							position: absolute;
							background: transparent;
							top: 0px;
							padding: 0.5rem;
							display: flex;
							flex-direction: column;
							justify-content: space-between;
							align-items: center;
							width: 100%;
							height: 100%;

							.a {
								.h4 {
									font-family: var(--font-family-secondary);
									color: var(--color-primary);
									font-size: 1.2rem;
									&::first-letter {
										font-size: 1.6rem;
									}
								}
							}

							.technologies {
								transition: all ease-in-out 0.3s;
								display: flex;
								flex-flow: row nowrap;
								justify-content: center;
								align-items: center;
								gap: 1rem;
							}
						}
					}
					.p {
						position: absolute;
						padding: 1rem;
						transition: all ease-in-out 0.3s;
						opacity: 0;
						transform: translateY(2rem);
					}
					&:hover {
						transform: scale(1.05);
						.picture-container {
							.img {
								filter: blur(.2rem);
							}
							.description {
								
								

								.tech {
									&:hover {
										transform: scale(1.2);
                  
									}
								}
							}
						}
						.p {
							opacity: 1;
							transform: translateY(0);
						}
					}
				}
			}
		}
	}
</style>
