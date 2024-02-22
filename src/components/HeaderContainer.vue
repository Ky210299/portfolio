<script lang="ts">
	import { defineComponent, ref } from "vue";
	import IconArrowBarLeft from "./icons/IconArrowBarLeft.vue";
	import IconArrowBarRigth from "./icons/IconArrowBarRigth.vue";
	export default defineComponent({
		setup() {
			const isDeployed = ref<boolean>(false);
			return { isDeployed };
		},

		components: { IconArrowBarLeft, IconArrowBarRigth },
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<header class="header">
		<h1 class="h1"><a href="#home" class="a">LBM</a></h1>
		<nav class="nav" :class="{'nav-show' : isDeployed}" >
			<ul class="ul">
				<li class="li"><a href="#home" title="Home" class="a">Home</a></li>
				<li class="li">
					<a href="#projects" title="Projects" class="a">Projects</a>
				</li>
				<li class="li"><a href="#about" title="About" class="a">About</a></li>
			</ul>
		</nav>
		<IconArrowBarRigth
			v-if="isDeployed"
			@click="isDeployed = !isDeployed"
			class="header-menu"
		/>
		<IconArrowBarLeft
			v-else
			:class="{ show: !isDeployed }"
			@click="isDeployed = !isDeployed"
			id="nav-menu"
			class="header-menu"
		/>
	</header>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.header {
		.nav {
			.ul {
				display: flex;
				flex-flow: row nowrap;
				align-items: center;
				gap: 1rem;

				.li {
					margin: 0 1rem;

					.a {
						position: relative;
						transition: ease-in all 150ms;
						z-index: 1;
						padding: 0.2rem;
						color: white;
						border-radius: 0.5rem;
						font-family: var(--font-family-secondary);

						&::before,
						&::after {
							content: "";
							position: absolute;
							width: 100%;
							height: 100%;
							transition: 300ms;

							opacity: 0;
						}
						&::before {
							border-top: 1px solid white;
							top: 0;
							left: 0;
							border-top: 2px solid grey;
							border-bottom: 2px solid grey;
							transform: scale(2);
						}
						&::after {
							bottom: px;
							left: 0;
							top: 2px;

							z-index: -1;
							transform: scale(0);
						}
						&:hover {
							background-color: #000;
							text-shadow: 0 0 1rem rgb(255, 255, 255), 0 0 0.3rem white;
							&::after,
							&::before {
								opacity: 1;
								transform: scale(1);
							}
						}
					}
				}
			}
		}
		/* .header-menu {
			display: none;
		} */
	}

	@media screen and (width <= 800px) {
		.header {
			.header-menu.show {
				display: block;
			}
			.nav {
				display: none;
			}
			.nav-show{
				display: flex;
			}
		}
	}
</style>
