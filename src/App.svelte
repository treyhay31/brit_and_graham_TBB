<script>
  import bottom from './assets/bottom_greenery.png'
  import OnTap from './lib/OnTap.svelte'
  import OnTheMenu from './lib/OnTheMenu.svelte'
  import SeatingArrangement from './lib/SeatingArrangement.svelte'
</script>

<main>
  <h1>Now that the BIG stuff is taken care of...</h1>
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
    their very own Bridez Boiz.
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
  
  main {
    padding: 1em;
    margin: 4rem auto;
    color: var(--color-font);
    /*
    display: grid;
    place-items: center;
    place-content: center; 
    */
  }

  img {
    height: 4rem;
    width: 14rem;
    margin: 2rem auto;
  }
  
  img.flip {
    transform: rotate(180deg);
  }
  
  @font-face {
      font-family: 'Calinastiya';
      font-style: normal;
      font-weight: 400;
      src: url('/fonts/Calinastiya.ttf') format('truetype');
  }

  @font-face {
      font-family: 'Hello';
      font-style: normal;
      font-weight: 400;
      src: url('/fonts/Hello.ttf') format('truetype');
  }

  h1,h2,h3,h4,h5,h6 {
    font-family: 'Hello';
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
