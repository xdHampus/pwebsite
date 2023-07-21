<script lang="ts">
	import RepoCard from '$lib/elements/RepoCard.svelte';
	import type { Repo } from '$lib/util/repo';

	let repos: Repo[] = [
		{
			title: 'pwebsite',
			description: 'My personal website.',
			language: 'Svelte',
			url: 'https://github.com/xdhampus/pwebsite'
		},
		{
			title: 'pwebsite',
			description: 'My personal website.',
			language: 'Svelte',
			url: 'https://github.com/xdhampus/pwebsite'
		},
		{
			title: 'pwebsite',
			description: 'My personal website.',
			language: 'Svelte',
			url: 'https://github.com/xdhampus/pwebsite'
		},
		{
			title: 'pwebsite',
			description: 'My personal website.',
			language: 'Svelte',
			url: 'https://github.com/xdhampus/pwebsite'
		},
		{
			title: 'pwebsite',
			description: 'My personal website.',
			language: 'Svelte',
			url: 'https://github.com/xdhampus/pwebsite'
		},
	];
</script>

<section id="code">
	<h2>code</h2>

	<div>
		{#each repos as curRepo}
			<div>
				<RepoCard repo={curRepo} />
			</div>
		{/each}
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