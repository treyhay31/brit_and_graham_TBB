<script>
  const tables = [
    { table: 1, x: 20, y: 12 },
    { table: 2, x: 20, y: 24 },
    { table: 3, x: 20, y: 36 },
    { table: 4, x: 20, y: 48 },
    { table: 5, x: 20, y: 60 },
  ]

  let people = [
    { name: "Trey Hayden", table: 1 },
    { name: "Milo Hayden", table: 1 },
    { name: "Carissa Hayden", table: 1 },
    { name: "Harley Hayden", table: 1 },
    { name: "Christian Jones", table: 2 },
    { name: "Sara Jones", table: 2 },
    { name: "Lincoln Jones", table: 2 },
    { name: "Sylvie Jones", table: 2 },
  ]

  const sortName = () => {
    people.sort((personA, personB) => {
      if (personA.name > personB.name) return 1;
      if (personA.name < personB.name) return -1;
      return 0;
    })
  }

  const sortTable = () => {
    people.sort((personA, personB) => {
      if (personA.table > personB.table) return 1;
      if (personA.table < personB.table) return -1;
      return 0;
    })
  }

  let isTableShown = false;
  let peopleAtTheTable = []
  const showTable = (tableNumber) => {
    console.log(`TableNumber: ${tableNumber}`)
    isTableShown = true
    peopleAtTheTable = [
      ...people
        .filter(p => p.table === tableNumber)
        .map(p => p.name)
    ]
  }
  const removeTableView = () => {
    isTableShown = false
    peopleAtTheTable = []
  }
</script>

<section>
  <h3>Tables</h3>
  <svg viewBox="0 0 100 72" xmlns="http://www.w3.org/2000/svg">
    
    <circle on:click={() => showTable(1)} cx="20" cy="12" r="5" stroke-width="1" stroke="grey" />
    <text on:click={() => showTable(1)} x="20" y="12" text-anchor="middle" alignment-baseline="middle">1</text>
    <circle cx="20" cy="24" r="5" stroke-width="1" stroke="grey" />
    <text x="20" y="24" text-anchor="middle" alignment-baseline="middle">2</text>
    <circle cx="20" cy="36" r="5" stroke-width="1" stroke="grey" />
    <text x="20" y="36" text-anchor="middle" alignment-baseline="middle">3</text>
    <circle cx="20" cy="48" r="5" stroke-width="1" stroke="grey" />
    <text x="20" y="48" text-anchor="middle" alignment-baseline="middle">4</text>
    <circle cx="20" cy="60" r="5" stroke-width="1" stroke="grey" />
    <text x="20" y="60" text-anchor="middle" alignment-baseline="middle">5</text>
    
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

  {#if isTableShown}
    <div on:click={removeTableView} class="table-peeps">
      <ul> 
        {#each peopleAtTheTable as p} 
          <li>{p}</li>
        {/each}
      </ul>
    </div>
  {/if}
  <h3>Guest List</h3>
  <div class="guest-list"> 
    <h4 on:click={() => sortName()} class="name">Name</h4>
    <h4 on:click={() => sortTable()} class="table">Table</h4>
    {#each people as person}
      <p class="name">{person.name}</p>  
      <p class="table">{person.table}</p>  
    {/each}
  </div>
</section>

<style>
  section {
    display: grid;
  }
  h3 {
    font-family: 'Petit Formal Script', cursive;
    font-size: 2rem;
    margin: 2rem auto;
    color: var(--color-font);
  }
  svg {
    background-color: #1144ff11;
    width: 100%;
    height: 100%;
    border-radius: 6px;
  }
  circle {
    fill: var(--color-main);
    transition-duration: 1s;
  }
  circle:hover, circle:active {
    stroke-width: 0.2;
    cursor: pointer;
  }

  text:hover, text:active {
    cursor: pointer;
  }
  text {
    font-size: 0.3rem;
    font-family: 'Petit Formal Script', cursive;
    fill: white;
  }

  .table-peeps {
    position: fixed;
    width: 100vw;
    height: 100vh;
    top: 0;
    left: 0;
    background-color: #ab23abcc;
    backdrop-filter: blur(12px);
    display: grid;
    place-items: center;
    plae-content: center;
  }

  .table-peeps:hover {
    cursor: pointer;
  }

  .guest-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 0.3rem;
  }

  h4 {
    align-self: center;
    justify-self: center;
    font-size: 1.2rem;
    padding: 2rem;
  }

  h4:hover {
    cursor: pointer;
  }
  li {
    line-height: 3rem;
    color: #ffffff;
  }
  p, li {
    font-size: 1.5rem;
  }
  p.name {
    justify-self: end;
    padding-right: 1rem;
  }
  p.table {
    padding-left: 1rem;
    /* font-family: 'hello'; */
    font-style: italic;
    border-left: 1px solid #3f3f3f55;
  }

</style>