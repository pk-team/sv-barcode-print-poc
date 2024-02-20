<script lang="ts">
	import Barcode from "./Barcode.svelte";

    export let text = ''
    export let title = ''
</script>

<div class='barcode-label print' >
    <div class="title">{title}</div>
    <div class="value">{text}</div>
    <Barcode {text} type={"code128"} />
</div>

<style>
    .barcode-label {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.25rem;
        font-family: monospace;
        font-weight: bold;
        padding: 1rem;
        border: 1px solid #000;
    }

    .title {
        font-size: 1rem;
    }

    .value {
        font-size: 1.25rem;
    }

    @media print {
        
        .barcode-label {
            height: 100vh;
            width: 100vw;
            justify-content: center;
            page-break-inside: avoid;
            padding: 1rem;
        }


    }
</style>