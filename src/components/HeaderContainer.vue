<script lang="ts">
	import { defineComponent, Ref, ref } from "vue";
	import IconArrowBarLeft from "./icons/IconArrowBarLeft.vue";
	import IconArrowBarRigth from "./icons/IconArrowBarRigth.vue";
	export default defineComponent({
		setup() {
			let isDeployed: Ref<boolean> = ref(false);
			let hideHeader;
			return { isDeployed, hideHeader };
		
		},

		components: { IconArrowBarLeft, IconArrowBarRigth },
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<header  class="header">
		<h1 :class="{ 'h1-isDeployed': isDeployed }" class="h1">
			<a href="#home" class="a">LBM</a>
		</h1>
		<nav :class="{ 'nav-not-deployed': !isDeployed }" class="nav">
			<ul :class="{ 'nav-not-deployed': !isDeployed }" class="ul">
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
		z-index: 1;
		position: fixed;
		background: #18181840;
		backdrop-filter: blur(.5rem);
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
		.h1 {
			justify-self: flex-start;
			width: fit-content;
			height: fit-content;


			.a {
				transition: all ease 250ms;
				font-family: var(--font-family-secondary);
				transition: ease-in-out all 300ms;
				font-style: oblique;
				font-size: 3rem;
				text-shadow: 0px 0px 0.2rem var(--color-primary);
				color: var(--color-primary);
				background: none;
			}
			:hover {
				filter: brightness(2);
				background: none;
				transform: translateY(-3px);
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
						transition: all ease-in-out 190ms;
						position: relative;
						font-family: var(--font-family-primary);
						font-size: 1.3rem;
						font-weight: bold;

						z-index: 1;

						color: var(--color-primary);
						transform: scale(0.9);

						&:hover {
							transform: scale(1.2);
							text-shadow: 1px 1px 48px var(--color-secondary);
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
