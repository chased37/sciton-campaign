<script>
  import { fly, fade } from "svelte/transition";
  // @ts-ignore
  import { onMount } from "svelte";
  export let items = [];
  export let activeTabValue = 1;
  export let componentId;
  let src = "/images/bbl-hero-2.png";

  let animate = false;
  onMount(() => {
    animate = true;
  });

  const handleClick = (tabValue) => () => (activeTabValue = tabValue);
</script>

<div id={componentId} class="bbl__header">
  {#if animate}
    <div in:fade={{ duration: 300, delay: 500 }} class="bbl__logo">
      <img {src} class="bbl__image" alt="BBL HERO" />
    </div>
    <ul in:fade={{ duration: 300, delay: 500 }} class="bbl__nav">
      {#each items as item (item.value)}
        <li id={item.id} class={activeTabValue === item.value ? "active" : ""}>
          <span on:click={handleClick(item.value)}>{item.label}</span>
        </li>
      {/each}
    </ul>
  {/if}
</div>

{#each items as item (item.value)}
  {#if activeTabValue == item.value}
    <div in:fly={{ x: 200, duration: 600 }} class="box">
      <svelte:component this={item.component} />
    </div>
  {/if}
{/each}

<style>
  .box {
    padding-bottom: 3rem;
  }
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
    grid-template-columns: 1fr 4fr;
    align-items: center;
  }
  .bbl__logo {
    display: flex;
    justify-content: center;
    align-items: center;
    border-right: 1px solid rgba(0, 0, 0, 0.25);
    height: 50%;
    min-width: 290px;
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
    padding-left: 3rem;
  }
  .bbl__nav li {
    margin-right: 20px;
  }
  li.active > span {
    color: #bfa888;
    border-bottom: solid 1px #bfa888;
    transition: ease 0.2s;
  }

  @media screen and (max-width: 1000px) {
    .bbl__header {
      display: flex;
    }
    .bbl__nav {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr 1fr;
      padding: 0;
      width: 90%;
      margin: auto;
    }
    .bbl__nav li {
      margin: 0;
    }
    .bbl__nav li span {
      text-align: center;
    }
    .bbl__logo {
      display: none;
    }
  }
  @media screen and (max-width: 600px) {
    .bbl__header {
      display: none;
    }
    #features, #technology, #treatments {
      display: none;
    }
  }
</style>
