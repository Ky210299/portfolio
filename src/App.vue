<template>
	<div ref="test" class="scroll">
		<HeaderContainer />
		<Home id="home" />
		<main class="main" id="projects">
			<Projects />
		</main>
		<Contact id="contact" />
		<About />
	</div>
</template>

<script lang="ts" setup>

import HeaderContainer from "./components/HeaderContainer.vue";
import Home from "./views/Home.vue";
import Projects from "./views/Projects.vue";
import Contact from "./views/Contact.vue";
import About from "./views/About.vue";



</script>
<style>
.header {
	.nav {
		flex-grow: 1;
	}

	.h1 {
		flex-shrink: 1;
		justify-self: flex-start;
	}

	.header-menu {
		flex-shrink: 0;
		justify-self: flex-end;
	}
}

.profile-section {
	width: 90vw;
	display: flex;
	min-height: 100dvh;
	margin: auto;

}

.main {
	width: 90vw;
	margin: auto;
	display: flex;
	flex-flow: column wrap;
	justify-content: space-around;
	align-items: center;
	min-height: 100dvh;
	padding: 2rem;
	padding-top: 3rem;

}

.about-section {
	margin: auto;
	min-height: 100dvh;
	padding: 2rem;
	margin-top: 10rem;
}

#contact {
	width: 90vw;
	min-height: 100dvh;
	margin: auto;
	padding-inline: 2rem;
	padding-top: 4rem;

}

.footer {
	height: 5dvh;
}
</style>
