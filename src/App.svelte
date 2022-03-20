<script>
  import bottom from './assets/bottom_greenery.png'
  import top from './assets/greenery.png'
  import OnTap from './lib/OnTap.svelte'
  import OnTheMenu from './lib/OnTheMenu.svelte'
  import SeatingArrangement from './lib/SeatingArrangement.svelte'
  import './assets/DancingScript.woff'
</script>

<main>
  <h1>Brittany and Graham</h1>
  <p class="tidbit">(They're married)</p>

  <h2>What's on tap?</h2>
  <OnTap />
  <img src={bottom} alt="Wedding greenery" />

  <h2>What's on the menu?</h2>
  <OnTheMenu />
  <img src={bottom} alt="Wedding greenery" />

  <h2>Where do I sit?</h2>
  <SeatingArrangement />
  <img src={bottom} alt="Wedding greenery" />
  
  <h2>The Boiz</h2>
  <p>
    Where does something this unique and creative come from, you ask?
    Mostly from the bride and groom but the execution is provided by 
    their very own Bridez BoizZzZzZzZZzzz.
  </p>

  <img class="flip" src={bottom} alt="Wedding greenery" />

</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    --color-main: darkgreen;
    --color-font: #333333;
  }
  @font-face {
  font-family: "DancingScript";
  src: local("DancingScript"),
    url("./assets/DancingScript.woff") format("truetype");
  font-weight: normal;
    }
  
  main {
    padding: 5rem 5vw;
    color: var(--color-font);
    max-width: 90vw; 
    display: grid;
    justify-items: center;
  }

  img {
    height: 4rem;
    width: 14rem;
    margin: 2rem auto;
  }
   
  img.flip {
    transform: rotate(180deg);
  }

  h1,h2,h3,h4,h5,h6 {
    font-family: 'DancingScript', cursive;
    font-weight: 400;
    font-size: 2rem;
  }
  
  h1 {
    color: var(--color-main);
    font-size: 2.8rem;
    line-height: 1.5;
    max-width: 80vw;
  }

  h2 {
    color: var(--color-main);
    font-size: 2.8rem;
    line-height: 1.5;
    max-width: 80vw;
  }

  p {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
  }

  .tidbit {
    font-size: 0.7rem;
  }

  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }

    p {
      max-width: none;
    }
  }
</style>
