<script>
// @ts-nocheck

  let images = [
    { src: "/images/pc.jpg", alt: "Image 1 - Description of the image" },
    { src: "/images/keyboard.jpg", alt: "Image 2 - Description of the image" },
    { src: "/images/pc.jpg", alt: "Image 3 - Description of the image" },
    { src: "/images/keyboard.jpg", alt: "Image 4 - Description of the image" },
    { src: "/images/pc.jpg", alt: "Image 5 - Description of the image" },

    { src: "/images/pc.jpg", alt: "Image 3 - Description of the image" },
    { src: "/images/keyboard.jpg", alt: "Image 4 - Description of the image" },
    { src: "/images/pc.jpg", alt: "Image 5 - Description of the image" }
  ];

  let scrollPosition = 0;
  export let el;

  function getOffset(el) {
    if(el)
    {
      const rect = el.getBoundingClientRect();
      return {
        left: rect.left + window.scrollX,
        top: rect.top
      };
    }
  }

  

  /**
     * @param {{ deltaY: any; detail: any; wheelDelta: number; }} event
     */
  /*function handleScroll(event) {
    console.log(event)

    const deltaY = event.deltaY || event.detail || (-event.wheelDelta);

    if (deltaY > 0) {
      scrollPosition += 80; // Adjust the value as per your preference
    } else if (deltaY < 0) {
      scrollPosition -= 80; // Adjust the value as per your preference
    }
  }*/
    
</script>

<div class="gallery" bind:this={el}>
  {#each images as image, index}
    <div class="image-wrapper" style="animation-delay: {index * 1.5}s; transform: translateX({getOffset(el)?.top - scrollPosition < 0 ? getOffset(el)?.top - scrollPosition : 0}px)">
      <img src={image.src} alt={image.alt}>
    </div>
  {/each}
</div>

<style>
  .gallery {
    display: flex;
    overflow: hidden;
    width: 100%;
    height: 100%;
    scrollbar-width: none; /* Optional: To hide the scrollbar */
    transition: transform 0.9s ease-in-out;
    position: absolute;
    left: 0;
  }

  .image-wrapper {
    flex-shrink: 0;
    width: 50%;
    
  }

  .image-wrapper img {
    width: 100%;
    height: auto;
    margin: 0;


  }
</style>

<svelte:window bind:scrollY={scrollPosition} />