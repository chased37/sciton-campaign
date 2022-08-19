<script>
  import * as animateScroll from "svelte-scrollto";
import { cubicIn, cubicInOut } from "svelte/easing";

  let src = "/images/logo-sciton.avif";
  export let duration = "300ms";
  export let offset = 0;
  export let tolerance = 0;

  let headerClass = "show";
  let y = 0;
  let lastY = 0;

  function deriveClass(y, dy) {
    if (y < offset) {
      return "show";
    }

    if (Math.abs(dy) <= tolerance) {
      return headerClass;
    }

    if (dy < 0) {
      return "hide";
    }

    return "show";
  }

  function updateClass(y) {
    const dy = lastY - y;
    lastY = y;
    return deriveClass(y, dy);
  }

  function setTransitionDuration(node) {
    node.style.transitionDuration = duration;
  }

  $: headerClass = updateClass(y);
</script>

<main use:setTransitionDuration class={headerClass}>
  <div class="header__logo">
    <img class="header__image" {src} alt="Sciton" />
  </div>

  <div class="header__nav">
    <div class="header__link header__link--1">
      <!-- <a href="/">BBL HERO Treatments</a> -->
    </div>
    <div class="header__link header__link--2">
      <button
        on:click={() =>
          animateScroll.scrollTo({
            element: "#map",
            duration: 700,
            easing: cubicIn,
          })}>Find My Provider</button
      >
    </div>
    <div class="header__hamburger">
      <a
        target="_blank"
        href="https://www.google.com/url?q=https://sciton.com/bbl-hero-by-sciton/&source=gmail-imap&ust=1661469484000000&usg=AOvVaw0-M7ILVfLaFgfVbM7C1CmY"
        >Providers Learn More</a
      >
    </div>
  </div>
</main>

<svelte:window bind:scrollY={y} />

<style>
  main {
    width: 100%;
    height: 87px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: fixed;
    background-color: var(--tertiary);
    top: 0;
    z-index: 10;
    transition: transform 100ms linear;
  }
  .header__nav {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    align-items: center;
    justify-content: flex-end;
    font-family: var(--adrianna);
  }
  .header__logo {
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }
  .header__image {
    width: 200px;
    height: auto;
    padding-left: 2rem;
  }
  .header__link button {
    text-decoration: none;
    color: black;
    background-color: var(--offwhite);
    border: none;
    font-size: 15px;
    font-family: var(--adrianna);
  }
  .header__link button:hover {
    cursor: pointer;
  }
  .header__hamburger a {
    text-decoration: none;
    color: black;
    background-color: var(--offwhite);
    border: none;
    font-size: 15px;
    font-family: var(--adrianna);
  }
  .show {
    transform: translateY(0%);
  }
  .hide {
    transform: translateY(-100%);
  }
  .header__link--2 {
    height: 60%;
    border-right: solid 1px rgba(0, 0, 0, 0.25);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .header__hamburger {
    height: 60%;
    border-right: solid 1px rgba(0, 0, 0, 0.25);
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .logo {
    position: absolute;
    top: 5px;
    right: 15px;
    font-size: 1.2rem;
    color: #0e2431;
  }
</style>
