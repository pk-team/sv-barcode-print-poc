<script lang="ts">
	import type { KitBarcode } from "../types";
	import BarcodeLabel from "./BarcodeLabel.svelte";

    export let kit: KitBarcode
</script>

<div class="kit-barcode-set">
	<BarcodeLabel title={`PCV ${kit.model}`} text={kit.pcv} />
	<BarcodeLabel title={`KIT ${kit.model}`} text={kit.kitNo} />
	<BarcodeLabel title={`VIN ${kit.model}`} text={kit.vin} />
</div>