<script>
  import food from './../assets/food.svg'
  import bottom from './../assets/bottom_greenery.png';

  let count = 0
  const increment = () => {
    count += 1
  }

  // console.log(dancing)
  //  console.log(dancing)
  // console.log("hi")
  const foods = [
    {
      owner: "Appetizers",
      title: "On The Move",
      ingredients: ["Chicken Salad", "Pimento Cheese", "Ham & Cheese"],
      image: food,
    }, 
    {
      owner: "Appetizers",
      title: "On The Table",
      ingredients: ["Cheese", "Charcuterie", "Mixed Fruits"],
      image: food,
    },
    {
      owner: "Main Meal",
      title: "Plated",
      ingredients: ["Mixed Greens and Veggies", "Goat Cheese", "Balsamic Dressing", "Delicate Dinner Rolls with Butter"],
      image: food,
    },
    {
      owner: "Main Meal",
      title: "Buffet",
      ingredients: ["Caribbean Jerk Chicken", "Cajun Shrimp With Andouille Sausage", "Cheese Grits","Mixed Vegetables in Garlic and Olive Oil"],
      image: food,
    },
  ]
</script>



<!-- <button on:click={increment}>
  Meals: {count}
</button> -->

<section>
    {#each foods as f}
  <div class="drink">
    <h3>{f.owner}</h3>
    <h4>{f.title}</h4>
    <img src={f.image} alt="beverage container" />
    <ul class="cardIngredients">
      {#each f.ingredients as ingredient}
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
    line-height: 1.6rem;
    border-bottom: 1px solid #33333333;
    padding-bottom: 0.2rem;
    font-size: 1.2rem;
  }

  .greenery {
    height: 4rem;
    width: 14rem !important;
    margin: 2rem auto;
  }
  
  h3 {
    font-family: 'DancingScript', cursive;
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