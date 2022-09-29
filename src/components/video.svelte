<script>
  // @ts-nocheck

  import { fly, fade } from "svelte/transition";
  import IntersectionObserver from "svelte-intersection-observer";

  let node;
</script>

<IntersectionObserver once element={node} let:intersecting>
  <main bind:this={node}>
    <div class="video__heading">
      {#if intersecting}
        <h2
          transition:fly={{ y: 50, delay: 250, duration: 400 }}
          class="video__header"
        >
          Get Beautiful, Younger Looking Skin with Zero Downtime.
        </h2>
        <h4
          transition:fly={{ y: 30, delay: 400, duration: 400 }}
          class="video__subtext"
        >
          With BBL HERO
        </h4>
      {/if}
    </div>
    <div class="video__player">
      <!-- <img {src} alt="Alissa" /> -->
      <video controls type="video/mp4" src="./assets/images/sciton_vid_edit2.mp4">
        <track
          src="captions_en.vtt"
          kind="captions"
          srclang="en"
          label="english_captions"
        />
      </video>
    </div>
  </main>
</IntersectionObserver>

<style>
  main {
    width: 100%;
    min-height: 800px;
    height: auto;
    display: grid;
    overflow: hidden;
    padding-bottom: 50px;
    grid-template-columns: 1fr;
  }
  .video__heading {
    font-family: var(--ivyMode);
    color: var(--secondary);
    display: grid;
    grid-template-columns: 1fr;
    height: 50%;
    padding-bottom: 2rem;
  }
  .video__header {
    font-size: 66px;
    text-align: center;
    width: 80%;
    margin: auto;
    padding-bottom: 2rem;
  }
  .video__subtext {
    font-size: 24px;
    text-align: center;
  }
  .video__player {
    margin: auto;
  }
  .video__player video {
    width: 100%;
    margin: auto;
    height: auto;
    max-height: 1000px;
    background-size: contain;
  }
  @media screen and (max-width: 600px) {
    main {
      min-height: 0;
      height: auto;
    }
    .video__header {
      font-size: 50px;
    }
  }
</style>
