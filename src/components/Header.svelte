<script>
  import Breadcrumb from "./Breadcrumb.svelte";
  import Icon from "./Icon.svelte";
  export let data;
</script>

<style>
  header {
    padding: 2rem 4rem;
    position: relative;
    z-index: 10;
    color: var(--white);
  }

  .backgrounds,
  .backgrounds .image,
  .backgrounds .color {
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    height: 100%;
    width: 100%;
    z-index: -1;
  }

  .backgrounds .color {
    background: linear-gradient(
      90deg,
      var(--darkblue) 35%,
      var(--lightblue) 100%
    );
    opacity: 85%;
  }

  .backgrounds .image {
    background: url("/assets/img/background.jpg");
    background-size: cover;
    background-position: center;
  }

  .company {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-gap: 2rem;
  }

  .company img {
    height: 100%;
  }

  .product {
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-gap: 2rem;
    align-items: center;
  }

  .picture {
    width: 100%;
    filter: drop-shadow(0 0 0.5rem var(--white));
  }

  .shortDescription {
    font-size: 0.75rem;
  }

  .date {
    position: absolute;
    bottom: 0.75rem;
    right: 0.75rem;
    opacity: 0.25;
    font-size: 80%;
    font-style: italic;
  }
</style>

<header>
  <div class="backgrounds">
    <div class="image" />
    <div class="color" />
  </div>
  <!-- <div class="row company">
    <img
      class="picture"
      src="./assets/img/logoABMTECNAwhite.png"
      alt={data.title} />
  </div> -->
  <div class="row product">
    <img
      class="picture"
      src="./assets/img/{data.productPicture}"
      alt={data.title} />
    <div class="intro">
      <Breadcrumb {data} />

      <h1 class="title">{data.title}</h1>
      <em class="shortDescription">{data.shortDescription}</em>
      <div class="date">{new Date().toLocaleDateString()}</div>
    </div>
  </div>
</header>
