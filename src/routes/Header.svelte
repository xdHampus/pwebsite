<script lang="ts">
	import { page } from '$app/stores';

	const links = [
		{ title: "Home", url: "/" },
		{ title: "Color", url: "/color" },
		{ title: "code", url: "/code" },
  	];
</script>

<header class="flex justify-center w-screen ">
	<div class="flex-1"></div>
	<nav class="justify-center inline-flex bg-mantle rounded-3xl gap-1">
		{#each links as link}
			<!-- svelte-ignore a11y-click-events-have-key-events -->
			<a 
				class="active:brightness-110 hover:brightness-100 rounded-3xl 
					{$page.url.pathname === link.url ? 'bg-flamingo active:bg-flamingo' : 'hover:bg-surface0 active:bg-surface0'}
				" 
				href={link.url}
				>
				<span
					class="{$page.url.pathname === link.url ? 'text-base' : 'text-flamingo'}"
				>{link.title}</span>
			</a>
		{/each}
	</nav>
	<div class="flex-1"></div>
</header>

<style>

	nav {
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: space-around;
	}

	a {
		width: 8em;
		padding: 0 1em 0 1em;
		display: flex;
		align-items: center;
		justify-content: center;
		transition-duration: 75ms;
		filter: brightness(0.95);
	}
	span {
		font-weight: 700;
		font-size: 1.3em;
		text-transform: lowercase;
		letter-spacing: 0.01em;
	}

</style>
