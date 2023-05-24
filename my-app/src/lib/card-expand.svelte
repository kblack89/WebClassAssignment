<div id="card-container">
    <div class="card">
      <img src="images/tardis.jpg" alt="Image 1">
    </div>
    <div class="card">
      <img src="images/tardis.jpg" alt="Image 2">
    </div>
    <div class="card">
      <img src="images/tardis.jpg" alt="Image 3">
    </div>
    <!-- Repeat the above card structure for the remaining cards -->
  </div>

  <style>

.card-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 10px;
}

.card {
  position: relative;
  overflow: hidden;
  transition: 0.3s;
}

.card img {
  width: 10%;
  height: 10%;
  object-fit: cover;
}

.card:hover {
  transform: scale(1.1);
  z-index: 1;
}

.card:hover ~ .card {
  filter: blur(4px);
}
  </style>

  <script>

const cards = document.querySelectorAll('.card');

cards.forEach(card => {
  card.addEventListener('mouseenter', () => {
    cards.forEach(c => {
      if (c !== card) {
        c.classList.add('blur');
      }
    });
  });

  card.addEventListener('mouseleave', () => {
    cards.forEach(c => {
      c.classList.remove('blur');
    });
  });
});
  </script>