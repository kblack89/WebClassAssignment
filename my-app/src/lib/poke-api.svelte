<script>
  let pokemonImage = '';
  let isPokeballVisible = true;
  let pokeballTransition = null;

  async function fetchRandomPokemon() {
    const response = await fetch('https://pokeapi.co/api/v2/pokemon?limit=1000');
    const data = await response.json();
    const pokemonCount = data.count;
    const randomPokemonId = Math.floor(Math.random() * pokemonCount) + 1;
    const pokemonResponse = await fetch(`https://pokeapi.co/api/v2/pokemon/${randomPokemonId}`);
    const pokemonData = await pokemonResponse.json();
    pokemonImage = pokemonData.sprites.front_default;
    isPokeballVisible = true; // Reset the visibility of the pokeball image
  }

  import { fade } from 'svelte/transition';

  function hidePokeball() {
    isPokeballVisible = false;
    pokeballTransition = fade({ duration: 2000 });
  }
</script>

<div class="container">
  {#if isPokeballVisible}
    <div class="pokeBack">
      <img class="pokeball" src="/images/PokeBall.png" alt="pokemon ball" on:click={hidePokeball} in:fade="{pokeballTransition}">
      <img class="pokeimage" src={pokemonImage} alt=" ">
    </div>
  {/if}
  <div><button on:click={fetchRandomPokemon}>Generate a Random Pokémon</button></div>
</div>

<style>
  img {
    width: 300px;
    height: 300px;
    margin-bottom: -550px;
    margin-left: 10px;
  }

  button {
    padding: 10px 20px;
    font-size: 16px;
    margin-top: 600px;
    margin-left: 10px;
  }

  .pokeBack {
    background-image: url("/images/pokegrass.jpg");
    height: 70%;
    width: 100%;
    opacity: 1;
    transition: opacity 2s ease;
  }

  .container {
    height: 100%;
    width: 100%;
  }

  .pokeball {
    height: 100%;
    width: 40%;
    transition: opacity 2s ease;
  }

  .pokeimage {
    opacity: 0;
  }

  .pokeBack.hide {
    opacity: 0;
  }

  .pokeball.hide {
    opacity: 0;
  }


    button {
      padding: 10px 20px;
      font-size: 16px;
  margin-top: 600px;
      margin-left: 10px;

    }
    .pokeBack{
      background-image: url("/images/pokegrass.jpg");
      height: 70%;
      width: 100%;
    }

    .container{
      height: 100%;
      width: 100%;
    
    }

    .pokeball {
      height: 100%;
      width: 40%

    }

  </style>
