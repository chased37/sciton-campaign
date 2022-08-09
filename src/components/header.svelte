<script>

    let src = "/images/logo-sciton.png"
	
</script>




<main>
<div class="header__logo">
    <img class="header__image" {src} alt="Sciton"/>
</div>

<div class="header__nav">
    <div class="header__link header__link--1">
        <!-- <a href="/">BBL HERO Treatments</a> -->
    </div>
    <div class="header__link header__link--2">
        <a href="/">Find My Provider</a>
    </div>
    <div class="header__hamburger"></div>
</div>
</main>


<style>
    main {
        width: 100%;
        height: 87px;
        display: grid;
        grid-template-columns: 1fr 1fr;
        position: fixed;
        background-color: var(--tertiary);
    }
    .header__nav {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        align-items: center;
        justify-content: flex-end;
        font-family: var(--adrianna);
    }
    .header__logo {
        display: flex;
        justify-content: flex-start;
        align-items: center;
    }
    .header__image {
        width: 200px;
        height: auto;
        padding-left: 2rem;
    }
    .header__link a {
        text-decoration: none;
        color: black;
    }
</style>