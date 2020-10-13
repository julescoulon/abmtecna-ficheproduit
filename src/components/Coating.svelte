<script>
  export let data;
  import Icon from "./Icon.svelte";
</script>

<style>
  .coatingList {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 0.5rem;
  }

  .coating span {
    margin-left: 0.5rem;
  }
</style>

<div class="coatings">
  <h3>Nos revêtements</h3>
  <div>{data.coatingDesc}</div>
  <div class="coatingList">
    {#each data.coatingList as coating}
      <div class="coating">
        <Icon icon={coating[0]} />
        <span>{coating[1]}</span>
      </div>
    {/each}
  </div>
</div>
