<script>
// @ts-nocheck
  import GalleryTop  from '$lib/gallery-slideshow.svelte';
  import CardFlip  from '$lib/card-flip.svelte';
  import TopDisp from '$lib/top-content-disp.svelte';
  import ComeIntoView from '../lib/come-into-view.svelte';
  import RandomPokemon from '$lib/poke-api.svelte';  
  import CardExpand from  '$lib/card-expand.svelte';
  import FollowMouse from '$lib/follow-mouse-div.svelte';
  import Footer from '$lib/footer.svelte';
</script>

<div class="title-section ">
  <TopDisp />
</div>

<div class = "general-section">
  <GalleryTop />
</div> 

<div class = "general-section">
<CardFlip />
</div>

<div class = "general-section">
<ComeIntoView />
</div>

<div class = "general-section">
<RandomPokemon />
 </div>

<div class = "general-section">
<CardExpand />
 </div>

<div class = "general-section">
 <FollowMouse />
 </div>

<Footer />


