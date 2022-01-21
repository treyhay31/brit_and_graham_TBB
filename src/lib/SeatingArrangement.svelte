<script>
  const tables = [
    /*1*/ ["AB", "CD", "EF", "GH"], 
    /*2*/ ["IJ", "KL", "MN", "NO"], 
    /*3*/ ["PQ", "RS", "TU", "VW"], 
    /*4*/ ["XY", "ZZ", "00", "11"], 
    /*5*/ ["22", "33", "44", "55"], 
    /*6*/ ["66", "77", "88", "99"], 
    /*7*/ ["12", "34", "56", "78"], 
    /*8*/ ["90", "GG", "QQ", "VV"], 
  ]
  const sortName = () => {
    console.log("sorting guests by name...")
  }

  const sortTable = () => {
    console.log("sorting guests by table...")
  }
</script>

<section>
  <h3>Tables</h3>
  <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
    
    <circle cx="20" cy="12" r="5" stroke-width="1" stroke="grey" />
    <text x="19" y="13" text-anchor="middle" alignment-baseline="middle">1</text>
    <circle cx="20" cy="24" r="5" stroke-width="1" stroke="grey" />
    <text x="19" y="25" text-anchor="middle" alignment-baseline="middle">2</text>
    <circle cx="20" cy="36" r="5" stroke-width="1" stroke="grey" />
    <text x="19" y="37" text-anchor="middle" alignment-baseline="middle">3</text>
    <circle cx="20" cy="48" r="5" stroke-width="1" stroke="grey" />
    <text x="19" y="49" text-anchor="middle" alignment-baseline="middle">4</text>
    <circle cx="20" cy="60" r="5" stroke-width="1" stroke="grey" />
    <text x="19" y="61" text-anchor="middle" alignment-baseline="middle">5</text>
    
    <circle cx="40" cy="12" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="40" y="12" text-anchor="middle" alignment-baseline="middle">6</text>
    <circle cx="40" cy="24" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="40" y="24" text-anchor="middle" alignment-baseline="middle">7</text>
    <circle cx="40" cy="36" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="40" y="36" text-anchor="middle" alignment-baseline="middle">8</text>
    <circle cx="40" cy="48" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="40" y="48" text-anchor="middle" alignment-baseline="middle">9</text>
    <circle cx="40" cy="60" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="40" y="60" text-anchor="middle" alignment-baseline="middle">10</text>

    <circle cx="60" cy="12" r="5" stroke-width="1" stroke="grey" />
    <text x="60" y="12" text-anchor="middle" alignment-baseline="middle">11</text>
    <circle cx="60" cy="24" r="5" stroke-width="1" stroke="grey" />
    <text x="60" y="24" text-anchor="middle" alignment-baseline="middle">12</text>
    <circle cx="60" cy="36" r="5" stroke-width="1" stroke="grey" />
    <text x="60" y="36" text-anchor="middle" alignment-baseline="middle">13</text>
    <circle cx="60" cy="48" r="5" stroke-width="1" stroke="grey" />
    <text x="60" y="48" text-anchor="middle" alignment-baseline="middle">14</text>
    <circle cx="60" cy="60" r="5" stroke-width="1" stroke="grey" />
    <text x="60" y="60" text-anchor="middle" alignment-baseline="middle">15</text>

    <circle cx="80" cy="12" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="80" y="12" text-anchor="middle" alignment-baseline="middle">16</text>
    <circle cx="80" cy="24" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="80" y="24" text-anchor="middle" alignment-baseline="middle">17</text>
    <circle cx="80" cy="36" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="80" y="36" text-anchor="middle" alignment-baseline="middle">18</text>
    <circle cx="80" cy="48" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="80" y="48" text-anchor="middle" alignment-baseline="middle">19</text>
    <circle cx="80" cy="60" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="80" y="60" text-anchor="middle" alignment-baseline="middle">20</text>
  </svg>
  <h3>Guest List</h3>
  <div> 
    <h4 on:click={sortName} class="name">Name</h4>
    <h4 on:click={sortTable} class="table">Table</h4>
    {#each tables as table, i}
      {#each table as person}
        <p class="name">{person}</p>  
        <p class="table">{i}</p>  
      {/each}
    {/each}
  </div>
</section>

<style>
  h3 {
    font-family: 'hello';
    font-size: 2rem;
    margin: 1rem auto;
    color: var(--color-font);
  }
  svg {
    background-color: #1144ff11;
  }
  circle {
    transition-duration: 1s;
  }
  circle:hover, circle:active {
    r: 3;
    stroke-width: 0.2;
    cursor: pointer;
  }

  text:hover, text:active {
    cursor: pointer;
  }
  text {
    font-size: 0.2rem;
    fill: red;
  }

  div {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 0.3rem;
    max-width: 25vw;
  }

  h4 {
    align-self: center;
    justify-self: center;
    font-size: 1.2rem;
    padding: 1rem;
  }

  p {
    font-size: 1.5rem;
  }
  p.name {
    justify-self: end;
  }
  p.table {
    padding-left: 1rem;
    /* font-family: 'hello'; */
    font-style: italic;
  }

</style>