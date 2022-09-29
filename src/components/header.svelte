<script>
  import * as animateScroll from "svelte-scrollto";
  import { cubicIn, cubicInOut } from "svelte/easing";

  let src = "./assets/images/SCITON logo-01.png";
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

  function hamburgerScroll() {
    document.getElementById("hamburger__checkbox").click();
    animateScroll.scrollTo({
      element: "#map",
      duration: 700,
      easing: cubicIn,
    });
  }

  $: headerClass = updateClass(y);
</script>

<main use:setTransitionDuration class={headerClass}>
  <div class="header__logo">
    <img class="header__image" {src} alt="Sciton" />
  </div>

  <div class="header__nav">
    <div class="header__link header__link--2">
      <button
        on:click={() =>
          animateScroll.scrollTo({
            element: "#map",
            duration: 700,
            easing: cubicIn,
          })}>Find a Provider</button
      >
    </div>
    <div class="header__hamburger">
      <a
        target="_blank"
        href="https://www.google.com/url?q=https://sciton.com/bbl-hero-by-sciton/&source=gmail-imap&ust=1661469484000000&usg=AOvVaw0-M7ILVfLaFgfVbM7C1CmY"
        >Visit sciton.com</a
      >
    </div>
    <div class="container nav-container">
      <input
        id="hamburger__checkbox"
        class="checkbox"
        type="checkbox"
        name=""
      />
      <div class="hamburger-lines">
        <span class="line line1" />
        <span class="line line2" />
        <span class="line line3" />
      </div>
      <div class="menu-items">
        <li class="hamburger__link">
          <a on:click={hamburgerScroll}>Find a Provider</a>
        </li>
        <li class="hamburger__link">
          <a
            href="https://www.google.com/url?q=https://sciton.com/bbl-hero-by-sciton/&source=gmail-imap&ust=1661469484000000&usg=AOvVaw0-M7ILVfLaFgfVbM7C1CmY"
            >Visit sciton.com</a
          >
        </li>
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
    z-index: 10;
    transition: transform 100ms linear;
  }
  .header__nav {
    display: grid;
    grid-template-columns: 1fr 1fr;
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
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .header__hamburger,
  .header__link--2 {
    min-width: 230px;
  }

  .container {
    display: none;
    width: 40px;
    height: 40px;
    margin-right: 2rem;
  }
  @media screen and (max-width: 700px) {
    .header__nav {
      grid-template-columns: 1fr;
      display: flex;
      justify-content: flex-end;
      align-items: center;
    }

    .header__hamburger,
    .header__link--2 {
      min-width: 150px;
      border: none;
      display: none;
    }
    .header__image {
      width: 150px;
    }

    .container {
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .navbar {
      width: 100%;
    }

    .nav-container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 40px;
    }

    .navbar .menu-items {
      display: flex;
    }

    .navbar .nav-container li {
      list-style: none;
    }

    .navbar .nav-container a {
      text-decoration: none;
      color: #0e2431;
      font-weight: 500;
      font-size: 1.2rem;
      padding: 0.7rem;
    }

    .navbar .nav-container a:hover {
      font-weight: bolder;
    }

    .nav-container {
      display: block;
      position: relative;
      height: 40px;
    }

    .nav-container .checkbox {
      position: absolute;
      display: block;
      height: 40px;
      width: 40px;
      z-index: 5;
      opacity: 0;
      cursor: pointer;
    }

    .nav-container .hamburger-lines {
      display: block;
      height: 30px;
      width: 40px;
      margin: 5px auto 0 auto;
      z-index: 5;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .nav-container .hamburger-lines .line {
      display: block;
      height: 2px;
      width: 90%;
      border-radius: 10px;
      background: var(--primary);
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

    .menu-items {
      height: 100vh;
      width: calc(100vw + 20px);
      display: flex;
      margin-left: 200%;
      margin-top: 25px;
      flex-direction: column;
      transition: transform 0.5s ease-in-out;
      text-align: center;
      list-style: none;
      background-color: white;
      top: 0;
    }

    .navbar .menu-items li {
      margin-bottom: 1.2rem;
      font-size: 1.5rem;
      font-weight: 500;
    }

    .nav-container input[type="checkbox"]:checked ~ .menu-items {
      transform: translateX(-100%);
    }

    .nav-container input[type="checkbox"]:checked ~ .hamburger-lines .line1 {
      transform: rotate(45deg) scaleX(110%);
    }

    .nav-container input[type="checkbox"]:checked ~ .hamburger-lines .line2 {
      transform: scaleY(0);
    }

    .nav-container input[type="checkbox"]:checked ~ .hamburger-lines .line3 {
      transform: rotate(-45deg) scaleX(110%);
    }

    .hamburger__link {
      color: var(--primary);
      text-decoration: none;
      height: 50px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .hamburger__link:hover {
      background-color: rgba(211, 211, 211, 0.514);
    }
    .hamburger__link a {
      text-decoration: none;
      margin: auto;
      width: 100%;
      text-align: center;
      height: 100%;
      color: var(--primary);
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .hamburger__link a:hover {
      cursor: pointer;
    }
  }
</style>
