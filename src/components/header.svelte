<script>
  let src = "/images/logo-sciton.png";
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
      <a href="/">Find My Provider</a>
    </div>
    <div class="header__hamburger" />
  </div>
</main>

<svelte:window bind:scrollY={y}/>

<style>
  main {
    width: 100%;
    height: 87px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: fixed;
    background-color: var(--tertiary);
    top: 0;
    z-index: 1;
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
  .header__link a {
    text-decoration: none;
    color: black;
  }
  .show {
    transform: translateY(0%);
  }
  .hide {
    transform: translateY(-100%);
  }
</style>
