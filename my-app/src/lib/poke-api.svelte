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
  
  <main>
    <h1>Random Pokémon Image</h1>
    <img src={pokemonImage} alt="Random Pokemon">
    <button on:click={fetchRandomPokemon}>Fetch Random Pokémon</button>
  </main>
  
  <style>
    main {
      text-align: center;
      padding: 20px;
    }
  
    h1 {
      margin-bottom: 20px;
    }
  
    img {
      width: 200px;
      height: 200px;
      margin-bottom: 20px;
    }
  
    button {
      padding: 10px 20px;
      font-size: 16px;
    }
  </style>
   <!--I will take this opacity code and make a find a pokemon div. you press the buitton to generate random pokemon and hover over them to make them visible-->
  