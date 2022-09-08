<script>
  // @ts-nocheck
  import ImageCompare from "svelte-image-compare";

  const slides = [
    {
      id: "one",
      text: "2 MONTHS AFTER 1 TX",
      subtext: "Actual patient results.",
      blurb: "Courtesy of Jason Pozner, MD",
      backgroundImage: "./images/B&A-07.jpg",
      foregroundImage: "./images/B&A-08.jpg",
    },
    {
      id: "two",
      text: "1 MONTH POST TX",
      subtext: "Actual patient results.",
      blurb: "Courtesy of Steven Swengel, MD",
      backgroundImage: "./images/B&A-01.jpg",
      foregroundImage: "./images/B&A-02.jpg",
    },
    {
      id: "three",
      text: "AFTER 3 TX",
      subtext: "Actual patient results.",
      blurb: "Courtesy of Patrick Bitter, MD, FAAD",
      backgroundImage: "./images/B&A-09.jpg",
      foregroundImage: "./images/B&A-10.jpg",
    },
  ];
</script>

{#each slides as slide (slide.id)}
  <div id={slide.id} class="compare__slide">
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
{/each}

<style>
  .compare__slide {
    height: 600px;
    border: 1px solid var(--secondary);
    border-radius: 10px;
    margin: auto;
    width: 450px;
    overflow: hidden;
    z-index: 1;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr 1fr 1fr;
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
    .compare__slide {
      height: 500px;
      width: 350px;
    }
    .compare__img-layout {
      height: 300px;
    }
    .compare__slide-text {
      font-size: 25px;
    }
    .compare__slide-blurb {
      font-size: 15px;
    }
  }
  @media screen and (max-width: 1150px) {
    .compare__slide:nth-child(3) {
      display: none;
    }
  }
  @media screen and (max-width: 730px) {
    .compare__slide:nth-child(1) {
      display: none;
    }
  }
</style>
