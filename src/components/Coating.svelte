<script>
  export let data;
  import Icon from "./Icon.svelte";
</script>

<style>
  .coatings {
    margin: 0.5rem 0;
  }
  .coating {
    margin-left: 1rem;
  }
  .coating span {
    margin-left: 0.25rem;
  }
</style>

<div class="coatings">
  <strong>Nos revêtements :</strong>
  {#each data.coatingList as coating}
    <span class="coating">
      <Icon icon={coating[0]} />
      <span>{coating[1]}</span>
    </span>
  {/each}
</div>
