<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Birthday Cake</title>

<style>

body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    background:radial-gradient(circle,#1b0033,#000);
    font-family:Arial;
    overflow:hidden;
}

/* title */
h1{
    color:white;
    margin-bottom:40px;
    text-shadow:0 0 20px pink;
}

/* cake */
.cake{
    position:relative;
    cursor:pointer;
    transition:0.5s;
}

.layer{
    width:240px;
    height:120px;
    background:white;
    border-radius:20px;
    box-shadow:0 10px 25px rgba(0,0,0,0.5);
}

.icing{
    width:240px;
    height:45px;
    background:#8a4fff;
    border-radius:20px 20px 0 0;
    position:absolute;
    top:0;
}

/* candles */
.candles{
    position:absolute;
    top:-60px;
    width:100%;
    display:flex;
    justify-content:space-around;
}

.candle{
    width:12px;
    height:45px;
    background:#eee;
    border-radius:4px;
    position:relative;
}

.flame{
    width:14px;
    height:20px;
    background:orange;
    border-radius:50%;
    position:absolute;
    top:-20px;
    left:-1px;
    animation:flicker .25s infinite alternate;
    box-shadow:0 0 15px orange;
}

@keyframes flicker{
    from{transform:scale(1);}
    to{transform:scale(1.3);opacity:.6;}
}

/* explosion hearts */
.heart{
    position:absolute;
    color:pink;
    font-size:20px;
    animation:fly 2s linear forwards;
}

@keyframes fly{
    to{
        transform:translateY(-300px) scale(2);
        opacity:0;
    }
}

</style>
</head>

<body>

<h1>🎉 Happy Birthday 🎉</h1>

<div class="cake" onclick="explode()">

<div class="candles">
<div class="candle"><div class="flame"></div></div>
<div class="candle"><div class="flame"></div></div>
<div class="candle"><div class="flame"></div></div>
</div>

<div class="icing"></div>
<div class="layer"></div>

</div>

<!-- music -->
<audio id="music">
<source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<script>

function explode(){

document.getElementById("music").play();

for(let i=0;i<25;i++){
let heart=document.createElement("div");
heart.className="heart";
heart.innerHTML="💖";

heart.style.left=Math.random()*window.innerWidth+"px";
heart.style.top="60%";

document.body.appendChild(heart);

setTimeout(()=>heart.remove(),2000);
}
}

</script>

</body>
</html>
