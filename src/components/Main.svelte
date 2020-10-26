<script>
  import Breadcrumb from "./Breadcrumb.svelte";

  import Coating from "./Coating.svelte";
  import Stock from "./Stock.svelte";
  import Icon from "./Icon.svelte";

  export let data;

  let li = document.querySelectorAll("li");
  for (let i = 0; i < li.length; i++) {
    console.log(li);
  }
</script>

<style>
  main {
    padding: 2rem 4rem;
    padding-bottom: 0;
    flex-grow: 1;
    background: url("/assets/img/logoABMTECNAwhitebg.png");
    background-position: center;
    background-size: auto 75%;
    background-repeat: no-repeat;
  }

  .imgCover {
    height: 100%;
    background-size: cover;
    background-position: center;
  }

  ul {
    list-style-type: square;
    margin-left: 1rem;
    color: var(--orange);
  }

  li span {
    color: var(--black);
  }

  table {
    font-style: italic;
  }

  table td:first-child {
    font-weight: bold;
  }

  table td {
    padding-right: 0.5rem;
  }
</style>

<main>
  <div class="row column-layout two-columns">
    <div>
      {#each data.description as desc}
        <p>{desc}</p>
      {/each}
      <h3>Composition</h3>
      <ul>
        {#each data.compositions as composition}
          <li><span>{composition}</span></li>
        {/each}
      </ul>
      {#if data.compositionDesc}
        {#each data.compositionDesc as compositionDesc}
          <p>
            {@html compositionDesc}
          </p>
        {/each}
      {/if}
      <h3>Avantages</h3>
      <ul>
        {#each data.avantages as avantage}
          <li>
            <span>
              {@html avantage}
            </span>
          </li>
        {/each}
      </ul>
    </div>

    <div class="area stretch">
      <h3>Domaines d'applications</h3>
      <ul>
        {#each data.areas as area}
          <li><span>{area}</span></li>
        {/each}
      </ul>
      <div
        class="imgCover"
        style="background-image:url(./assets/img/{data.imageContent})" />
    </div>
  </div>
  <div class="row">
    <h2>Notre sélection</h2>
    <div class="column-layout two-columns ">
      <div class="info">
        <h3>Productions</h3>
        <ul>
          {#each data.infos as info}
            <li>
              <span>
                {@html info}
              </span>
            </li>
          {/each}
        </ul>
      </div>
      <div class="designations">
        <h3>Désignation</h3>
        <table>
          {#each data.designations as designation}
            <tr>
              <td>{designation[0]}</td>
              <td>
                <Icon icon={'arrow-right'} />
              </td>
              <td>
                {@html designation[1]}
              </td>
            </tr>
          {/each}
        </table>
      </div>
    </div>
    <Stock {data} />
  </div>

  <div class="row">
    <Coating {data} />
  </div>
</main>
