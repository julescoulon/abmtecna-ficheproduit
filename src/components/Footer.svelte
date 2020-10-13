<script>
    import Icon from "./Icon.svelte";
</script>

<style>
    footer {
        padding: 2rem 4rem;
        display: grid;
        grid-gap: 2rem;
        grid-template-columns: 1fr 2fr 1fr;
        font-size: 0.75rem;
        align-items: center;
        color: var(--darkblue);
    }

    img {
        width: 100%;
    }

    ul {
        list-style: none;
    }
</style>

<footer>
    <img src="./assets/img/logoABMTECNA.png" alt="Logo ABM TECNA" />
    <ul class="contact">
        <li>
            <Icon icon={'envelope'} />
            commercial@abm-tecna.be
        </li>
        <li>
            <Icon icon={'phone-alt'} />
            +32 71 85 82 80
        </li>
        <li>
            <Icon icon={'map-marker-alt'} />
            PAE Martinrou, Rue des Sources 5, B-6220 Fleurus
        </li>
        <li>
            <Icon icon={'external-link'} />
            abm-tecna.com
        </li>
    </ul>
    <div class="social">
        <Icon icon={'twitter'} style={'Brands'} />
        <Icon icon={'linkedin'} style={'Brands'} />
        <Icon icon={'facebook'} style={'Brands'} />
        <Icon icon={'youtube'} style={'Brands'} />
    </div>
</footer>
