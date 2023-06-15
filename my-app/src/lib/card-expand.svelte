<script>
    let images = [
      "/images/purple galaxy.jpg",
      "/images/rain.jpg",
      "/images/troll.jpg",
      "/images/bigmouth.jpg",
      "/images/mist.jpg",
      "/images/octo.jpg",
      "/images/ritual.jpg",
      "/images/skulleyes.jpg",
      "/images/skullmoon.jpg",
      "/images/snakewold.jpg",
      "/images/noms.jpg",
      "/images/town.jpg"
    ];
  
    let hoveredImage = null;
  
    function handleHover(image) {
      hoveredImage = image;
    }
  
    function handleLeave() {
      hoveredImage = null;
    }
  </script>
  
    <div class="gallery">
      {#each images as image}
        <img src={image} alt="Really cool stuff" 
          on:mouseenter={() => handleHover(image)}
          on:mouseleave={handleLeave}
          class:hovered={hoveredImage !== null && hoveredImage !== image}
        />
      {/each}
    </div>
    
  
  <style>
    .gallery {
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      grid-gap: 10px;
    }
  
    .gallery img {
      width: 90%;
      height: auto;
      -webkit-transition: 400ms ease 100ms;
      -moz-transition: 400ms ease 100ms;
      transition: 400ms ease 100ms;
    }
  
    .gallery:hover img:not(:hover) {
      filter: blur(5px);
    }
  
    .gallery img:hover {
      transform: scale(1.80);
      filter: none;
      z-index:10;
    }
  
    .gallery img.hovered {
      filter: blur(3px);
      opacity: 1.0;
     
    }
  </style>
  
