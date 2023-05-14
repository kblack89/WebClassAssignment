
<style>
  /* Slideshow container */
  .slideshow-container {
    max-width: 500px;
    position: relative;
    margin: auto;
  }

  /* Hide the images by default */
  .mySlides {
    display: none;
  }
</style>

<div class="slideshow-container">
  <!-- Slides -->
  <div class="mySlides">
    <img src="/images/pc.jpg" alt="A pc" style="width:100%">
  </div>

  <div class="mySlides">
    <img src="/images/keyboard.jpg" alt="A keyboard" style="width:100%">
  </div>

  <div class="mySlides">
    <img src="/images/pc.jpg" alt="Same pc again" style="width:100%">
  </div>
</div>

<script>
  var slides = document.querySelectorAll('.slideshow-container img');
  var currentSlideIndex = 0;

  function showNextSlide() {
    slides[currentSlideIndex].classList.remove('slide-in');
    currentSlideIndex = (currentSlideIndex + 1) % slides.length;
    slides[currentSlideIndex].classList.add('slide-in');
  }

  setInterval(showNextSlide, 2000);
</script>