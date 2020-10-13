<script>
    import Icon from "./Icon.svelte";

    export let data;
    import { onMount } from "svelte";

    onMount(() => {
        let values = document.querySelectorAll("#arrayToFuse th");
        for (let i = 1; i < values.length + 1; i++) {
            if (values[i]) {
                if (values[i].innerHTML == values[i - 1].innerHTML) {
                    let column = Number(values[i - 1].getAttribute("colspan"));
                    values[i - 1].parentNode.removeChild(values[i - 1]);
                    values[i].setAttribute("colspan", column + 1);
                }
            }
        }
    });
</script>

<style>
    table {
        font-size: 80%;
        width: 100%;
        border-collapse: collapse;
    }

    td,
    th {
        border: solid 1px var(--lightblue);
        padding: 0.1rem 0;
    }

    td {
        text-align: center;
    }

    th:empty {
        border: none;
    }

    thead tr:last-child {
        font-size: 80%;
    }

    tbody tr:nth-child(2n) {
        background-color: var(--verylightblue);
    }
</style>

<div class="stock">
    <h3>Notre stock disponible</h3>
    <table>
        <thead>
            <tr id="arrayToFuse">
                {#each data.stock[0].head[0] as head}
                    <th colspan="1">{head}</th>
                {/each}
            </tr>
            <tr>
                {#each data.stock[0].head[1] as head}
                    <th>{head}</th>
                {/each}
            </tr>
        </thead>
        <tbody>
            {#each data.stock[0].body as body}
                <tr>
                    {#each body as bod}
                        {#if bod == 'X'}
                            <td>
                                <Icon icon={'check'} />
                            </td>
                        {:else}
                            <td>{bod}</td>
                        {/if}
                    {/each}
                </tr>
            {/each}
        </tbody>
    </table>
</div>
