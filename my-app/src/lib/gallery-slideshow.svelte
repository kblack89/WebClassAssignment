<script>
    //Script that deals with the gallery images and movement event
  let images = [
    { src: "/images/blue galaxy.jpg", alt: "Image 1 - Description of the image" },
    { src: "/images/lab.jpg", alt: "Image 2 - Description of the image" },
    { src: "/images/skyhigh.jpg", alt: "Image 3 - Description of the image" },
    { src: "/images/blue galaxy.jpg", alt: "Image 4 - Description of the image" },
    { src: "/images/lab.jpg", alt: "Image 5 - Description of the image" },
    { src: "/images/skyhigh.jpg", alt: "Image 6 - Description of the image" },
    { src: "/images/lab.jpg", alt: "Image 7 - Description of the image" },
    { src: "/images/blue galaxy.jpg", alt: "Image 8 - Description of the image" },
    { src: "/images/skyhigh.jpg", alt: "Image 9 - Description of the image" },
    { src: "/images/lab.jpg", alt: "Image 10 - Description of the image" },
    { src: "/images/blue galaxy.jpg", alt: "Image 11 - Description of the image" },
    { src: "/images/skyhigh.jpg", alt: "Image 12 - Description of the image" },
    { src: "/images/lab.jpg", alt: "Image 13 - Description of the image" },
    { src: "/images/blue galaxy.jpg", alt: "Image 14 - Description of the image" }
  ];

  let scrollPosition = 0;
  export let el;

  function getOffset(el) {
    if(el) {
      const rect = el.getBoundingClientRect();
      return {
        left: rect.left + window.scrollX,
        top: rect.top
      };
    }
  }
</script>
 <!-- End of script section -->

 <!-- The html for the gallery -->
<h1>Space... Science... Art...</h1>
<div class="gallery fade-in" bind:this={el}>
  {#each images as image, index}
    <div class="image-wrapper" style="animation-delay: {index * 1.5}s; transform: translateX({getOffset(el)?.top - scrollPosition < 0 ? getOffset(el)?.top - scrollPosition : 0}px)">
      <img src={image.src} alt={image.alt}>
    </div>
  {/each}
</div>
<!-- end html section -->

<style>
  /* Styles for the image gallery transitions and display*/
  .gallery {
    display: flex;
    overflow: hidden;
    width: 100%;
    height: 100%;
    scrollbar-width: none; 
    transition: transform 0.9s ease-in-out;
    position: absolute;
    left: 0;
    opacity: 0;
  }

  .fade-in {
    animation: fade-in 3s forwards;
  }

  @keyframes fade-in {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }

  .gallery img {
    object-fit: cover;
    width: 100%;
    height: auto;
  }

  .image-wrapper {
    flex-shrink: 0;
    width: 40%;
  }

  .image-wrapper img {
    height: 400px; 
    object-fit: cover;
  }

</style>

<svelte:window bind:scrollY={scrollPosition} />
