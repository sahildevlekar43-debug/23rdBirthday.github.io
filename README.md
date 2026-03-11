<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Shreyu ❤️</title>

<style>

body{
margin:0;
font-family:Segoe UI;
color:white;
text-align:center;
background:linear-gradient(135deg,#0f0f0f,#2b0033,#000);
overflow-x:hidden;
}

.glass{
background:rgba(255,255,255,0.08);
backdrop-filter:blur(10px);
border-radius:20px;
padding:25px;
margin:30px auto;
width:90%;
max-width:700px;
}

/* loading */

#loading{
position:fixed;
width:100%;
height:100%;
background:black;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
z-index:999;
}

/* buttons */

button{
padding:14px 30px;
border:none;
border-radius:40px;
background:#ff4d6d;
color:white;
font-size:18px;
cursor:pointer;
margin-top:20px;
}

/* slider */

.carousel{
position:relative;
max-width:600px;
margin:auto;
overflow:hidden;
}

.carousel-track{
display:flex;
transition:transform .7s ease;
}

.slide{
width:220px;
margin:0 12px;
border-radius:20px;
opacity:.5;
filter:blur(3px);
transform:scale(.8);
transition:.5s;
}

.slide.active{
opacity:1;
filter:none;
transform:scale(1.05);
}

.nav{
position:absolute;
top:50%;
transform:translateY(-50%);
background:#ff4d6d;
border:none;
color:white;
font-size:24px;
border-radius:50%;
padding:8px 14px;
}

.nav.left{left:10px}
.nav.right{right:10px}

/* hearts */

.heart{
position:fixed;
bottom:-20px;
animation:float 6s linear infinite;
}

@keyframes float{
0%{transform:translateY(0)}
100%{transform:translateY(-110vh)}
}

/* stars */

.star{
position:absolute;
background:white;
border-radius:50%;
opacity:.7;
}

/* cake */

.cake{
font-size:80px;
cursor:pointer;
}

/* fireworks */

.fireworks{
font-size:50px;
animation:boom 1s infinite alternate;
}

@keyframes boom{
from{transform:scale(1)}
to{transform:scale(1.3)}
}

.hidden{display:none}

</style>
</head>

<body>

<div id="loading">
<h2>Preparing something special for Shreyu ❤️</h2>
</div>

<!-- intro -->

<section id="page1" class="hidden">
<h1 onclick="secretTap()">Shreyu ❤️</h1>
<p>Sahil made something special for you</p>
<button onclick="nextPage(1)">Continue</button>
</section>

<section id="page2" class="hidden">
<h2>Wait...</h2>
<p>Are you really ready for this surprise?</p>
<button onclick="nextPage(2)">Yes I am</button>
</section>

<section id="page3" class="hidden">
<h2>Important Question 😌</h2>

<button onclick="nextPage(3)">Yes I'm ready ❤️</button>
<button id="noBtn" onmouseover="moveButton()">No</button>

</section>

<section id="page4" class="hidden">
<h2>Last chance 😄</h2>
<button onclick="startSite()">Show me the surprise</button>
</section>

<!-- main -->

<div id="main" class="hidden">

<div class="glass">
<h2>You've been my world for</h2>
<div id="timer"></div>
</div>

<div class="glass">

<h2>Our Memories 📸</h2>

<div class="carousel">

<button class="nav left" onclick="moveSlide(-1)">❮</button>

<div class="carousel-track" id="track">

<img src="photo1.jpg" class="slide">
<img src="photo2.jpg" class="slide">
<img src="photo3.jpg" class="slide">
<img src="photo4.jpg" class="slide">
<img src="photo5.jpg" class="slide">
<img src="photo6.jpg" class="slide">
<img src="photo7.jpg" class="slide">
<img src="photo8.jpg" class="slide">

</div>

<button class="nav right" onclick="moveSlide(1)">❯</button>

</div>

</div>

<div class="glass">

<h2>Reasons I Love You ❤️</h2>

<button onclick="showReason()">What more?</button>

<div id="reasons"></div>

</div>

<div class="glass">

<h2>Memory Quiz 😄</h2>

<p>Our favourite activity?</p>

<button onclick="quiz()">Talking nonsense</button>
<button onclick="quiz()">Fighting</button>
<button onclick="quiz()">Both</button>

</div>

<div class="glass">

<h2>Open Your Gift 🎁</h2>

<button onclick="openGift()">Tap to open</button>

<p id="giftText" class="hidden">
The best gift in my life was meeting you ❤️
</p>

</div>

<div class="glass">

<h2>A Message For You 💌</h2>

<p id="typeText"></p>

</div>

<div class="glass">

<h2>Make a Birthday Wish 🎂</h2>

<div class="cake" onclick="blowCandle()">🎂</div>

<p id="cakeText" class="hidden">Happy Birthday Shreyu ❤️</p>

</div>

<button onclick="holdHand()">Hold my hand ✋</button>

</div>

<section id="finalPage" class="hidden">

<h1>I Love You Shreyu ❤️</h1>

<div class="fireworks">🎆 🎇 🎆</div>

</section>

<audio id="music" loop>
<source src="music.mp3">
</audio>

<script>

/* loading */

setTimeout(()=>{
loading.style.display="none"
page1.classList.remove("hidden")
},2000)

/* pages */

function nextPage(p){
document.getElementById("page"+p).style.display="none"
document.getElementById("page"+(p+1)).classList.remove("hidden")
}

function startSite(){
page4.style.display="none"
main.classList.remove("hidden")
music.play()
}

/* trap */

function moveButton(){
noBtn.style.position="absolute"
noBtn.style.left=Math.random()*200+"px"
noBtn.style.top=Math.random()*100+"px"
}

/* timer */

const start=new Date("Dec 3 2023 19:00")

setInterval(()=>{
const diff=new Date()-start
const d=Math.floor(diff/86400000)
timer.innerHTML=d+" days together ❤️"
},1000)

/* slider */

let i=0
const slides=document.querySelectorAll(".slide")

function showSlides(){

slides.forEach(s=>s.classList.remove("active"))

slides[i].classList.add("active")

i=(i+1)%slides.length

}

setInterval(showSlides,4000)
showSlides()

function moveSlide(d){
i+=d
if(i<0)i=slides.length-1
if(i>=slides.length)i=0
showSlides()
}

/* reasons */

const reasons=[
"Your smile",
"Your madness",
"The way you care",
"How you make normal days fun",
"Because life is better with you"
]

let r=0

function showReason(){
if(r<reasons.length){
let div=document.createElement("div")
div.innerText=reasons[r]
reasons.appendChild(div)
r++
}
}

/* quiz */

function quiz(){
alert("Correct answer 😄")
}

/* gift */

function openGift(){
giftText.classList.remove("hidden")
}

/* message */

const text=`Dear Shreyu ❤️ First of all… Happy Birthday to the cutest troublemaker in my life. I honestly didn’t expect that one person could become such an important part of my life so quickly, but somehow you did it...`

let t=0

function typeWriter(){
if(t<text.length){
typeText.innerHTML+=text.charAt(t)
t++
setTimeout(typeWriter,20)
}
}

typeWriter()

/* cake */

function blowCandle(){
cakeText.classList.remove("hidden")
}

/* final */

function holdHand(){
main.style.display="none"
finalPage.classList.remove("hidden")
}

/* secret */

let taps=0
function secretTap(){
taps++
if(taps==5){
alert("Secret message: I love you even more ❤️")
}
}

</script>

</body>
</html>
