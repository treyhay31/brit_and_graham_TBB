<script>
    import bottom from './../assets/bottom_greenery.png';
</script>

<section>
  <h1>
    <span>Pittsburgh</span>
    <span>Cookie</span>
    <span>Tradition</span>
  </h1>
  <p>
    The Pittsburgh cookie table, a western Pennsylvania tradition, 
    is said to have started during the Great Depression. 
    Like others worldwide, Pittsburghers struggled. Still life went on–couples married and 
    often celebrated with a reception after the wedding ceremony. 
    However, many Pittsburghers simply could not afford a wedding cake. 
    <br />
    <br />
    Instead, as legend goes, the mother of the bride, extended family, 
    and closest friends baked cookies from scratch with recipes passed down through several generations. 
    By the time Pittsburgh recovered from the Great Depression, 
    the cookie table had become a treasured tradition which the Jones family has continued.
    <br />
    <br />
    Please enjoy the deliciousness baked lovingly by the family and friends of Brittany and Graham. 
    To-go boxes are provided so you may take some of the tradition home with you!
  </p>
  
  <img class="greenery" src={bottom} alt="Wedding greenery" />
</section>

<style>
  section {
    display: grid;
    place-content: center;
    place-items: center;
  }
  img {
    height: 4rem;
    width: 14rem;
    margin: 2rem auto;
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


  h1,h2,h3,h4,h5,h6 {
    font-family: 'DancingScript', cursive;
    font-weight: 400;
    font-size: 2rem;
    text-align: center;
  }

  h1 {
    color: var(--color-main);
    font-size: 3rem !important;
    line-height: 1.5;
    background-color: #ffffffdd;
    border-radius: 50px;
    padding: 1rem 5rem;
/*     max-width: 80vw; */
  }
  h1 span {
    display: block;
    text-align: center;
  }
  h2 {
    color: var(--color-main);
    font-size: 2.2rem !important;
    line-height: 1.5;
    max-width: 80vw;
  }

  p {
    font-size: 1.3rem;
    text-align: left;
    font-family: "Arial", sans-serif;
    font-weight: 400 !important;
    margin-left: auto;
    margin-right: auto;
    max-width: 75%;
    padding: 1rem 0.3rem;
    text-align: center;
    background: radial-gradient(circle, white 0%, white 50%, #ffffff22 100%);
    border-radius: 3px;
  }

  h4 {
    grid-column: 1 / -1;
    line-height: 0.2rem;
    padding: 0.8rem 0;
    font-style: italic;
    font-size: 0.88rem;
  }
  
  svg {
    fill: pink;
  }
</style>