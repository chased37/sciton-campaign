<script>
  let src = "./images/SCITON logo-01.png";
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
      <li />
      Sciton, Inc.
      <li />
      925 Commercial St., Palo Alto, CA 94303
      <li />
      +1.888.646.6999
      <li />
      <a target="_blank" href="https://sciton.com/">sciton.com</a>
    </ul>

    <p class="footer__copyright">
      Copyright © 2022 Sciton, Inc. All Rights Reserved. Sciton, BBL and HERO
      are registered trademarks or trademarks of Sciton Inc.
    </p>
  </div>
</div>

<style>
  .footer {
    height: 300px;
    width: 100%;
    display: grid;
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
</style>
