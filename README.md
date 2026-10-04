# birthday-surprise-page
Birthday surprise interactive webpage for a special celebration
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Birthday Surprise 🎂✨</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html,body{
    width:100%;
    height:100%;
    overflow:hidden;
    font-family:Arial,sans-serif;
}

body{
    background:
      radial-gradient(circle at 50% 30%,#5b0a6f 0%,#21002f 35%,#07000d 100%);
    color:white;
}

/* ---------- BACKGROUND ---------- */

.stars{
    position:fixed;
    inset:0;
    overflow:hidden;
}

.star{
    position:absolute;
    width:3px;
    height:3px;
    background:white;
    border-radius:50%;
    box-shadow:0 0 10px white;
    animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
    from{opacity:.2;transform:scale(.5)}
    to{opacity:1;transform:scale(1.5)}
}


/* ---------- BLUE BUTTERFLIES ---------- */

.butterfly{
    position:fixed;
    bottom:-80px;
    font-size:28px;
    z-index:4;
    pointer-events:none;

    filter:
      drop-shadow(0 0 6px #00bfff)
      drop-shadow(0 0 15px #008cff);

    animation:
      butterflyFly linear infinite,
      butterflyWings .35s ease-in-out infinite alternate;
}

@keyframes butterflyFly{

    0%{
        transform:
          translate3d(0,0,0)
          rotate(-10deg);
        opacity:0;
    }

    10%{
        opacity:1;
    }

    25%{
        transform:
          translate3d(80px,-25vh,0)
          rotate(10deg);
    }

    50%{
        transform:
          translate3d(-70px,-50vh,0)
          rotate(-8deg);
    }

    75%{
        transform:
          translate3d(100px,-75vh,0)
          rotate(12deg);
    }

    100%{
        transform:
          translate3d(-40px,-120vh,0)
          rotate(-10deg);
        opacity:0;
    }
}

@keyframes butterflyWings{
    from{
        filter:
          drop-shadow(0 0 5px #00bfff)
          drop-shadow(0 0 10px #008cff);
    }

    to{
        filter:
          drop-shadow(0 0 12px #00e5ff)
          drop-shadow(0 0 25px #006eff);
    }
}


/* ---------- OPEN SCREEN ---------- */

#intro{
    position:fixed;
    inset:0;
    z-index:100;
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    background:
      radial-gradient(circle,#5c0873,#17001f 70%);
    transition:1s;
}

.introTitle{
    font-size:18px;
    letter-spacing:5px;
    opacity:.8;
}

.gift{
    font-size:100px;
    margin:25px;
    cursor:pointer;
    filter:drop-shadow(0 0 25px #ff4fd8);
    animation:giftFloat 1.5s infinite ease-in-out;
}

@keyframes giftFloat{
    0%,100%{
        transform:translateY(0) rotate(-4deg)
    }

    50%{
        transform:translateY(-15px) rotate(4deg)
    }
}

.openText{
    font-size:16px;
    padding:12px 25px;
    border:1px solid #ff69d8;
    border-radius:30px;
    box-shadow:0 0 20px #ff1493;
}


/* ---------- MAIN ---------- */

.main{
    position:relative;
    z-index:5;
    width:100%;
    height:100%;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    padding:20px;
}

.content{
    animation:appear 1.5s ease;
}

@keyframes appear{
    from{
        opacity:0;
        transform:scale(.7) translateY(40px);
    }

    to{
        opacity:1;
        transform:scale(1) translateY(0);
    }
}

.top{
    font-size:15px;
    letter-spacing:5px;
    color:#ffd6fa;
}

h1{
    margin-top:12px;
    font-size:clamp(48px,13vw,105px);
    line-height:.9;
    font-weight:900;

    background:linear-gradient(
      90deg,
      #fff,
      #ff9bea,
      #ffd700,
      #fff,
      #ff70d9
    );

    background-size:300%;
    -webkit-background-clip:text;
    color:transparent;

    animation:
      gradient 4s linear infinite,
      glow 2s ease-in-out infinite alternate;
}

@keyframes gradient{
    0%{
        background-position:0%
    }

    100%{
        background-position:300%
    }
}

@keyframes glow{
    from{
        filter:drop-shadow(0 0 5px #ff69d8);
    }

    to{
        filter:
        drop-shadow(0 0 15px #ff1493)
        drop-shadow(0 0 35px #9b00ff);
    }
}

.name{
    margin-top:20px;
    font-size:clamp(28px,7vw,55px);
    font-weight:bold;
    color:#ffd700;

    text-shadow:
      0 0 10px #ffd700,
      0 0 30px #ff8c00;
}

.message{
    max-width:600px;
    margin:20px auto;
    font-size:17px;
    line-height:1.7;
    color:#f9eafa;
}


/* ---------- CAKE ---------- */

.cake{
    position:relative;
    width:150px;
    height:75px;
    margin:45px auto 20px;
    border-radius:12px;

    background:linear-gradient(
      #ff72c6,
      #d92c8d
    );

    box-shadow:
      0 10px 30px #ff1493,
      inset 0 8px 10px rgba(255,255,255,.3);
}

.cake:before{
    content:"";
    position:absolute;
    width:150px;
    height:30px;
    top:-15px;
    left:0;
    background:#fff;
    border-radius:50%;
}

.cake:after{
    content:"🎀";
    position:absolute;
    left:58px;
    bottom:15px;
    font-size:30px;
}

.candle{
    position:absolute;
    width:12px;
    height:45px;

    background:
      linear-gradient(
        90deg,
        #fff,
        #ffd700,
        #fff
      );

    top:-55px;
    left:69px;
    border-radius:5px;
    z-index:2;
}

.flame{
    position:absolute;
    width:18px;
    height:25px;
    left:-3px;
    top:-25px;

    border-radius:50%;

    background:
      linear-gradient(
        #fff,
        #ffd700,
        #ff4500
      );

    box-shadow:0 0 20px #ffae00;

    animation:
      flame .4s infinite alternate;
}

@keyframes flame{
    from{
        transform:scale(.9) rotate(-4deg)
    }

    to{
        transform:scale(1.15) rotate(5deg)
    }
}


/* ---------- BUTTON ---------- */

button{
    border:none;
    outline:none;

    padding:15px 30px;

    border-radius:50px;

    font-size:16px;
    font-weight:bold;

    color:white;

    background:
      linear-gradient(
        45deg,
        #ff1493,
        #8a2be2
      );

    box-shadow:
      0 0 15px #ff1493,
      0 0 35px rgba(255,20,147,.4);

    cursor:pointer;

    animation:
      pulse 1.8s infinite;
}

@keyframes pulse{
    0%,100%{
        transform:scale(1);
    }

    50%{
        transform:scale(1.06);
    }
}


/* ---------- BALLOONS ---------- */

.balloon{
    position:fixed;

    width:55px;
    height:70px;

    border-radius:50%;

    bottom:-100px;

    z-index:2;

    animation:
      balloonUp 8s linear infinite;
}

.balloon:after{
    content:"";

    position:absolute;

    width:1px;
    height:110px;

    background:#ffffffaa;

    top:68px;
    left:50%;
}

.b1{
    left:7%;

    background:#ff3b81;

    box-shadow:
      0 0 20px #ff3b81;

    animation-delay:0s;
}

.b2{
    left:25%;

    background:#00e5ff;

    box-shadow:
      0 0 20px #00e5ff;

    animation-delay:2s;
}

.b3{
    right:25%;

    background:#ffd700;

    box-shadow:
      0 0 20px #ffd700;

    animation-delay:4s;
}

.b4{
    right:7%;

    background:#9d4edd;

    box-shadow:
      0 0 20px #9d4edd;

    animation-delay:1s;
}

@keyframes balloonUp{

    0%{
        transform:
          translateY(0)
          rotate(-5deg);
    }

    100%{
        transform:
          translateY(-120vh)
          rotate(8deg);
    }
}


/* ---------- HEARTS ---------- */

.heart{
    position:fixed;

    bottom:-30px;

    font-size:22px;

    z-index:3;

    animation:
      heartUp 6s linear infinite;
}

@keyframes heartUp{

    0%{
        transform:
          translateY(0)
          scale(.5);

        opacity:0;
    }

    15%{
        opacity:1
    }

    100%{
        transform:
          translateY(-110vh)
          scale(1.3)
          rotate(20deg);

        opacity:0;
    }
}


/* ---------- FINAL MESSAGE ---------- */

#final{
    position:fixed;
    inset:0;

    z-index:200;

    background:
      rgba(10,0,18,.96);

    display:none;

    align-items:center;
    justify-content:center;

    text-align:center;

    padding:25px;
}

.finalBox{
    max-width:600px;

    animation:
      finalIn 1s ease;
}

.finalEmoji{
    font-size:70px;
}

.finalBox h2{
    margin:20px 0;

    font-size:
      clamp(35px,9vw,65px);

    color:#ffd700;

    text-shadow:
      0 0 25px #ff1493;
}

.finalBox p{
    font-size:18px;

    line-height:1.8;

    color:#f7dff5;
}

.from{
    margin-top:25px;

    color:#ff69d8;

    font-size:20px;
}

@keyframes finalIn{

    from{
        opacity:0;
        transform:scale(.5);
    }

    to{
        opacity:1;
        transform:scale(1);
    }
}

</style>
</head>

<body>


<!-- INTRO -->

<div id="intro" onclick="openGift()">

    <div class="introTitle">
        A SPECIAL SURPRISE FOR YOU
    </div>

    <div class="gift">
        🎁
    </div>

    <div class="openText">
        TAP THE GIFT TO OPEN ✨
    </div>

</div>


<!-- STARS -->

<div class="stars">

    <span class="star" style="left:8%;top:12%"></span>
    <span class="star" style="left:18%;top:30%"></span>
    <span class="star" style="left:32%;top:10%"></span>
    <span class="star" style="left:48%;top:25%"></span>
    <span class="star" style="left:65%;top:12%"></span>
    <span class="star" style="left:82%;top:25%"></span>
    <span class="star" style="left:92%;top:10%"></span>
    <span class="star" style="left:12%;top:65%"></span>
    <span class="star" style="left:88%;top:70%"></span>

</div>


<!-- BLUE BUTTERFLIES -->

<div class="butterfly" style="left:5%;animation-duration:10s;animation-delay:0s;">
    🦋
</div>

<div class="butterfly" style="left:18%;font-size:22px;animation-duration:12s;animation-delay:2s;">
    🦋
</div>

<div class="butterfly" style="left:32%;font-size:35px;animation-duration:9s;animation-delay:4s;">
    🦋
</div>

<div class="butterfly" style="left:48%;font-size:25px;animation-duration:11s;animation-delay:1s;">
    🦋
</div>

<div class="butterfly" style="left:63%;font-size:32px;animation-duration:10s;animation-delay:5s;">
    🦋
</div>

<div class="butterfly" style="left:78%;font-size:24px;animation-duration:13s;animation-delay:3s;">
    🦋
</div>

<div class="butterfly" style="left:90%;font-size:30px;animation-duration:9s;animation-delay:6s;">
    🦋
</div>


<!-- BALLOONS -->

<div class="balloon b1"></div>
<div class="balloon b2"></div>
<div class="balloon b3"></div>
<div class="balloon b4"></div>


<!-- MAIN -->

<div class="main">

    <div class="content">

        <div class="top">
            ✨ TODAY IS YOUR SPECIAL DAY ✨
        </div>

        <h1>
            HAPPY<br>
            BIRTHDAY
        </h1>

        <div class="name">
            🦋 MANORANJANI 🦋
        </div>

        <div class="message">

            Wishing you a day filled with endless smiles,
            beautiful memories, happiness and lots of love. 🥳

            <br>

            May every moment of your life shine brighter! ✨

        </div>


        <!-- CAKE -->

        <div class="cake">

            <div class="candle">

                <div class="flame"></div>

            </div>

        </div>


        <button onclick="surprise(event)">
            🎁 OPEN YOUR SURPRISE
        </button>

    </div>

</div>


<!-- FINAL -->

<div id="final">

    <div class="finalBox">

        <div class="finalEmoji">
            🎂🦋💖
        </div>

        <h2>
            HAPPY BIRTHDAY🎊!
        </h2>

        <p>

            Hope you thi was your
            unforgettable moments.

            keep smile on your face🤗🌟

            <br><br>

            Keep smiling and keep shining! 💫

        </p>

        <div class="from">
            by RIO 🫠💝
        </div>

    </div>

</div>


<script>


/* OPEN GIFT */

function openGift(){

    const intro =
        document.getElementById("intro");

    intro.style.opacity="0";

    intro.style.transform=
        "scale(1.3)";

    setTimeout(()=>{

        intro.style.display="none";

        createHearts();

    },900);

}


/* SURPRISE */

function surprise(e){

    e.stopPropagation();

    document.getElementById("final")
        .style.display="flex";

    fireworks();

}


/* HEARTS */

function createHearts(){

    setInterval(()=>{

        const heart =
            document.createElement("div");

        heart.className="heart";

        heart.innerHTML =
            ["❤️","💖","💗","💕","✨"]
            [Math.floor(Math.random()*5)];

        heart.style.left =
            Math.random()*100+"vw";

        heart.style.animationDuration =
            (4+Math.random()*4)+"s";

        document.body.appendChild(heart);

        setTimeout(()=>{

            heart.remove();

        },8000);

    },700);

}


/* CONFETTI + FIREWORKS */

function fireworks(){

    for(let i=0;i<150;i++){

        const piece =
            document.createElement("div");

        piece.style.position="fixed";

        piece.style.width="8px";

        piece.style.height="8px";

        piece.style.left="50%";

        piece.style.top="50%";

        piece.style.zIndex="999";

        piece.style.background =
            [
                "#ff1493",
                "#ffd700",
                "#00e5ff",
                "#7fff00",
                "#ffffff",
                "#ff69b4"
            ]
            [Math.floor(Math.random()*6)];

        piece.style.borderRadius =
            Math.random()>0.5
            ? "50%"
            : "0";

        document.body.appendChild(piece);

        const angle =
            Math.random()*Math.PI*2;

        const distance =
            150+Math.random()*400;

        const x =
            Math.cos(angle)*distance;

        const y =
            Math.sin(angle)*distance;

        piece.animate(

            [
                {
                    transform:
                        "translate(-50%,-50%) scale(1)",

                    opacity:1
                },

                {
                    transform:
                        `translate(
                            calc(-50% + ${x}px),
                            calc(-50% + ${y}px)
                        )
                        rotate(720deg)
                        scale(0)`,

                    opacity:0
                }

            ],

            {
                duration:
                    1200+Math.random()*1000,

                easing:
                    "cubic-bezier(.1,.8,.2,1)"
            }

        );

        setTimeout(()=>{

            piece.remove();

        },2500);

    }

}

</script>

</body>
</html>