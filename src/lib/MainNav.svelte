<script>
  import { Router, Route, Link } from "svelte-navigator";
  import OnTap from "./OnTap.svelte";
  import OnTheMenu from "./OnTheMenu.svelte";
  import SeatingArrangement from "./SeatingArrangement.svelte";
  import Cookie from "./Cookie.svelte";
  import CocktailIcon from './nav/CocktailIcon.svelte'
  import CakeIcon from './nav/CakeIcon.svelte'
  import SeatingIcon from './nav/SeatingIcon.svelte'
  import CookieIcon from './nav/CookieIcon.svelte'
  import '../assets/DancingScript.woff';
</script>

<nav>
  <Link class="link" to="/OnTap">
    <CocktailIcon fill="darkgreen" />
  </Link>
  <Link class="link" to="/OnTheMenu">
    <CakeIcon fill="darkgreen" />
  </Link>
  <Link class="link" to="/SeatingArrangement">
    <SeatingIcon fill="darkgreen" />
  </Link>
  <Link class="link" to="/Cookie">
    <CookieIcon fill="darkgreen" />
  </Link>
</nav>

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
  nav {
    z-index: 1000;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 10vh;
    background: linear-gradient(180deg, #d0bcc0, #fdf8f9);
    color: var(--color-font);
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    place-items: center;
    place-content: center;
  }
  .link > :global(a) {
    text-decoration: none;
  }
  
  :global(a) {
    background-color: transparent;
  }
  
  svg {
    height: 5vh;
    width: auto;
  }
</style>
