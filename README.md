# Raksha-Bandhan

<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>Happy Raksha</title>

        <link rel="stylesheet" href="Raksha.css">
    </head>
    <body>
        <div class="box">
            <div class="block">
                <span style="--i:0;"></span>
                <span style="--i:1;"></span>
                <span style="--i:2;"></span>
                <span style="--i:3  ;"></span>
            </div>

            <div class="text">
                <span style="--i:0;" data-text="Happy">Happy</span>
                <span style="--i:1;" data-text="Raksha">Raksha</span>
                <span style="--i:2;" data-text="Bandhan">Bandhan</span>
                <span style="--i:3;COLOR:blue;" data-text="2023">2023</span>
            </div>
        </div>
    </body>
</html>

/* css */
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@700&display=swap');

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Oswald', sans-serif;
}

body{
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background:#333;
}

.box{
    position: relative;
    height: 200px;
    transform-style: preserve-3d;
    animation: animate 5s linear infinite;
}
@keyframes animate{
    0%{
        transform: rotateX(-20deg) rotateY(360deg);
    }
    100%{
        transform: rotateX(-20deg) rotateY(0deg);
    }
}
.box div{
    position: absolute;
    inset: 0;
    transform-style: preserve-3d;
}
.box div.block span{
    position: absolute;
    width: 200px;
    left: calc(50% - 100px);
    height: 100px;
    background: #444;
    transform: rotateY(calc(90deg * var(--i))) translateZ(100px);
    transition: 0.5s;

}
.box:hover div.block span{
    background: #f00;
    filter: drop-shadow(0 0 10px #fff);
}

.box div.text span{
    position: absolute;
    width: 100%;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    transform: rotateY(calc(90deg * var(--i))) translateZ(150px);
    cursor: pointer;
    color: #fff;
    font-size: 4em;
    text-transform: uppercase;
    z-index: 10;
    line-height: 1em;
    -webkit-text-stroke: 1px #000;
    transform-style: preserve-3d;

}

.box div.text span:nth-child(1){
    font-size: 6em;
}
.box div.text span::before{
    content: attr(data-text);
    position: absolute;
    bottom: 7px;
    transform-origin: bottom;
    transform: rotateX(-90deg);
    color: rgba(0,0,0,0.1);
    -webkit-text-stroke: 0px #000;
    filter: blur(5px);
}
.box div.text span::after{
    content:'';
    position: absolute;
    top: 100px;
    width: 360px;
    height: 60px;
    background: #444;
    transform: rotateX(-90deg);
    transition: 0.5s;
}
.box:hover div.text span::after{
    background: #f00;
    filter: drop-shadow(0 0 50px #f00);
}
