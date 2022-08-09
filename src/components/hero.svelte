<script>
    let src = 'images/bbl-hero.png'
</script>

<main>
    <div class="hero__block">
        <h1 class="hero__text">Skin That Looks as Young as You Feel</h1>
        <img class="hero__image" {src} alt="BBL Hero"/>
    </div>

</main>

<style>
    /* your styles go here */
    main {
        width: 100%;
        height: calc(90vh);
        min-height: 800px;
        background-image: url("images/CLEO.jpg");
        background-size: cover;
        box-shadow:inset 0 0 0 2000px rgba(123, 123, 123, 0.3);
        display: flex;
        justify-content: center;
        align-items: center;

    }

    .hero__block {
        display: grid;
        grid-template-columns: 1fr;
        justify-content: center;
        align-items: center;
        min-height: 200px;
        height: auto;
    }
  
    .hero__text {
        color: white;
        text-align: center;
        font-size: 72px;
        padding: 1rem;
        width: auto;
        font-weight: var(--regular);
        font-family: var(--ivyMode);
    }
    .hero__image {
        width: 300px;
        height: auto;
        margin: auto;
    }

</style>