<script>
  import bottom from './../assets/bottom_greenery.png';
  let input = ""
  const tables = [
    { table: 1, x: 20, y: 12 },
    { table: 2, x: 20, y: 24 },
    { table: 3, x: 20, y: 36 },
    { table: 4, x: 20, y: 48 },
    { table: 5, x: 20, y: 60 },
  ]

  let people = [
    `Hayden, Carissa|||Skyline|||1`,
    `Hayden, Trey|||Skyline|||1`,
    `Holland, Corinne|||Skyline|||1`,
    `Holland, David|||Skyline|||1`,
    `Jones, Christian|||Skyline|||1`,
    `Jones, Sara|||Skyline|||1`,
    `Kaufman, Bryn|||Skyline|||1`,
    `Kaufman, Kendall|||Skyline|||1`,
    `Sigala, Daniel|||Skyline|||1`,
    `Sigala, Kelsey|||Skyline|||1`,
    `Sommovigo, Rose|||Skyline|||1`,
    `Angel, Riley|||RA Bistro|||2`,
    `Bishop, Hilary|||RA Bistro|||2`,
    `Bowden, Jesse|||RA Bistro|||2`,
    `Coryea, Hilary|||RA Bistro|||2`,
    `Ellis, Katie|||RA Bistro|||2`,
    `Evans, Caroline|||RA Bistro|||2`,
    `Evans, Nick|||RA Bistro|||2`,
    `Evans, Stuart|||RA Bistro|||2`,
    `Keilman, Tyler|||RA Bistro|||2`,
    `Lyons, Stacy|||RA Bistro|||2`,
    `Ruehle, Ben|||RA Bistro|||2`,
    `Braun, Kathryn|||Reserve|||3`,
    `Evans, Charlie|||Reserve|||3`,
    `Evans, Judy|||Reserve|||3`,
    `French, Charlotte|||Reserve|||3`,
    `French, Scott|||Reserve|||3`,
    `Gorry, Anne|||Reserve|||3`,
    `Gorry, James|||Reserve|||3`,
    `Gorry, Scott|||Reserve|||3`,
    `Jones, Dan|||Reserve|||3`,
    `Jones, Dawn|||Reserve|||3`,
    `Carpenter, Joshua|||Apocalypse|||4`,
    `Carpenter, Katelyn|||Apocalypse|||4`,
    `Jones, Dennis|||Apocalypse|||4`,
    `Jones, Donald|||Apocalypse|||4`,
    `Jones, Geniene|||Apocalypse|||4`,
    `Jones, Lori|||Apocalypse|||4`,
    `Linski, Donna|||Apocalypse|||4`,
    `Linski, Kyle|||Apocalypse|||4`,
    `Linski, Liz|||Apocalypse|||4`,
    `Linski, Tom|||Apocalypse|||4`,
    `Robison, Darlene|||Apocalypse|||4`,
    `Johnson, Eddie|||Shoemakers|||5`,
    `Johnson, Eric|||Shoemakers|||5`,
    `Johnson, Jammie|||Shoemakers|||5`,
    `Johnson, Nancy|||Shoemakers|||5`,
    `Meador, Andy|||Shoemakers|||5`,
    `Meador, Sarah|||Shoemakers|||5`,
    `Smoot, Gary|||Shoemakers|||5`,
    `Smoot, Laura|||Shoemakers|||5`,
    `Smoot, Sam|||Shoemakers|||5`,
    `Blauw, Elizabeth|||El Jefe|||6`,
    `Blauw, Jennifer|||El Jefe|||6`,
    `Blauw, Matthew|||El Jefe|||6`,
    `Blauw, Russell|||El Jefe|||6`,
    `French, Alexander|||El Jefe|||6`,
    `French, Arthur|||El Jefe|||6`,
    `French, Candace|||El Jefe|||6`,
    `French, Jennifer|||El Jefe|||6`,
    `French, Kelly|||El Jefe|||6`,
    `French, Matthew|||El Jefe|||6`,
    `Bobic, Daniel|||White Hart|||7`,
    `Bobic, Rachel|||White Hart|||7`,
    `Hromika, Shannon|||White Hart|||7`,
    `Jones, Alexis|||White Hart|||7`,
    `Jones, Allen|||White Hart|||7`,
    `Jones, Carrie|||White Hart|||7`,
    `Jones, Kyle|||White Hart|||7`,
    `Kaufman, Jared|||White Hart|||7`,
    `Kaufman, Kristi|||White Hart|||7`,
    `Lockhart, Jacob|||White Hart|||7`,
    `Saunders, Bre|||White Hart|||7`,
    `Hedrick, Joe|||Mission House|||8`,
    `Hedrick, Katie|||Mission House|||8`,
    `Hedrick, Stephanie|||Mission House|||8`,
    `Hott, Chris|||Mission House|||8`,
    `Hott, Sarah|||Mission House|||8`,
    `Hrach, Dan|||Mission House|||8`,
    `Hrach, Jan|||Mission House|||8`,
    `Long, Shannon|||Mission House|||8`,
    `Long, Thomas|||Mission House|||8`,
    `Schneider, Becky|||Mission House|||8`,
    `Schneider, Paul|||Mission House|||8`,
    `Deckard, Mary|||Texas Tavern|||9`,
    `Kagey, Brian|||Texas Tavern|||9`,
    `Kagey, Dave|||Texas Tavern|||9`,
    `Kagey, Jane|||Texas Tavern|||9`,
    `Kagey, Tara|||Texas Tavern|||9`,
    `Shelor, Belva|||Texas Tavern|||9`,
    `Stevens, Ashley|||Texas Tavern|||9`,
    `Stevens, Bucky|||Texas Tavern|||9`,
    `Twery, Randy|||Texas Tavern|||9`,
    `Twery, Seth|||Texas Tavern|||9`,
    `Winters, Esther|||Texas Tavern|||9`,
    `Bochonok, Debby|||Water Dog|||10`,
    `Bochonok, Jeff|||Water Dog|||10`,
    `Bonacquisti, Brian|||Water Dog|||10`,
    `Bonacquisti, Susan|||Water Dog|||10`,
    `Houston, Leola|||Water Dog|||10`,
    `Houston, Randolph|||Water Dog|||10`,
    `Morrison, Diane|||Water Dog|||10`,
    `Morrison, Jim|||Water Dog|||10`,
    `Potente, Joe|||Water Dog|||10`,
    `Potente, Liz|||Water Dog|||10`,
    `Berthoud, Emily|||Starr Hill|||11`,
    `Craig, Brooke|||Starr Hill|||11`,
    `Craig, Michael|||Starr Hill|||11`,
    `Curtis, Ethan|||Starr Hill|||11`,
    `Curtis, Mandy|||Starr Hill|||11`,
    `Geneva, Steve|||Starr Hill|||11`,
    `Minard, Brittany|||Starr Hill|||11`,
    `Minard, Philip|||Starr Hill|||11`,
    `Waltz, Michael|||Starr Hill|||11`,
    `Bell, Ethan|||Mrs. Joy's|||12`,
    `Bell, Katie|||Mrs. Joy's|||12`,
    `Davis, Cidney|||Mrs. Joy's|||12`,
    `Fields, Julie|||Mrs. Joy's|||12`,
    `Fields, Ryan|||Mrs. Joy's|||12`,
    `Greene, Cheyenne|||Mrs. Joy's|||12`,
    `Jensen, Brandi|||Mrs. Joy's|||12`,
    `McAllister, Caleb|||Mrs. Joy's|||12`,
    `McAllister, Rachel|||Mrs. Joy's|||12`,
    `Pearce, Lauren|||Mrs. Joy's|||12`,
    `Smith, Twon|||Mrs. Joy's|||12`,
    `Gallant, Matthew|||Aji Ramen|||13`,
    `Gallant, Morgan|||Aji Ramen|||13`,
    `Gutierrez, Brian|||Aji Ramen|||13`,
    `Mohring, Kelsey|||Aji Ramen|||13`,
    `O'Neil, Michael|||Aji Ramen|||13`,
    `Ogden, Michelle|||Aji Ramen|||13`,
    `Ross, Brian|||Aji Ramen|||13`,
    `Ross, Lauren|||Aji Ramen|||13`,
    `Wenger, Blake|||Aji Ramen|||13`,
    `Wenger, Kristin|||Aji Ramen|||13`,
    `Austin, Lauren|||The Cavalier|||14`,
    `Austin, Ryan|||The Cavalier|||14`,
    `Cockrell, Daniel|||The Cavalier|||14`,
    `Cockrell, Gabbie|||The Cavalier|||14`,
    `Gillispie, Nathan|||The Cavalier|||14`,
    `Gillispie, Sarah|||The Cavalier|||14`,
    `Mullen, Josh|||The Cavalier|||14`,
    `Mullen, Loren|||The Cavalier|||14`,
    `Warwick, Jennifer|||The Cavalier|||14`,
    `Warwick, Matthew|||The Cavalier|||14`,
    `Curtis, Holly|||Farm Basket|||15`,
    `Curtis, Tyler|||Farm Basket|||15`,
    `McGunigle, Meg|||Farm Basket|||15`,
    `Melone, Alyssa|||Farm Basket|||15`,
    `Melone, Jacob|||Farm Basket|||15`,
    `Morton, Brittney|||Farm Basket|||15`,
    `Morton, Zach|||Farm Basket|||15`,
    `Reinwald, Kelly|||Farm Basket|||15`,
    `Russell, Katelyn|||Farm Basket|||15`,
    `Tyer, Natalie|||Farm Basket|||15`,
  ].map(row => {
    const [name, table, tableNumber] = row.split('|||') 
    const [last, first] = name.split(", ")
    return {
      name,
      last, 
      first,
      table,
      tableNumber
    }
  })

  const parsedPeople = [
  {
    "name": "Hayden, Carissa",
    "last": "Hayden",
    "first": "Carissa",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Hayden, Trey",
    "last": "Hayden",
    "first": "Trey",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Holland, Corinne",
    "last": "Holland",
    "first": "Corinne",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Holland, David",
    "last": "Holland",
    "first": "David",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Jones, Christian",
    "last": "Jones",
    "first": "Christian",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Jones, Sara",
    "last": "Jones",
    "first": "Sara",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Kaufman, Bryn",
    "last": "Kaufman",
    "first": "Bryn",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Kaufman, Kendall",
    "last": "Kaufman",
    "first": "Kendall",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Sigala, Daniel",
    "last": "Sigala",
    "first": "Daniel",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Sigala, Kelsey",
    "last": "Sigala",
    "first": "Kelsey",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Sommovigo, Rose",
    "last": "Sommovigo",
    "first": "Rose",
    "table": "Skyline",
    "tableNumber": "1"
  },
  {
    "name": "Angel, Riley",
    "last": "Angel",
    "first": "Riley",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Bishop, Hilary",
    "last": "Bishop",
    "first": "Hilary",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Bowden, Jesse",
    "last": "Bowden",
    "first": "Jesse",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Coryea, Hilary",
    "last": "Coryea",
    "first": "Hilary",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Ellis, Katie",
    "last": "Ellis",
    "first": "Katie",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Evans, Caroline",
    "last": "Evans",
    "first": "Caroline",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Evans, Nick",
    "last": "Evans",
    "first": "Nick",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Evans, Stuart",
    "last": "Evans",
    "first": "Stuart",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Keilman, Tyler",
    "last": "Keilman",
    "first": "Tyler",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Lyons, Stacy",
    "last": "Lyons",
    "first": "Stacy",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Ruehle, Ben",
    "last": "Ruehle",
    "first": "Ben",
    "table": "RA Bistro",
    "tableNumber": "2"
  },
  {
    "name": "Braun, Kathryn",
    "last": "Braun",
    "first": "Kathryn",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "Evans, Charlie",
    "last": "Evans",
    "first": "Charlie",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "Evans, Judy",
    "last": "Evans",
    "first": "Judy",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "French, Charlotte",
    "last": "French",
    "first": "Charlotte",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "French, Scott",
    "last": "French",
    "first": "Scott",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "Gorry, Anne",
    "last": "Gorry",
    "first": "Anne",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "Gorry, James",
    "last": "Gorry",
    "first": "James",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "Gorry, Scott",
    "last": "Gorry",
    "first": "Scott",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "Jones, Dan",
    "last": "Jones",
    "first": "Dan",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "Jones, Dawn",
    "last": "Jones",
    "first": "Dawn",
    "table": "Reserve",
    "tableNumber": "3"
  },
  {
    "name": "Carpenter, Joshua",
    "last": "Carpenter",
    "first": "Joshua",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Carpenter, Katelyn",
    "last": "Carpenter",
    "first": "Katelyn",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Jones, Dennis",
    "last": "Jones",
    "first": "Dennis",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Jones, Donald",
    "last": "Jones",
    "first": "Donald",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Jones, Geniene",
    "last": "Jones",
    "first": "Geniene",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Jones, Lori",
    "last": "Jones",
    "first": "Lori",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Linski, Donna",
    "last": "Linski",
    "first": "Donna",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Linski, Kyle",
    "last": "Linski",
    "first": "Kyle",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Linski, Liz",
    "last": "Linski",
    "first": "Liz",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Linski, Tom",
    "last": "Linski",
    "first": "Tom",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Robison, Darlene",
    "last": "Robison",
    "first": "Darlene",
    "table": "Apocalypse",
    "tableNumber": "4"
  },
  {
    "name": "Johnson, Eddie",
    "last": "Johnson",
    "first": "Eddie",
    "table": "Shoemakers",
    "tableNumber": "5"
  },
  {
    "name": "Johnson, Eric",
    "last": "Johnson",
    "first": "Eric",
    "table": "Shoemakers",
    "tableNumber": "5"
  },
  {
    "name": "Johnson, Jammie",
    "last": "Johnson",
    "first": "Jammie",
    "table": "Shoemakers",
    "tableNumber": "5"
  },
  {
    "name": "Johnson, Nancy",
    "last": "Johnson",
    "first": "Nancy",
    "table": "Shoemakers",
    "tableNumber": "5"
  },
  {
    "name": "Meador, Andy",
    "last": "Meador",
    "first": "Andy",
    "table": "Shoemakers",
    "tableNumber": "5"
  },
  {
    "name": "Meador, Sarah",
    "last": "Meador",
    "first": "Sarah",
    "table": "Shoemakers",
    "tableNumber": "5"
  },
  {
    "name": "Smoot, Gary",
    "last": "Smoot",
    "first": "Gary",
    "table": "Shoemakers",
    "tableNumber": "5"
  },
  {
    "name": "Smoot, Laura",
    "last": "Smoot",
    "first": "Laura",
    "table": "Shoemakers",
    "tableNumber": "5"
  },
  {
    "name": "Smoot, Sam",
    "last": "Smoot",
    "first": "Sam",
    "table": "Shoemakers",
    "tableNumber": "5"
  },
  {
    "name": "Blauw, Elizabeth",
    "last": "Blauw",
    "first": "Elizabeth",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "Blauw, Jennifer",
    "last": "Blauw",
    "first": "Jennifer",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "Blauw, Matthew",
    "last": "Blauw",
    "first": "Matthew",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "Blauw, Russell",
    "last": "Blauw",
    "first": "Russell",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "French, Alexander",
    "last": "French",
    "first": "Alexander",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "French, Arthur",
    "last": "French",
    "first": "Arthur",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "French, Candace",
    "last": "French",
    "first": "Candace",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "French, Jennifer",
    "last": "French",
    "first": "Jennifer",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "French, Kelly",
    "last": "French",
    "first": "Kelly",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "French, Matthew",
    "last": "French",
    "first": "Matthew",
    "table": "El Jefe",
    "tableNumber": "6"
  },
  {
    "name": "Bobic, Daniel",
    "last": "Bobic",
    "first": "Daniel",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Bobic, Rachel",
    "last": "Bobic",
    "first": "Rachel",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Hromika, Shannon",
    "last": "Hromika",
    "first": "Shannon",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Jones, Alexis",
    "last": "Jones",
    "first": "Alexis",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Jones, Allen",
    "last": "Jones",
    "first": "Allen",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Jones, Carrie",
    "last": "Jones",
    "first": "Carrie",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Jones, Kyle",
    "last": "Jones",
    "first": "Kyle",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Kaufman, Jared",
    "last": "Kaufman",
    "first": "Jared",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Kaufman, Kristi",
    "last": "Kaufman",
    "first": "Kristi",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Lockhart, Jacob",
    "last": "Lockhart",
    "first": "Jacob",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Saunders, Bre",
    "last": "Saunders",
    "first": "Bre",
    "table": "White Hart",
    "tableNumber": "7"
  },
  {
    "name": "Hedrick, Joe",
    "last": "Hedrick",
    "first": "Joe",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Hedrick, Katie",
    "last": "Hedrick",
    "first": "Katie",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Hedrick, Stephanie",
    "last": "Hedrick",
    "first": "Stephanie",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Hott, Chris",
    "last": "Hott",
    "first": "Chris",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Hott, Sarah",
    "last": "Hott",
    "first": "Sarah",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Hrach, Dan",
    "last": "Hrach",
    "first": "Dan",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Hrach, Jan",
    "last": "Hrach",
    "first": "Jan",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Long, Shannon",
    "last": "Long",
    "first": "Shannon",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Long, Thomas",
    "last": "Long",
    "first": "Thomas",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Schneider, Becky",
    "last": "Schneider",
    "first": "Becky",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Schneider, Paul",
    "last": "Schneider",
    "first": "Paul",
    "table": "Mission House",
    "tableNumber": "8"
  },
  {
    "name": "Deckard, Mary",
    "last": "Deckard",
    "first": "Mary",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Kagey, Brian",
    "last": "Kagey",
    "first": "Brian",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Kagey, Dave",
    "last": "Kagey",
    "first": "Dave",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Kagey, Jane",
    "last": "Kagey",
    "first": "Jane",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Kagey, Tara",
    "last": "Kagey",
    "first": "Tara",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Shelor, Belva",
    "last": "Shelor",
    "first": "Belva",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Stevens, Ashley",
    "last": "Stevens",
    "first": "Ashley",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Stevens, Bucky",
    "last": "Stevens",
    "first": "Bucky",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Twery, Randy",
    "last": "Twery",
    "first": "Randy",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Twery, Seth",
    "last": "Twery",
    "first": "Seth",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Winters, Esther",
    "last": "Winters",
    "first": "Esther",
    "table": "Texas Tavern",
    "tableNumber": "9"
  },
  {
    "name": "Bochonok, Debby",
    "last": "Bochonok",
    "first": "Debby",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Bochonok, Jeff",
    "last": "Bochonok",
    "first": "Jeff",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Bonacquisti, Brian",
    "last": "Bonacquisti",
    "first": "Brian",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Bonacquisti, Susan",
    "last": "Bonacquisti",
    "first": "Susan",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Houston, Leola",
    "last": "Houston",
    "first": "Leola",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Houston, Randolph",
    "last": "Houston",
    "first": "Randolph",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Morrison, Diane",
    "last": "Morrison",
    "first": "Diane",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Morrison, Jim",
    "last": "Morrison",
    "first": "Jim",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Potente, Joe",
    "last": "Potente",
    "first": "Joe",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Potente, Liz",
    "last": "Potente",
    "first": "Liz",
    "table": "Water Dog",
    "tableNumber": "10"
  },
  {
    "name": "Berthoud, Emily",
    "last": "Berthoud",
    "first": "Emily",
    "table": "Starr Hill",
    "tableNumber": "11"
  },
  {
    "name": "Craig, Brooke",
    "last": "Craig",
    "first": "Brooke",
    "table": "Starr Hill",
    "tableNumber": "11"
  },
  {
    "name": "Craig, Michael",
    "last": "Craig",
    "first": "Michael",
    "table": "Starr Hill",
    "tableNumber": "11"
  },
  {
    "name": "Curtis, Ethan",
    "last": "Curtis",
    "first": "Ethan",
    "table": "Starr Hill",
    "tableNumber": "11"
  },
  {
    "name": "Curtis, Mandy",
    "last": "Curtis",
    "first": "Mandy",
    "table": "Starr Hill",
    "tableNumber": "11"
  },
  {
    "name": "Geneva, Steve",
    "last": "Geneva",
    "first": "Steve",
    "table": "Starr Hill",
    "tableNumber": "11"
  },
  {
    "name": "Minard, Brittany",
    "last": "Minard",
    "first": "Brittany",
    "table": "Starr Hill",
    "tableNumber": "11"
  },
  {
    "name": "Minard, Philip",
    "last": "Minard",
    "first": "Philip",
    "table": "Starr Hill",
    "tableNumber": "11"
  },
  {
    "name": "Waltz, Michael",
    "last": "Waltz",
    "first": "Michael",
    "table": "Starr Hill",
    "tableNumber": "11"
  },
  {
    "name": "Bell, Ethan",
    "last": "Bell",
    "first": "Ethan",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "Bell, Katie",
    "last": "Bell",
    "first": "Katie",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "Davis, Cidney",
    "last": "Davis",
    "first": "Cidney",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "Fields, Julie",
    "last": "Fields",
    "first": "Julie",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "Fields, Ryan",
    "last": "Fields",
    "first": "Ryan",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "Greene, Cheyenne",
    "last": "Greene",
    "first": "Cheyenne",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "Jensen, Brandi",
    "last": "Jensen",
    "first": "Brandi",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "McAllister, Caleb",
    "last": "McAllister",
    "first": "Caleb",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "McAllister, Rachel",
    "last": "McAllister",
    "first": "Rachel",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "Pearce, Lauren",
    "last": "Pearce",
    "first": "Lauren",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "Smith, Twon",
    "last": "Smith",
    "first": "Twon",
    "table": "Mrs. Joy's",
    "tableNumber": "12"
  },
  {
    "name": "Gallant, Matthew",
    "last": "Gallant",
    "first": "Matthew",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "Gallant, Morgan",
    "last": "Gallant",
    "first": "Morgan",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "Gutierrez, Brian",
    "last": "Gutierrez",
    "first": "Brian",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "Mohring, Kelsey",
    "last": "Mohring",
    "first": "Kelsey",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "O'Neil, Michael",
    "last": "O'Neil",
    "first": "Michael",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "Ogden, Michelle",
    "last": "Ogden",
    "first": "Michelle",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "Ross, Brian",
    "last": "Ross",
    "first": "Brian",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "Ross, Lauren",
    "last": "Ross",
    "first": "Lauren",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "Wenger, Blake",
    "last": "Wenger",
    "first": "Blake",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "Wenger, Kristin",
    "last": "Wenger",
    "first": "Kristin",
    "table": "Aji Ramen",
    "tableNumber": "13"
  },
  {
    "name": "Austin, Lauren",
    "last": "Austin",
    "first": "Lauren",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Austin, Ryan",
    "last": "Austin",
    "first": "Ryan",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Cockrell, Daniel",
    "last": "Cockrell",
    "first": "Daniel",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Cockrell, Gabbie",
    "last": "Cockrell",
    "first": "Gabbie",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Gillispie, Nathan",
    "last": "Gillispie",
    "first": "Nathan",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Gillispie, Sarah",
    "last": "Gillispie",
    "first": "Sarah",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Mullen, Josh",
    "last": "Mullen",
    "first": "Josh",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Mullen, Loren",
    "last": "Mullen",
    "first": "Loren",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Warwick, Jennifer",
    "last": "Warwick",
    "first": "Jennifer",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Warwick, Matthew",
    "last": "Warwick",
    "first": "Matthew",
    "table": "The Cavalier",
    "tableNumber": "14"
  },
  {
    "name": "Curtis, Holly",
    "last": "Curtis",
    "first": "Holly",
    "table": "Farm Basket",
    "tableNumber": "15"
  },
  {
    "name": "Curtis, Tyler",
    "last": "Curtis",
    "first": "Tyler",
    "table": "Farm Basket",
    "tableNumber": "15"
  },
  {
    "name": "McGunigle, Meg",
    "last": "McGunigle",
    "first": "Meg",
    "table": "Farm Basket",
    "tableNumber": "15"
  },
  {
    "name": "Melone, Alyssa",
    "last": "Melone",
    "first": "Alyssa",
    "table": "Farm Basket",
    "tableNumber": "15"
  },
  {
    "name": "Melone, Jacob",
    "last": "Melone",
    "first": "Jacob",
    "table": "Farm Basket",
    "tableNumber": "15"
  },
  {
    "name": "Morton, Brittney",
    "last": "Morton",
    "first": "Brittney",
    "table": "Farm Basket",
    "tableNumber": "15"
  },
  {
    "name": "Morton, Zach",
    "last": "Morton",
    "first": "Zach",
    "table": "Farm Basket",
    "tableNumber": "15"
  },
  {
    "name": "Reinwald, Kelly",
    "last": "Reinwald",
    "first": "Kelly",
    "table": "Farm Basket",
    "tableNumber": "15"
  },
  {
    "name": "Russell, Katelyn",
    "last": "Russell",
    "first": "Katelyn",
    "table": "Farm Basket",
    "tableNumber": "15"
  },
  {
    "name": "Tyer, Natalie",
    "last": "Tyer",
    "first": "Natalie",
    "table": "Farm Basket",
    "tableNumber": "15"
  }
]
  const filteredPeople = (input) => {
    if (input === null || 
        input === undefined || 
        input === "") {
      return parsedPeople
    }
    return parsedPeople.filter(p => 
      p.name.startsWith(input))
  }
  
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