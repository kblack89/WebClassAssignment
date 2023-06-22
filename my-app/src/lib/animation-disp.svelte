<!-- Html for a looping video animation-->
<div class="video-container">
  <video autoplay loop src="\animation.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>
<!-- end html section -->

<style>
  /*styles to make the video the desired size*/
  .video-container video {
    position: absolute;
    transform: translate(-50%, 0%);
    width: 100%;
    height: 10%;
    object-fit: cover;
    height: 80vh;
  }
  
</style>