<script>
  export let data;
  import Icon from "../Icon.svelte";
</script>

<style>
  .coatings div {
    margin-top: 0.5rem;
    display: flex;
    justify-content: space-evenly;
  }

  .icon-wrapper {
    color: var(--orange);
    border: solid 1.5px var(--orange);
    display: inline-flex;
    justify-content: center;
    align-items: center;
    height: 2.25rem;
    width: 2.25rem;
    border-radius: 50%;
    margin-right: 0.25rem;
  }
</style>

<div class="coatings">
  <h3>Nos revêtements</h3>
  <div>
    {#each data.coatingList as coating}
      <span class="coating">
        <span class="icon-wrapper">
          <Icon icon={coating[0]} />
        </span>
        <span>{coating[1]}</span>
      </span>
    {/each}
  </div>
</div>
