<script>
  import Breadcrumb from "./Breadcrumb.svelte";
  export let data;
</script>

<style>
  header {
    padding: 0 4rem;
    position: relative;
    z-index: 10;
    color: var(--white);
    min-height: 11rem;

    display: flex;
    align-items: center;
  }

  .backgrounds,
  .backgrounds .image,
  .backgrounds .color {
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    height: 100%;
    width: 100%;
    z-index: -1;
  }

  /* .backgrounds .color {
    background: linear-gradient(
      90deg,
      var(--lightblue) 0%,
      var(--darkblue) 75%
    );
  } */

  .backgrounds .image {
    background-image: radial-gradient(
        circle at 67% 83%,
        hsla(317, 0%, 96%, 0.05) 0%,
        hsla(317, 0%, 96%, 0.05) 1%,
        transparent 1%,
        transparent 5%,
        transparent 5%,
        transparent 100%
      ),
      radial-gradient(
        circle at 24% 80%,
        hsla(317, 0%, 96%, 0.05) 0%,
        hsla(317, 0%, 96%, 0.05) 27%,
        transparent 27%,
        transparent 63%,
        transparent 63%,
        transparent 100%
      ),
      radial-gradient(
        circle at 23% 5%,
        hsla(317, 0%, 96%, 0.05) 0%,
        hsla(317, 0%, 96%, 0.05) 26%,
        transparent 26%,
        transparent 82%,
        transparent 82%,
        transparent 100%
      ),
      radial-gradient(
        circle at 21% 11%,
        hsla(317, 0%, 96%, 0.05) 0%,
        hsla(317, 0%, 96%, 0.05) 35%,
        transparent 35%,
        transparent 45%,
        transparent 45%,
        transparent 100%
      ),
      radial-gradient(
        circle at 10% 11%,
        hsla(317, 0%, 96%, 0.05) 0%,
        hsla(317, 0%, 96%, 0.05) 21%,
        transparent 21%,
        transparent 81%,
        transparent 81%,
        transparent 100%
      ),
      radial-gradient(
        circle at 19% 61%,
        hsla(317, 0%, 96%, 0.05) 0%,
        hsla(317, 0%, 96%, 0.05) 20%,
        transparent 20%,
        transparent 61%,
        transparent 61%,
        transparent 100%
      ),
      radial-gradient(
        circle at 13% 77%,
        hsla(317, 0%, 96%, 0.05) 0%,
        hsla(317, 0%, 96%, 0.05) 63%,
        transparent 63%,
        transparent 72%,
        transparent 72%,
        transparent 100%
      ),
      radial-gradient(
        circle at 30% 93%,
        hsla(317, 0%, 96%, 0.05) 0%,
        hsla(317, 0%, 96%, 0.05) 33%,
        transparent 33%,
        transparent 82%,
        transparent 82%,
        transparent 100%
      ),
      linear-gradient(90deg, rgb(2, 125, 194), rgb(17, 23, 94));
  }

  .product {
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-gap: 2rem;
    align-items: center;
  }

  .picture_wrapper {
    position: relative;
  }

  .productPicture {
    width: 100%;
    /* background: radial-gradient(
      rgba(100%, 100%, 100%, 0.65) 0%,
      transparent 65%
    ); */
    /* filter: drop-shadow(0 0 0.5rem var(--white)); */
  }

  .providerPicture {
    width: 20%;
    position: absolute;
    left: 0;
    bottom: 0;

    /* filter: drop-shadow(0rem 0rem 0rem var(--white)); */
  }

  .shortDescription {
    font-size: 0.75rem;
  }

  .date {
    position: absolute;
    bottom: 0.75rem;
    right: 0.75rem;
    opacity: 0.25;
    font-size: 80%;
    font-style: italic;
  }

  .logo {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    transform: translateY(50%);
  }

  .logo div {
    position: relative;
    display: flex;
    justify-content: center;
  }

  .logo img {
    position: absolute;
    border: solid 1px white;
    margin-top: 0.25rem;
    padding: 0.25rem;
    /* border-radius: 50%; */
    width: 12rem;
    /* box-shadow: 0 0.2rem 4px rgba(0, 0, 0, 0.25); */
  }

  .logo svg {
  }
</style>

<header>
  <div class="backgrounds">
    <div class="color" />

    <div class="image" />
  </div>
  <div class="logo">
    <div>
      <img src="./assets/img/logoABMTECNA.png" alt="Logo ABM TECNA" />
      <svg width="300" height="50">
        <path d="M 0 25 L 50 0 L 250 0 L 300 25 L 0 25 " fill="white" />
      </svg>
    </div>
  </div>

  <div class="row product">
    <div class="picture_wrapper">
      <img
        class="productPicture"
        src="./assets/img/{data.productPicture}"
        alt={data.title} />
      <!-- <img
        class="providerPicture"
        src="./assets/img/{data.providerPicture}"
        alt={data.provider} /> -->
    </div>
    <div class="intro">
      <Breadcrumb {data} />

      <h1 class="title">{data.title}</h1>
      <em class="shortDescription">{data.shortDescription}</em>
      <div class="date">{new Date().toLocaleDateString()}</div>
    </div>
  </div>
</header>
