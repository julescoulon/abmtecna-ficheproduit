<script>
  import Coating from "./Coating.svelte";

const file = "bandePrimaPLY";
let path = `../data/${file}.json`;
  import * as data from "../data/"+file+".json";
</script>

<style>
  .page {
    border: solid 2px red;
    margin: 0 auto;
    width: 210mm;
    height: 297mm;
    font-family: sans-serif;
    white-space: pre-line;
    padding: 2rem;
  }

  li {
    margin-left: 2rem;
  }

  .page > * {
    margin-bottom: 1rem;
  }
  table {
    font-size: 75%;
  }

  .coatingList {
    display: flex;
    justify-content: space-around;
    margin: 0.5rem;
  }
</style>

<div class="page">
  <h1 class="title">{data.title}</h1>
  <div class="description">{data.description}</div>
  <ul class="area">
    <h2>Domaines d'applications</h2>
    {#each data.areas as area}
      <li>{area}</li>
    {/each}
  </ul>
  <div class="info">
    <h2>Informations</h2>
    {#each data.infos as info}
      {info}
      <br />
    {/each}
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
