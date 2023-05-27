<div class="title-section ">
  <h2 class = "TitlePt1">KYLE BLACK</h2>
  <h5 class = "TitlePt2">A GUIDE TO EPICNESS!</h5>
  <div class="titleimage"></div> 
  <h5 class = "TitlePt3">The many Hobbies, Interests and Passsions I have.</h5>

  </div>
  <style>


.TitlePt1
{
margin-right: 1200px;
color:coral;
animation: glow 2s ease-in-out infinite alternate;
transform: translate(0, 10vh);
  transition: all 1s;
 
}

.TitlePt2
{
margin-right: 1200px;
color:coral;
animation: glow 2s ease-in-out infinite alternate;
transform: translate(0, 10vh);
  transition: all 1s;

}

.TitlePt3
{
margin-left: 1000px;
margin-top: -180px;
color:coral;
animation: glow 2s ease-in-out infinite alternate;
transform: translate(0, 10vh);
  transition: all 1s;
  }




.title-section {
  background-color: rgba(0, 0, 0, 0.445);
  flex: 70%;
  padding: 80px;
  text-align: center;
  color: rgb(255, 255, 255);
  font-size: 50PX;
  height: 600px;
  margin-left: 100px;
  margin-right: 100px;
  animation: fadeIn 5s;  
}


.titleimage {
  background-image: url("/images/jokerme.png");
  color: #aaa;
  height:320px;
  width:500px;
  padding: 5px;
  display: grid;
  place-items: center;
  margin:0 auto;
  margin-top: -380px;
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
</style>