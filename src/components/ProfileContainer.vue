<script lang="ts">
	import { defineComponent } from "vue";
	import BarSocials from "./BarSocials.vue";
	export default defineComponent({ components: { BarSocials } });
</script>

<template>
	<section class="profile-section" id="home">
		<div class="profile-section-text">
			<h2 class="h2">Hi! I'm Leonardo Bazan Marquez</h2>
			<h3 class="h3">
				<strong>Frontend developed and data scientist</strong>
			</h3>
			<BarSocials />
		</div>
	</section>
</template>

<style scoped></style>
