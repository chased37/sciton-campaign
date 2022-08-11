<script>
  let src = "images/roxanne.jpg";

  import * as animateScroll from "svelte-scrollto";
</script>

<main>
  <div class="overview__text">
    <h2 class="overview__heading">What is <br /> BBL &reg; HERO &trade;?</h2>
    <p class="overview__desc">
      BroadBand Light (BBL®) from Sciton® is world renowned for its outstanding
      outcomes, ease of use, and innovative technology. <br /> <br /> The next generation
      BBL is here. With BBL® HERO™ (High Energy Rapid Output) you can quickly deliver
      forever results from head to toe.
    </p>
    <div class="overview__c-button">
      <button
        type="button"
        class="overview__button"
        on:click={() =>
          animateScroll.scrollTo({ element: "#map", duration: 700 })}
        >FIND LOCAL PROVIDER</button
      >
    </div>
  </div>
  <div class="overview__image">
    <div />
  </div>
</main>

<style>
  main {
    height: 800px;
    width: 90%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin: auto;
  }
  .overview__text {
    display: flex;
    flex-direction: column;
    grid-template-columns: 1fr;
    justify-content: center;
    align-items: center;
  }
  .overview__heading,
  .overview__desc {
    width: 80%;
    text-align: left;
    line-height: 1.5;
    padding-bottom: 3rem;
  }
  .overview__heading {
    font-family: var(--ivyMode);
    color: var(--secondary);
    font-size: 66px;
  }
  .overview__desc {
    font-family: var(--adrianna);
    color: var(--bodyText);
    font-size: 18px;
  }
  .overview__c-button {
    width: 80%;
  }
  .overview__button {
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
  .overview__button:hover {
    cursor: pointer;
  }
  .overview__image {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .overview__image div {
    width: 90%;
    height: 90%;
    background-image: url("images/roxanne.jpg");
    margin: auto;
    background-repeat: no-repeat;
    background-size: 220%;
    border-radius: 28px;
    background-position: center;
  }
</style>
