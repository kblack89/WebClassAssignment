<script>
    import { onMount } from 'svelte';
  
    let isImageVisible = false;
  
    onMount(() => {
      window.addEventListener('scroll', showImage);
    });
  
    function showImage() {
      if (!isImageVisible && window.scrollY >= 2300) {
        isImageVisible = true;
      }
    }

  </script>
  
  <div class="container">
    {#if isImageVisible}
    <h1 class="text visible">MOVIES I LOVE</h1>
      <img class="image visible" src="images/tardis.jpg" alt="A cool thing" />
      <h1 class="text visible">MOVIES I LOVE</h1>
      <img class="image visible" src="images/tardis.jpg" alt="A cool thing" />
      <p class="text visible">This is a good movie</p>
      <img class="image visible" src="images/tardis.jpg" alt="A cool thing" />
      <p class="text visible">This is a good movie</p>
    {:else}
      <img class="image" src="images/tardis.jpg" alt="Another cool thing" />
      <h1 class="text">..the great space race</h1>
      <img class="image" src="images/tardis.jpg" alt="Another cool thing" />
      <p class="text">This is a good movie</p>
      <img class="image" src="images/tardis.jpg" alt="Another cool thing" />
      <p class="text">This is a good movie</p>
    {/if}
  </div>
  
  <style>
    .container {
      display: flex;
      justify-content: center; /* Center the content horizontally */
      align-items: center; /* Center the content vertically */
      height: 100%; /* Adjust the container height to center vertically */
    }
  
    .image {
      opacity: 0;
      transform: translateY(100%);
      max-width: 30%;
      height: auto;
      transition: opacity 0.3s ease, transform 0.5s ease;
      padding: 80px;
    }
  
    .image.visible {
      opacity: 1;
      transform: translateY(0);
      animation: fadeIn 3s;
    }
  
    .text {
      opacity: 0;
      max-width: 80%;
      height: auto;
      transition: opacity 0.3s ease, transform 0.5s ease;
    }
  
    .text.visible {
      opacity: 1;
      animation: fadeIn 3s;
    }
 
    @keyframes fadeIn {
      0% { opacity: 0; }
      100% { opacity: 1; }
    }
    
  </style>
  