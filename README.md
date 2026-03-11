<html>
<head>

<title>Happy Birthday Shreyu ❤️</title>

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>

body{
margin:0;
font-family:'Segoe UI',sans-serif;
color:white;
text-align:center;
overflow-x:hidden;
background:linear-gradient(135deg,#0f0f0f,#2b0033,#000);
}

/* loading */

#loading{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:#000;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
z-index:999;
}

.bar{
width:200px;
height:8px;
background:#333;
border-radius:10px;
margin-top:20px;
overflow:hidden;
}

.progress{
height:100%;
width:0%;
background:#ff4d6d;
animation:load 3s forwards;
}

@keyframes load{to{width:100%}}

.hero{
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
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

.slider{
width:260px;
margin:auto;
overflow:hidden;
border-radius:20px;
}

.slider img{
width:100%;
display:none;
}

.message{
max-width:600px;
margin:auto;
line-height:1.8;
white-space:pre-line;
color:#ddd;
}

.cake{
font-size:80px;
cursor:pointer;
}

.star{
position:absolute;
background:white;
border-radius:50%;
opacity:.7;
animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
from{opacity:.3}
to{opacity:1}
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

.fireworks{
font-size:50px;
animation:boom 1s infinite alternate;
}

@keyframes boom{
from{transform:scale(1)}
to{transform:scale(1.3)}
}

.reasonBox{
margin-top:20px;
}

.reasonItem{
background:#ff4d6d;
margin:8px auto;
padding:10px;
border-radius:20px;
width:250px;
}

</style>
</head>

<body>

<!-- loading -->

<div id="loading">

<h2>Preparing something special for Shreyu ❤️</h2>

<div class="bar">
<div class="progress"></div>
</div>

</div>

<!-- page 1 -->

<section class="hero hidden" id="page1">

<h1 onclick="secretTap()">Shreyu ❤️</h1>

<p>Sahil made something special for you</p>

<button onclick="nextPage(1)">Continue</button>

</section>

<!-- page 2 -->

<section class="hero hidden" id="page2">

<h2>Wait...</h2>

<p>Are you really ready for this surprise?</p>

<button onclick="nextPage(2)">Yes I am</button>

</section>

<!-- page 3 -->

<section class="hero hidden" id="page3">

<h2>Important Question 😌</h2>

<p>Are you ready for the surprise?</p>

<div style="position:relative;height:120px">

<button onclick="nextPage(3)">Yes I'm ready ❤️</button>

<button id="noBtn" onmouseover="moveButton()" style="position:absolute">
No
</button>

</div>

</section>

<!-- page 4 -->

<section class="hero hidden" id="page4">

<h2>Last chance 😄</h2>

<p>Are you REALLY ready?</p>

<button onclick="startSite()">Show me the surprise</button>

</section>

<!-- main site -->

<div id="main" class="hidden">

<section>

<h2>You've been my world for</h2>

<div class="timer" id="timer"></div>

</section>

<!-- photo slider -->

<section>

<h2>Our Memories 📸</h2>

<div class="slider" id="slider">

<img src="photo1.jpg">
<img src="photo2.jpg">
<img src="photo3.jpg">
<img src="photo4.jpg">
<img src="photo5.jpg">
<img src="photo6.jpg">
<img src="photo7.jpg">
<img src="photo8.jpg">

</div>

</section>

<!-- reasons -->

<section>

<h2>Reasons I Love You ❤️</h2>

<button onclick="showReason()">What more?</button>

<div id="reasonsContainer" class="reasonBox"></div>

</section>

<!-- message -->

<section>

<h2>A Message For You 💌</h2>

<p class="message" id="typeText"></p>

</section>

<!-- cake -->

<section>

<h2>Make a Birthday Wish 🎂</h2>

<div class="cake" onclick="blowCandle()">🎂</div>

<p id="cakeMessage" class="hidden">

Happy Birthday Shreyu ❤️  
I love you so much.  

— Sahil

</p>

</section>

<section>

<button onclick="showFinal()">One Last Thing</button>

</section>

</div>

<!-- final page -->

<section class="hero hidden" id="finalPage">

<h1>I Love You Shreyu ❤️</h1>

<div class="fireworks">🎆 🎇 🎆</div>

<p>You make my life beautiful.</p>

</section>

<audio id="music" loop>
<source src="music.mp3">
</audio>

<script>

/* loading */

setTimeout(()=>{
document.getElementById("loading").style.display="none";
document.getElementById("page1").classList.remove("hidden");
},3000);

/* navigation */

function nextPage(p){
document.getElementById("page"+p).style.display="none";
document.getElementById("page"+(p+1)).classList.remove("hidden");
}

function startSite(){
document.getElementById("page4").style.display="none";
document.getElementById("main").classList.remove("hidden");
document.getElementById("music").play();
}

/* no button trap */

function moveButton(){
const b=document.getElementById("noBtn");
b.style.left=Math.random()*200+"px";
b.style.top=Math.random()*80+"px";
}

/* timer */

const startDate=new Date("December 3 2023 19:00");

setInterval(()=>{
const diff=new Date()-startDate;

const d=Math.floor(diff/86400000);
const h=Math.floor(diff/3600000)%24;
const m=Math.floor(diff/60000)%60;
const s=Math.floor(diff/1000)%60;

document.getElementById("timer").innerHTML=
d+" days "+h+" hrs "+m+" min "+s+" sec";

},1000);

/* slider */

let slideIndex=0;
const slides=document.querySelectorAll("#slider img");

function showSlides(){
slides.forEach(s=>s.style.display="none");
slideIndex++;
if(slideIndex>slides.length)slideIndex=1;
slides[slideIndex-1].style.display="block";
setTimeout(showSlides,3000);
}

showSlides();

/* reasons reveal */

const reasons=[
"Your beautiful smile",
"Your madness",
"The way you care",
"How you make normal days fun",
"How you irritate me but I still like you",
"Because you are simply you",
"And because life is better with you ❤️"
];

let reasonIndex=0;

function showReason(){

if(reasonIndex<reasons.length){

const div=document.createElement("div");

div.className="reasonItem";

div.innerText=reasons[reasonIndex];

document.getElementById("reasonsContainer").appendChild(div);

reasonIndex++;

}else{

alert("Okay okay… Aur bohot hai, but tum click karte karte thak jaogi na, isiliye filal keliye aage badte hai 😄");

}

}

/* message typing */

const text=`Dear Shreyu ❤️

First of all… Happy Birthday to the cutest troublemaker in my life.

I honestly didn’t expect that one person could become such an important part of my life so quickly, but somehow you did it. Now you’re the person I talk to the most, think about the most, and the one who makes even normal days feel special.

You have this amazing ability to make me laugh, irritate me a little, and still make me smile at the same time.

Happy Birthday Shreyu ❤️

— Sahil`;

let i=0;

function typeWriter(){

if(i<text.length){

document.getElementById("typeText").innerHTML+=text.charAt(i);

i++;

setTimeout(typeWriter,25);

}

}

typeWriter();

/* hearts */

setInterval(()=>{

const h=document.createElement("div");

h.className="heart";

h.innerHTML="❤️";

h.style.left=Math.random()*100+"vw";

document.body.appendChild(h);

setTimeout(()=>h.remove(),6000);

},300);

/* stars */

for(let i=0;i<60;i++){

const s=document.createElement("div");

s.className="star";

s.style.width=Math.random()*3+"px";

s.style.height=s.style.width;

s.style.top=Math.random()*100+"vh";

s.style.left=Math.random()*100+"vw";

document.body.appendChild(s);

}

/* cake + confetti */

function blowCandle(){

document.querySelector(".cake").innerHTML="🎂✨";

document.getElementById("cakeMessage").classList.remove("hidden");

confetti();

}

function confetti(){

for(let i=0;i<50;i++){

const c=document.createElement("div");

c.style.position="fixed";

c.style.width="6px";

c.style.height="6px";

c.style.background="white";

c.style.top=Math.random()*100+"vh";

c.style.left=Math.random()*100+"vw";

document.body.appendChild(c);

setTimeout(()=>c.remove(),2000);

}

}

/* final */

function showFinal(){

document.getElementById("main").style.display="none";

document.getElementById("finalPage").classList.remove("hidden");

}

/* secret tap */

let taps=0;

function secretTap(){

taps++;

if(taps==5){

alert("Secret message: I love you even more than you know ❤️");

}

}

</script>

</body>
</html>
