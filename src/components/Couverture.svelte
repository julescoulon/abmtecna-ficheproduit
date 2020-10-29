<style>
    :root {
        --bigbande: calc(75% / 4);
        --smallbande: calc(25% / 4);
    }
    .background {
        background: var(--darkblue);
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
        flex-grow: 1;
        color: var(--white);
        position: relative;
    }

    .center > * {
        z-index: 100;
    }

    .center::before,
    .center::after {
        content: "";
        display: block;
        position: absolute;
        height: 50%;
        width: 100%;
    }

    .center::before {
        top: 0;
        background: var(--darkblue);
        height: 65%;
    }
    .center::after {
        height: 35%;
        bottom: 0;
        background: repeating-linear-gradient(
            var(--lightblue) 0%,
            var(--lightblue) var(--smallbande),
            var(--darkblue) var(--smallbande),
            var(--darkblue) var(--bigbande)
        );
    }

    h1 {
        font-size: 350%;
    }

    h2 {
        text-transform: uppercase;
        font-size: 200%;
    }

    .center img {
        position: absolute;
        right: 0;
        height: 50%;
        transform: translateX(50%);
        opacity: 0.1;
    }

    .logo {
        width: 100%;
        text-align: center;
        padding: 2.5rem 0;
        background: white;
        display: flex;
        justify-content: center;
    }

    /* .logo:before {
        content: "";
        display: block;
        height: calc(210mm / 1.414);
        width: calc(210mm / 1.414);
        background: red;
        position: absolute;
        bottom: 0;

        transform: translateY(50%) rotate(45deg);
    } */

    .logo img {
        width: calc(100% / 3);
    }
</style>

<div class="background">
    <div class="center">
        <h1>Bandes transporteuses<br /></h1>
        <h2>Textiles et à câbles d'acier</h2>
        <img src="./assets/img/logoABMTECNAwhitebg.png" alt="" />
    </div>
    <div class="logo"><img src="./assets/img/logoABMTECNA.png" alt="" /></div>
</div>
