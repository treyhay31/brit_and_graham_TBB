<script>
  import bottom from './assets/bottom_greenery.png';
  import qr from './assets/brit_and_graham_qr.png';
  import top from './assets/greenery.png';
  import MainNav from './lib/MainNav.svelte';
  import OnTap from './lib/OnTap.svelte';
  import OnTheMenu from './lib/OnTheMenu.svelte';
  import SeatingArrangement from './lib/SeatingArrangement.svelte';
  import './assets/DancingScript.woff';
  import { Router, Route, Link } from "svelte-navigator";
</script>

<Router>

  <nav>
    <Link to="/MainNav">Home</Link>
    <Link to="/OnTap">On Tap</Link>
    <Link to="/OnTheMenu">On The Menu</Link>
    <Link to="/SeatingArrangement">Seating Arrangement</Link>
  </nav>
  
  <main>
    <h1>Brittany and Graham</h1>
    <p class="tidbit">(They're married)</p>
    <img src={bottom}  alt="Wedding greenery" />

    <MainNav/>
  
<!--     <h2>What's on tap?</h2>
    <OnTap />
    <img src={bottom} alt="Wedding greenery" />
  
    <h2>What's on the menu?</h2>
    <OnTheMenu />
    <img src={bottom} alt="Wedding greenery" />
  
    <h2>Where do I sit?</h2>
    <SeatingArrangement />
    <img src={bottom} alt="Wedding greenery" /> -->
    
    <img class="flip" src={bottom} alt="Wedding greenery" />
    <h2>The Boiz</h2>
    <p>
      Where does something this unique and creative come from, you ask?
      Mostly from the bride and groom but the execution is provided by 
      their very own Bridez BoizZzZzZzZZzzz. (Trey, Christian and honorary mention       Bryn)
    </p>
  
    <img class="qr" src={qr} alt="QR code to this site" />

  </main>
</Router>

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
  img.qr {
    width: 30rem;
    height: 30rem;
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
    background-color: #ffffffdd;
    border-radius: 50px;
    padding: 1rem 5rem;
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

  .mainNav {
    text-decoration: none !important;
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
