<script></script>

<main>
    <div class="treatments__heading">
        <h2 class="treatments__title">Treatable Areas</h2>
        <p class="treatments__desc">BBL &reg; HERO &trade; can treat the face and neck for most skin types. Its complimentary treatment, BBL &reg; HERO &trade;, handles all the rest. </p>
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
    <div class="treatments__link">
        <a href="/">Find Local Provider</a>
    </div>
</main>

<style>
    main {
        display: grid;
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
        color: var(--primary);
        font-family: var(--adrianna);
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
    .treatments__link {
        max-width: 250px;
        margin: auto;
        padding: .8rem 2rem;
        background-color: var(--secondary);
        border: none;
        border-radius: 5px;
    }
    .treatments__link a {
        text-decoration: none;
        font-family: var(--adrianna);
        color: var(--tertiary);
    }

</style>