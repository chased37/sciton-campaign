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
    <div class="header__hamburger">
      <div class="hamburger-lines">
        <span class="line line1" />
        <span class="line line2" />
        <span class="line line3" />
      </div>
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
  .header__link--2 {
    height: 60%;
    border-right: solid 1px rgba(0, 0, 0, 0.25);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .nav-container .hamburger-lines {
  display: block;
  height: 26px;
  width: 32px;
  position: absolute;
  top: 17px;
  left: 20px;
  z-index: 2;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.nav-container .hamburger-lines .line {
  display: block;
  height: 4px;
  width: 100%;
  border-radius: 10px;
  background: #0e2431;
}

.nav-container .hamburger-lines .line1 {
  transform-origin: 0% 0%;
  transition: transform 0.4s ease-in-out;
}

.nav-container .hamburger-lines .line2 {
  transition: transform 0.2s ease-in-out;
}

.nav-container .hamburger-lines .line3 {
  transform-origin: 0% 100%;
  transition: transform 0.4s ease-in-out;
}

.header__ .menu-items {
  padding-top: 120px;
  box-shadow: inset 0 0 2000px rgba(255, 255, 255, .5);
  height: 100vh;
  width: 100%;
  transform: translate(-150%);
  display: flex;
  flex-direction: column;
  margin-left: -40px;
  padding-left: 50px;
  transition: transform 0.5s ease-in-out;
  text-align: center;
}

.navbar .menu-items li {
  margin-bottom: 1.2rem;
  font-size: 1.5rem;
  font-weight: 500;
}

.logo {
  position: absolute;
  top: 5px;
  right: 15px;
  font-size: 1.2rem;
  color: #0e2431;
}

.nav-container input[type="checkbox"]:checked ~ .menu-items {
  transform: translateX(0);
}

.nav-container input[type="checkbox"]:checked ~ .hamburger-lines .line1 {
  transform: rotate(45deg);
}

.nav-container input[type="checkbox"]:checked ~ .hamburger-lines .line2 {
  transform: scaleY(0);
}

.nav-container input[type="checkbox"]:checked ~ .hamburger-lines .line3 {
  transform: rotate(-45deg);
}

.nav-container input[type="checkbox"]:checked ~ .logo{
  display: none;
}


</style>
