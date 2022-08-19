<script>
  import { fly, fade } from "svelte/transition";
  import { onMount } from "svelte";
  let src = "/images/bbl-hero.png";
  let inIcon = "/images/linkedin.png";
  let tiktokIcon = "/images/tiktok.png";
  let instaIcon = "/images/insta.png";

  let size = 30;
  let animate = false;
  onMount(() => {
    animate = true;
  });
</script>

<main>
  {#if animate}
    <div class="hero__block">
      <h1 in:fly={{ duration: 400, y: 100, delay: 300 }} class="hero__text">
        Skin That Looks as Young as You Feel
      </h1>
      <img
        in:fade={{ delay: 600, duration: 300 }}
        class="hero__image"
        {src}
        alt="BBL Hero"
      />
    </div>
    <ul in:fade={{ delay: 600, duration: 500 }} class="hero__socials">
      <li class="hero__socials-item">
        <a href="/"
          ><img
            height={size - 5}
            width={size - 5}
            style="margin:auto"
            src={inIcon}
            alt="LinkedIn Link"
          /></a
        >
      </li>
      <li class="hero__socials-item">
        <a href="/"
          ><img
            height={size}
            width={size}
            src={instaIcon}
            alt="Instagram Link"
          /></a
        >
      </li>
      <li class="hero__socials-item">
        <a href="/"
          ><img
            height={size}
            width={size}
            src={tiktokIcon}
            alt="TikTok Link"
          /></a
        >
      </li>
    </ul>
  {/if}
</main>

<style>
  /* your styles go here */
  main {
    width: 100%;
    height: calc(90vh - 30px);
    min-height: 800px;
    background-image: url("/images/CLEO.jpg");
    background-size: cover;
    box-shadow: inset 0 0 0 2000px rgba(123, 123, 123, 0.3);
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }

  .hero__block {
    display: grid;
    grid-template-columns: 1fr;
    justify-content: center;
    align-items: center;
    min-height: 200px;
    height: auto;
  }

  .hero__text {
    color: white;
    text-align: center;
    font-size: 72px;
    padding: 1rem;
    width: auto;
    font-weight: var(--regular);
    font-family: var(--ivyMode);
  }
  .hero__image {
    width: 300px;
    height: auto;
    margin: auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .hero__socials {
    background-color: white;
    padding: 1rem 0.5rem;
    border-radius: 15px;
    position: absolute;
    right: 15px;
    bottom: 15px;
  }
  .hero__socials-item {
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
