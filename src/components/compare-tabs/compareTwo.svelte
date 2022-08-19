<script>
  // @ts-nocheck

  import ImageCompare from "svelte-image-compare";

  const slides = [
    {
      id: "one",
      text: "1 MONTH POST 1 TX",
      subtext: "Actual patient results.",
      blurb: "Courtesy of Erin Blackwell, AYA Medical Spa",
      backgroundImage: "/images/bbl1_before.avif",
      foregroundImage: "/images/bbl1_after.avif",
    },
    {
      id: "two",
      text: "1 MONTH POST TX",
      subtext: "Actual patient results.",
      blurb: "Courtesy of Dr. Jason Pozner",
      backgroundImage: "/images/bbl2_before.avif",
      foregroundImage: "/images/bbl2_after.avif",
    },
    {
      id: "three",
      text: "AFTER 3 TREATMENTS",
      subtext: "Actual patient results.",
      blurb: "Courtesy of Chris Adigun, MD",
      backgroundImage: "/images/bbl3_before.avif",
      foregroundImage: "/images/bbl3_after.avif",
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
