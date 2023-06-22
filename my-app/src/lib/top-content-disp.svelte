<div class="title-section">
  <div class="grid-container">
    <div class="titles">
      <h2 class="TitlePt1">KYLE BLACK</h2>
      <h5 class="TitlePt2">A GUIDE TO EPICNESS!</h5>
    </div>
    <div class="titleimage"></div>
    <h5 class="TitlePt3">The many Hobbies, Interests and<br> Passions I have.</h5>
  </div>
</div>
  <style>

.TitlePt1, .TitlePt2, .TitlePt3 {
  animation: glow 2s ease-in-out infinite alternate;
  transform: translate(0, 10vh);
  transition: all 1s;
}

.TitlePt1, .TitlePt2, .TitlePt3, .titleimage  { 
  display:flex;
  justify-content: flex-start;
}


.title-section {
  flex: 70%;
  padding: 80px;
  text-align: center;
  color: rgb(0, 0, 0);
  font-size: 50PX;
  height: auto;
  margin-left: 100px;
  margin-right: 100px;
  animation: fadeIn 5s;  
  color:rgb(245, 112, 24);
  height: auto;
}

.titleimage {
    background-image: url("/images/jokerme.png");
    color: #aaa;
    height: 320px;
    width: 50vh;
    padding: 5px;
    justify-content: center;
    align-items: center;
    position: relative;
    left: 50%;
  transform: translateX(-50%) translateY(-30%);
  }

@keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}
@keyframes glow {
  from {
    text-shadow: 0 0 5px rgba(255, 255, 255, 0.158), 0 0 10px rgba(255, 255, 255, 0), 0 0 15px #ff7c029d, 0 0 20x #ff7c028a, 0 0 25px #ff7c024d, 0 0 30px #ff7c0254, 0 0 35px #ff7c0260;
  }
  
  to {
    text-shadow: 0 0 5px rgba(255, 255, 255, 0.13), 0 0 10px #fca24e00, 0 0 15px #fca24e8f, 0 0 20px #fca24e7c, 0 0 25px #fca24e5b, 0 0 30px #fca24e4f, 0 0 35px #fca24e5b;
  }
}
.TitlePt3 {
  justify-content: flex-end;
  align-items: center;
  position: relative;
  transform: translateY(-50%);
  word-wrap: break-word;
  margin-top: 20px;
}

@media (max-width: 768px) {
  .grid-container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .titleimage {
    width:auto;
  }

  .TitlePt3 {
    position: static;
    margin-top: 10px;
    text-align: center;
  }
}

</style>