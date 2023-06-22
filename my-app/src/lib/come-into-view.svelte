<script>
  //Script that deals with the transition and scroll for the images and text
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
    if (typeof window !== 'undefined' && !isContentVisible && window.pageYOffset >= 2300) {
      isContentVisible = true;
    }
  }

  onMount(() => {
    if (typeof window !== 'undefined') {
      window.addEventListener('scroll', showContent);
    }
  });
</script>
<!-- end script section -->

<!-- Html for the content that goes through the array to display the content -->
<div class="come-into-view-container">
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
<!-- end Html section -->

<style>
  /* Styles for the content transitions, etc*/
  .come-into-view-container {
    display: grid;
    grid-template-rows: auto 80px 80px 1fr;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    align-items: center;
    margin-top: 100px;
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
    transition: opacity 4s ease, transform 4s ease;
    align-self: start;
  }

  .text {
    opacity: 0;
    text-align: center;
    transition: opacity 6s ease;
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
    transition: opacity 6s ease; /* Added transition for title */
  }

  .title.visible {
    opacity: 1;
  }

  @media (max-width: 768px) {
    .come-into-view-container {
      grid-template-columns: 1fr;
      width:auto;
    }

    .image {
      height: auto;
    }

    .text {
      font-size: 24px;
      height: auto;
    }

    .title {
      font-size: 72px;
      height: auto;
    }
  }

  @media (max-width: 480px) {
    .title {
      font-size: 48px;
    }
  }
</style>