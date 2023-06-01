<script>
  const images = [
    "/images/arcade.jpg",
    "/images/books.jpg",
    "/images/chalkboard.jpg",
    "/images/controller.jpg",
    "/images/desk-trooper.jpg",
    "/images/headphones.jpg",
    "/images/keyboard.jpg",
    "/images/pc.jpg",
    "/images/tardis.jpg",
    "/images/scifi.jpg",
    "/images/skyhigh.jpg",
    "/images/spooky.jpg",
    "/images/troll.jpg",
    "/images/wtf.jpg",
    "/images/beakers.jpg",
    "/images/lab.jpg",
    "/images/tree.jpg",
    "/images/rain.jpg",

    // Add more image paths as needed
  ];
</script>

<div class="flipping-card-container">
  {#each images as image, index}
    <div class="flipping-card">
      <div class="flipping-card-inner">
        <div class="flipping-card-front">
          <img src={image} alt="Image {index + 1}">
        </div>
        <div class="flipping-card-back">
          <a href="https://example.com" target="_blank">Link to Website {index + 1}</a>
        </div>
      </div>
    </div>
  {/each}
</div>

  
<style>
    .flipping-card-container {
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      grid-gap: 10px;
    }
    
    .flipping-card {
      background-color: transparent;
      width: 200px;
      height: 260px;
      perspective: 1000px;
    }
    
    .flipping-card-inner {
      position: relative;
      width: 100%;
      height: 100%;
      text-align: center;
      transition: transform 0.8s;
      transform-style: preserve-3d;
    }
    
    .flipping-card:hover .flipping-card-inner {
      transform: rotateY(180deg);
      box-shadow: 0 0 10px 5px coral;
    }
    
    .flipping-card-front,
    .flipping-card-back {
      box-shadow: 0 0px 24px 5px rgb(248, 159, 87);
      position: absolute;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      -webkit-backface-visibility: hidden;
      backface-visibility: hidden;
      border: 1px solid coral;
      border-radius: 1rem;
    }
    
    .flipping-card-front img,
    .flipping-card-back img {
      max-width: 100%;
      max-height: 100%;
      object-fit: cover;
    }
    
    .flipping-card-front {
      background: linear-gradient(
        120deg,
        bisque 60%,
        rbg(225, 231, 222) 88%,
        rgb(255, 211, 195) 40% rgba(255, 127, 80, 0.603) 48%
      );
      color: coral;
    }
    
    .flipping-card-back {
      background: linear-gradient(
        120deg,
        rbg(225, 174, 145) 30%,
        coral 88%,
        bisque 40%,
        rgb(255, 185, 160) 78%
      );
      transform: rotateY(180deg);
    }
    </style>
    