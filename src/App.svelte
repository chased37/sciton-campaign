<script>
  import Header from "./components/header.svelte";
  import Hero from "./components/hero.svelte";
  import Bbl from "./components/bbl.svelte";
  import Video from "./components/video.svelte";
  import Compare from "./components/compare.svelte";
  import Testimonial from "./components/testimonial.svelte";
  import Newsletter from "./components/newsletter.svelte";
  import Divider from "./components/divider.svelte";
  import StoreLocator from "./components/storeLocator.svelte";
  import Footer from "./footer.svelte";

  import { fade } from "svelte/transition";
  import { onMount } from "svelte";

  let y;

  let animate = false;
  onMount(() => {
    animate = true;
  });

  import * as animateScroll from "svelte-scrollto";
</script>

<Header duration="150ms" offset={50} tolerance={5} />
<main>
  <Hero />
  {#if animate}
    {#if y < 50}
      <div in:fade={{ delay: 1000, duration: 300 }} id="bbl-anchor">
        <button
          on:click={() =>
            animateScroll.scrollTo({ element: "#bbl", duration: 700 })}
          >&darr;</button
        >
      </div>
    {/if}
  {/if}

  <Bbl componentId="bbl" />
  <Video />
  <Compare />
  <StoreLocator />
  <Testimonial />
  <Divider />
  <Newsletter />
  <Footer />
</main>

<svelte:window bind:scrollY={y} />

<style>
  main {
    position: relative;
  }
  #bbl-anchor {
    position: fixed;
    width: 100%;
    top: 75%;
    display: flex;
    justify-content: center;
  }
  #bbl-anchor button {
    margin: auto;
    background-color: none;
    outline: none;
    border: none;
    background: none;
    font-size: 35px;
    color: rgba(255, 255, 255, 0.478);
    transition: transform 400ms ease-in-out;
    font-family: var(--ivyMode);
  }
  #bbl-anchor button:hover {
    cursor: pointer;
    transform: translateY(15%);
    transition: transform 400ms ease-in-out;
  }
</style>
