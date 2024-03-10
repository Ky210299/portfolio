<script lang="ts">
	import { defineComponent, Ref, ref } from "vue";
	import BarProjectFilter from "../components/BarProjectFilter.vue";


	import CardProjectContainer from "../components/CardProjectContainer.vue";
	export default defineComponent({
		setup() {
			type projectImg = string | undefined;

			interface IProject {
				name: string;
				link: string;
				description: string;
				techs: Array<ITech>;
				img: projectImg;
			}

			interface ITech {
				name: string;
				icon: string;
			}
			const techs = {
				html: {
					name: "HTML",
					icon: "./src/components/icons/HtmlIcon.vue",
				},
				css: {
					name: "CSS",
					icon: "./src/components/icons/CssIcon.vue",
				},
				javascript: {
					name: "JavaScript",
					icon: "./src/components/icons/JavaScriptIcon.vue",
				},
				vue: {
					name: "Vue.js",
					icon: "./src/components/icons/VueIcon.vue",
				},
				python: {
					name: "Python",
					icon: "./src/components/icons/PythonIcon.vue",
				},
				django: {
					name: "DJango",
					icon: "./src/components/icons/DjangoIcon.vue",
				},
			};

			let projects: Ref = ref<Array<IProject>>([
				{
					name: "Example Project 1",
					link: "https://google.com",
					description: "Recopila datos con Web scrapping",
					img: "../../descarga.jpeg",
					techs: [techs.html, techs.css, techs.javascript, techs.python],
				},
				{
					name: "Example Project 2",
					link: "https://google.com",
					description:
						"Administra y optimiza recursos al diseñar instalaciones electrica de una forma intuitiva",
					img: "../../descarga.jpeg",
					techs: [
						techs.python,
						techs.django,
						techs.html,
						techs.css,
						techs.javascript,
					],
				},
				{
					name: "Example Project 3",
					link: "https://google.com",
					description: "Un foro para conseguir compañeros de trabajo ",
					img: "../../descarga.jpeg",
					techs: [techs.html, techs.css, techs.javascript],
				},
				{
					name: "Example Project 3",
					link: "https://google.com",
					description:
						"Una CLI para reproducir musica mientras trabajas por consola!",
					img: "../../descarga.jpeg",
					techs: [techs.python],
				},
			]);

			return { projects, techs };
		},

		components: { BarProjectFilter, CardProjectContainer },
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<div class="project-view">
		<h2 class="h2">Projects</h2>
		<section class="projects-section">
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
								<h3 class="h3">{{ project.name }}</h3>
							</a>
							<ul class="technologies">
								<li v-for="tech of project.techs" :key="tech.name" class="tag">
									<svg :href="tech.icon"></svg>
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
		margin: auto;
		display: flex;
		flex-flow: column wrap;
		justify-content: space-around;
		align-items: center;
		width: 100%;

		.h2 {
			width: 100%;
			padding-left: 1rem;
			margin-bottom: 1rem;
			font-family: var(--font-family-secondary);
			color: var();
			font-size: 2rem;
			text-transform: uppercase;
			line-height: 100%;
			border-bottom: 1px solid var(--color-palette--cuaternary);
			&::first-letter {
				font-size: 2em;
				color: var(--color-palette--cuaternary);
			}
		}
		.projects-section {
			width: 100%;
			display: flex;
			align-items: center;
			.grid {
				width: 100%;
				display: grid;
				gap: 1.5rem;
				justify-content: center;
				align-items: flex-start;

				grid-auto-flow: row;
				grid-template-columns: repeat(auto-fit, minmax(15rem, 1fr));

				.article {
					transition: all ease 0.3s;
					position: relative;
					display: flex;
					flex-flow: column nowrap;
					justify-content: center;
					align-items: center;

					.picture-container {
						position: relative;
						display: flex;
						justify-content: center;
						align-items: center;
						width: 100%;
						height: 100%;

						.img {
							transition: all ease 0.5s;
							background: none;
							border-radius: 1rem;

							object-fit: contain;
						}
						.description {
							position: absolute;
							top: 0px;
							padding: 0.5rem;
							display: flex;
							flex-direction: column;
							justify-content: space-between;
							align-items: center;
							width: 100%;
							height: 100%;

							background: transparent;
							font-size: larger;

							transition: all ease 0.3s;

							.a {
								.h3 {
									text-align: center;
									font-family: var(--font-family-secondary);
									color: var(--color-primary);
									font-size: 1.2em;
									font-weight: 400;
								}
							}

							.technologies {
								display: flex;
								flex-flow: row wrap;
								justify-content: center;
								align-items: center;
								gap: 0.6rem;

								color: var(--color-primary);

								transition: all ease-in-out 0.3s;

								.tag {
									border: 2px solid var(--color-palette--secondary);
									text-align: center;
									padding: 0.25rem;
									font-size: 0.8rem;
									line-height: 100%;
									border-radius: 0.4rem;

									transition: all ease-in-out 0.3s;
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

								filter: blur(0.2rem);
							}
							.description {
								.tag {
									filter: contrast(1);
									&:hover {
										transform: scale(1.1);
										filter: brightness(2);
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
