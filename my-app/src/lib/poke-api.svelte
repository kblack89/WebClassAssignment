<script>
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

<style>
  .grid-container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    height: 600px;
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
  }

  .pokeImage {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    margin-bottom: 20px; /* Adjust the margin-bottom value as desired */
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
    margin-right: 10px; /* Add this line to move the p tags to the right by 10px */
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
</style>
