<script lang="ts">
	import type { KitBarcode } from '../types';
	import KitBarcodeSet from './KitBarcodeSet.svelte';

	export let kits: KitBarcode[] = [];
</script>

{#each kits as kit}
	<KitBarcodeSet {kit} />
{/each}
