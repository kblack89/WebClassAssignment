<script>
  //Script that makes an array of images and stores the currently hovered over image and deals with the events
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
<!-- end script section -->

 <!--Html that loops through the images and links to hover effects in the script -->
<div>
  <h2>Some spooky art to enjoy..</h2>
</div>
  <div class="gallery">
    {#each images as image}
      <img src={image} alt="Really cool stuff" 
        on:mouseenter={() => handleHover(image)}
        on:mouseleave={handleLeave}
        class:hovered={hoveredImage !== null && hoveredImage !== image}/>
    {/each}
</div>
<!-- end html section -->

<style>
    /* Styles for the gallery, gridifying where nesssecary and adding the blur effect when hovered over an image */
  .gallery {
    display: grid;
    grid-gap: 10px;
    padding: 10px;
    justify-content: center;
  }

  .gallery img {
    width: 100%;
    height: auto;
    transition: 400ms ease 100ms;
  }

  .gallery img:hover {
    transform: scale(1.8);
    filter: none;
    z-index: 10;
  }

  .gallery img.hovered {
    filter: blur(3px);
    opacity: 1.0;
  }

  @media (min-width: 600px) {
    .gallery {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  @media (min-width: 900px) {
    .gallery {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  @media (min-width: 1200px) {
    .gallery {
      grid-template-columns: repeat(4, 1fr);
    }
  }

  @media (min-width: 1600px) {
    .gallery {
      grid-template-columns: repeat(6, 1fr);
    }
  }

  @media (max-width: 599px) {
    .gallery img {
      width: 100%;
    }
  }

  .gallery:hover img:not(:hover) {
    filter: blur(5px);
  }
</style>
