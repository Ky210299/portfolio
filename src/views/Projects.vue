<script lang="ts">
	import { defineComponent, Ref, ref } from "vue";
	import BarProjectFilter from "../components/BarProjectFilter.vue";
	import BarIndex from "../components/BarIndex.vue";
	import CardProjectContainer from "../components/CardProjectContainer.vue";
	export default defineComponent({
		setup() {
			type projectImg = string | undefined;

			interface IProject {
				name: string;
				link: string;
				description: string;
				techs: Array<string>;
				img: projectImg;
			}

			function Project(
				this: IProject,
				name: string,
				link: string,
				description: string,
				img: projectImg = undefined,
				techs: Array<string>
			) {
				(this.name = name),
					(this.link = link),
					(this.description = description),
					(this.img = img),
					(this.techs = techs);
			}

			let projects = ref([
				{
					name: "Web Scrapping whit Python",
					link: "https://google.com",
					decription: "Un projecto que recopila datos con Web scrapping",
					img: "../../public/descarga.jpeg",
					techs: ["HTML", "CSS", "JavaScript", "Python", "Pandas"],
				},
			]);

			return { projects };
		},

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
				<article
					v-for="project of projects"
					:key="project['name']"
					@click=""
					class="article"
				>
					<div class="picture-container">
						<img :src="project.img" alt="Imagen" class="img" loading="lazy" />
						<div class="description">
							<a href="#" class="a" title="Project Title">
								<h4 class="h4">{{ project.name }}</h4>
							</a>
							<ul class="technologies">
								<li
									v-for="(tag, index) of project.techs"
									:key="index"
									class="tag"
								>
									{{ tag }}
								</li>
							</ul>
						</div>
					</div>
					<p class="project-description">
						{{ project.decription }}
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
					border: none;
					position: relative;
					display: flex;
					flex-flow: column nowrap;
					justify-content: center;
					align-items: center;
					height: fit-content;

					box-shadow: 0px 0px 162px -17px var(--color-secondary);
					&::before {
						content: "";
						position: absolute;
						background-color: var(--color-primary);
						border-radius: 1rem;
						opacity: 0.1;

						left: -0.1rem;
						bottom: -0.1rem;
						right: -0.1rem;
						filter: blur(1px);
					}
					.picture-container {
						position: relative;
						display: flex;
						justify-content: center;
						align-items: center;
						width: 100%;
						height: 100%;

						.img {
							transition: all ease 0.5s;

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

								.tag {
									transition: all ease-in-out 0.3s;
									font-size: 0.8rem;
									text-align: center;
									background: transparent;
									color: var(--color-primary);
									filter: grayscale(0.6) brightness(1) contrast(0.4);
									box-shadow: inset 0 0 2px var(--color-primary);
									padding-inline: 0.5rem;
									border-radius: 1rem;
								}
							}
						}
					}
					.project-description {
						position: absolute;
						padding: 1rem;
						transition: all ease-in-out 0.3s;
						opacity: 0;
						transform: translateY(2rem);
					}
					&:hover {
						transform: scale(1.05);
						cursor: pointer;
						.picture-container {
							.img {
								opacity: 0.7;
								border: 1px solid var(--color-palette--secondary);
								filter: blur(0.2rem);
							}
							.description {
								.tag {
									filter: contrast(1);
									&:hover {
										transform: scale(1.2);
										filter: grayscale(0) brightness(2);
										box-shadow: inset 0 0 3px var(--color-primary);
									}
								}
							}
						}
						.project-description {
							opacity: 1;
							transform: translateY(0);
						}
					}
				}
			}
		}
	}
</style>
