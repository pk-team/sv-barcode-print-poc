<script lang="ts">
	import type { KitBarcode } from '../types';
	import KItBarcodeSet from './KitBarcodeSet.svelte';

	export let kits: KitBarcode[] = [];
</script>

{#each kits as kit}
	<KItBarcodeSet {kit} />
{/each}
