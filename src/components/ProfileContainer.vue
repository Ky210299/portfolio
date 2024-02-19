<script lang="ts">
	import { defineComponent } from "vue";
	import BarSocials from "./BarSocials.vue";
	export default defineComponent({ components: { BarSocials } });
</script>

<template>
	<section class="profile-section">
		<div class="profile-section-text">
			<h2 class="h2">Hi! I'm Leonardo Bazan Marquez</h2>
			<h3 class="h3">FullStack Developep</h3>
		</div>
		<BarSocials />
	</section>
</template>

<style scoped></style>
