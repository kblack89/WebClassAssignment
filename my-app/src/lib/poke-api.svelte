<script>
  //This script section fetches from the pokemon api and finds a random pokemon to display on button click and also pulls data from the api to find the name and type of that pokemon
  let pokemonImage = null;
  let pokemonName = '';
  let pokemonType = '';
  let showPokemon = false; // Initially set to false

  async function fetchRandomPokemon() {
    const response = await fetch('https://pokeapi.co/api/v2/pokemon?limit=1000');
    const data = await response.json();
    const pokemonCount = 1000; //It did fetch but there was an issue and the documentation on the site was incorrect
    const randomPokemonId = Math.floor(Math.random() * pokemonCount) + 1;
    const pokemonResponse = await fetch(`https://pokeapi.co/api/v2/pokemon/${randomPokemonId}`);
    const pokemonData = await pokemonResponse.json();
    pokemonImage = pokemonData.sprites.front_default;
    pokemonName = capitalizeFirstLetter(pokemonData.name);
    pokemonType = capitalizeFirstLetter(pokemonData.types[0].type.name);
    showPokemon = true; // Set to true after fetching a random Pokémon
  }

  function capitalizeFirstLetter(string) {
    return string.charAt(0).toUpperCase() + string.slice(1);
  }
</script>
<!-- end script section -->

  <!-- The html for the text, background image and pokemon image. Uses the Api references such as pokemonName to generate the correct data where referenced-->
<div class="grid-container">
  <div class="pokeBack">
    <div class="pokeImage {showPokemon ? 'visible' : 'hidden'}"> <!-- Add dynamic class -->
      {#if showPokemon}
        <img src={pokemonImage} alt=" ">
      {/if}
    </div>
  </div>
  <div class="pokeData">
    <p class="name">Name: {pokemonName}</p>
    <p class="type">Type: {pokemonType}</p>
  </div>
  <div><button on:click={fetchRandomPokemon}>Generate a Random Pokémon</button></div>
</div>
<!-- end html section -->

<style>
   /* Styles for the pokemon fetching componant. Just flex, grid and other css code to make the layout as desired*/
  .grid-container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    height:100%;
    width: 100%;
    padding: 10px;
  }

  .pokeBack {
    background-image: url("/images/pokegrass.jpg");
    height: 600px;
    width: 100%;
    display: flex;
    justify-content: flex-end;
    align-items: flex-end;
    padding-right: 10px;
    background-size:cover;
    background-position: center;
  }

  .pokeImage {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    margin-bottom: 20px; 
  }

  img {
    width: 40%;
   }

  .pokeData {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    padding-left: 40px;
    margin-right: 10px; 
  }
  button {
    padding: 10px 20px;
    font-size: 16px;
    grid-column: span 2;
  }

  p {
    margin-top: 0;
    text-align: right;
    margin-right: 10px;
  }
  .visible {
    opacity: 1;
  }

  .hidden {
    opacity: 0;
  }
  @media (max-width: 768px) {
    .grid-container {
      grid-template-columns: 1fr;
      height: auto;
    }

    .pokeBack {
      height: auto;
      padding: 10px;
      justify-content: center;
      align-items: center;
    }

    .pokeImage {
      margin-bottom: 10px;
    }

    img {
      width: 80%;
    }
    .pokeData {
      padding-left: 0;
      text-align: center;
    }
  }
  
</style>
