<script>

  let m = { x: 0, y: 0 };

  let top = 0;
  let left = 0;

  function handleMousemove(event) {
    m.x = event.offsetX;
    m.y = event.offsetY;
    console.log(m);

    top = -m.y / 20;
    left = -m.x / 20;
  }

</script>

<div id="follow" on:mousemove={handleMousemove}>
  <div class ="imageHolder" style="top:{top}px;left:{left}px">
    <img src="/images/jokerme.png" alt="me as joker">
  </div>
</div>

<style>

  #follow{
    margin:auto;
    position: relative;
    width:600px;
    overflow:hidden;
    height:600px;
    border-radius: 100%;
  }

  .imageHolder{
    pointer-events: none;
    position: absolute;
  }
  .imageHolder img{

   
    width:600px;

    height:400px;
   
  }


</style>


