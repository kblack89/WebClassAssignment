<script>
  let images = [
    { src: "/images/pc.jpg", alt: "Image 1 - Description of the image" },
    { src: "/images/keyboard.jpg", alt: "Image 2 - Description of the image" },
    { src: "/images/pc.jpg", alt: "Image 3 - Description of the image" },
    { src: "/images/keyboard.jpg", alt: "Image 4 - Description of the image" },
    { src: "/images/pc.jpg", alt: "Image 5 - Description of the image" }
  ];
</script>

<div class="gallery">
  <div class="image-container">
    {#each images as image}
      <div class="image-wrapper">
        <img src={image.src} alt={image.alt}>
      </div>
    {/each}
  </div>
</div>

<style>
  .gallery {
    display: flex;
    overflow-x: auto;
    scrollbar-width: none; /* Optional: To hide the scrollbar */
    transition: transform 0.9s ease-in-out;
    margin: 1px;
     width:100%;
     overflow: hidden; 
  }

  .gallery:hover {
    transform: translateX(40px); /* Adjust the value as per your preference */
  }

  .image-wrapper {
    flex-shrink: 0;
    width: 50%; /* Adjust the width as per your preference */
  }

  .image-wrapper img {
    width: 100%;
    height: auto;
    margin: 0px;
  }
  .image-container{

 display: flex;
  }
</style>