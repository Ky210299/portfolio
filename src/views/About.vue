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
				Frontend web developer with an electrical engineering
				background.
			</p>
			<p class="p">
				I love setting myself new challenges that solve problems or
				optimize
				results.
			</p>
			<p class="p">
				I enjoy teamwork and I believe it is the best way to achieve
				great
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
	justify-content: space-between;
	align-items: center;

	.text {
		margin: auto;
		max-width: 19rem;

		.h2 {
			font-family: var(--font-family-secondary);
			font-size: 2rem;
			font-weight: bold;
			margin-bottom: 1rem;
			border-bottom: 1px solid var(--color-palette--cuaternary);
			padding-left: 1rem;

			&::first-letter {
				font-size: 2em;
				color: var(--color-palette--cuaternary);
			}
		}

		.p {
			font-style: var(--font-family-primary);
			font-size: 1rem;
			text-wrap: pretty;
			line-height: 100%;
			margin-bottom: .5rem;

		}
	}

	.picture {
		overflow: hidden;
		border-radius: 100%;
		max-width: 15rem;
		margin: auto;
		box-shadow: 0 0 .5rem black;

		.img {
			object-fit: cover;
		}
	}
}
</style>
