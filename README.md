<html>
<head>

<title>Happy Birthday Shreyu ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>

body{
margin:0;
font-family:'Segoe UI',sans-serif;
background:#0f0f0f;
color:white;
text-align:center;
overflow-x:hidden;
}

.hero{
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
animation:fade 1s;
}

.hidden{display:none;}

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
white-space:pre-line;
}

.cake{
font-size:80px;
cursor:pointer;
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

@keyframes fade{
from{opacity:0}
to{opacity:1}
}

/* stars */

.stars{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
pointer-events:none;
z-index:-1;
}

.star{
position:absolute;
background:white;
border-radius:50%;
animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
from{opacity:0.2}
to{opacity:1}
}

/* fireworks */

.fireworks{
font-size:40px;
margin-top:20px;
animation:boom 1s infinite alternate;
}

@keyframes boom{
from{transform:scale(1)}
to{transform:scale(1.3)}
}

</style>
</head>

<body>

<div class="stars" id="stars"></div>

<!-- PAGE 1 -->

<section class="hero" id="page1">

<h1>Shreyu ❤️</h1>

<p>Sahil made something special for you</p>

<button onclick="nextPage(1)">Continue</button>

</section>

<!-- PAGE 2 -->

<section class="hero hidden" id="page2">

<h1>Wait...</h1>

<p>Are you really ready for this surprise?</p>

<button onclick="nextPage(2)">Yes I am</button>

</section>

<!-- PAGE 3 -->

<section class="hero hidden" id="page3">

<h1>Important Question 😌</h1>

<p>Are you ready for the surprise?</p>

<div style="position:relative;height:120px;">

<button onclick="nextPage(3)">Yes I'm ready ❤️</button>

<button id="noBtn" onmouseover="moveButton()" style="position:absolute">
No
</button>

</div>

</section>

<!-- PAGE 4 -->

<section class="hero hidden" id="page4">

<h1>Last chance 😄</h1>

<p>Are you REALLY ready?</p>

<button onclick="startSite()">Show me the surprise</button>

</section>

<!-- MAIN PAGE -->

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

Happy Birthday Shreyu ❤️  
I love you so much.  
Thank you for being in my life.

— Sahil

</p>

</section>

<section>

<h2>One Last Thing...</h2>

<button onclick="showFinal()">Click here</button>

</section>

</div>

<!-- FINAL PAGE -->

<section class="hero hidden" id="finalPage">

<h1>Happy Birthday Shreyu ❤️</h1>

<div class="fireworks">🎆 🎇 🎆 🎇</div>

<p>You are the most beautiful part of my life.</p>

<p>Love you forever.</p>

<p>— Sahil</p>

</section>

<audio id="music" loop>
<source src="music.mp3" type="audio/mpeg">
</audio>

<script>

function nextPage(page){
document.getElementById("page"+page).style.display="none";
document.getElementById("page"+(page+1)).classList.remove("hidden");
}

function startSite(){
document.getElementById("page4").style.display="none";
document.getElementById("main").classList.remove("hidden");
document.getElementById("music").play();
}

function moveButton(){
alert("Nice try 😄 You have to press YES.");
const button=document.getElementById("noBtn");
button.style.left=Math.random()*200+"px";
button.style.top=Math.random()*80+"px";
}

function showFinal(){
document.getElementById("main").style.display="none";
document.getElementById("finalPage").classList.remove("hidden");
}

const startDate=new Date("December 3, 2023 19:00:00");

function updateTimer(){
const now=new Date();
const diff=now-startDate;

const seconds=Math.floor(diff/1000);
const minutes=Math.floor(seconds/60);
const hours=Math.floor(minutes/60);
const days=Math.floor(hours/24);
const years=Math.floor(days/365);

document.getElementById("timer").innerHTML=
years+" years "+
(days%365)+" days "+
(hours%24)+" hours "+
(minutes%60)+" minutes "+
(seconds%60)+" seconds";
}

setInterval(updateTimer,1000);

const text=`Dear Shreyu ❤️

First of all… Happy Birthday to the cutest troublemaker in my life.

I honestly didn’t expect that one person could become such an important part of my life so quickly, but somehow you did it. Now you’re the person I talk to the most, think about the most, and the one who makes even normal days feel special.

You have this amazing ability to make me laugh, irritate me a little, and still make me smile at the same time. Life with you is never boring, and I wouldn’t want it any other way.

Every random conversation, every joke, every small moment we share means more to me than you probably realize. Being with you just feels easy and comfortable, like things are exactly the way they should be.

So on your birthday, I just want you to know that I’m really lucky to have you in my life. Thank you for being you — for your smile, your madness, your kindness, and for making my life a lot more fun.

I hope today makes you as happy as you make me.

Happy Birthday, Shreyu ❤️

Now enjoy your day… but remember, I’m still your favorite person.

— Sahil`;

let i=0;

function typeWriter(){
if(i<text.length){
document.getElementById("typeText").innerHTML+=text.charAt(i);
i++;
setTimeout(typeWriter,30);
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

function createStars(){

const container=document.getElementById("stars");

for(let i=0;i<60;i++){

const star=document.createElement("div");

star.classList.add("star");

const size=Math.random()*3;

star.style.width=size+"px";
star.style.height=size+"px";

star.style.top=Math.random()*100+"vh";
star.style.left=Math.random()*100+"vw";

container.appendChild(star);

}

}

createStars();

</script>

</body>
</html>
