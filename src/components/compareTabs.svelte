<script>
  // @ts-nocheck
  import { flip } from "svelte/animate";
  import ImageCompare from "svelte-image-compare";

  export let slides;
</script>

<!-- svelte-ignore a11y-missing-attribute -->
<div class="compare">
    {#each slides as slide (slide.id)}
      <div
        id={slide.id}
        class="compare__slide"
      >
        <div class="compare__layout">
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
      </div>
    {/each}
</div>

<style>
  .compare {
    width: 100%;
    overflow-x: hidden;
    height: 100%;
    position: relative;
  }
  .compare__img-layout {
    width: 100%;
    border-radius: 10px;
    height: 450px;
    position: relative;
  }

  .compare__slide {
    height: 600px;
    border: 1px solid var(--secondary);
    border-radius: 10px;
    width: 500px;
  }
  .compare__layout {
    width: auto;
    height: 100%;
  }
  .compare__slide-text,
  .compare__slide-subtext,
  .compare__slide-blurb {
    font-family: var(--adrianna);
    width: 80%;
  }
  .compare__slide-subtext {
    color: var(--bodyText);
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
    margin: auto;
  }
  .compare__slide-blurb {
    color: var(--secondary);
    text-align: center;
    margin: auto;
  }
</style>
