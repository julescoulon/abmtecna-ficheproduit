<script>
  import Breadcrumb from "./Breadcrumb.svelte";

  import Coating from "./Coating.svelte";
  import Stock from "./Stock.svelte";
  import Icon from "./Icon.svelte";

  export let data;
</script>

<style>
  #content {
    background: url("/assets/img/logoABMTECNAwhitebg.png");
    background-position: center;
    background-size: auto 75%;
    background-repeat: no-repeat;
  }

  .imgCover {
    margin-top: 1rem;
    height: 100%;
    background-size: cover;
    background-position: center;
  }

  ul {
    list-style-type: none;
    margin-left: 0rem;
    margin-bottom: 0.5rem;
    color: var(--black);
  }

  ul li::before {
    content: "\f054";
    font-family: "Font Awesome 5 Pro";
    font-weight: 900;

    color: var(--orange);
    margin-right: 0.5rem;
    display: inline-block;
    transform: scale(0.65);
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

  h2,
  h3 {
    text-transform: uppercase;
  }
  h2:after {
    content: "";
    display: block;
    background: var(--orange);
    width: 35%;
    height: 2px;
  }
</style>

<div id="content">
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
</div>
