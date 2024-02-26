<script lang="ts">
	import { defineComponent, Ref, ref } from "vue";
	import IconArrowBarLeft from "./icons/IconArrowBarLeft.vue";
	import IconArrowBarRigth from "./icons/IconArrowBarRigth.vue";
	export default defineComponent({
		setup() {
			let isDeployed: Ref<boolean> = ref(false);
			return { isDeployed };
		},

		components: { IconArrowBarLeft, IconArrowBarRigth },
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<header class="header">
		<h1 :class="{ 'h1-isDeployed': isDeployed }" class="h1">
			<a href="#home" class="a">LBM</a>
		</h1>
		<nav :class="{ 'nav-not-deployed': !isDeployed }" class="nav">
			<ul :class="{ 'nav-not-deployed': !isDeployed }" class="ul">
				<li class="li">
					<a href="#home" title="Home" class="a">Home</a>
				</li>
				<li class="li">
					<a href="#home" title="Home" class="a">Home</a>
				</li>
				<li class="li">
					<a href="#home" title="Home" class="a">Home</a>
				</li>
				<li class="li">
					<a href="#home" title="Home" class="a">Home</a>
				</li>
				<li class="li">
					<a href="#home" title="Home" class="a">Home</a>
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
		transition: all ease 500ms;
		.header-menu {
			display: none;
		}
		.h1 {
			justify-self: flex-start;
			
			.a {
				transition: all ease 250ms;
				font-family: var(--font-family-secondary);
				transition: ease-in-out all 300ms;
				font-style: oblique;
				font-size: 3rem;
				text-shadow: 0px 0px 3px var(--color-palette--primary);
				color: var(--color-primary);
				&:hover {
					text-shadow: -0.2rem 0.1rem 1rem var(--color-palette--primary);

					transform: translateX(5px);
					transform: translateY(-3px);
				}
			}
		}
		.nav {
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
						transition: all ease-in-out 190ms;
						position: relative;
						font-family: var(--font-family-primary);
						font-size: 1.3rem;
						font-weight: bold;

						z-index: 1;

						text-shadow: 0 0 0.5rem rgb(114, 114, 114);
						color: var(--color-primary);
						transform: scale(0.9);

						&:hover {
							transform: scale(1.4);
							text-shadow: 0 0 2rem white,
								0 0 10rem var(--color-palette--primary);
						}
					}
				}
			}
		}
	}

	@media screen and (width <= 800px) {
		.header {
			transition: all ease-out .4s;
			padding: 0;
			.header-menu {
				display: block;
			}
			.h1 {
				transition: all ease-in-out 400ms;
				padding-left: 1rem;
				&.h1-isDeployed {
					position: absolute;
					opacity: 1;

					z-index: -1;

					.a {
						text-align: center;
					}

					.a {
						color: var(--color-secondary);
					}
				}
			}
			.nav {
				transform: translateX(0);
				

				height: auto;

				.ul {
					justify-content: center;
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
