<script>
    import Icon from "../Icon.svelte";
    import Bande from "../illustrations/Bande.svelte";
</script>

<style>
    .background {
        background-image: radial-gradient(
                circle at 100% 40%,
                rgba(23, 23, 23, 0.05) 0%,
                rgba(23, 23, 23, 0.05) 50%,
                rgba(109, 109, 109, 0.05) 50%,
                rgba(109, 109, 109, 0.05) 100%
            ),
            radial-gradient(
                circle at 88% 90%,
                rgba(92, 92, 92, 0.05) 0%,
                rgba(92, 92, 92, 0.05) 50%,
                rgba(199, 199, 199, 0.05) 50%,
                rgba(199, 199, 199, 0.05) 100%
            ),
            radial-gradient(
                circle at 100% 25%,
                rgba(230, 230, 230, 0.05) 0%,
                rgba(230, 230, 230, 0.05) 50%,
                rgba(25, 25, 25, 0.05) 50%,
                rgba(25, 25, 25, 0.05) 100%
            ),
            linear-gradient(90deg, var(--lightblue), var(--darkblue));
        height: 100%;
        display: flex;
        flex-direction: column;
        position: relative;
        overflow: hidden;
    }

    .center {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        flex-grow: 1;
        color: var(--white);
        position: relative;
    }

    .center > * {
        z-index: 100;
    }

    .center img {
        position: absolute;
        left: 0;
        height: 30%;
        transform: translateX(-50%);
        opacity: 0.1;
    }

    .logo {
        width: 100%;
        text-align: center;
        background: white;
        display: flex;
        height: 15%;
        justify-content: center;
        align-items: center;
    }

    .columns {
        width: 100%;
        height: 100%;
        display: flex;
    }

    .column {
        display: flex;
        flex-direction: column;
        justify-content: center;
        font-size: 1rem;
        font-size: 0.8rem;
    }

    .column:first-child {
        width: 25%;
    }

    .column:last-child {
        width: 75%;
        padding: 2rem;
    }

    .column > div {
        margin-bottom: 1rem;
    }

    ul {
        list-style-type: none;
    }

    li {
        margin: 0;
    }

    li > div {
        margin-left: 0.5rem;
    }

    h1,
    h2 {
        margin: 0;
        line-height: 1;
    }

    h1 {
        font-size: 1.5rem;
        margin-bottom: 0.75rem;
    }

    h2 {
        font-size: 1rem;
        margin-bottom: 0.5rem;
        text-transform: uppercase;
    }

    .contact {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        grid-gap: 1rem;
        border-left: solid 0.25rem var(--orange);
        padding-left: 1rem;
    }

    .contact li {
        display: flex;
        align-items: top;
        margin-bottom: 0.25rem;
    }
    .contact li::before {
        display: none;
    }

    ul li::before {
        content: "\f054";
        display: inline-block;
        font-family: "Font Awesome 5 Pro";
        font-weight: 900;

        color: var(--orange);
        margin-right: 0.5rem;
        transform: scale(0.65);
    }

    .service li {
        display: grid;
        grid-template-columns: min-content 1fr 1fr;
        justify-content: flex-start;
    }
</style>

<div class="background">
    <div class="center coluns">
        <div class="columns">
            <div class="column" />
            <div class="column">
                <div>
                    <h1>Intéressé par l'un de nos produits ?</h1>
                    <div>
                        Lorem ipsum dolor sit, amet consectetur adipisicing
                        elit. Consequatur voluptate quidem quis cumque ea
                        repudiandae maxime possimus officiis dicta totam
                        voluptates ex quisquam, adipisci, tempore qui iusto
                        aliquam accusamus minus.
                    </div>
                </div>
                <div class="service">
                    <h1>Service 24h/24</h1>
                    <ul>
                        <li>
                            <div>Demande d’intervention, de prestation :</div>
                            <div>+32 498 17 29 24</div>
                        </li>
                        <li>
                            <div>Commande de pièces détachées :</div>
                            <div>+32 496 33 02 11</div>
                        </li>
                    </ul>
                </div>
                <h1>Contact</h1>
                <div class="contact">
                    <div>
                        <h2>Fleurus</h2>
                        <ul>
                            <li>
                                <Icon icon={'map-marker-alt'} />
                                <div>
                                    Rue des Sources, 5
                                    <br />
                                    B-6220 Fleurus
                                </div>
                            </li>
                            <li>
                                <Icon icon={'phone-alt'} />
                                <div>+32 71 85 85 00</div>
                            </li>
                            <li>
                                <Icon icon={'envelope'} />
                                <div>commercial@abm-tecna.be</div>
                            </li>
                        </ul>
                    </div>
                    <div>
                        <h2>Gent</h2>
                        <ul>
                            <li>
                                <Icon icon={'map-marker-alt'} />
                                <div>Zwedenstraat 9 <br /> B-9440 Evergem</div>
                            </li>
                            <li>
                                <Icon icon={'phone-alt'} />
                                <div>+32 92 45 24 62</div>
                            </li>
                            <li>
                                <Icon icon={'envelope'} />
                                <div>sales@abm-tecna.be</div>
                            </li>
                        </ul>
                    </div>
                    <div>
                        <h2>Tournai</h2>
                        <ul>
                            <li>
                                <Icon icon={'map-marker-alt'} />
                                <div>
                                    Rue du bois, 16B
                                    <br />
                                    B-7530 Tournai
                                </div>
                            </li>
                            <li>
                                <Icon icon={'phone-alt'} />
                                <div>+32 69 57 71 07</div>
                            </li>
                            <li>
                                <Icon icon={'envelope'} />
                                <div>commercial@abm-tecna.be</div>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>

        <img src="./assets/img/logoABMTECNAwhitebg.png" alt="" />
    </div>
    <div class="logo" />
</div>
