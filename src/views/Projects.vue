<script lang="ts">
import { defineComponent, Ref, ref } from "vue";
import BarProjectFilter from "../components/BarProjectFilter.vue";
import CardProjectContainer from "../components/CardProjectContainer.vue";
export default defineComponent({
	setup() {
		type ProjectImg = string | undefined;
		type Link = string | undefined;


		interface IProject {
			name: string;
			links: IProjectLinks;
			description: string;
			techs: Array<ITech>;
			img: ProjectImg;
		}

		interface ILink {

			name: string,
			linkDescription: string,
			link: Link,
		}

		interface IProjectLinks {
			deployedLink: ILink
			githubLink: ILink
		}

		interface ITech {
			name: string;
			fileName: string;
			src: string;
		}
		const techs = {
			html: {
				name: "HTML",
				fileName: "HtmlIcon",
				src: "./src/components/icons/",
			},
			css: {
				name: "CSS",
				fileName: "CssIcon",
				src: "./src/components/icons/",
			},
			javascript: {
				name: "JavaScript",
				fileName: "javascriptIcon",
				src: "./src/components/icons/",
			},
			vue: {
				name: "Vue.js",
				fileName: "VueIcon",
				src: "./src/components/icons/",
			},
			python: {
				name: "Python",
				fileName: "PythonIcon",
				src: "./src/components/icons/",
			},
			django: {
				name: "DJango",
				fileName: "DjangoIcon",
				src: "./src/components/icons/",
			},
		};

		let projects: Ref = ref<Array<IProject>>([
			{
				name: "Example Project 1",
				links: {

					deployedLink: {
						name: "deployedLink",
						linkDescription: "See the site",
						link: undefined,

					}, githubLink: {
						name: "githubLink",
						linkDescription: "See the source code",
						link: "https://github.com/ky210299/portfolio",
					}
				},
				description: "Recopila datos con Web scrapping",
				img: "../../descarga.jpeg",
				techs: [techs.html, techs.css, techs.javascript, techs.python],
			},
			{
				name: "Example Project 2",
				links: {

					deployedLink: {
						name: "deployedLink",
						linkDescription: "See the site",
						link: "https://google.com"

					}, githubLink: {
						name: "githubLink",
						linkDescription: "See the source code",
						link: undefined
					}
				},
				description:
					"Administra y optimiza recursos al diseñar instalaciones electrica de una forma intuitiva y rapida",
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
				links: {

					deployedLink: {
						name: "deployedLink",
						linkDescription: "See the site",
						link: "https://google.com",
					},

					githubLink: {
						name: "githubLink",
						linkDescription: "See the source code",
						link: "https://github.com/ky210299/portfolio",
					}
				},
				description: "Un foro para conseguir compañeros de trabajo ",
				img: "../../descarga.jpeg",
				techs: [techs.html, techs.css, techs.javascript],
			},

			{
				name: "Example Project 3",
				links: {

					deployedLink: {
						name: "deployedLink",
						linkDescription: "See the site",
						link: undefined

					}, githubLink: {
						name: "githubLink",
						linkDescription: "See the source code",
						link: "https://github.com/ky210299/portfolio"
					}
				},
				description:
					"Una CLI para reproducir musica por consola mientras trabajas !",
				img: "../../descarga.jpeg",
				techs: [techs.python],
			},
		]);

		return { projects };
	},

	components: {
		BarProjectFilter,
		CardProjectContainer,

	},
});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<div class="project-view">
		<h2 class="h2">Projects</h2>
		<section class="projects-section">
			<div class="grid">
				<article v-for="project of projects" :key="project['name']"
					@click="" class="article">

					<div class="picture-container">

						<img :src="project.img" alt="Imagen" class="img"
							loading="lazy" />

						<div class="project-info">

							<a href="#" class="a" title="Project Title" _bl>
								<h3 class="h3">{{ project.name }}</h3>
							</a>

							<ul class="technologies">
								<li v-for="tech of project.techs"
									:key="tech.name" class="tag">
									<img :src="`${tech.src}${tech.fileName}.svg`"
										:alt="tech.name" :title="tech.name" ></img>
								</li>
							</ul>

							<p class="project-description">
								{{ project.description }}
							</p>

						</div>
					</div>

					<ul class="project-links">

						<li v-for=" link in project.links" :key="link.name"
							class="project-links-item">

							<a class="project-links-item-text" v-if="link.link != undefined" :href="link">

								{{ link.linkDescription }}

							</a>
						</li>
					</ul>

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
		margin-bottom: 2rem;
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
			grid-template-columns: repeat(auto-fill, minmax(15rem, 1fr));

			.article {
				position: relative;
				display: flex;
				flex-flow: column nowrap;
				justify-content: center;
				align-items: center;
				margin-bottom: 2rem;
				
				

				.picture-container {

					position: relative;
				
					display: flex;
					justify-content: center;
					align-items: center;
					width: 100%;
				

					transition: all ease 0.3s;

					.img {
						z-index: -1;
						transition: all ease 0.5s;
						background: none;
						border-radius: 1rem;
						object-fit: contain;
					}

					.project-info {
						filter: contrast(2);
						position: absolute;
						top: 0px;
						padding: 0.5rem;
						display: flex;
						flex-flow: column wrap;
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

							z-index: -1;
							color: var(--color-primary);

							
							

							.tag {
								
								width: 1.1rem;
								height: 1.1rem;
								
								transition: all ease-in-out 0.2s;
								filter: blur(1px) saturate(.4);

								&:hover{
									
									
									transform: scale(1.1);
									filter: blur(0) saturate(1);
								}
							}
						}

						.project-description {
							position: absolute;
							font-size: .7em;
							top: 3rem;
							width: 100%;
							padding-inline: 2rem;

							text-wrap: pretty;

							transition: all ease-in-out 0.3s;
							opacity: 0;
							transform: translateY(4rem);

						}
					}

					&:hover {
						transform: scale(1.05);
						cursor: pointer;


						.project-description {
							opacity: 1;
							transform: translateY(0);
							filter: contrast(2);
						}

					}

					&:hover {

						.img {
							opacity: 0.8;

							filter: blur(0.3rem);
						}
					}
				}


				.project-links {

					display: flex;
					flex-flow: row nowrap;
					padding-inline: 2rem;
					justify-content: space-between;
					align-items: center;
					gap: 1rem;
					position: absolute;
					bottom: -1.5rem;
					width: 100%;
					
					
					.project-links-item {
						overflow-x: visible;
						flex: 1;
					
						&:hover {

							
							transform: scale(1.05);
							filter: brightness(1.2);
							
						}
					    
						.project-links-item-text{
							text-align: center;
							text-wrap: nowrap;
							
							
						}
					
						border-radius: .1rem;
						transition: all ease 200ms;


					}
				}

			}
		}
	}
}

</style>
