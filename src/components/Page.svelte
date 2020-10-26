<script>
  import Header from "./Header.svelte";
  import Main from "./Main.svelte";
  import Footer from "./Footer.svelte";

  import Coating from "./Coating.svelte";

  export let data;
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
</div>
