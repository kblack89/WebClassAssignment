<script>
    import { onMount } from 'svelte';
  
    let isImageVisible = false;
  
    onMount(() => {
      window.addEventListener('scroll', showImage);
    });
  
    function showImage() {
      if (!isImageVisible && window.scrollY >= 2400) {
        isImageVisible = true;
      }
    }

  </script>
  
  <div class="container">
    {#if isImageVisible}
      <img class="image visible" src="images/tardis.jpg" alt="A cool thing" />
    {:else}
      <img class="image" src="images/tardis.jpg" alt="Another cool thing" />
    {/if}
    <div class="content">
      <p>This is the text that becomes visible on hover.</p>
    </div>
  </div>
    
  <style>
    .container {
      position: relative;
      display: inline-block;
      overflow: hidden;
   
    }
  
    .content {
      opacity: 0;
      transform: translateY(100%);
      position: absolute;
      top: 100%;
      left: 0;
      padding: 0.5rem;
      background-color: #f5f5f5;
      border: 1px solid #ccc;
      border-radius: 4px;
      z-index: 1;
      transition: opacity 0.3s ease, transform 0.5s ease;
    }
  
    .container:hover .content {
      opacity: 1;
      transform: translateY(0);
      
    }
  
    .image {
      opacity: 0;
      transform: translateY(100%);
      max-width: 80%;
      height: auto;
      transition: opacity 0.3s ease, transform 0.5s ease;
    
    }
  
    .image.visible {
      opacity: 1;
      transform: translateY(0);
      animation: fadeIn 5s;  
      
    }
    @keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}
  </style>
  