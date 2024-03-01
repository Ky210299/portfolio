<template>
	<div ref="test" @scroll="onScroll($event)" class="scroll">
		<HeaderContainer :class="{ 'show' : scrollDown }" />
		<ProfileContainer />
		<main class="main">
			<Projects />
		</main>
		<About />
		<AppFooter />
	</div>
</template>

<script lang="ts" setup>
	import { ref } from "vue";
	import HeaderContainer from "./components/HeaderContainer.vue";
	import ProfileContainer from "./components/ProfileContainer.vue";
	import Projects from "./views/Projects.vue";
	import About from "./views/About.vue";
	import AppFooter from "./components/AppFooter.vue";
	// import Background from "./components/Background.vue";

	const position = ref(0);
	const scrollDown = ref(false);
	const test = ref();

	const onScroll = (event: any) => {
		const scroll = test.value.scrollTop;

		if (scroll > position.value) {
			scrollDown.value = true;
		} else {
			scrollDown.value = false;
		}
		position.value = scroll;
	};
</script>
<style scoped>
	.scroll {
		height: 100vh;
		overflow-y: scroll;
	}
	.show{
		transform: translateY(-100%);
	}
</style>
