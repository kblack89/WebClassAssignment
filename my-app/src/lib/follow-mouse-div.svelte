<div id="follow">
  <img src="/images/jokerme.png" alt="me as joker">
</div>

<style>
#follow {
  position: absolute;
  text-align: center;
  cursor: pointer;
  transition: transform 0.3s ease;
}

#follow img {
  transform: translate(0, 0);
  
}

#follow:hover img {
  transform: translate(calc(-50% + var(--mouse-x)), calc(-50% + var(--mouse-y)));
}
</style>

<script>
document.addEventListener('mousemove', (e) => {
  const follow = document.getElementById('follow');
  if (follow) {
    follow.style.setProperty('--mouse-x', e.clientX + 'px');
    follow.style.setProperty('--mouse-y', e.clientY + 'px');
  }
});
</script>
