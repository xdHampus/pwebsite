<script lang="ts">
	import Header from './Header.svelte';
	import '../app.css';
	import IconGithub from '~icons/mdi/github';
	import SunnyOutlineLoop from '~icons/line-md/sunny-outline-loop';
	import MoonAltLoop from '~icons/line-md/moon-alt-loop';

	import { writable } from 'svelte/store'

	import { Card } from '$lib/components/components';
	import { onMount } from 'svelte'
	
	export const lightMode = writable(false);
	

	onMount(async () => {
		
		if (typeof localStorage !== 'undefined') {
			lightMode.set(localStorage['lightMode'] === 'true' || false)
			lightMode.subscribe((value) => localStorage['lightMode'] = value)
		}

		lightMode.set(window.matchMedia('(prefers-color-scheme: light)').matches)

	})


</script>

<div class="h-screen bg-base text-text app {$lightMode == true ? 'latte':'frappe'}">
	<Header />

	<main>
		<slot />
	</main>

	<footer>
		<button class:hidden={!$lightMode} on:click={() => lightMode.set(false)}>
			<MoonAltLoop class="ease-in-out duration-200 hover:scale-125" />
		</button>
		<button class:hidden={$lightMode} on:click={() => lightMode.set(true)}>
			<SunnyOutlineLoop class="ease-in-out duration-200 hover:scale-125" />
		</button>

		<p>xdHampus</p>
		
		<a href="https://github.com/xdHampus">
			<IconGithub class="ease-in-out duration-200 hover:scale-125" />
		</a>
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: row;
		justify-content: center;
		gap: 0.5rem;
		align-items: center;
		padding: 12px;
	}

	footer {
		font-weight: bold;
		font-size: 1.5em;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
