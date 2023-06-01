<script>
    let images = [
      "/images/pc.jpg",
      "/images/pc.jpg",
      "/images/pc.jpg",
    ];
  
    let texts = [
      'Text 1',
      'Text 2',
      'Text 3'
    ];
  </script>
  
  <style>
    .container {
      display: grid;
      grid-template-rows: repeat(6, 1fr); /* Updated value */
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
      align-items: center;
    }
  
    .image {
      width: 100%;
      height: 300px;
      object-fit: cover;
    }
  
    .text {
      text-align: center;
    }
  </style>
  
  <div class="container">
    {#each Array(3) as _, i} <!-- Create 3 empty grids -->
      <div></div>
    {/each}
  
    {#each texts as text, i}
      <div class="text">{text}</div>
    {/each}
  
    {#each images as image, i}
      <img src={image} alt={`Image ${i + 1}`} class="image">
    {/each}
  </div>