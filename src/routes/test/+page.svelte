<script lang="ts">
	import Barcode from "$lib/components/LotBarcode/Barcode.svelte";

    
</script>
<h1 class="no-print">Types of barcodes</h1>

<div class="grid print" >
    <Barcode type="code128" text="BPA3A2A2335500103"  maxWidthPx={300} />
    <Barcode type="code39" text="BPA3A2A2335500103" maxWidthPx={300} />
    <Barcode type="pdf417" text="BPA3A2A2335500103" maxWidthPx={300} />
</div>

<style>

    .grid {
        display: grid;
        grid-auto-rows: 200px;
        gap: 1rem;
        width: 500px;
        margin-inline: auto;
        border: 1px solid blue;
    }

/*     
    @media print {
        :not(.print) {
            display: none;
        }
    } */
</style>