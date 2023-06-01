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
    <div class="grid-item">
      <h1 class="text visible">MOVIES I LOVE</h1>
      <p class="text visible">This is a good movie</p>
    </div>
    <div class="grid-item">
      <img class="image visible" src="images/tardis.jpg" alt="A cool thing" />
    </div>
    <div class="grid-item">

      <p class="text visible">This is a good movie</p>
    </div>
    <div class="grid-item">
      <img class="image visible" src="images/tardis.jpg" alt="A cool thing" />
    </div>
    <div class="grid-item">
      <p class="text visible">This is a good movie</p>
    </div>
    <div class="grid-item">
      <img class="image visible" src="images/tardis.jpg" alt="A cool thing" />
    </div>
    <div class="grid-item">
      <p class="text visible">This is a good movie</p>
    </div>
    {:else}
    <div class="grid-item">
      <img class="image" src="images/tardis.jpg" alt="Another cool thing" />
    </div>
    <div class="grid-item">
      <h1 class="text">..the great space race</h1>
    </div>
    <div class="grid-item">
      <img class="image" src="images/tardis.jpg" alt="Another cool thing" />
    </div>
    <div class="grid-item">
      <p class="text">This is a good movie</p>
    </div>
    <div class="grid-item">
      <img class="image" src="images/tardis.jpg" alt="Another cool thing" />
    </div>
    <div class="grid-item">
      <p class="text">This is a good movie</p>
    </div>
    {/if}
  </div>
  
  
  <style>
.container {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 1fr 1fr;
  grid-gap: 20px;
  justify-items: center;
  align-items: center;
  height: 100%;
}

.grid-item {
  text-align: center;
}

.image {
  opacity: 0;
  transform: translateY(100%);
  max-width: 100%;
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
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@media (min-width: 768px) {
  .container {
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: auto;
  }
}

    
  </style>
  