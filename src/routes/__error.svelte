<script context="module" lang="ts">
	import type { Load } from '@sveltejs/kit'

	export const load: Load = ({ error, status }) => {
		return {
			props: {
				title: `${status}: ${error.message}`
			}
		}
	}
</script>

<script lang="ts">
	export let title: string
</script>

<div class="error">
	<h1>{title}</h1>
	<a class="btn" href="/">Come Back Home 🏠</a>
	<img src="/10.svg" alt="404" />
</div>

<style>
	.home:hover {
		opacity: 90%;
	}
	.error {
		height: 100vh;
		display: grid;
		gap: var(--spacing-32);
		place-content: center;
		place-items: center;
	}

	img {
		max-width: 50vw;
		max-height: 70vh;
		border-radius: 50%;
		object-fit: cover;
	}
</style>
