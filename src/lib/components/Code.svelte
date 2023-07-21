<script lang="ts">
	import RepoCard from '$lib/elements/RepoCard.svelte';
	import type { Repo } from '$lib/util/repo';
	import { onMount } from 'svelte';

	let repos: Repo[];
	onMount(async () => {
		const res = await fetch('https://api.github.com/users/xdHampus/repos');
		repos = await res.json();
		repos.sort((a, b) => {
			return new Date(a.pushed_at) < new Date(b.pushed_at) ? 1 : -1;
		});
	});
</script>

<section id="code">
	<h2>code</h2>

	<div>
		{#if repos}
			{#each repos as curRepo}
				<div>
					<RepoCard repo={curRepo} />
				</div>
			{/each}
		{/if}
	</div>
</section>

<style lang="scss">
	#code > div {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	@media (min-width: 768px) {
		#code > div {
			display: flex;
			flex-direction: row;
			flex-wrap: wrap;
			row-gap: 3%;
			column-gap: 1%;
			margin-left: 10%;
			margin-right: 10%;
			justify-content: space-between;
		}
		#code > div > div {
			width: 48%;
		}
	}
</style>
