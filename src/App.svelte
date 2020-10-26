<script context="module">
  let opt = {
    margin: 0,
    filename: "product.pdf",
    image: { type: "jpeg", quality: 0.98 },
    html2canvas: { scale: 5 },
  };

  export function viewPDF() {
    html2pdf()
      .from(document.getElementById("toPDF"))
      .set(opt)
      .output("dataurlstring")
      .then(function (pdfAsString) {
        document.getElementById("pdfViewer").src = pdfAsString;
      });
  }

  export function downloadPDF() {
    html2pdf().from(document.getElementById("toPDF")).set(opt).save();
  }
</script>

<script>
  import Page from "./components/Page.svelte";

  import * as bandePrimaPLY from "./data/bandePrimaPLY.json";
  import * as bandePrimaFlex from "./data/bandePrimaFlex.json";
  import * as bandePrimaLiftTextile from "./data/bandePrimaLiftTextile.json";
  import * as bandePrimaRock from "./data/bandePrimaRock.json";
  import * as bandePrimaStable from "./data/bandePrimaStable.json";
  import * as bandePrimaSteel from "./data/bandePrimaSteel.json";
  const products = [
    "bandePrimaPLY",
    "bandePrimaFlex",
    "bandePrimaLiftTextile",
    "bandePrimaRock",
    "bandePrimaStable",
    "bandePrimaSteel",
  ];

  $: selected = products[0];
  $: data = eval(selected);

  $: hidePreview = true;
</script>

<style>
  header {
    color: white;
    padding: 1rem;
  }

  h2 {
    color: white;
    text-align: center;
  }
  h2:after {
    display: none;
  }

  form {
    display: flex;
  }

  button,
  select {
    color: inherit;
    background: none;
    border: solid 2px white;
    font-size: inherit;
    padding: 0.5rem;
    margin-right: 1rem;
  }

  iframe {
    width: 100%;
    height: 150vw;
    max-width: 210mm;
    max-height: 297mm;
    margin: 0 auto;
    display: block;
    transition: 0.2s ease-in;
  }
</style>

<header>
  <h1>Fiches produits ABM TECNA</h1>
  <form on:submit|preventDefault>
    <select bind:value={selected}>
      {#each products as product}
        <option value={product}>{product}</option>
      {/each}
    </select>
    <button on:click={downloadPDF}>Download PDF</button>
    <button on:click={viewPDF}>Preview PDF</button>
    <!-- <button
      on:click={() => (hidePreview = !hidePreview)}>{hidePreview ? 'Hide' : 'Show'}
      Preview</button> -->
  </form>
</header>
{#if hidePreview}
  <h2>Preview HTML</h2>
  <div id="toPDF">
    <Page {data} />
  </div>
{/if}
<h2>Preview PDF</h2>
<iframe id="pdfViewer" title="" />
