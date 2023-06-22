<script>
  //Script that has an array of images and deals with scrolling to set off desired effects
  import { onMount } from "svelte";
    const images = [
      { path: "/images/Elden.jpg", link: "https://store.steampowered.com/app/1245620/ELDEN_RING/" },
      { path: "/images/batman.jpg", link: "https://store.steampowered.com/app/209000/Batman_Arkham_Origins/" },
      { path: "/images/battle.jpg", link: "https://store.steampowered.com/app/578080/PUBG_BATTLEGROUNDS/" },
      { path: "/images/cod.jpg", link: "https://store.steampowered.com/app/2000950/Call_of_Duty_Modern_Warfare/" },
      { path: "/images/cola.jpg", link: "https://store.steampowered.com/app/377160/Fallout_4/" },
      { path: "/images/crash.jpg", link: "https://store.steampowered.com/app/1378990/Crash_Bandicoot_4_Its_About_Time/" },
      { path: "/images/creed.jpg", link: "https://store.steampowered.com/app/911400/Assassins_Creed_III_Remastered/" },
      { path: "/images/creeper.jpg", link: "https://www.minecraft.net/en-us/store/minecraft-java-bedrock-edition-pc" },
      { path: "/images/dishonored.jpg", link: "https://store.steampowered.com/app/403640/Dishonored_2/" },
      { path: "/images/dragonborn.jpg", link: "https://store.steampowered.com/app/489830/The_Elder_Scrolls_V_Skyrim_Special_Edition/" },
      { path: "/images/gow.jpg", link: "https://store.steampowered.com/app/1593500/God_of_War/" },
      { path: "/images/halo.jpg", link: "https://store.steampowered.com/app/976730/Halo_The_Master_Chief_Collection/" },
      { path: "/images/little-nightmares.jpg", link: "https://store.steampowered.com/app/424840/Little_Nightmares/" },
      { path: "/images/lou.jpg", link: "https://store.steampowered.com/app/1888930/The_Last_of_Us_Part_I/" },
      { path: "/images/miles.jpg", link: "https://store.steampowered.com/app/1817190/Marvels_SpiderMan_Miles_Morales/" },
      { path: "/images/pika.jpg", link: "https://pokemon-planet.com/" }
    ];
  let isVisible = false;

  onMount(() => {
    function handleScroll() {
      const scrollPosition = window.scrollY || document.documentElement.scrollTop;
      isVisible = scrollPosition >= 1100;
    }

 window.addEventListener('scroll', handleScroll);
    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });

</script>
<!-- end script section -->
<!-- Html for the card flip gallery -->
<h1>A collection of epic games!!</h1>
  <div class="card-flip-container {`flipping-card-container ${isVisible ? 'visible' : ''}`}">
    {#each images as image, index}
      <div class="flipping-card">
        <div class="flipping-card-inner">
          <div class="flipping-card-front">
            <img src={image.path} alt="Image {index + 1}">
          </div>
            <div class="flipping-card-back">
            <a href={image.link} target="_blank">Click me!</a>
          </div>
        </div>
      </div>
    {/each}
  </div>
<div class="come-into-view-container">
</div>
<!-- end html section -->

<style>
   /* Styles for the cards that create the flipping, glow and other effects seen*/
  .card-flip-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    grid-gap: 10px;
    justify-items: center;
    height: auto;
    margin-top: 20px;
    margin-bottom: 20px;
    max-width: 100%;
  }

  .flipping-card {
    background-color: transparent;
    width: 100%;
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
    box-shadow: 0 0 100px 30px rgb(255, 74, 2);
  }

  .flipping-card-front, .flipping-card-back {
    box-shadow: 0 0px 24px 5px rgb(245, 112, 24);
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
    border: 1px solid rgb(245, 112, 24);
    border-radius: 1rem;
  }

  .flipping-card-front img, .flipping-card-back img {
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

  a {
    text-decoration: none;
    color: rgb(245, 112, 24);
  }

  a:hover {
    text-decoration: underline;
    color: rgb(255, 167, 109);
  }

  .flipping-card-container.visible .flipping-card {
    opacity: 1;
    transition: opacity 1.5s ease;
  }

  .flipping-card-container:not(.visible) .flipping-card {
    opacity: 0;
    transition: opacity 1.5s ease;
  }

  .come-into-view-container {
    margin-top: 100px;
  }
</style>
