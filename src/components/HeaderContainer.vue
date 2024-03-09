<script lang="ts">
	import { defineComponent, Ref, ref } from "vue";
	import IconArrowBarLeft from "./icons/IconArrowBarLeft.vue";
	import IconArrowBarRigth from "./icons/IconArrowBarRigth.vue";
	export default defineComponent({
		setup() {
			type pageId = `#${string}`;
			interface Ipages {
				name: string;
				id: pageId;
			}

			let isDeployed: Ref<boolean> = ref(false);
			const pages = ref<Array<Ipages>>([
				{
					name: "Home",
					id: "#home",
				},
				{
					name: "Projects",
					id: "#projects",
				},
				{
					name: "About",
					id: "#about",
				},
			]);
			return { isDeployed, pages };
		},

		components: { IconArrowBarLeft, IconArrowBarRigth },
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<header class="header">
		<div :class="{ 'logo-isDeployed': isDeployed }" class="logo">
			<a href="#home" class="a">LBM</a>
		</div>
		<nav :class="{ 'nav-not-deployed': !isDeployed }" class="nav">
			<ul :class="{ 'nav-not-deployed': !isDeployed }" class="ul">
				<li class="li" v-for="page of pages" :key="page.id">
					<a :href="page.id" :title="page.name" class="a">{{ page.name }}</a>
				</li>
			</ul>
		</nav>
		<IconArrowBarRigth
			v-show="isDeployed"
			@click="isDeployed = !isDeployed"
			class="header-menu"
		/>
		<IconArrowBarLeft
			v-show="!isDeployed"
			@click="isDeployed = !isDeployed"
			id="nav-menu"
			class="header-menu"
		/>
	</header>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.header {
		overflow-y: hidden;
		transition: all ease 500ms;
		z-index: 1;
		position: fixed;
		background: #18181840;
		backdrop-filter: blur(0.5rem);
		filter: contrast(1.3);
		@media (prefers-color-scheme: light) {
			mix-blend-mode: darken;
		}

		width: 100%;
		min-height: 4rem;
		display: flex;
		flex-flow: row nowrap;
		align-items: center;
		padding: 0.5rem;
		border-bottom-left-radius: 1rem;
		border-bottom-right-radius: 1rem;

		.header-menu {
			display: none;
		}
		.logo {
			justify-self: flex-start;
			width: fit-content;
			height: fit-content;

			.a {
				transition: ease-in-out all 300ms;
				font-family: var(--font-family-logo);
				font-size: 3rem;

				font-style: oblique;
				color: var(--color-primary);
				

			
			}
			:hover {
				text-shadow: 0 0 1rem var(--color-secondary);
				
					filter: contrast(1.3);
				transform: translateY(-1px);
			}
		}
		.nav {
			margin-right: 3rem;
			justify-self: flex-end;
			transition: ease-in all 200ms;
			.ul {
				display: flex;
				flex-flow: row wrap;
				align-items: center;
				justify-content: flex-end;
				background: none;
				gap: 1rem;

				.li {
					padding: 0.3rem;
					transition: ease-in-out all 150ms;
					.a {
						position: relative;
						z-index: 1;

						color: var(--color-primary);
						font-family: var(--font-family-secondary);
						font-size: 1.5rem;
						font-weight: 900;
						text-shadow: 2rem 0.1rem 2rem var(--color-palette--cuaternary),
							2rem -2rem 2rem var(--color-palette--tertiary),
							-2rem -2rem 2rem var(--color-palette--secondary),
							-2rem 2rem 2rem var(--color-palette--primary);

						filter: drop-shadow();
						transition: all ease 290ms;
						transform: scale(1);

						&:hover {
							text-shadow: -1px -1px 0.1rem var(--color-palette--cuaternary),
								-1px 1px 0.1rem var(--color-palette--tertiary),
								1px 1px 0.1rem var(--color-palette--secondary),
								1px 1px 0.1rem var(--color-palette--primary);

							transform: scale(1.1);
							filter: saturate(0.7) contrast(1.5);
						}
					}
				}
			}
		}
	}

	@media screen and (width <= 800px) {
		.header {
			padding: 0;
			.header-menu {
				display: block;
				fill: var(--color-primary);
			}
			.logo {
				transition: all ease-in 200ms;
				padding-left: .5rem;
				
				&.logo-isDeployed {
					position: absolute;
				




					.a {
						filter: blur(1rem);
					}
				}
			}
			.nav {
				margin-right: 1rem;
				transition: all ease-out 0.7s;
				transform: translateX(0);

				height: auto;

				.ul {
					justify-content: flex-end;
					flex-wrap: wrap;

					&.nav-not-deployed {
						flex-flow: row nowrap;
					}
				}
				&.nav-not-deployed {
					transform: translateX(300%);
					overflow: hidden;
					height: auto;
				}
			}
		}
	}
</style>
