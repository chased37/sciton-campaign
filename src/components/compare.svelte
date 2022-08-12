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
      text: "1 MONTH POST 1 TX",
      subtext: "Actual patient results.",
      blurb: "Courtesy of Erin Blackwell, AYA Medical Spa",
      backgroundImage: "/images/bbl1_before.jpg",
      foregroundImage: "/images/bbl1_after.jpg",
    },
    {
      id: "two",
      text: "1 MONTH POST TX",
      subtext: "Actual patient results.",
      blurb: "Courtesy of Dr. Jason Pozner",
      backgroundImage: "/images/bbl2_before.jpg",
      foregroundImage: "/images/bbl2_after.jpg",
    },
    {
      id: "three",
      text: "AFTER 3 TREATMENTS",
      subtext: "Actual patient results.",
      blurb: "Courtesy of Chris Adigun, MD",
      backgroundImage: "/images/bbl3_before.jpg",
      foregroundImage: "/images/bbl3_after.jpg",
    },
  ];
</script>

<IntersectionObserver once element={node} let:intersecting>
  {#if intersecting}
    <h3
      transition:fly={{ y: 50, delay: 250, duration: 400 }}
      class="compare__heading"
    >
      Results You Can See
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
    overflow: hidden;
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
  @media screen and (max-width: 1450px) {
    main {
      grid-template-columns: 1fr 1fr;
    }
    .compare__slide:nth-child(2) {
      display: none;
    }
  }
</style>
