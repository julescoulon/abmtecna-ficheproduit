<script>
  import Icon from "../Icon.svelte";
  import PageNumber from "./PageNumber.svelte";

  let coordonees = [
    ["", "<b>ABM-TECNA</b>"],
    [
      "map-marker-alt",
      "PAE Martinrou, Rue des Sources 5, B-6220 FLEURUS, Belgique <br/>",
    ],
    ["phone-alt", "+32 71 85 85 00"],
    ["phone-alt", "+32 71 85 82 80"],
    ["envelope", "commercial@abm-tecna.be"],
    ["link", "abm-tecna.be"],
  ];
  export let countPage;
</script>

<style>
  footer {
    position: absolute;
    left: 4rem;
    right: 4rem;
    bottom: 2rem;
    font-size: 0.75rem;
    color: var(--darkblue);
  }

  ul {
    list-style: none;
    margin: 0;
  }

  li {
    margin-right: 0.5rem;
    display: inline-block;
  }

  .line {
    height: 2px;
    background: linear-gradient(
      90deg,
      var(--darkblue) 35%,
      var(--lightblue) 100%
    );
    margin-bottom: 0.5rem;
  }

  .sideBorders:before,
  .sideBorders:after {
    content: "";
    display: block;
    position: absolute;
    bottom: 0;
    height: calc(297mm / 4);
    background: var(--darkblue);
    width: 0.5rem;
  }

  .sideBorders:before {
    left: 0;
  }

  .sideBorders:after {
    right: 0;
  }
</style>

<footer>
  <div class="line" />
  <ul>
    {#each coordonees as coordonee, index}
      <li>
        {#if coordonee[0]}
          <Icon icon={coordonee[0]} />
        {/if}
        <span>
          {@html coordonee[1]}
        </span>
      </li>
      {#if index == 1}<br />{/if}
    {/each}
  </ul>
  <PageNumber {countPage} />
</footer>
<div class="sideBorders" />
