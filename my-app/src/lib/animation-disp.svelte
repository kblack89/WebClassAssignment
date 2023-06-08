<style>
    .video-container {
      position: relative;
      width: 100%;
      height: 100vh; /* Adjust the height as needed */
    }
  
    .video-container video {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 100%; /* Set the initial width */
      height: 50%; /* Set the initial height */
      object-fit: cover;
    }
  </style>
  
  <div class="video-container">
    <video autoplay loop>
      <source src="\animation.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </div>
  