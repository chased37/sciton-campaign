<script>
  // @ts-nocheck

  import { fly } from "svelte/transition";
  // @ts-nocheck
  import IntersectionObserver from "svelte-intersection-observer";
  import CompareTabs from "./compareTabs.svelte";
  import ImageCompare from "svelte-image-compare";

  let node;
  const slides = [
    {
      id: "one",
      text: "1 MONTH POST 1TX",
      subtext:
        "Actual patient results before (left) and post 1 treatment (right).",
      blurb: "Courtesy of Laura Granger, MD.",
      backgroundImage: "/images/alissa.jpg",
      foregroundImage: "/images/CLEO.jpg",
    },
    {
      id: "two",
      text: "1 MONTH POST 1TX",
      subtext:
        "Actual patient results before (left) and post 1 treatment (right).",
      blurb: "Courtesy of Laura Granger, MD.",
      backgroundImage: "/images/alissa.jpg",
      foregroundImage: "/images/CLEO.jpg",
    },
    {
      id: "three",
      text: "1 MONTH POST 1TX",
      subtext:
        "Actual patient results before (left) and post 1 treatment (right).",
      blurb: "Courtesy of Laura Granger, MD.",
      backgroundImage: "/images/alissa.jpg",
      foregroundImage: "/images/CLEO.jpg",
    },
  ];
</script>

<IntersectionObserver once element={node} let:intersecting>
  {#if intersecting}
    <h3
      transition:fly={{ y: 50, delay: 250, duration: 400 }}
      class="compare__heading"
    >
      Before and After
    </h3>
  {/if}
  <main bind:this={node}>
    {#each slides as slide (slide.id)}
      {#if intersecting}
        <div
          transition:fly={{ y: 10, delay: 400, duration: 500 }}
          id={slide.id}
          class="compare__slide"
        >
          <div class="compare__img-layout">
            <ImageCompare
              before={slide.backgroundImage}
              after={slide.foregroundImage}
              contain={true}
              overlay={false}
            />
          </div>
          <p class="compare__slide-subtext">{slide.subtext}</p>
          <p class="compare__slide-text">{slide.text}</p>
          <p class="compare__slide-blurb">{slide.blurb}</p>
        </div>
      {/if}
    {/each}
  </main>
</IntersectionObserver>

<style>
  main {
    width: 100%;
    min-height: 700px;
    overflow: hidden;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    align-items: center;
    justify-content: center;
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
  .compare__slide {
    height: 600px;
    border: 1px solid var(--secondary);
    border-radius: 10px;
    margin: auto;
    width: 450px;
  }
  .compare__img-layout {
    width: 100%;
    border-radius: 10px;
    height: 450px;
    position: relative;
  }
  .compare__slide-text,
  .compare__slide-subtext,
  .compare__slide-blurb {
    font-family: var(--adrianna);
    width: 80%;
  }
  .compare__slide-subtext {
    color: rgba(0, 0, 0, 0.413);
  }
  .compare__slide-text {
    font-size: 30px;
    text-align: center;
    line-height: 1.3;
    margin: auto;
    color: var(--primary);
  }
  .compare__slide-subtext {
    font-size: 13px;
    text-align: center;
    padding: 0.5rem 0;
    margin: auto;
  }
  .compare__slide-blurb {
    color: var(--secondary);
    text-align: center;
    margin: auto;
  }
</style>
