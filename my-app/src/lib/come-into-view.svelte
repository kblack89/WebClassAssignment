<script>
  import { onMount } from 'svelte';

  let images = [
    "/images/lotr.jpg",
    "/images/spiderman.jpg",
    "/images/jp.jpg",
  ];

  let texts = [
    'Lord Of The Rings',
    'Spider-man',
    'Jurassic Park'
  ];

  let isContentVisible = false;

  function showContent() {
    if (typeof window !== 'undefined' && !isContentVisible && window.pageYOffset >= 2200) {
      isContentVisible = true;
    }
  }

  onMount(() => {
    if (typeof window !== 'undefined') {
      window.addEventListener('scroll', showContent);
    }
  });
</script>

<div class="container">
  <h1 class="{`title ${isContentVisible ? 'visible' : ''}`}">MOVIES</h1>

  {#each Array(2) as _} 
    <div class="empty-div"></div>
  {/each}

  {#each texts as text}
    <div class="{`text ${isContentVisible ? 'visible' : ''}`}">{text}</div>
  {/each}

  {#each images as image}
    <img src={image} alt="" class="{`image ${isContentVisible ? 'visible' : ''}`}">
  {/each}
</div>

<style>
  .container {
    display: grid;
    grid-template-rows: auto 80px 80px 1fr;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    align-items: center;
  }

  .empty-div {
    height: 80px;
  }

  .image {
    opacity: 0;
    transform: translateY(100%);
    width: 100%;
    height: 350%;
    object-fit: cover;
    transition: opacity 2s ease, transform 2s ease;
    align-self: start;
  }

  .text {
    opacity: 0;
    text-align: center;
    transition: opacity 2s ease;
    align-self: start;
    color:rgb(245, 112, 24);
  }

  .visible {
    opacity: 1;
    transform: translateY(0);
  }

  .title {
    font-size: 150px;
    opacity: 0;
    transition: opacity 2s ease; /* Added transition for title */
  }

  .title.visible {
    opacity: 1;
  }
</style>
