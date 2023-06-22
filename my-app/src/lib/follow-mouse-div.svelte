<script>
  //Script that deals with the mouse movement event
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
<!-- end script section -->

<!-- Html for the image that moves with the mouse -->
<div id="follow" on:mousemove={handleMousemove}>
  <div class ="imageHolder" style="top:{top}px;left:{left}px">
    <img src="/images/jokerme.png" alt="me as joker">
  </div>
</div>
<!-- end Html section -->

<style>
  /* Styles for the content display and transforming*/
  #follow{
    margin:auto;
    position: relative;
    width:300px;
    overflow:hidden;
    height:400px;
    border-radius: 100%;
    background-color: rgba(0, 0, 0, 0);
  }

.imageHolder {
  pointer-events: none;
  position: absolute;
  top: 50%;
  left: 25%; 
  transform: translate(-20%, -5%);
  margin-top: 0px;
}
.imageHolder img{
  width:600px;
  height:400px;
     }

</style>


