<script lang="ts">
	import Barcode from "./Barcode.svelte";

    export let text = ''
    export let title = ''
</script>

<div class="barcode-label print"> 
    <div class="inner">
        <div class="title">{title}</div>
        <div class="value">{text}</div>
        <Barcode {text} type={"code128"} />
    </div>
</div>

<style>
    /* On windows machine, Seagull XP Driver Settings > Page Setup (you must do this EVERY time you print) */
    /* 3.8x2.85 inches (w+h), 0.1inch gap; Orientation: Portrait (both, incl in print dialog)*/

    .barcode-label {
        display: flex;
        flex-direction: column;
        align-items: center;
        font-family: monospace;
        font-weight: bold;
        padding: 1rem;
    }

    .inner {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.25rem;
    }

    .value {
        font-size: 1.25rem;
    }

    @media print {
        .barcode-label {
            width: 100%;
            height: 100vh;
            justify-content: center;
            page-break-after: always;
            padding: 0 1rem !important;
            border: 4px dashed black;
        }
        
        .inner {
            /* use only for shitty label printer */
            transform: rotateZ(90deg);
        }

        .barcode-label .value {
            text-overflow: ellipsis;
        }

        .barcode-label :global(canvas) {
            width: 100%;
        }
    }
</style>