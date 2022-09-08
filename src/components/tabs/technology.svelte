<script>
  // @ts-nocheck
  import * as animateScroll from "svelte-scrollto";
</script>

<main>
  <div class="technology__text">
    <h2 class="technology__heading">Technology</h2>
    <p class="technology__desc">
      Practitioners all over the world describe their BBL module as the
      workhorse in their practice. They have come to rely on optimized and
      consistent delivery provided by the advanced technological features that
      set it apart from the competition.<br /> <br />

      But none of that would matter if results weren’t there to back it up. The
      proof is in the pudding, as shown by the plethora of impressive before and
      after images, patient accolades, and industry awards.
      <br /> <br />
    </p>
    <ul class="technology__list">
      <li>
        Fast lunch time, low social downtime, procedures with ‘wow’ results
      </li>
      <li>
        Comfortable treatments allow you to skip the numbing cream, with
        integrated ComfortCool technology
      </li>
      <li>
        Customized treatments that address your specific skin condition and
        treatment goals
      </li>
      <li>
        Versatility to quickly switch between treatments and areas with safe
        protocol driven software
      </li>
    </ul>
    <p class="technology__desc">
      BBL HERO includes 9 wavelength filters to deliver a wide variety of
      customizable treatment applications in one handpiece, as opposed to
      competitor IPL devices that require a different handpiece for each
      individual wavelength.
    </p>
    <div class="technology__c-button">
      <button
        class="technology__button"
        on:click={() =>
          animateScroll.scrollTo({ element: "#map", duration: 700 })}
        >FIND LOCAL PROVIDER</button
      >
    </div>
  </div>
  <div class="technology__image">
    <div />
  </div>
</main>

<style>
  main {
    min-height: 800px;
    width: 90%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding-bottom: 3rem;
    margin: auto;
  }
  .technology__text {
    display: flex;
    flex-direction: column;
    grid-template-columns: 1fr;
    justify-content: center;
    align-items: center;
  }
  .technology__heading,
  .technology__desc {
    width: 80%;
    text-align: left;
  }
  .technology__heading {
    font-family: var(--ivyMode);
    color: var(--secondary);
    font-size: 66px;
    padding: 3rem 0;
  }
  .technology__desc {
    font-family: var(--adrianna);
    color: var(--bodyText);
    font-size: 15px;
    line-height: 1.5;
  }
  .technology__c-button {
    width: 80%;
    padding-top: 3rem;
  }
  .technology__button {
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
  .technology__button:hover {
    cursor: pointer;
  }
  .technology__image {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .technology__image div {
    width: 90%;
    height: 90%;
    background-image: url("./images/technology.gif");
    background-repeat: no-repeat;
    margin: auto;
    background-size: 220%;
    border-radius: 28px;
    background-position: center;
  }
  .technology__list {
    list-style: disc;
    width: 70%;
    line-height: 1.5;
    font-family: var(--adrianna);
    color: var(--bodyText);
    padding: 1.3rem 0;
    margin-left: 1rem;
  }

  @media screen and (max-width: 1000px) {
    main {
      grid-template-columns: 1fr;
    }
    .technology__image {
      display: none;
    }
  }
</style>
