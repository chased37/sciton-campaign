<script>
  let size = 50;
  let inIcon = "/images/linkedin-fixed.png";
  let tiktokIcon = "/images/tiktok.png";
  let instaIcon = "/images/insta.png";
</script>

<div class="newsletter">
  <div class="newsletter__image" />
  <div class="newsletter__socials">
    <ul class="newsletter__socials-list">
      <li class="newsletter__socials-item">
        <a target="_blank" href="https://www.linkedin.com/company/sciton"
          ><img
            height={size + 7}
            width={size + 7}
            style="margin:auto"
            src={inIcon}
            alt="LinkedIn Link"
          /></a
        >
      </li>
      <li class="newsletter__socials-item">
        <a target="_blank" href="https://www.instagram.com/sciton_inc/"
          ><img
            height={size}
            width={size}
            src={instaIcon}
            alt="Instagram Link"
          /></a
        >
      </li>
      <li class="newsletter__socials-item">
        <a target="_blank" href="https://www.tiktok.com/@sciton"
          ><img
            height={size}
            width={size}
            src={tiktokIcon}
            alt="TikTok Link"
          /></a
        >
      </li>
    </ul>
  </div>
  <div class="newsletter__form">
    <h1 class="newsletter__heading">Stay in The Know</h1>
    <div>
      <input class="newsletter__input" type="text" placeholder="Name" />
    </div>
    <div>
      <input class="newsletter__input" type="email" placeholder="Email" />
    </div>
    <div>
      <input class="newsletter__input" type="tel" placeholder="Mobile" />
    </div>
    <div>
      <button class="newsletter__button">SIGN UP</button>
    </div>
  </div>
</div>

<style>
  .newsletter {
    width: 100%;
    height: 800px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
  }
  .newsletter__image {
    background-image: url("/images/alissa.jpg");
    width: 100%;
    height: auto;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
  }

  .newsletter__form {
    position: absolute;
    height: 80%;
    width: 45%;
    display: grid;
    grid-template-columns: 1fr;
    border-top: 7px solid var(--secondary);
    border-left: 7px solid var(--secondary);
    border-bottom: 7px solid var(--secondary);
    border-radius: 3px;
    padding: 3rem 0 1rem 10rem;
    right: 0;
    top: -3%;
  }
  .newsletter__socials {
    display: flex;
    align-items: flex-end;
    justify-content: flex-end;
  }
  .newsletter__socials-list {
    display: flex;
    flex-direction: row;
    margin-right: 30%;
    margin-bottom: 5px;
  }
  .newsletter__socials-item {
    margin: 0 1rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .newsletter__socials-item a {
    height: auto;
    width: auto;
  }
  .newsletter__heading {
    font-family: var(--ivyMode);
    font-style: italic;
    color: var(--secondary);
    font-size: 40px;
  }
  .newsletter__input {
    background-color: var(--offWhite);
    border: none;
    border-bottom: 2px solid var(--secondary);
    width: 300px;
    height: 50px;
    font-size: 20px;
    color: var(--secondary);
    font-family: var(--adrianna);
    padding-left: 1rem;
  }
  .newsletter__input:focus {
    outline: none;
  }
  .newsletter__button {
    padding: 1rem 3rem;
    background-color: var(--secondary);
    color: var(--tertiary);
    box-shadow: none;
    border-radius: 3px;
    font-family: var(--adrianna);
    font-size: 20px;
    outline: none;
    border: none;
  }
  .newsletter__button:hover {
    cursor: pointer;
  }
  @media screen and (max-width: 1200px) {
    .newsletter__form {
      border: none;
    }
  }
  @media screen and (max-width: 770px) {
    .newsletter {
      grid-template-columns: 1fr 2fr;
    }
    .newsletter__form {
      right: 10%;
      top: 10;
    }
  }
  @media screen and (max-width: 630px) {
    .newsletter {
      grid-template-columns: 1fr;
      height: 600px;
    }
    .newsletter__image {
      display: none;
    }
    .newsletter__form {
      position: inherit;
      order: -1;
      width: auto;
      margin: auto;
      padding: 0;
      right: 0;
      top: 0;
      left: 0;
      bottom: 0;
      height: 500px;
    }
    .newsletter__socials {
      width: 100%;
      justify-content: center;
    }
    .newsletter__socials-list {
      margin: 0;
    }
  }
</style>
