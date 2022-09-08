<script>
  // @ts-nocheck

  // @ts-ignore
  import { onMount } from "svelte";
  import { fly, fade } from "svelte/transition";
  import CompareOne from "./compare-tabs/compareOne.svelte";
  import CompareTwo from "./compare-tabs/compareTwo.svelte";

  export let activeTabValue = 1;

  let animate = false;
  onMount(() => {
    animate = true;
  });

  const boxes = [
    { value: 1, id: "one", component: CompareOne },
    { value: 2, id: "two", component: CompareTwo },
  ];

  const handleClick = (tabValue) => () => (activeTabValue = tabValue);
</script>

<h3
  transition:fly={{ y: 50, delay: 250, duration: 400 }}
  class="compare__heading"
>
  Results You Can See
</h3>

<div class="compare__track">
  {#each boxes as box (box.value)}
    {#if activeTabValue == box.value}
      <div class="box" in:fade={{ delay: 200, duration: 500 }}>
        <svelte:component this={box.component} />
      </div>
    {/if}
  {/each}
</div>

<div class="compare__nav">
  {#if animate}
    <ul in:fade={{ duration: 300 }} class="compare__nav-c">
      {#each boxes as box (box.value)}
        <li id={box.id} class={activeTabValue === box.value ? "active" : ""}>
          <span on:click={handleClick(box.value)}><button /></span>
        </li>
      {/each}
    </ul>
  {/if}
</div>

<style>
  .compare__track {
    width: 100%;
    min-height: 700px;
    overflow: hidden;
  }
  .box {
    width: 100%;
    display: grid;
    height: 100%;
    min-height: 700px;
    grid-template-columns: 1fr 1fr 1fr;
  }
  .compare__heading {
    width: 100%;
    height: auto;
    font-family: var(--ivyMode);
    color: var(--secondary);
    font-size: 66px;
    text-align: center;
    padding-top: 4rem;
  }

  .compare__nav {
    height: 75px;
    width: 100%;
  }

  .compare__nav-c {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    flex-direction: row;
  }

  span {
    border: 1px solid transparent;
    border-top-left-radius: 0.25rem;
    border-top-right-radius: 0.25rem;
    display: block;
    padding: 0.5rem 1rem;
    cursor: pointer;
  }

  li > span > button:hover {
    cursor: pointer;
  }

  li > span > button {
    background-color: lightgrey;
    border: none;
    border-radius: 3px;
    width: 35px;
    height: 5px;
    transition: ease 0.7s;
  }

  li.active > span > button {
    width: 100px;
    transition: ease 0.7s;
    background-color: var(--secondary);
  }

  @media screen and (max-width: 1450px) {
    .compare__track {
      grid-template-columns: 1fr 1fr;
    }
  }
  @media screen and (max-width: 1150px) {
    .box {
      grid-template-columns: 1fr 1fr;
    }
  }
  @media screen and (max-width: 730px) {
    .box {
      grid-template-columns: 1fr;
    }
  }
  @media screen and (max-width: 630px) {
    .compare__heading {
      font-size: 50px;
    }
  }
</style>
