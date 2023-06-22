<nav>
    <div class="topnav">
        <button onclick="window.location.href = '/';">Main </button>
        <button onclick="window.location.href = '/about';">About </button>
    </div>
</nav>

<style>
.topnav {
  position: fixed;
  inset:0 0 auto 0;
  display: flex;
  justify-content: center;
  opacity: 0;
  transform: translateY(-20px);
  animation: fadeIn 1s forwards;
  transition: opacity 1.5s;
  background-color: #000000;
  padding: 10px;
  z-index: 1000;
}


.topnav button {
  position:relative;
  text-align: center;
  padding: 20px 60px;
  border-radius: 7px;
  border: 1px solid rgb(245, 112, 24);
  font-size: 14px;
  text-transform: uppercase;
  font-weight: 600;
  letter-spacing: 5px;
  background: transparent;
  color:rgb(245, 112, 24);
  overflow: hidden;
  box-shadow: 0 0 0 0 transparent;
  -webkit-transition: all 0.2s ease-in;
  -moz-transition: all 0.2s ease-in;
  transition: all 0.2s ease-in;
  margin: 10px;
}

button:hover {
  background: rgb(49, 27, 1);
  box-shadow: 0 0 10px 5px rgb(245, 112, 24);
  -webkit-transition: all 0.2s ease-out;
  -moz-transition: all 0.2s ease-out;
  transition: all 0.2s ease-out;
}

button:hover::before {
  -webkit-animation: sh02 0.5s 0s linear;
  -moz-animation: sh02 0.5s 0s linear;
  animation: sh02 0.5s 0s linear;
}

button::before {
  content: '';
  display: block;
  width: 0px;
  height: 86%;
  position: absolute;
  top: 7%;
  left: 0%;
  opacity: 0;
  background: #fff;
  box-shadow: 0 0 50px 30px rgb(134, 134, 134);
  -webkit-transform: skewX(-20deg);
  -moz-transform: skewX(-20deg);
  -ms-transform: skewX(-20deg);
  -o-transform: skewX(-20deg);
  transform: skewX(-20deg);
}
@keyframes fadeIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}


@keyframes sh02 {
  from {
    opacity: 0;
    left: 0%;
  }

  50% {
    opacity: 1;
  }

  to {
    opacity: 0;
    left: 100%;
  }
}

button:active {
  box-shadow: 0 0 0 0 transparent;
  -webkit-transition: box-shadow 0.2s ease-in;
  -moz-transition: box-shadow 0.2s ease-in;
  transition: box-shadow 0.2s ease-in;
}

</style>
