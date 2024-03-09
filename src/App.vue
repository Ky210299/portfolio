<template>
	<div ref="test" @scroll="onScroll()" class="scroll">
		<HeaderContainer :class="{ show: scrollDown }" />
		<Home />
		<main class="main">
			<Projects />
		</main>
		<About />
	</div>
</template>

<script lang="ts" setup>
	import { ref } from "vue";
	import HeaderContainer from "./components/HeaderContainer.vue";
	import Home from "./views/Home.vue";

	import Projects from "./views/Projects.vue";
	import About from "./views/About.vue";

	const position = ref(0);
	const scrollDown = ref(false);
	const test = ref();

	const onScroll = () => {
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
	.show {
		transform: translateY(-100%);
	}
</style>
