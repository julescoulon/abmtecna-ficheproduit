<script>
  import Header from "./fiches/Header.svelte";
  import Main from "./fiches/Main.svelte";
  import Footer from "./fiches/Footer.svelte";
  import Couverture from "./catalogue/Couverture.svelte";
  import CouvertureArriere from "./catalogue/CouvertureArriere.svelte";

  export let data;
  export let type;
</script>

<style>
  .page {
    background: white;
    height: 297mm;

    /* display: flex;
    flex-direction: column; */
    position: relative;
  }

  main {
    flex-grow: 1;
    padding: 0 4rem;
    padding-top: 2.5rem;
  }
</style>

<!-- Catalogue -->

{#if type == 'fiche'}
  <div class="page">
    <Header {data} />
    <main>
      <Main {data} />
    </main>
    <Footer />
  </div>
{:else if type == 'catalogue'}
  <div class="page">
    <Couverture />
  </div>
  <div class="page">
    <Header {data} />
    <main>
      <Main {data} />
    </main>
    <Footer />
  </div>
  <div class="page">
    <CouvertureArriere />
  </div>
{/if}
