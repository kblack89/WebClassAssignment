<div class="container">
    {#if isImageVisible}
      <img class="image visible" src="images/tardis.jpg" alt="Your Image" />
    {:else}
      <img class="image" src="images/tardis.jpg" alt="Your Image" />
    {/if}
    <div class="content">
      <p>This is the text that becomes visible on hover.</p>
    </div>
  </div>
  