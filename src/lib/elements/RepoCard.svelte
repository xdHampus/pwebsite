<script lang="ts">
	import type { Repo } from '$lib/util/repo';
	export let repo: Repo;
</script>

<div class="repo-card">
	<div class="repo-card-header">
		<p>
			{repo.name}
		</p>
		<a href={repo.html_url}>
			<img src="/icons/link-out.svg" alt="link" />
		</a>
	</div>
	<span class="repo-card-description">
		{repo.description || 'No description provided.'}
	</span>
	<span class="repo-card-language">
		{repo.language || 'Unspecified language'}
	</span>
</div>

<style lang="scss">
	.repo-card {
		border-radius: 1rem;
		background-color: var(--bg-2);
		border: var(--bg-2-stroke) 1px solid;

		padding: 10px 10px 10px 10px;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		gap: 5px;
		height: 80%;
	}

	.repo-card-header {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: baseline;
	}

	.repo-card-header > p {
		margin-top: 0px;
		margin-bottom: 5px;
		font-size: 1.6rem;
		font-weight: bold;
		color: var(--text-1);
	}

	.repo-card-header > a > img {
		scale: 1.8;
		padding-right: 10px;
	}

	.repo-card-description {
		font-size: 1.2rem;
	}

	.repo-card-language {
		font-style: italic;
		font-size: 1rem;
	}
</style>
