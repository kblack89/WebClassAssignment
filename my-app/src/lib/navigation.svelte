<nav>
    <div class="topnav">
        <button onclick="window.location.href = '/';">Main </button>
        <button onclick="window.location.href = '/about';">About </button>
    </div>
</nav>

<style>


.topnav {
      display: flex;
      justify-content: center;
      opacity: 0;
      transform: translateY(-20px);
      animation: slideIn 1.0s ease-out forwards;
    }

    @keyframes slideIn {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
  .nav-button {
      /* Your existing button styles */
      position: relative;
      padding: 10px 20px;
      border-radius: 7px;
      border: 1px solid rgb(61, 106, 255);
      font-size: 14px;
      text-transform: uppercase;
      font-weight: 600;
      letter-spacing: 2px;
      background: transparent;
      color: #fff;
      overflow: hidden;
      box-shadow: 0 0 0 0 transparent;
      -webkit-transition: all 2.2s ease-in;
      -moz-transition: all 2.2s ease-in;
      transition: all 2.2s ease-in;
    }


    button {
  position:relative;
  text-align: center;
  padding: 20px 60px;
  border-radius: 7px;
  border: 1px solid rgb(40, 15, 70);
  font-size: 14px;
  text-transform: uppercase;
  font-weight: 600;
  letter-spacing: 2px;
  background: transparent;
  color:coral;
  overflow: hidden;
  box-shadow: 0 0 0 0 transparent;
  -webkit-transition: all 0.2s ease-in;
  -moz-transition: all 0.2s ease-in;
  transition: all 0.2s ease-in;
}

button:hover {
  background: rgb(122, 32, 150);
  box-shadow: 0 0 30px 5px rgba(80, 11, 87, 0.815);
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
  box-shadow: 0 0 50px 30px #fff;
  -webkit-transform: skewX(-20deg);
  -moz-transform: skewX(-20deg);
  -ms-transform: skewX(-20deg);
  -o-transform: skewX(-20deg);
  transform: skewX(-20deg);
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
