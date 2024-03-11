<script lang="ts">
	import { defineComponent, ref } from "vue";
	export default defineComponent({
		setup() {
			const profileUrl = "https://api.github.com/users/Ky210299";
			let imgSrc = ref<string>("");
			fetch(profileUrl, {
				method: "GET",
				headers: {
					"X-GitHub-Api-Version": "2022-11-28",
				},
			})
				.then((response) => {
					if (!response.ok) {
						throw new Error("Error to fetch user account");
					}

					return response.json();
				})
				.then((userData) => {
					imgSrc.value = userData.avatar_url;
				})
				.catch((error) => {
					console.log("Error ", error);
				});
			return { imgSrc };
		},
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<section id="about" class="about-section">
		<div class="text">
			<h2 class="h2">About me</h2>
			<p class="p">
				Full stack web developer with an electrical engineering background.
			</p>
			<p class="p">
				I love setting myself new challenges that solve problems or optimize
				results.
			</p>
			<p class="p">
				I enjoy teamwork and I believe it is the best way to achieve great
				things.
			</p>
		</div>
		<div class="picture">
			<img :src="imgSrc" alt="Leonardo Picture" class="img" />
		</div>
	</section>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.about-section {
		width: 90vw;
		display: flex;
		flex-flow: row wrap-reverse;
		justify-content: space-around;
		align-items: center;
		gap: 2rem;
		.text {
			flex: 1;
			max-width: 25rem;
			min-width: 13rem;
			.h2 {
				font-family: var(--font-family-secondary);
				font-size: 2rem;
				font-weight: bold;
				margin-bottom: 1rem;
				border-bottom: 1px solid var(--color-palette--secondary);
				padding-left: 1rem;
				&::first-letter {
					font-size: 3rem;
					color: var(--color-palette--tertiary);
				}
			}
			.p {
				font-style: var(--font-family-primary);
				font-size: 1rem;
				text-wrap: pretty;
				padding: 0rem 1rem;
				margin-bottom: 1rem;
			}
		}
		.picture {
			overflow: hidden;
			border-radius: 100%;
			border: 1px solid var(--color-palette--tertiary);
			.img {
				max-width: 18rem;
				object-fit: cover;
			}
		}
	}
</style>
