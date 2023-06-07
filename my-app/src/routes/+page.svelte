<script>
// @ts-nocheck

  import  GalleryTop  from '$lib/gallery-slideshow.svelte';
  import  CardFlip  from '$lib/card-flip.svelte';
 import TopDisp from '$lib/top-content-disp.svelte';
  import ComeIntoView from '../lib/come-into-view.svelte';
  import RandomPokemon from '$lib/poke-api.svelte';
  import NavDisp from  '$lib/navigation.svelte';
  import CardExpand from  '$lib/card-expand.svelte';
  import FollowMouse from '$lib/follow-mouse-div.svelte';

  import Footer from '$lib/footer.svelte';


  
  </script>



<link rel="stylesheet" href="\src\main.css">
<div>
<NavDisp />
</div>

<div class="title-section ">
<TopDisp />
  </div>


 <div class = "general-section">
  <!--This section will display an image gallery that moves right when scrolled up and left when scrolled right.Content will be images from my room-->
   <GalleryTop />
</div> 


<div class = "general-section">
   <!--This section will display an collection of cards that will animate and flip over when clicked then show link </h2>
  Content will be a selection of games I</p>-->
    <CardFlip />
</div>

<div class = "general-section">
<ComeIntoView />

 <!--This section will display a few images with big text beside them that moves into view when the section is scrolled </h2>
  <p>Content will be images showing movies I like</p>-->
</div>

<div class = "general-section">
<RandomPokemon />
  <!--This section will display api data to show a random api when the button is clicked.m it will display a different background depending on the pokemon type-->
</div>

<div class = "general-section">
<CardExpand />
 <!--This section will display an image gallery that expands each image and blurs out the rest when hovered over</h2>
  <p>Content will be horror, fantasy and sci-fi art-->
</div>

<div class = "general-section">
 <FollowMouse />
  <!--This section will display text around an image that moves slowly a small amount of pixels in the opposite direction the mouse moves when hovered over it.
  Content will be an image of me-->
</div>

<Footer />


