<script context="module" lang="ts">
  export type  BarcodeType = 'code128' | 'code39' | 'code93' | 'codabar' | 'i2of5' | '2of5' | 'upc' | 'ean' | 'isbn' | 'pdf417' | 'datamatrix' | 'qrcode' | 'maxicode' | 'azteccode' | 'datamatrix' | 'datamatrixrect' | 'code128' | 'code39' | 'code93' | 'codabar' | 'i2of5' | '2of5' | 'upc' | 'ean' | 'isbn' | 'pdf417' | 'datamatrix' | 'qrcode' | 'maxicode' | 'azteccode' | 'datamatrix' | 'datamatrixrect' | 'code128' | 'code39' | 'code93' | 'codabar' | 'i2of5' | '2of5' | 'upc' | 'ean' | 'isbn' | 'pdf417' | 'datamatrix' | 'qrcode' | 'maxicode' | 'azteccode' | 'datamatrix' | 'datamatrixrect' | 'code128' | 'code39' | 'code93' | 'codabar' | 'i2of5' | '2of5' | 'upc' | 'ean' | 'isbn' | 'pdf417' | 'datamatrix' | 'qrcode' | 'maxicode' | 'azteccode' | 'datamatrix' | 'datamatrixrect' | 'code128' | 'code39' | 'code93' | 'codabar' | 'i2of5' | '2of5' | 'upc' | 'ean' | 'isbn' | 'pdf417' | 'datamatrix' | 'qrcode' | 'maxicode' | 'azteccode' | 'datamatrix' | 'datamatrixrect' | 'code128' | 'code39' | 'code93' | 'codabar' | 'i2of5' | '2of5' | 'upc' | 'ean' | 'isbn' | 'pdf417' | 'datamatrix' | 'qrcode' | 'maxicode'
   
</script>

<script lang="ts">
  import { onMount } from 'svelte';
  import * as bwipjs from 'bwip-js';

  export let type: BarcodeType = 'code128';
  export let text: string = 'Example Text';
  export let includetext = false
  export let maxWidthPx : number  | undefined = undefined;

  let canvasElement: HTMLCanvasElement;

  let style = maxWidthPx ? 'max-width: ' + maxWidthPx + 'px' : '';

  onMount(() => {
    try {
      bwipjs.toCanvas(canvasElement, {
        bcid: type,           // Barcode type
        text: text,              // Text to encode
        scale: 3,                // 3x scaling factor
        height: 10,              // Bar height, in millimeters
        includetext,       // Show human-readable text
        textxalign: 'center',    // Always good to set this
      });
    } catch (err) {
      console.error(err);
    }
  });
</script>

<canvas bind:this={canvasElement} {style}></canvas>
