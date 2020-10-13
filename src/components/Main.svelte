<script>
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
        flex-grow: 1;
    }

    ul {
        list-style-type: square;
        margin-left: 1rem;
        color: var(--orange);
    }

    li span {
        color: var(--black);
    }

    .column-layout {
        display: grid;
        grid-gap: 2rem;
        align-items: stretch;
    }

    .column-layout.two-columns {
        grid-template-columns: repeat(2, 1fr);
    }

    .column-layout .v-center {
        align-self: center;
    }

    .column-layout .stretch {
        display: flex;
        flex-direction: column;
    }

    .row {
        margin-bottom: 1rem;
    }

    .imgCover {
        margin-top: 1rem;
        height: 100%;
        background-size: cover;
        background-position: center;
    }
</style>

<main>
    <div class="row">
        <div class="description">
            {#each data.description as desc}
                <p>{desc}</p>
            {/each}
        </div>
    </div>
    <div class="row">
        <div class="column-layout two-columns">
            <div class="composition">
                <h3>Composition</h3>
                {#each data.compositions as composition}
                    <p>{composition}</p>
                {/each}
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
                    style="background-image:url(https://abm-tecna.com/wp-content/uploads/2020/05/bande.jpg)" />
            </div>
        </div>
    </div>
    <div class="row">
        <h2>Notre sélection</h2>
        <div class="column-layout two-columns">
            <div class="info">
                <h3>Productions</h3>
                <ul>
                    {#each data.infos as info}
                        <li><span>{info}</span></li>
                    {/each}
                </ul>
            </div>
            <Coating {data} />
        </div>
    </div>
    <div class="row">
        <Stock {data} />
    </div>
</main>
