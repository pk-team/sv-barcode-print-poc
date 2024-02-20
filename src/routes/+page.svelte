<script lang="ts">
	import { lots } from '$lib/data';
</script>

<h1>Lots and Kits</h1>

{#each lots as lot}
	<div class="lot">
		<h2>Lot: <a href={`/lot-barcodes/lot/${lot.lotNo}`}>{lot.lotNo} {lot.pcv} {lot.model}</a></h2>
		<div class="kits">
			{#each lot.kits as kit}
				<div class="kit">
					<a href={`/lot-barcodes/kit/${kit.kitNo}`}>Kit {kit.kitNo}</a>
				</div>
			{/each}
		</div>
	</div>
{/each}

<style>
	.lot {
		margin-bottom: 1rem;
	}

	.lot h2 {
		font-weight: 400;
		margin-bottom: 0.5rem;
	}

	.lot h2 a {
		font-weight: 600;
	}

	.kits {
		display: flex;
		flex-direction: column;
		border-left: var(--border);
		border-width: 2px;
		padding-left: 1rem;
		margin-left: 0.5rem;
	}

	.kit {
		padding: 0.5rem 0;
		border-bottom: var(--border);
		stroke-width: 2px;
	}

	.kit:hover {
		cursor: pointer;
		background-color: #f0f0f0;
	}

	.kit:hover a {
		font-weight: 600;
	}
</style>
