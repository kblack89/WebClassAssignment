<script>
  // Images array with src and alt information
  let images = [
      { src: "/images/pc.jpg", alt: "Image 1 - Description of the image" },
      { src: "/images/keyboard.jpg", alt: "Image 2 - Description of the image" },
      { src: "/images/pc.jpg", alt: "Image 3 - Description of the image" }
  ];
</script>

<div class="gallery">
  {#each images as image}
      <img src={image.src} alt={image.alt}>
  {/each}
</div>

<style>
  .gallery {
      display: flex;
      justify-content: space-between;
  }

  .gallery img {
      width: 30%;
      height: auto;
  }
</style>