<script>
  // @ts-ignore
  import Carousel from "./carousel.svelte";
  const slides = [
    {
      id: "one",
      text: "I have never tried lasers before, so I was anxious about the treatment and results. I was shocked how easy the HERO treatment was, and the immediate results of glowing smooth skin. I have aleady signed up for my next BBL® HERO™ treatment in 3 months.",
      author: "Lindsay P.",
    },
    {
      id: "two",
      text: `I thought about writing a review for the BBL® HERO™, but then I thought "just look at my pictures, they speak for themselves!" This truly has been a life changer for me in both my appearance and confidence. My family and friends have all made comments on how youthful and bright my skin looks. And I cannot stop smiling thank you, Sciton.`,
      author: "Yvonne S.",
    },
    {
      id: "three",
      text: "BBL HERO, has been a remarkably successful and relatively painless way to erase years of sundamage from my face, arms and chest. I would highly reccomend this treatment option to anyone wishing for a more youthful complexion without the need for recovery or downtime.",
      author: "Tracy B.",
    },
  ];
</script>

<main>
  <Carousel speed={350} {slides} />
</main>

<style>
  main {
    width: 100%;
    height: 900px;
    background-image: url("./images/group.jpg");
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    overflow: hidden;
    display: flex;
    align-items: flex-end;
  }
  @media screen and (max-width: 850px) {
    main {
      height: 700px;
    }
  }
</style>
