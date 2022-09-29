<script>
  // @ts-nocheck
  import { blur } from "svelte/transition";

  let src = "./assets/images/quote.png";
  let arrow = "./assets/images/chevron-dark.png";

  export let slides;
  export let speed;

  const rotateCarouselLeft = (e) => {
    slides = [slides[slides.length - 1], ...slides.slice(0, slides.length - 1)];
  };
  const rotateCarouselRight = (e) => {
    slides = [...slides.slice(1, slides.length), slides[0]];
  };
</script>

<!-- svelte-ignore a11y-missing-attribute -->
<div class="carousel">
  <div class="carousel__slides">
    {#each slides as slide (slide.id)}
      <div
        animate:blur={{ duration: speed }}
        id={slide.id}
        class="carousel__slide"
      >
        <div class="carousel__layout">
          <div class="carousel__c-icon">
            <img {src} alt="quote" />
          </div>
          <p class="carousel__slide-text">{slide.text}</p>
          <p class="carousel__slide-subtext">{slide.author}</p>
          <p style="padding-top: 5px;" class="carousel__slide-subtext">
            actual patient
          </p>
        </div>
      </div>
    {/each}
  </div>
  <!-- svelte-ignore a11y-missing-attribute -->
  <a
    on:click={rotateCarouselLeft}
    class="carousel__button carousel__button--left"><img src={arrow} /></a
  >
  <a
    on:click={rotateCarouselRight}
    class="carousel__button carousel__button--right"><img src={arrow} /></a
  >
</div>

<style>
  .carousel {
    margin-bottom: 3rem;
    width: 100vw;
    overflow-x: hidden;
    position: relative;
  }
  .carousel__slides {
    width: 100%;
    display: flex;
    justify-content: center;
    flex-wrap: nowrap;
    overflow: hidden;
    height: auto;
    align-items: center;
  }
  .carousel__slide {
    height: 500px;
    margin: auto;
    display: inline-block;
    margin: 0 50%;
    backdrop-filter: blur(4px);
    background: transparent
      linear-gradient(180deg, #2f2e2e69 0%, #47443f70 100%) 0% 0% no-repeat
      padding-box;
    border-radius: 10px;
  }
  .carousel__layout {
    width: 80vw;
    height: auto;
  }
  .carousel__button {
    position: absolute;
    margin: 0 1rem;
  }
  .carousel__button:hover {
    filter: brightness(90%);
    transition: all ease 0.2s;
    cursor: pointer;
  }
  .carousel__button--right {
    right: 0;
    top: 50%;
  }
  .carousel__button--left {
    left: 0;
    top: 50%;
    transform: rotate(180deg);
  }
  .carousel__slide-text,
  .carousel__slide-subtext {
    color: var(--tertiary);
    font-family: var(--adrianna);
    width: 80%;
  }
  .carousel__slide-text {
    font-size: 30px;
    text-align: center;
    line-height: 1.3;
    padding-bottom: 1rem;
    margin: auto;
  }
  .carousel__slide-subtext {
    font-size: 15px;
    text-align: right;
    margin: auto;
  }
  .carousel__c-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 150px;
    border-bottom: 1px solid var(--tertiary);
    width: 80%;
    margin: 0 auto 1rem auto;
  }
  .carousel__c-icon img {
    transform: rotate(180deg);
  }

  @media screen and (max-width: 1100px) {
    .carousel__slide-text {
      font-size: 25px;
    }
  }
  @media screen and (max-width: 850px) {
    .carousel {
      height: 100%;
      margin: 0;
    }
    .carousel__slides {
      height: 100%;
    }
    .carousel__button--right {
      right: 30px;
      top: 87%;
    }
    .carousel__button--left {
      left: 30px;

      top: 87%;
      transform: rotate(180deg);
    }
    .carousel__slide-text {
      font-size: 17px;
    }
  }
</style>
