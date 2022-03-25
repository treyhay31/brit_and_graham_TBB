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
  <main>
    <nav>
      Hello
    </nav>
    <h1>
      <span>Brittany</span>
      <span>&</span> 
      <span>Graham</span>
    </h1>
    <p class="tidbit">(They're married)</p>
    <img src={bottom}  alt="Wedding greenery" />

    <MainNav/>
  
    <img class="flip" src={bottom} alt="Wedding greenery" />
      
    <img class="qr" src={qr} alt="QR code to this site" />

    <h2>The Boiz</h2>
    <p class="boiz">
      Where does something this unique and creative come from, you ask?
      <br />
      <br />
      Mostly from the bride and groom but the execution is provided by 
      their very own Bridez BoizZzZzZzZZzzz. 
      <br />
      <br />
      (Trey, Christian, and honorary mention, Bryn)
    </p>
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
    position: relative;
  }

  nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 120%;
    height: 10vh;
    background-color: purple;
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
  h1 span {
    display: block;
    text-align: center;
  }
  h2 {
    color: var(--color-main);
    font-size: 2.8rem;
    line-height: 1.5;
    max-width: 80vw;
    background-color: #ffffffdd;
    border-radius: 50px;
    padding: 1rem 5rem;
  }

  p {
    max-width: 60vw;
    margin: 1rem auto;
    line-height: 1.35;
    font-size: 1.5rem;
    text-align: center;
  }
  p.boiz {
    color: white;
    background: radial-gradient(circle, var(--color-main) 0%, var(--color-main) 90%, transparent 100%);
    border-radius: 33px;
    padding: 2rem;
    font-size: 0.8rem;
  }
  .tidbit {
    font-size: 0.7rem;
  }

  .mainNav {
    text-decoration: none !important;
  }
</style>
