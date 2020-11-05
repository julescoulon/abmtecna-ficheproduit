<script>
    import Bande from "../illustrations/Bande.svelte";
</script>

<style>
    .background {
        background-image: radial-gradient(
                circle at 0% 40%,
                rgba(23, 23, 23, 0.05) 0%,
                rgba(23, 23, 23, 0.05) 50%,
                rgba(109, 109, 109, 0.05) 50%,
                rgba(109, 109, 109, 0.05) 100%
            ),
            radial-gradient(
                circle at 12% 90%,
                rgba(92, 92, 92, 0.05) 0%,
                rgba(92, 92, 92, 0.05) 50%,
                rgba(199, 199, 199, 0.05) 50%,
                rgba(199, 199, 199, 0.05) 100%
            ),
            radial-gradient(
                circle at 0% 25%,
                rgba(230, 230, 230, 0.05) 0%,
                rgba(230, 230, 230, 0.05) 50%,
                rgba(25, 25, 25, 0.05) 50%,
                rgba(25, 25, 25, 0.05) 100%
            ),
            linear-gradient(90deg, var(--darkblue), var(--lightblue));
        height: 100%;
        display: flex;
        flex-direction: column;
        position: relative;
        overflow: hidden;
    }

    .center {
        text-align: center;
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

    h1 {
        font-size: 350%;
        position: relative;
    }

    h1:after {
        content: "";
        display: block;
        width: 100%;
        background: var(--orange);
        height: 2px;
        margin-top: 0.5rem;
    }

    h2 {
        text-transform: uppercase;

        font-size: 200%;
    }

    .center img {
        position: absolute;
        right: 0;
        height: 30%;
        transform: translateX(50%);
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

    .logo img {
        height: calc(100% / 2.5);
    }

    .illustration {
        margin-bottom: 2rem;
        height: 200px;
    }

    .date {
        position: absolute;
        right: 0;
        bottom: 0;
        padding: 1rem 1.5rem;
        opacity: 0.5;
        font-style: italic;
    }
</style>

<div class="background">
    <div class="center">
        <div class="illustration">
            <Bande />
        </div>
        <h1>Bandes transporteuses<br /></h1>
        <h2>Textiles et à câbles d'acier</h2>
        <img src="./assets/img/logoABMTECNAwhitebg.png" alt="" />
        <div class="date">Publié le {new Date().toLocaleDateString()}</div>
    </div>
    <div class="logo"><img src="./assets/img/logoABMTECNA.png" alt="" /></div>
</div>
