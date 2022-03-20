<script>
// import beer from './../assets/beer.svg'
// import drink from './../assets/drink.svg'
import food from './../assets/food.svg'
// import wine from './../assets/wine.svg'
// import cocktail from './../assets/cocktail.svg'
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
      ingredients: ["Caribbean Jerk Chicken With Apple Chutney", "Cajun Shrimp With Andouille Sausage, mushrooms, green onions, red peppers, topped with Cream Sauce", "Cheese Grits","Mixed Vegetables in Garlic and Olive Oil"],
      image: food,
    },
  ]
   console.log(foods.length)
  console.log("hi")
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
    <ul>
      {#each f.ingredients as ingredient}
        <li>{ingredient}</li>
      {/each}
    </ul>
  </div>
  {/each}
</section>

<style>
  
  section {
    display: grid;
    grid-gap: 0.75rem;
    grid-template-columns: 1fr;
  }

  .drink {
    min-width: 10rem;
    background: linear-gradient(17deg, #5bca5b22, #8ffc8f55);
    border-radius: 7px;
    padding: 1.5rem;
    backdrop-filter: blur(15px);
    white-space: pre-line;
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
    font-family: 'DancingScript', cursive;
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