<script lang="ts">
import { defineComponent, Ref, ref } from "vue";
import BarProjectFilter from "../components/BarProjectFilter.vue";
import CardProjectContainer from "../components/CardProjectContainer.vue";
export default defineComponent({
	setup() {
		type ProjectImg = string | undefined;
		type Link = string | undefined;

		const svgSrc = "./"

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
				src: svgSrc,
			},
			css: {
				name: "CSS",
				fileName: "CssIcon",
				src: svgSrc,
			},
			javascript: {
				name: "JavaScript",
				fileName: "javascriptIcon",
				src: svgSrc,
			},
			vue: {
				name: "Vue.js",
				fileName: "VueIcon",
				src: svgSrc,
			},
			python: {
				name: "Python",
				fileName: "PythonIcon",
				src: svgSrc,
			},
			django: {
				name: "DJango",
				fileName: "DjangoIcon",
				src: svgSrc,
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
				img: "/Sin título.jpg",
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

						<img :src="project.img" alt="Project imagen" class="img"
							loading="lazy" />

						<div class="project-info">

							<a href="#" class="a" title="Project Title" _bl>
								<h1 class="h1">{{ project.name }}</h1>
							</a>

							<ul class="technologies">
								<li v-for="tech of project.techs"
									:key="tech.name" class="tag">
									<img :src="`${tech.src}${tech.fileName}.svg`"
										alt="tech.name"
										:title="tech.name"></img>
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

							<a class="project-links-item-text"
								v-if="link.link != undefined" :href="link">

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
			gap: 2rem;

			justify-content: center;
			align-items: flex-start;

			grid-auto-flow: row;
			grid-template-columns: repeat(auto-fill, minmax(15rem, 1fr));

			.article {
				display: flex;
				flex-flow: column nowrap;
				justify-content: center;
				align-items: center;
				width: 100%;
				height: 100%;
				position: relative;

				.picture-container {

					position: relative;
					margin-bottom: .7rem;
					display: flex;
					justify-content: center;
					align-items: center;
					width: 100%;
					height: 100%;

					transition: all ease 0.3s;

					.img {

						transition: all ease 0.5s;
						border-radius: .5rem;
						object-fit: cover;
						height: 100%;
						width: 100%;
					}

					.project-info {
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

							background-color: var(--color-secondary);
							opacity: .75;
							border-radius: .5rem;
							padding-inline: 1rem;
							padding-block: .1rem;
							filter: contrast(.55);

							.h1 {
								text-align: center;
								font-family: var(--font-family-secondary);
								color: var(--color-primary);
								font-size: 1em;
								font-weight: 500;


							}
						}

						.technologies {
							display: flex;
							flex-flow: row wrap;
							justify-content: center;
							align-items: center;
							padding-inline: 1rem;
							padding-block: .3rem;
							gap: 0.6rem;

							background: transparent;
							color: var(--color-primary);
							border-radius: .5rem;

							backdrop-filter: blur(10px);


							.tag {

								width: 1.1rem;
								height: 1.1rem;

								transition: all ease-in-out 0.2s;
								filter: saturate(.4);

								&:hover {

									transform: scale(1.1);
									filter: saturate(1);
								}
							}
						}

						.project-description {
							position: absolute;
							font-size: 1rem;
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
							filter: contrast(1.5);

						}
					}

					&:hover {

						.img {
							opacity: 0.5;
							filter: blur(5px);
						}
					}
				}

				.project-links {

					display: grid;
					grid-template-columns: 45% 45%;
					grid-auto-flow: column;
					gap: 5%;
					width: 100%;
					
						
					.project-links-item {
						justify-self: center;
						text-align: center;
						transition: all ease .3s;
				

						.project-links-item-text {
							
							text-wrap: nowrap;
							border-radius: .5rem;
							padding-inline: .5rem;
							padding-block: .5rem;
							color: var(--color-primary);
							background-color: var(--color-palette--primary);
							filter: contrast(.5) saturate(1);
							width: max-content;
						}

						&:hover {

							transform: scale(1.05);
							filter: contrast(2) ;

						}

					}
				}
			}
		}
	}
}
</style>
