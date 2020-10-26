<script>
  import Header from "./Header.svelte";
  import Main from "./Main.svelte";
  import Footer from "./Footer.svelte";

  import Coating from "./Coating.svelte";

  // import * as data from "../data/bandePrimaPLY.json";
  // import * as data from "../data/bandePrimaFlex.json";
  // import * as data from "../data/bandePrimaLiftTextile.json";
  // import * as data from "../data/bandePrimaRock.json";
  // import * as data from "../data/bandePrimaStable.json";
  import * as data from "../data/bandePrimaSteel.json";
</script>

<style>
  .page {
    background: white;
    margin: 0 auto;
    width: 210mm;
    height: 297mm;
    display: flex;
    flex-direction: column;
    position: relative;
  }
</style>

<div class="page">
  <Header {data} />
  <Main {data} />
  <Footer />
  <div class="border" />
</div>
