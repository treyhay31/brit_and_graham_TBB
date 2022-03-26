<script>
  import beer from './../assets/beer.svg'
  import drink from './../assets/drink.svg'
  import food from './../assets/food.svg'
  import wine from './../assets/wine.svg'
  import cocktail from './../assets/cocktail.svg'
  import bottom from './../assets/bottom_greenery.png';
  
  const drinks = [
    {
      owner: "His",
      title: "Good Ol' Parker",
      ingredients: ["Whiskey", "Ginger", "Bitters"],
      image: cocktail,
    },
    {
      owner: "Hers",
      title: "Marvelous Ms. Maisie",
      ingredients: ["Vodka", "Gingerbeer", "Lime", "Blackberry Simple Syrup"],
      image: cocktail,
    },
    {
      owner: "Wine",
      title: "Red",
      ingredients: ["Merlot", "Cabernet Sauvignon"],
      image: wine,
    },
    {
      owner: "Wine",
      title: "White",
      ingredients: ["Riesling", "Sauvignon Blanc"],
      image: wine,
    }, 
    {
      owner: "Beer",
      title: "Lager",
      ingredients: ["Bud Light", "Miller Lite", "Full Nelson", "Yuengling"],
      image: beer,
    }, 
    {
      owner: "Self Serve",
      title: "Essentials",
      ingredients: ["Water", "Iced Tea", "Coffee"],
      image: drink,
    },
    {
      owner: "Downstairs",
      title: "Liquor",
      ingredients: ["Crown Royal", "Absolute", "Tanqueray","Rum"],
      image: cocktail,
    },
    {
      owner: "Downstairs",
      title: "Classic Mixers",
      ingredients: ["Club Soda", "Tonic", "Ginger Beer","Bitters"],
      image: drink,
    },
    {
      owner: "Downstairs",
      title: "Sweet Mixers",
      ingredients: ["Cranberry Juice", "Pineapple Juice","Ginger Ale","Sprite","Coca-Cola","Orange Juice"],
      image: drink,
    }
  ]
</script>

<section>
  {#each drinks as d}
  <div class="drink">
    <h3>{d.owner}</h3>
    <h4 class="cardTitle">{d.title}</h4>
    <img class="cardImage" src={d.image} alt="beverage container" />
    <ul class="cardIngredients">
      {#each d.ingredients as ingredient}
        <li>{ingredient}</li>
      {/each}
    </ul>
  </div>
  {/each}
  <img class="greenery" src={bottom} alt="Wedding greenery" />
</section>

<style>
  section {
    display: grid;
    grid-gap: 0.75rem;
    grid-template-columns: 1fr;
  }
  
  .greenery {
    height: 4rem;
    width: 14rem !important;
    margin: 2rem auto;
  }

  .drink {
    min-width: 10rem;
    max-width: 70vw;
    background: linear-gradient(17deg, #dbfbdbcc, #8ffc8fdd);
    border-radius: 7px;
    padding: 1.5rem;
    backdrop-filter: blur(15px);

    display: grid;
    grid-gap: 0.4rem;
    grid-template-columns: 1fr 3fr;
    place-items: center;
    place-content: center;
    transition-duration: 0.2s;

    font-weight: 300;
  }

.cardIngredients{
  font-size: 0.8rem !important;
 }

  .drink:hover, .drink:active {
    cursor: pointer;
    transform: scale(1.02);
    filter: hue-rotate(56deg);
  }

  ul { 
    list-style: none;
    padding: 0.5rem 0;
    margin: 0;
    text-align: start;
    justify-self: start;
  }

  li {
    font-size: 1.2rem;
    line-height: 1.6rem;
    border-bottom: 1px solid #33333333;
    padding-bottom: 0.2rem;
  }

  h3 {
    font-family: 'Petit Formal Script', cursive;
    font-size: 2.5rem;
    font-weight: 100;
    padding: 0.5rem 0;
    margin: 0;
    grid-column: 1 / -1;
    padding: 1rem 0;
  }

  h4 {
    grid-column: 1 / -1;
    padding: 0.8rem 0;
    font-style: italic;
    font-size: 0.88rem;
  }

  img {
    height: 4rem;
    width: 4rem;
    justify-self: start;
    opacity: 44%;
  }
  
  svg {
    fill: pink;
  }
</style>