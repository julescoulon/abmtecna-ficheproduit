<script>
  export let coating;
  import Icon from "./Icon.svelte";
</script>

<style>
  .coating {
    display: grid;
    align-items: center;
    grid-gap: 0.5rem;
    grid-template-columns: 40px 1fr;
    margin-bottom: 0.5rem;
  }
</style>

<span class="coating">
  <Icon icon={coating[0]} />
  <span>{coating[1]}</span>
</span>
