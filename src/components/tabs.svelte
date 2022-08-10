<script>
  import { fly } from "svelte/transition";
  export let items = [];
  export let activeTabValue = 1;
  let src = "images/bbl-hero-2.png";

  const handleClick = (tabValue) => () => (activeTabValue = tabValue);
</script>

<div class="bbl__header">
  <div class="bbl__logo">
    <img {src} class="bbl__image" alt="BBL HERO" />
  </div>
  <ul class="bbl__nav">
    {#each items as item (item.value)}
      <li class={activeTabValue === item.value ? "active" : ""}>
        <span on:click={handleClick(item.value)}>{item.label}</span>
      </li>
    {/each}
  </ul>
</div>

{#each items as item (item.value)}
  {#if activeTabValue == item.value}
    <div in:fly={{ x: 200, duration: 600 }} class="box">
      <svelte:component this={item.component} />
    </div>
  {/if}
{/each}

<style>
  .bbl__header {
    height: 150px;
    background-color: var(--tertiary);
  }
  .bbl__nav {
    display: flex;
    flex-wrap: wrap;
    list-style: none;
    width: 100%;
  }
  li {
    margin-bottom: -1px;
  }

  span {
    border: 1px solid transparent;
    border-top-left-radius: 0.25rem;
    border-top-right-radius: 0.25rem;
    display: block;
    padding: 0.5rem 1rem;
    cursor: pointer;
  }
  .bbl__header {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 3fr;
  }
  .bbl__logo {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .bbl__image {
    width: 200px;
    height: auto;
  }
  .bbl__nav {
    display: flex;
    align-items: center;
    font-family: var(--adrianna);
    font-size: 22px;
  }
  .bbl__nav li {
    margin-right: 20px;
  }
  li.active > span {
    color: #bfa888;
    border-bottom: solid 1px #bfa888;
    transition: ease 0.2s;
  }
</style>
