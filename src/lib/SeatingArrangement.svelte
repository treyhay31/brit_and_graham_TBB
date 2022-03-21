<script>
  import bottom from './../assets/bottom_greenery.png';
  import parsedPeople from './data.json';
  
  let input = ""

  const filteredPeople = (input) => {
    if (input === null || 
        input === undefined || 
        input === "") {
      return parsedPeople
    }
    const results = parsedPeople.filter(p => 
      p.name.toLowerCase().startsWith(input) || 
      p.table.toLowerCase().startsWith(input))

    console.log(`results with input: ${input}`, results)

    return results
  }
  
  const sortName = () => {
    parsedPeople.sort((personA, personB) => {
      if (personA.name > personB.name) return 1;
      if (personA.name < personB.name) return -1;
      return 0;
    })
  }

  const sortTable = () => {
    parsedPeople.sort((personA, personB) => {
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
    <circle cx="50" cy="12" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="50" y="12" text-anchor="middle" alignment-baseline="middle">BG</text>
    
    <circle cx="30" cy="22" r="4" stroke-width="1" stroke="grey" />
    <text x="30" y="22" text-anchor="middle" alignment-baseline="middle">1</text>
    <circle cx="22" cy="15" r="4" stroke-width="1" stroke="grey" />
    <text x="22" y="15" text-anchor="middle" alignment-baseline="middle">2</text>
    <circle cx="14" cy="22" r="4" stroke-width="1" stroke="grey" />
    <text x="14" y="22" text-anchor="middle" alignment-baseline="middle">7</text>
    <circle cx="22" cy="29" r="4" stroke-width="1" stroke="grey" />
    <text x="22" y="29" text-anchor="middle" alignment-baseline="middle">4</text>
    
    <circle cx="80" cy="15" r="4" stroke-width="1" stroke="darkgrey" />
    <text x="80" y="15" text-anchor="middle" alignment-baseline="middle">3</text>
    <circle cx="72" cy="22" r="4" stroke-width="1" stroke="darkgrey" />
    <text x="72" y="22" text-anchor="middle" alignment-baseline="middle">6</text>
    <circle cx="85" cy="24" r="4" stroke-width="1" stroke="darkgrey" />
    <text x="85" y="24" text-anchor="middle" alignment-baseline="middle">5</text>

    <circle cx="70" cy="36" r="4" stroke-width="1" stroke="darkgrey" />
    <text x="70" y="36" text-anchor="middle" alignment-baseline="middle">8</text>
    <circle cx="83" cy="36" r="4" stroke-width="1" stroke="grey" />
    <text x="83" y="36" text-anchor="middle" alignment-baseline="middle">11</text>
      
    <circle cx="22" cy="50" r="4" stroke-width="1" stroke="grey" />
    <text x="22" y="50" text-anchor="middle" alignment-baseline="middle">12</text>
    <circle cx="18" cy="64" r="4" stroke-width="1" stroke="grey" />
    <text x="18" y="64" text-anchor="middle" alignment-baseline="middle">13</text>
    <circle cx="30" cy="59" r="4" stroke-width="1" stroke="grey" />
    <text x="30" y="59" text-anchor="middle" alignment-baseline="middle">15</text>
      
    <circle cx="78" cy="50" r="4" stroke-width="1" stroke="grey" />
    <text x="78" y="50" text-anchor="middle" alignment-baseline="middle">9</text>
    <circle cx="70" cy="59" r="4" stroke-width="1" stroke="grey" />
    <text x="70" y="59" text-anchor="middle" alignment-baseline="middle">10</text>
    <circle cx="82" cy="62" r="4" stroke-width="1" stroke="grey" />
    <text x="82" y="62" text-anchor="middle" alignment-baseline="middle">14</text>
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
  <input class="your-name" type="text" bind:value={input}>
  <div class="guest-list"> 
    <h4 on:click={() => sortName()} class="name">Name</h4>
    <h4 on:click={() => sortTable()} class="table">Table</h4>
    <h4>#</h4>
    {#each filteredPeople(input) as person}
      <p class="p-name">{person.name}</p>  
      <p class="p-table">{person.table}</p>  
      <p class="p-table-no">{person.tableNumber}</p>
    {/each}
  </div>
  <img class="greenery" src={bottom} alt="Wedding greenery" />
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

  .greenery {
    height: 4rem;
    width: 14rem !important;
    margin: 2rem auto;
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
  .your-name {
    font-size: 2rem;
    
  }
  .guest-list {
    display: grid;
    grid-template-columns: 5fr 5fr 1fr;
    grid-gap: 0.3rem;
    place-items: center;
    background: #eeeeee99;
    backdrop-filter: blur(12px);
    padding: 1.5rem;
  }

  h4 {
    align-self: center;
    justify-self: center;
    font-size: 1.9rem;
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
  .p-name {
    justify-self: start;
  }
  .p-table-no {
    justify-self: end;
  }
  

</style>