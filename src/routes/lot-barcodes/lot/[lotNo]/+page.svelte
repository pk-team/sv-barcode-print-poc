<script lang="ts">
    import { page } from '$app/stores';
    import { lots } from '$lib/data';
    import LotBarcodes from '$lib/components/LotBarcode/LotBarcodes.svelte';

    let lot = lots.find((lot) => lot.lotNo === $page.params.lotNo) ?? null;
</script>

{#if lot}
    <LotBarcodes kits={lot.kits} />
{:else}
    <div>not found</div>
{/if}