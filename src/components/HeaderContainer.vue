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
				name: "Contact",
				id: "#contact",
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
	<header class="header" :class="{ 'header__is-deployed': isDeployed }">
		<div :class="{ 'logo-isDeployed': isDeployed }" class="logo">
			<a href="#home" class="a">LBM</a>
		</div>
		<nav :class="{ 'nav-not-deployed': !isDeployed }" class="nav">
			<ul :class="{ 'nav-not-deployed': !isDeployed }" class="ul">
				<li class="li" v-for="page of pages" :key="page.id">
					<a :href="page.id" :title="page.name" class="a">{{ page.name
						}}</a>
				</li>
			</ul>
		</nav>
		<IconArrowBarRigth v-show="isDeployed" @click="isDeployed = !isDeployed" class="header-menu" />
		<IconArrowBarLeft v-show="!isDeployed" @click="isDeployed = !isDeployed" id="nav-menu" class="header-menu" />
	</header>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
.header {
	padding: 1rem;
	overflow: hidden;
	transition: all ease 500ms;
	z-index: 1;
	position: fixed;
	background: transparent;
	backdrop-filter: blur(10px);




	width: 100%;
	min-height: 2rem;
	max-height: 3rem;
	display: flex;
	flex-flow: row nowrap;
	align-items: center;

	.header-menu {
		display: none;
	}

	.logo {
		justify-self: flex-start;
		width: 0%;
		z-index: -12;

		.a {
			transition: ease-in-out all 200ms;
			font-family: var(--font-family-logo);
			font-size: 2rem;
			font-style: oblique;
			color: var(--color-primary);
		}

	}

	.nav {
		justify-self: flex-end;
		transition: ease-in all 200ms;
		background: transparent;

		.ul {
			display: flex;
			flex-flow: row wrap;
			align-items: center;
			justify-content: flex-end;
			gap: 1rem;

			background: none;

			.li {
				padding: 0.3rem;

				.a {
					position: relative;
					font-size: 1.2rem;

					color: var(--color-primary);
					font-family: var(--font-family-secondary);

					font-weight: 500;



					transition: all ease 300ms;
					transform: scale(1);

					&:hover {

						transform: scale(1.05);
					}
				}
			}
		}
	}
}

@media screen and (width <=800px) {
	.header {
		padding: 0;
		overflow: hidden;
		width: 100%;

		transition: all ease-out 0.4s;

		.header-menu {
			display: block;
			fill: var(--color-primary);
		}

		.logo {
			padding-left: 1rem;
			width: 0%;
			opacity: 1;

			transition: all ease-in-out .3s;

			.a {
				width: 100%;
			}


			&.logo-isDeployed {
				position: absolute;
				width: 0%;
				opacity: 0;
				filter: blur(1rem);

				.a {
					width: 0%;
				}
			}
		}

		.nav {
			justify-self: center;
			padding: 0;
			margin: 0;

			transition: all ease-out 0.8s;
			transform: translateX(0);

			.ul {
				padding: 0;
				margin: 0;
				gap: 1rem;
				justify-content: center;
				align-items: center;
				flex-wrap: wrap;

				.li {
					padding: 0;
					margin: 0;

					.a {
						padding: 0;
						margin: 0;
						font-size: 1.1rem;

						text-shadow: none;

						&:hover {
							text-shadow: none;

						}
					}
				}

				&.nav-not-deployed {
					flex-flow: row nowrap;
				}
			}

			&.nav-not-deployed {
				overflow: hidden;

				transform: translateX(300%) scale(0);
				transition: all ease-in 0.7s;
				opacity: 0;
			}
		}
	}
}
</style>
