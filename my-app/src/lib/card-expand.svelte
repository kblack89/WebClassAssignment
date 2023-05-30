<script>
    let images = [
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg",
      "/images/headphones.jpg"
    ];
  
    let hoveredImage = null;
  
    function handleHover(image) {
      hoveredImage = image;
    }
  
    function handleLeave() {
      hoveredImage = null;
    }
  </script>
  
  <style>
    .gallery {
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      grid-gap: 10px;
    }
  
    .gallery img {
      width: 100%;
      height: auto;
      -webkit-transition: 400ms ease 100ms;
      -moz-transition: 400ms ease 100ms;
      transition: 400ms ease 100ms;
    }
  
    .gallery:hover img:not(:hover) {
      filter: blur(5px);
    }
  
    .gallery img:hover {
      transform: scale(1.30);
      filter: none;
      z-index:10;
    }
  
    .gallery img.hovered {
      filter: blur(3px);
      opacity: 0.7;
     
    }
  </style>
  
  <div class="gallery">
    {#each images as image}
      <img src={image} alt="Really cool stuff" 
        on:mouseenter={() => handleHover(image)}
        on:mouseleave={handleLeave}
        class:hovered={hoveredImage !== null && hoveredImage !== image}
      />
    {/each}
  </div>
  