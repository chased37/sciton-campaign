<script>
// @ts-nocheck

  let src = "/images/roxanne.jpg";

  import * as animateScroll from "svelte-scrollto";
</script>

<main>
  <div class="features__text">
    <h2 class="features__heading">
      BBL &reg; HERO &trade; is a fast and comfortable way to improve your
      overall skin complexion.
    </h2>
    <p class="features__desc">
      Light energy delivered by BBL® HERO &trade; stimulates your cells to
      regenerate and restore your skin's youthful appearance, giving you
      smoother skin, smaller pores and even pigmentation. <br /> <br /> HERO &trade;
      means immediate results delivered in a comfortable lunchtime treatment with
      no downtime.
    </p>
    <div class="features__c-button">
      <button
        class="features__button"
        on:click={() =>
          animateScroll.scrollTo({ element: "#map", duration: 700 })}
        >FIND LOCAL PROVIDER</button
      >
    </div>
  </div>
  <div class="features__image">
    <div />
  </div>
</main>

<style>
  main {
    min-height: 800px;
    width: 90%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin: auto;
  }
  .features__text {
    display: flex;
    flex-direction: column;
    grid-template-columns: 1fr;
    justify-content: center;
    align-items: center;
  }
  .features__heading,
  .features__desc {
    width: 80%;
    text-align: left;
    padding-bottom: 3rem;
    line-height: 1.5;
  }
  .features__heading {
    font-family: var(--ivyMode);
    color: var(--secondary);
    font-size: 40px;
  }
  .features__desc {
    font-family: var(--adrianna);
    color: var(--bodyText);
    font-size: 18px;
  }
  .features__c-button {
    width: 80%;
  }
  .features__button {
    max-width: 250px;
    margin: auto;
    padding: 0.8rem 2rem;
    background-color: var(--secondary);
    border: none;
    border-radius: 5px;
    text-decoration: none;
    font-family: var(--adrianna);
    color: var(--tertiary);
  }
  .features__button:hover {
    cursor: pointer;
  }
  .features__image {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .features__image div {
    width: 90%;
    height: 90%;
    background-image: url("/images/features.gif");
    background-repeat: no-repeat;
    margin: auto;
    background-size: 220%;
    border-radius: 28px;
    background-position: center;
  }
  @media screen and (max-width: 1000px) {
    main {
      grid-template-columns: 1fr;
    }
    .features__image {
      display: none;
    }
    .features__heading {
      font-size: 50px;
    }
  }
</style>
