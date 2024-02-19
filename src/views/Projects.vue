<script lang="ts">
	import { defineComponent } from "vue";
	import BarProjectFilter from "../components/BarProjectFilter.vue";
	import BarIndex from "../components/BarIndex.vue";
	import CardProjectContainer from "../components/CardProjectContainer.vue";
	export default defineComponent({
		components: { BarProjectFilter, BarIndex, CardProjectContainer },
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<aside class="aside">
		<select name="technologies" id="technologies-filter">
			Tech
		</select>
		<select name="languages" id="technologies-filter">
			Lang
		</select>
		<select name="date" id="technologies-filter">
			Date
		</select>
	</aside>
	<section class="projects-section" id="projects">
		<h2 class="h2">Projects</h2>

		<div class="grid">
			<article class="article">
				<a href="#" title="Project Title">
					<img src="#" alt="Imagen" class="img" loading="lazy" />
					<h4 class="h4">Project Name</h4>
				</a>
			</article>
			<article class="article">
				<a href="#" title="Project Title">
					<img src="#" alt="Imagen" class="img" loading="lazy" />
					<h4 class="h4">Project Name</h4>
				</a>
			</article>
			<article class="article">
				<a href="#" title="Project Title">
					<img src="#" alt="Imagen" class="img" loading="lazy" />
					<h4 class="h4">Project Name</h4>
				</a>
			</article>
			<article class="article">
				<a href="#" title="Project Title">
					<img src="#" alt="Imagen" class="img" loading="lazy" />
					<h4 class="h4">Project Name</h4>
				</a>
			</article>
		</div>
	</section>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped></style>
