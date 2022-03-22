<script>
  import { Router, Route, Link } from "svelte-navigator";
  import OnTap from "./OnTap.svelte";
  import OnTheMenu from "./OnTheMenu.svelte";
  import SeatingArrangement from "./SeatingArrangement.svelte";
  import Cookie from "./Cookie.svelte";
  import '../assets/DancingScript.woff';
</script>

<section>
  <Route path ="/OnTap">
     <OnTap />
  </Route>    
  <Route path ="/OnTheMenu">
    <OnTheMenu />
  </Route>  
  <Route path ="/SeatingArrangement">
    <SeatingArrangement />
  </Route>
    <Route path ="/Cookie">
      <Cookie />
  </Route>
  <Route path ="/"></Route>

  <h2><Link class="mainNav" to="/OnTap">On Tap</Link></h2>
  <h2><Link class="mainNav" to="/OnTheMenu">On The Menu</Link></h2>
  <h2><Link class="mainNav" to="/SeatingArrangement">Seating Arrangement</Link>  </h2>
  <h2><Link class="mainNav" to="/Cookie">Pittsburg Cookie Tradition</Link></h2>

</section>

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
  
  section {
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
    text-align: center;
    text-decoration: none !important; 
  }

  p {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
  }

  .tidbit {
    font-size: 0.7rem;
  }

/*   .MainNav > :global(a) {
      text-decoration: none;
    }    
    :global(a) {
        ...
    } */

  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }

    p {
      max-width: none;
    }
  }
</style>
