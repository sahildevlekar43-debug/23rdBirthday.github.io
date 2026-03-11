<!DOCTYPE html>
<html>
<head>

<title>Happy Birthday Shreya ❤️</title>

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta name="theme-color" content="#ff4d6d">

<link rel="manifest" href="manifest.json">

<meta name="apple-mobile-web-app-capable" content="yes">

<style>

body{
margin:0;
font-family:'Segoe UI',sans-serif;
background:#0f0f0f;
color:white;
text-align:center;
overflow-x:hidden;
}

section{
padding:40px 20px;
}

.hero{
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
}

button{
padding:14px 30px;
font-size:18px;
border:none;
border-radius:40px;
background:#ff4d6d;
color:white;
cursor:pointer;
margin-top:20px;
}

.timer{
color:#ff4d6d;
font-size:22px;
font-weight:bold;
}

.gallery{
display:flex;
overflow-x:auto;
gap:15px;
padding:20px;
}

.gallery img{
width:220px;
border-radius:20px;
}

.message{
max-width:500px;
margin:auto;
line-height:1.8;
color:#d6d6d6;
font-size:18px;
}

.hidden{
display:none;
}

.heart{
position:fixed;
bottom:-20px;
color:#ff4d6d;
animation:float 6s linear infinite;
}

@keyframes float{
0%{transform:translateY(0)}
100%{transform:translateY(-110vh)}
}

.cake{
font-size:80px;
cursor:pointer;
margin-top:20px;
}

</style>

</head>

<body>


<section class="hero" id="start">

<h1>Shreya ❤️</h1>

<p>Sahil made something special for you</p>

<button onclick="startSite()">Are you ready for your surprise?</button>

</section>


<div id="main" class="hidden">


<section>

<h2>You've been my world for</h2>

<div class="timer" id="timer"></div>

</section>


<section>

<h2>Our Memories 📸</h2>

<div class="gallery">

<img src="photo1.jpg">
<img src="photo2.jpg">
<img src="photo3.jpg">
<img src="photo4.jpg">

</div>

</section>


<section>

<h2>A Message For You 💌</h2>

<p class="message" id="typeText"></p>

</section>


<section>

<h2>Make a Birthday Wish 🎂</h2>

<div class="cake" onclick="blowCandle()">🎂</div>

<p id="cakeMessage" class="hidden">

Happy Birthday Shreya ❤️  
May all your dreams come true.

I love you more than words can explain.

— Sahil

</p>

</section>

</div>


<audio id="music" loop>

<source src="music.mp3" type="audio/mpeg">

</audio>


<script>


function startSite(){

document.getElementById("start").style.display="none";
document.getElementById("main").classList.remove("hidden");

document.getElementById("music").play();

}



const startDate = new Date("December 3, 2023 19:00:00");

function updateTimer(){

const now = new Date();
const diff = now - startDate;

const seconds = Math.floor(diff/1000);
const minutes = Math.floor(seconds/60);
const hours = Math.floor(minutes/60);
const days = Math.floor(hours/24);
const years = Math.floor(days/365);

document.getElementById("timer").innerHTML =
years+" years "+
(days%365)+" days "+
(hours%24)+" hours "+
(minutes%60)+" minutes "+
(seconds%60)+" seconds";

}

setInterval(updateTimer,1000);



const text = "Dear Shreya ❤️ From the moment you entered my life on 3 December 2023 at 7 PM everything became brighter. Every moment with you means the world to me. Happy Birthday my love. Forever yours — Sahil ❤️";

let i = 0;

function typeWriter(){

if(i < text.length){

document.getElementById("typeText").innerHTML += text.charAt(i);

i++;

setTimeout(typeWriter,40);

}

}

typeWriter();



function createHeart(){

const heart=document.createElement("div");

heart.classList.add("heart");

heart.innerHTML="❤️";

heart.style.left=Math.random()*100+"vw";

heart.style.fontSize=Math.random()*20+10+"px";

document.body.appendChild(heart);

setTimeout(()=>{heart.remove()},6000);

}

setInterval(createHeart,300);



function blowCandle(){

document.querySelector(".cake").innerHTML="🎂✨";

document.getElementById("cakeMessage").classList.remove("hidden");

}

</script>


</body>
</html>
