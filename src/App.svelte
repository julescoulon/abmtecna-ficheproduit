<script context="module">
</script>

<script>
  import Page from "./components/Page.svelte";

  import * as bandePrimaPLY from "./data/bandePrimaPLY.json";
  import * as bandePrimaFlex from "./data/bandePrimaFlex.json";
  import * as bandePrimaLiftTextile from "./data/bandePrimaLiftTextile.json";
  import * as bandePrimaRock from "./data/bandePrimaRock.json";
  import * as bandePrimaStable from "./data/bandePrimaStable.json";
  import * as bandePrimaSteel from "./data/bandePrimaSteel.json";
  import { onMount } from "svelte";
  import Icon from "./components/Icon.svelte";
  const products = [
    "bandePrimaPLY",
    "bandePrimaFlex",
    "bandePrimaLiftTextile",
    "bandePrimaRock",
    "bandePrimaStable",
    "bandePrimaSteel",
  ];

  let toPDF, pdfViewer, opt;
  onMount(() => {
    toPDF = document.getElementById("toPDF");
    pdfViewer = document.getElementById("pdfViewer");
    opt = {
      margin: 0,
      filename: data.title + ".pdf",
      image: { type: "jpeg", quality: 0.98 },
      html2canvas: { scale: 8, dpi: 300, letterRendering: true },
      // jsPDF: { unit: "mm", format: "a4", orientation: "portrait" },
    };
  });

  function viewPDF() {
    html2pdf()
      .then(() => (state = "loading"))
      .set(opt)
      .from(toPDF)
      .toPdf()
      .get("pdf")
      .then(function (pdf) {
        let numberOfPages = pdf.internal.getNumberOfPages();
        pdf.deletePage(numberOfPages);
      })
      .output("dataurlstring")
      .then(function (pdfAsString) {
        pdfViewer.src = pdfAsString;
        state = "done";
      });
  }

  function downloadPDF() {
    html2pdf()
      .set(opt)
      .from(toPDF)
      .toPdf()
      .get("pdf")
      .then(function (pdf) {
        pdf.deletePage(2);
      })
      .save();
  }

  $: selected = products[0];
  $: data = eval(selected);

  let type = "catalogue";
  $: type, console.log("Type : ", type);

  let state = "";

  $: state, console.log("State : ", state);
</script>

<style>
  header,
  nav {
    color: white;
    padding: 1rem;
    z-index: 999;
  }

  nav {
    position: sticky;
    left: 0;
    right: 0;
    top: 0;
    background: #303030;
  }

  h1,
  h2 {
    text-align: center;
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
    align-items: center;
  }

  .column {
    display: flex;
    flex-direction: column;
    padding-right: 1rem;
    line-height: 1.5;
  }

  .state {
    transform: scale(2);
    margin: 0 auto;
  }

  a,
  select {
    color: inherit;
    background: none;
    border: solid 2px white;
    font-size: inherit;
    padding: 0.5rem;
    margin-right: 1rem;
  }

  a:hover {
    color: #303030;
    background: white;
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

  #toPDF {
    width: 210mm;
    margin: 0 auto;
  }
</style>

<header>
  <h1>Fiches produits ABM TECNA</h1>
</header>
<nav>
  <form on:submit|preventDefault>
    <div class="column">
      <label>
        <input type="radio" bind:group={type} value="fiche" checked={true} />
        Fiche produit
      </label>
      <label>
        <input type="radio" bind:group={type} value="catalogue" />
        Catalogue
      </label>
    </div>

    {#if type == 'fiche'}
      <select bind:value={selected}>
        {#each products as product}
          <option value={product}>{product}</option>
        {/each}
      </select>
    {/if}
    <div class="state">
      {#if state == 'loading'}
        <Icon icon={'spinner'} />
      {:else if state == 'done'}
        <Icon icon={'check'} />
      {/if}
    </div>

    <div class="action">
      <a href="./#" on:click={downloadPDF}>Download PDF</a>
      <a href="./#preview" on:click={viewPDF}>Preview PDF</a>
    </div>
  </form>
</nav>
<h2>Preview HTML</h2>
<div id="toPDF">
  <Page {data} {type} />
</div>
<h2 id="preview">Preview PDF</h2>
<iframe id="pdfViewer" title="" />
