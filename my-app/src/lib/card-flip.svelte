<div class ="flipping-card">
    <div class ="flipping-card-inner">
        <div class ="flipping-card-front">
            <p class ="title">Hi</p>
            <p>hover over</p>
        </div>
        <div class ="flipping-card-back">
            <p class ="title">Bye</p>
            <p>See ya later!</p>
        </div>
    </div>
</div>
<div class ="flipping-card">
    <div class ="flipping-card-inner">
        <div class ="flipping-card-front">
            <p class ="title">Hi</p>
            <p>hover over</p>
        </div>
        <div class ="flipping-card-back">
            <p class ="title">Bye</p>
            <p>See ya later!</p>
        </div>
    </div>
</div>
<div class ="flipping-card">
    <div class ="flipping-card-inner">
        <div class ="flipping-card-front">
            <p class ="title">Hi</p>
            <p>hover over</p>
        </div>
        <div class ="flipping-card-back">
            <p class ="title">Bye</p>
            <p>See ya later!</p>
        </div>
    </div>
</div>

<style>

.flipping-card {
    background-color: transparent;
    width: 200px;
    height: 260px;
    perspective: 1000px;
}

.title {
    font-size: 1.5em;
    font-weight:900;
    text-align: center;
    margin: 0;
}
.flipping-card-inner {
position: relative;
width: 100%;
height: 100%;
text-align: center;
transition: transform 0.8s;
transform-style: preserve-3d;
}

.flipping-card:hover .flipping-card-inner {
transform: rotateY(180deg);
    }

.flipping-card-front, .flipping-card-back {
box-shadow: 0 8px 14px 0 rgba(0, 0, 0, 0.2);
position: absolute;
display: flex;
flex-direction: column;
justify-content: center;
width: 100%;
height: 100%;
-webkit-backface-visibility: hidden;
backface-visibility: hidden;
border: 1px solid coral;
border-radius: 1rem;
 }

 .flipping-card-front {
    background: linear-gradient(120deg, bisque 60%, rbg(225, 231, 222) 88%,
    rgb(255, 211, 195) 40% rgba(255, 127, 80, 0.603) 48%);
    color: coral;
 }
 .flipping-card-back {
    background: linear-gradient(120deg, rbg(225, 174, 145) 30%, coral 88%,
    bisque 40%, rgb(255, 185, 160)78%);
    color: white;
    transform: rotateY(180deg);
 }

</style>
