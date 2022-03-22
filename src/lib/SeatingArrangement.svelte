<script>
  import { fade, fly } from 'svelte/transition';
  import bottom from './../assets/bottom_greenery.png';
  import parsedPeople from './data.json';

  const fillArray = (val, num) => {
    let a = []
    for(var i = 0; i < num; i++){
        a.push(val)
    }
    return a
  }
  let selected = ""
  let input = ""
  let tableStrokes = fillArray("grey", 16)
  let tableStrokeWidths = fillArray(1, 16)
  console.log("tables", tableStrokes, tableStrokeWidths)
  const filteredPeople = (input) => {
    if (input === null || 
        input === undefined || 
        input === "") {
      return parsedPeople
    }
    
    if (isNaN(input)) {
      const i = input.toLowerCase()
      return parsedPeople.filter(p => 
        p.first.toLowerCase().startsWith(i) || 
        p.last.toLowerCase().startsWith(i) ||
        p.table.toLowerCase().startsWith(i))
    }

    return parsedPeople.filter(p => p.tableNumber === `${input}`)
  }

  const highlightTable = (person) => {
    tableStrokes = fillArray("grey", 16)
    tableStrokes[person.tableNumber] = "#92fe81"
    tableStrokeWidths = fillArray(1, 16)
    tableStrokeWidths[person.tableNumber] = 2
    
    selected = `${person.first} ${person.last} @ ${person.table} (${person.tableNumber})`
    input = ""
  }
  $: hasInput = () => input !== ""
</script>

<section>
  <h3>Where am I sitting?</h3>
  <h4>{selected}</h4>
  <input placeholder="Name..." class="your-name" type="text" bind:value={input}>
  {#if hasInput()}
    <ul in:fade out:fade class="drop-down">
      {#each filteredPeople(input) as person, index}
        <li in:fly="{{ y: 200, duration: 1000, delay: (0 + 100 * index) }}" out:fade on:click="{() => highlightTable(person)}">
  				{person.name}
  			</li>
      {/each}
  	</ul>
  {/if}
  <svg viewBox="0 0 100 72" xmlns="http://www.w3.org/2000/svg">
    <text id="selected-text" y="4" x="50%" text-anchor="middle" alignment-baseline="middle">{selected}</text>
    <circle cx="50" cy="12" r="5" stroke-width="1" stroke="darkgrey" />
    <text x="50" y="12" text-anchor="middle" alignment-baseline="middle">BG</text>
    
    <circle cx="30" cy="22" r="4" stroke-width="{tableStrokeWidths[1]}" stroke="{tableStrokes[1]}" />
    <text x="30" y="22" text-anchor="middle" alignment-baseline="middle">1</text>
    <circle cx="22" cy="15" r="4" stroke-width="{tableStrokeWidths[2]}" stroke="{tableStrokes[2]}" />
    <text x="22" y="15" text-anchor="middle" alignment-baseline="middle">2</text>
    <circle cx="14" cy="22" r="4" stroke-width="{tableStrokeWidths[7]}" stroke="{tableStrokes[7]}" />
    <text x="14" y="22" text-anchor="middle" alignment-baseline="middle">7</text>
    <circle cx="22" cy="29" r="4" stroke-width="{tableStrokeWidths[4]}" stroke="{tableStrokes[4]}" />
    <text x="22" y="29" text-anchor="middle" alignment-baseline="middle">4</text>
    
    <circle cx="80" cy="15" r="4" stroke-width="{tableStrokeWidths[3]}" stroke="{tableStrokes[3]}" />
    <text x="80" y="15" text-anchor="middle" alignment-baseline="middle">3</text>
    <circle cx="72" cy="22" r="4" stroke-width="{tableStrokeWidths[6]}" stroke="{tableStrokes[6]}" />
    <text x="72" y="22" text-anchor="middle" alignment-baseline="middle">6</text>
    <circle cx="85" cy="24" r="4" stroke-width="{tableStrokeWidths[5]}" stroke="{tableStrokes[5]}" />
    <text x="85" y="24" text-anchor="middle" alignment-baseline="middle">5</text>

    <circle cx="70" cy="36" r="4" stroke-width="{tableStrokeWidths[8]}" stroke="{tableStrokes[8]}" />
    <text x="70" y="36" text-anchor="middle" alignment-baseline="middle">8</text>
    <circle cx="83" cy="36" r="4" stroke-width="{tableStrokeWidths[11]}" stroke="{tableStrokes[11]}" />
    <text x="83" y="36" text-anchor="middle" alignment-baseline="middle">11</text>
      
    <circle cx="22" cy="50" r="4" stroke-width="{tableStrokeWidths[12]}" stroke="{tableStrokes[12]}" />
    <text x="22" y="50" text-anchor="middle" alignment-baseline="middle">12</text>
    <circle cx="18" cy="64" r="4" stroke-width="{tableStrokeWidths[13]}" stroke="{tableStrokes[13]}" />
    <text x="18" y="64" text-anchor="middle" alignment-baseline="middle">13</text>
    <circle cx="30" cy="59" r="4" stroke-width="{tableStrokeWidths[15]}" stroke="{tableStrokes[15]}" />
    <text x="30" y="59" text-anchor="middle" alignment-baseline="middle">15</text>
      
    <circle cx="78" cy="50" r="4" stroke-width="{tableStrokeWidths[9]}" stroke="{tableStrokes[9]}" />
    <text x="78" y="50" text-anchor="middle" alignment-baseline="middle">9</text>
    <circle cx="70" cy="59" r="4" stroke-width="{tableStrokeWidths[10]}" stroke="{tableStrokes[10]}" />
    <text x="70" y="59" text-anchor="middle" alignment-baseline="middle">10</text>
    <circle cx="82" cy="62" r="4" stroke-width="{tableStrokeWidths[14]}" stroke="{tableStrokes[14]}" />
    <text x="82" y="62" text-anchor="middle" alignment-baseline="middle">14</text>
  </svg>

  <h3>Guest List</h3>
  <div class="guest-list"> 
    <h4 class="name">Name</h4>
    <h4 class="table">Table</h4>
    <h4>#</h4>    
    {#each filteredPeople(input) as person}
      <p on:click={() => highlightTable(person)} class="p-name">{person.name}</p>  
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
    color: var(--color-main);
    background-color: #ffffffdd;
    border-radius: 50px;
    padding: 1rem 2rem;
    max-width: 80vw;
  }

  ul.drop-down {
    color: var(--color-main);
    background-color: #efefefbb;
  }
  ul.drop-down li {
    padding-left: 1rem;
    font-size: 2rem;
    color: var(--color-main);
    background-color: #efefefbb;
    border: 1px solid #2f5d0233;
  }
  #selected-text {
    fill: var(--color-main);
  }
  
  svg {
    background-color: #bbbbbbcc;
    width: 100%;
    height: 100%;
    border-radius: 6px;
    transition: all 0.4s;
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
    font-size: 1.4rem;
    font-style: italic;
    color: var(--color-main);
    border-radius: 50px;
    padding: 1rem 2rem;
    margin: 1rem 1rem;
    border: 1px solid var(--color-main);
    outline: 1px solid var(--color-main);
    transition: all 0.8s;
  }
  .your-name:active, 
  .your-name:focus {
    box-shadow:
			3px -3px 20px var(--color-main), 
			-3px 3px 20px #1beabd88;
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
    color: var(--color-main);
    align-self: center;
    justify-self: center;
    font-size: 1.9rem;
    padding: 2rem;
    background-color: #ffffffdd;
    border-radius: 50px;
    padding: 1rem 2rem;
    max-width: 80vw;
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
  
  @media screen and (max-width: 600px) {
    h3,h4 { font-size: 1.5rem; }
    .p-name,.p-table,.p-table-no {
      font-size: 1rem;
    }
  }
  @media screen and (max-width: 400px) {
    h3,h4 { font-size: 1.2rem; }
    .p-name,.p-table,.p-table-no {
      font-size: 0.8rem;
    }
  }
</style>