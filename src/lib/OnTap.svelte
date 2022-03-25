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
      ingredients: ["Budweiser", "Heineken", "Yuengling"],
      image: beer,
    }, 
    {
      owner: "Self Serve",
      title: "Essentials",
      ingredients: ["Water", "Iced Tea", "Coffee"],
      image: drink,
    }, 
    // {
    //   owner: "Food",
    //   title: "Appetizers On The Move",
    //   ingredients: ["Chicken Salad", "Pimento Cheese", "Ham & Cheese"],
    //   image: food,
    // }, 
    // {
    //   owner: "Food",
    //   title: "Appetizers On The Table",
    //   ingredients: ["Cheese", "Charcuterie", "Mixed Fruits"],
    //   image: food,
    // },
  ]
</script>

<section>
  {#each drinks as d}
  <div class="drink">
    <h3>{d.owner}</h3>
    <h4>{d.title}</h4>
    <img src={d.image} alt="beverage container" />
    <ul>
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
    background: linear-gradient(17deg, #5bca5b22, #8ffc8f55);
    border-radius: 7px;
    padding: 1.5rem;
    backdrop-filter: blur(15px);

    display: grid;
    grid-gap: 0.4rem;
    grid-template-columns: 1fr 1fr;
    place-items: center;
    place-content: center;
    transition-duration: 0.2s;
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
    justify-self: center;
  }

  li {
    line-height: 1.1rem;
    border-bottom: 1px solid #33333333;
  }

  h3 {
    font-family: 'Petit Formal Script', cursive;
    font-size: 2.5rem;
    font-weight: 100;
    line-height: 1rem;
    padding: 0.5rem 0;
    margin: 0;
    grid-column: 1 / -1;
    padding: 1rem 0;
  }

  h4 {
    grid-column: 1 / -1;
    line-height: 0.2rem;
    padding: 0.8rem 0;
    font-style: italic;
    font-size: 0.88rem;
  }

  img {
    height: 4rem;
    width: 4rem;
  }
  
  svg {
    fill: pink;
  }
</style>