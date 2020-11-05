<script>
    import Icon from "./../Icon.svelte";
    export let data;
</script>

<style>
    .breadcrumb {
        display: flex;
        align-items: center;
        font-size: 0.75rem;
    }
    .breadcrumb span {
        margin: 0 0.25rem;
    }
</style>

<div class="breadcrumb">
    {#each data.breadcrumb as breadcrum}
        <Icon icon={'angle-double-right'} />
        <span>{breadcrum}</span>
    {/each}
</div>
