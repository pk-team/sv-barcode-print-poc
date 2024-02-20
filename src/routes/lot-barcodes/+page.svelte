<script lang="ts">
	import KitBarcodeSet from '$lib/components/LotBarcode/KitBarcodeSet.svelte';
	import { lots } from '$lib/data';
</script>

<h1> Lots and Kits</h1>

{#each lots as lot}
	<div class="lot">
		<h2>Lot: <a href={`/lot-barcodes/lot/${lot.lotNo}`}>{lot.lotNo} {lot.pcv} {lot.model}</a></h2>
		{#each lot.kits as kit}
			<a href={`/lot-barcodes/kit/${kit.kitNo}`}>kit {kit.kitNo}</a>
		{/each}
	</div>
	
{/each}

<style>
	.lot {
		padding-left: 1rem;
		margin-bottom: 1rem;
	}

	.lot a {
		display: block;
	}
	
	.kit {
		padding-left: 2rem;
	}
</style>
