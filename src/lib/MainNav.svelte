<script>
  import { Router, Route, Link } from "svelte-navigator";
  import OnTap from "./OnTap.svelte";
  import OnTheMenu from "./OnTheMenu.svelte";
  import SeatingArrangement from "./SeatingArrangement.svelte";
  import Cookie from "./Cookie.svelte";
  import drink from '../assets/cocktail.svg';
  import food from '../assets/cake.svg';
  import seating from '../assets/seating.svg';
  import cookie from '../assets/cookie.svg';
  import '../assets/DancingScript.woff';
</script>

<nav>
  <Link class="mainNav link drink" to="/OnTap">
    <img src={drink} alt="on tap" />
  </Link>
  <Link class="mainNav link food" to="/OnTheMenu">
    <img src={food} alt="on the menu" />
  </Link>
  <Link class="mainNav link food" to="/SeatingArrangement">
    <img src={seating} alt="seating arrangement" />
  </Link>
  <Link class="mainNav link food" to="/Cookie">
    <img src={cookie} alt="pittsburg cookie tradition" />
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

  img {
    height: 5vh;
    width: auto;
  }
</style>
