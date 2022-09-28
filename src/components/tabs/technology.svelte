<script>
  // @ts-nocheck
  import * as animateScroll from "svelte-scrollto";
</script>

<main>
  <div class="technology__text">
    <h2 class="technology__heading">Technology</h2>
    <h3 class="technology__desc technology__desc--subhead">
      Your skin never looked <i>this</i> good.
    </h3>
    <p class="technology__desc">
      BBL HERO’s new advanced technology forever transforms skin. The best
      testament to a treatment’s efficacy? What you see when you look in the
      mirror.<br /> <br />

      Let your skin do the talking—and flaunt impressive head-to-toe results in
      minutes thanks to BBL HERO’s innovative technology. A fan favorite among
      patients and practitioners—BBL HERO boasts impressive before and after
      results, patient accolades, and industry awards. Here’s a sneak peek into
      the groundbreaking BBL HERO technology:
      <br /> <br />
      <strong class="technology__desc technology__desc--strong"
        >Quick and easy full-body treatments.</strong
      >
      Did you know BBL HERO delivers faster, more powerful, and more comfortable
      results than ever before? Treatments on large areas like the back, legs, and
      arms take as little as three minutes with HERO— BBL’s High Energy Rapid Output.
      <br /> <br />
      <strong class="technology__desc technology__desc--strong"
        >A comfortable, gentle experience with minimal downtime.</strong
      >
      Whew, breathe a sigh of relief—painful treatments are a thing of the past thanks
      to BBL HERO’s signature handpiece that gently removes pigment and other skin
      imperfections. The device’s ComfortCool technology keeps skin cool and comfortable
      so numbing cream isn’t needed. After treatment, most patients will feel warm
      for an additional 30 to 60 minutes.
      <br /> <br />
      <strong class="technology__desc technology__desc--strong"
        >Treat your unique skin concerns with BBL HERO’s proprietary, multi-pass
        approach.</strong
      >
      Now, it’s easy for providers to customize your treatment for powerful, long-lasting
      results. A single pass with the BBL HERO handpiece addresses the skin&#39;s
      overall appearance, while multiple passes using different wavelengths of light
      provide the appearance of tighter skin and correct:
    </p>
    <ul class="technology__list">
      <li>Pigmented lesions</li>
      <li>Skin flushing</li>
      <li>Acne</li>
      <li>And more!</li>
    </ul>
    <p class="technology__desc">
      With the broadest range of wavelengths on the market—in one
      handpiece—patients can experience exceptional results in as little as one
      treatment. Meet your skin’s new best friend–and show off beautiful skin
      with Sciton’s reliable and trusted BBL HERO.
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
  .technology__desc--subhead {
    font-size: 20px;
    padding-bottom: 10px;
  }
  .technology__desc--strong {
    font-weight: bold;
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
