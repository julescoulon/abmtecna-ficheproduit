<script>
  import Icon from "./Icon.svelte";
  export let data;
</script>

<style>
  header {
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-gap: 2rem;
    padding: 2rem 4rem;

    align-items: center;
    color: var(--white);
    /* padding-bottom: 3rem; */
    position: relative;
    z-index: 10;
  }
  /* 
    .backgrounds {
        clip-path: polygon(0 0, 100% 0%, 100% 90%, 50% 120%, 0 90%);
    } */

  .backgrounds,
  .backgrounds .image,
  .backgrounds .color {
    position: absolute;

    height: 100%;
    width: 100%;
  }

  .backgrounds .color {
    background: var(--darkblue);
    opacity: 85%;
  }

  .backgrounds .image {
    background: url("/assets/img/background.jpg");
    background-size: cover;
    background-position: center;
  }

  .intro {
    z-index: 1;
  }

  .picture {
    width: 100%;
    filter: drop-shadow(0 0 0.5rem var(--white));
  }

  .breadcrumb {
    display: flex;
    align-items: center;
    font-size: 0.75rem;
  }
  .breadcrumb span {
    margin: 0 0.25rem;
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
</style>

<header>
  <div class="backgrounds">
    <div class="image" />
    <div class="color" />
  </div>
  <img
    class="picture"
    src="./assets/img/{data.productPicture}"
    alt={data.title} />
  <div class="intro">
    <div class="breadcrumb">
      {#each data.breadcrumb as breadcrum}
        <Icon icon={'angle-double-right'} />
        <span>{breadcrum}</span>
      {/each}
    </div>
    <h1 class="title">{data.title}</h1>
    <em class="shortDescription">{data.shortDescription}</em>
    <div class="date">{new Date().toLocaleDateString()}</div>
  </div>
</header>
