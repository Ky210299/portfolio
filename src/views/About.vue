<script lang="ts">
	import { defineComponent } from "vue";
	export default defineComponent({
		setup() {
			const profileUrl = "https://api.github.com/users/Ky210299";
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
					const imgE = document.createElement("img");
					imgE.src = userData.avatar_url;
					imgE.alt = "Leonardo Picture";
					const avatarContainerE = document.querySelector(".picture");
					avatarContainerE?.appendChild(imgE);
				})
				.catch((error) => {
					console.log("Error ", error);
				});
		},
	});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<section id="about" class="about-section">
		<div class="text">
			<h2 class="h2">About me</h2>
			<p class="p">
				Front-end and data science developer with an electrical engineering
				background.
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
		<div class="picture"></div>
	</section>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
	.about-section {
		font-family: var(--font-family-primary);
		display: flex;
		flex-flow: row wrap-reverse;
		justify-content: space-around;
		align-items: center;
		gap: 2rem;
		.text {
			flex: 8;
			max-width: 40rem;
			min-width: 20rem;
			.h2 {
				font-family: var(--font-family-secondary);
				font-size: 2rem;
				font-weight: bold;
				margin-bottom: 1rem;
				border-bottom: 1px solid var(--color-palette--secondary);
				padding-bottom: 1rem;
				&::first-letter {
					font-size: 3rem;
					color: var(--color-palette--opposite);
				}
			}
			.p {
				font-style: var(--font-family--secondary);

				text-wrap: pretty;
				padding: 0rem 1rem;
				margin-bottom: 1rem;
			}
		}
		.picture {
			
			
			width: 17em;
			margin: 3rem;
			border-radius: 100%;
			overflow: hidden;
			border: 1px solid var(--color-palette--opposite);
			

			img {
				
				aspect-ratio: 16/9;
				object-fit: scale-down;
				
			}
		}
	}
</style>
