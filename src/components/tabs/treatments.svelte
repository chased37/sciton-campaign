<script>
  // @ts-nocheck

  import * as animateScroll from "svelte-scrollto";
</script>

<main>
  <div class="treatments__heading">
    <h2 class="treatments__title">Treatable Areas</h2>
    <p class="treatments__desc">
      BBL &reg; HERO &trade; can treat the face and neck for most skin types.
      Its complimentary treatment, BBL &reg; HERO &trade;, handles all the rest.
    </p>
  </div>
  <ul class="treatments__list">
    <li><p>FACE</p></li>
    <li><p>NECK</p></li>
    <li><p>DECOLLETE</p></li>
    <li><p>ARMS</p></li>
    <li><p>BACK</p></li>
    <li><p>ABDOMEN</p></li>
    <li><p>LEGS</p></li>
    <li><p>BUTTOCKS</p></li>
  </ul>
  <div class="treatments__c-button">
    <button
      type="button"
      class="treatments__button"
      on:click={() =>
        animateScroll.scrollTo({ element: "#map", duration: 700 })}
      >FIND LOCAL PROVIDER</button
    >
  </div>
</main>

<style>
  main {
    display: grid;
    min-height: 800px;
    grid-template-columns: 1fr;
    padding-top: 5rem;
  }
  .treatments__heading {
    padding-bottom: 3rem;
  }
  .treatments__title {
    font-family: var(--ivyMode);
    font-size: 66px;
    color: var(--secondary);
    text-align: center;
    padding-bottom: 2rem;
  }
  .treatments__desc {
    color: var(--bodyText);
    font-family: var(--adrianna);
    line-height: 1.5;
    text-align: center;
  }
  .treatments__list {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    height: 250px;
    width: 80%;
    margin: auto;
    padding-bottom: 3rem;
  }
  .treatments__list li {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .treatments__list li p {
    width: 60%;
    font-family: var(--adrianna);
    font-size: 20px;
    font-weight: 300;
    color: var(--secondary);
    padding: 1rem 10px;
    border-radius: 10px;
    text-align: center;
    border: 1px solid var(--secondary);
    margin: auto;
    min-width: 200px;
  }
  .treatments__c-button {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .treatments__button {
    text-decoration: none;
    font-family: var(--adrianna);
    color: var(--tertiary);
    max-width: 250px;
    margin: auto;
    padding: 0.8rem 2rem;
    background-color: var(--secondary);
    border: none;
    border-radius: 5px;
  }
  .treatments__button:hover {
    cursor: pointer;
  }
  @media screen and (max-width: 1200px) {
    .treatments__list {
      grid-template-columns: 1fr 1fr;
      height: auto;
      padding-bottom: 0;
      width: 100%;
    }
    .treatments__list li {
      margin: 1rem 0;
    }
    .treatments__heading {
      padding-bottom: 0;
    }
    .treatments__title {
      padding-bottom: 1rem;
    }
    .treatments__desc {
      width: 70%;
      margin: auto;
    }
  }
</style>
