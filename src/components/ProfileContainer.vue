<script lang="ts">
	import { defineComponent } from "vue";
	import BarSocials from "./BarSocials.vue";
	export default defineComponent({ components: { BarSocials } });
</script>

<template>
	<section class="profile-section">
		<div class="profile-section-text">
			<h2 class="h2"><em>Hi! I'm Leonardo Bazan Marquez</em></h2>
			<h3 class="h3"><strong>Frontend Developep</strong></h3>
			<BarSocials />
		</div>
		<div class="imagen"> Algo bonito aqui</div>
	</section>
</template>

<style scoped>

</style>
