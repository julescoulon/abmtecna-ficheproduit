<script>
  import Coating from "./Coating.svelte";
  import Icon from "./Icon.svelte";

  import * as data from "../data/bandePrimaPLY.json";
</script>

<style>
  .page {
    background: white;
    margin: 0 auto;
    width: 210mm;
    height: 297mm;
  }

  li {
    margin-left: 2rem;
  }

  .page > * {
    margin-bottom: 1rem;
  }
  table {
    font-size: 0.75rem;
  }

  .coatingList {
    display: flex;
    justify-content: space-around;
    margin: 0.5rem;
  }

  header,
  main {
    padding: 2rem;
  }

  header {
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-gap: 2rem;
    align-items: center;
    color: white;
    padding-bottom: 3rem;
    position: relative;
  }

  .backgrounds {
    clip-path: polygon(0 0, 100% 0%, 100% 80%, 0 100%);
  }

  .backgrounds,
  .backgrounds .image,
  .backgrounds .color {
    position: absolute;

    height: 100%;
    width: 100%;
  }

  .backgrounds .color {
    background: var(--darkblue);
    opacity: 85%;
  }

  .backgrounds .image {
    background: url("/assets/img/background.jpg");
    background-size: cover;
    background-position: center;
  }

  .intro {
    z-index: 1;
  }

  .picture {
    width: 100%;
    filter: drop-shadow(0 0 0.5rem var(--white));
  }

  .breadcrumb {
    display: flex;
    align-items: center;
    font-size: 0.75rem;
  }
  .breadcrumb span {
    margin: 0 0.25rem;
  }

  .title {
    margin-bottom: 0.5rem;
  }
</style>

<div class="page">
  <header>
    <div class="backgrounds">
      <div class="image" />
      <div class="color" />
    </div>
    <img
      class="picture"
      src="./assets/img/{data.productPicture}"
      alt={data.title} />
    <div class="intro">
      <div class="breadcrumb">
        {#each data.breadcrumb as breadcrum}
          <Icon icon={'angle-double-right'} />
          <span>{breadcrum}</span>
        {/each}
      </div>

      <h1 class="title">{data.title}</h1>
    </div>
  </header>
  <div class="description">{data.description}</div>
  <div class="area">
    {#each data.areas as area}<span>{area}</span>{/each}
  </div>
  <div class="info">
    <h2>Informations</h2>
    {#each data.infos as info}{info} <br />{/each}
  </div>
  <div class="composition">
    <h2>Composition</h2>
    {#each data.compositions as composition}{composition}{/each}
  </div>

  <div class="stock">
    <h2>Stock disponible</h2>
    <table>
      <thead>
        <tr>
          {#each data.stock[0].head as head}
            <th>{head}</th>
          {/each}
        </tr>
      </thead>
      <tbody>
        {#each data.stock[0].body as body}
          <tr>
            {#each body as bod}{bod}{/each}
          </tr>
        {/each}
      </tbody>
    </table>
  </div>

  <div class="coatings">
    <h2>Revêtements</h2>
    <div>{data.coatingDesc}</div>
    <div class="coatingList">
      {#each data.coatingList as coating}
        <Coating {coating} />
      {/each}
    </div>
  </div>
</div>
