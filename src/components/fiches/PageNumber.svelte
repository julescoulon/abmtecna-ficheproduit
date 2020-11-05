<script>
    import { onMount } from "svelte";
    export let countPage = "true";
    let pageList;
    let pageTotal;
    let currentPage;
    let currentNumber;
    onMount(() => {
        pageList = document.getElementsByClassName("page");
        pageTotal = pageList.length;
        currentPage = currentPage.parentElement.parentElement;
        for (const key in pageList) {
            if (pageList[key] == currentPage) {
                currentNumber = parseInt(key) + 1;
            }
        }
    });
</script>

<style>
    .pageNumber {
        position: absolute;
        right: 0;
        bottom: 0;
    }
</style>

<div class="pageNumber" bind:this={currentPage}>
    {#if countPage}Page <b>{currentNumber}</b> sur <b>{pageTotal}</b>{/if}
</div>
