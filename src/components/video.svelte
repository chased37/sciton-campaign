<script>
let src = "/images/alissa.jpg"

</script>


<main>
    <div class="video__heading">
        <h2 class="video__header">Get Beautiful, Younger Looking Skin with Zero Downtime.</h2>
        <h4 class="video__subtext">With BBL &reg; HERO &trade;</h4>
    </div>
    <div class="video__player">
        <img {src} alt="Alissa" />
    </div>
</main>

<style>
    main {
        width: 100%;
        max-height: 1200px;
        min-height: 800px;
        display: grid;
        overflow: hidden;
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
    .video__player img{
        width: 100%;
        height: auto;
        background-size: cover;
    }
</style>