<script>
// @ts-nocheck

  import  GalleryTop  from '$lib/gallery-slideshow.svelte';
  import  CardFlip  from '$lib/card-flip.svelte';
 
  import ComeIntoView from '../lib/come-into-view.svelte';
  import RandomPokemon from '$lib/poke-api.svelte';
  
  </script>

<link rel="stylesheet" href="\src\main.css">
<div class="topnav">
  <a href="/">Main</a>
  <a href="#news">News</a>
  <a href="#contact">Contact</a>
  <a href="/about">About</a>
</div>

<div class="title-section ">
  <h2 class = "TitlePt1">KYLE BLACK</h2>
  <h5 class = "TitlePt2">A GUIDE TO EPICNESS!</h5>
  <div class="titleimage"></div> 
  <h5 class = "TitlePt3">The many Hobbies, Interests and Passsions I have.</h5>

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
  <!--This section will display api data to show a random api when the button is clicked</h2>
  <p>Content will be an image from the poki api-->
</div>

<div class = "general-section">
  <br>
  <br>
  <br>
  <br>
  <h2 >This section will display an image gallery that expands each image and blurs out the rest when hovered over</h2>
  <p>Content will be horror, fantasy and sci-fi art</p>
</div>

<div class = "general-section">
  <br>
  <br>
  <br>
  <br>
  <h2 >This section will display text around an image that moves slowly a small amount of pixels in the opposite direction the mouse moves when hovered over it</h2>
  <p>Content will be an image of me</p>
</div>





<footer>

</footer>

