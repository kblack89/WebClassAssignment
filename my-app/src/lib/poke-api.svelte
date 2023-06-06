<script>
  let pokemonImage = '';

  async function fetchRandomPokemon() {
    const response = await fetch('https://pokeapi.co/api/v2/pokemon?limit=1000');
    const data = await response.json();
    const pokemonCount = data.count;
    const randomPokemonId = Math.floor(Math.random() * pokemonCount) + 1;
    const pokemonResponse = await fetch(`https://pokeapi.co/api/v2/pokemon/${randomPokemonId}`);
    const pokemonData = await pokemonResponse.json();
    pokemonImage = pokemonData.sprites.front_default;
  }
</script>

<div class="grid-container">
  <div class="pokeBack">
    <img src={pokemonImage} alt=" ">
  </div>
  <div class="pokeData">
    <p>gesrggsg</p>
    <p>grgegege</p>
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
    align-items: center;
    padding-right: 10px;
  }

  img {
    width: 300px;
    height: 300px;
  }

  .pokeData {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    padding-left: 10px;
  }

  button {
    padding: 10px 20px;
    font-size: 16px;
    grid-column: span 2;
  }
</style>
