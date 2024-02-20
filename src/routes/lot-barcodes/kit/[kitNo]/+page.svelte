<script lang="ts">
	import { page } from '$app/stores';
	import KitBarcodeSet from '$lib/components/LotBarcode/KitBarcodeSet.svelte';
	import { lots } from '$lib/data';

	let lot = lots.find((lot) => lot.lotNo === $page.params.kitNo.slice(0,15));
	let kit = lot?.kits?.find((kit) => kit.kitNo === $page.params.kitNo) ?? null;
</script>

{#if kit}
    <KitBarcodeSet {kit} />
{:else}
    <div>not found</div>
{/if}
