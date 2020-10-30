<script>
    import Icon from "./Icon.svelte";
    import Bande from "./illustrations/Bande.svelte";
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
        flex-grow: 1;
        border: solid 1px red;
        display: flex;
        align-items: center;
        padding: 2rem;
        font-size: 1rem;
        line-height: 1.5;
    }

    .column:last-child {
        width: 35%;
    }

    ul {
        list-style-type: none;
    }

    li {
        margin: 0;
    }

    li > span {
        margin-left: 0.25rem;
    }

    .contact {
        display: grid;
    }
</style>

<div class="background">
    <div class="center coluns">
        <div class="columns">
            <div class="column" />
            <div class="column">
                <div class="contact">
                    <h1>Contact</h1>
                    <div>
                        <h2>Fleurus</h2>
                        <div />
                        <ul>
                            <li>
                                <Icon icon={'map-marker-alt'} />
                                <span>Rue des Sources, 5 | B-6220 Fleurus</span>
                            </li>
                            <li>
                                <Icon icon={'phone-alt'} />
                                <span>+32 71 85 85 00</span>
                            </li>
                            <li>
                                <Icon icon={'envelope'} />
                                <span>commercial@abm-tecna.be</span>
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
