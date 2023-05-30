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
  
 
  <div class="pokeBack">
    <img src={pokemonImage} alt=" ">
    <button on:click={fetchRandomPokemon}>Generate a Random Pokémon</button>
</div>
  
  <style>

    img {
      width: 200px;
      height: 200px;
      margin-bottom: 20px;
    }
  
    button {
      padding: 10px 20px;
      font-size: 16px;
    }
    .pokeBack{
      background-image: url("/images/pokegrass.jpg");
      height: 900px;
      width: 900px;
      margin-top: -60px;
      margin-left: 400px;

    }

  </style>
