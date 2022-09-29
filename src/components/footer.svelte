<script>
  let src = "./assets/images/footer-logo.png";
  let beautyLogo = "./assets/images/newbeautylogo.png";
</script>

<div class="footer">
  <div class="footer__c">
    <div class="header__logo">
      <img
        class="header__image"
        style="width:150px;height:auto;"
        {src}
        alt="Sciton"
      />
    </div>

    <ul class="footer__list">
      <li>Sciton, Inc.</li>
      <li>925 Commercial St., Palo Alto, CA 94303</li>
      <li>+1.888.646.6999</li>
      <li>
        <a target="_blank" href="https://sciton.com/">sciton.com</a>
      </li>
    </ul>

    <p class="footer__copyright">
      Copyright © 2022 Sciton, Inc. All Rights Reserved. Sciton, BBL and HERO
      are registered trademarks or trademarks of Sciton Inc.
    </p>
  </div>

  <div class="footer__logo">
    <img
      class="footer__image"
      src={beautyLogo}
      height="75"
      width="75"
      alt="Sciton"
    />
  </div>
</div>

<style>
  .footer {
    height: 300px;
    width: 100%;
    display: grid;
    grid-template-columns: 2fr 1fr;
    font-family: var(--adrianna);
  }
  .footer__c {
    width: 80%;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 3fr;
    font-family: var(--adrianna);
    margin: auto;
    line-height: 1.5;
  }
  .footer__list,
  .footer__copyright {
    padding-left: 0.5rem;
  }
  .footer__list a {
    text-decoration: none;
    color: var(--primary);
  }
  .footer__list a:hover {
    color: var(--secondary);
  }
  .footer__copyright {
    font-size: 12px;
  }
  .footer__logo {
    width: 40%;
    display: flex;
    align-items: flex-start;
    justify-self: flex-end;
  }
  .footer__image {
    margin: 35% 0 0 0;
  }
  @media screen and (max-width: 650px) {
    .footer {
      grid-template-columns: 1fr;
      padding: 70px 0;
    }
    .footer__c {
      width: 90%;
    }
    .footer__logo {
     justify-content: flex-start;
     width: 90%;
     margin: auto;
    }
    .footer__image {
    margin: 0;
  }
  }
</style>
