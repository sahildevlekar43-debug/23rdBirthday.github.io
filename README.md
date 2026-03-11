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

/* loading */

#loading{
position:fixed;
width:100%;
height:100%;
background:black;
display:flex;
justify-content:center;
align-items:center;
z-index:999;
font-size:22px;
}

/* glass cards */

.glass{
background:rgba(255,255,255,0.08);
backdrop-filter:blur(10px);
border-radius:20px;
padding:30px;
margin:40px auto;
width:90%;
max-width:700px;
}

/* stars */

.star{
position:absolute;
background:white;
border-radius:50%;
opacity:.7;
}

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

/* carousel */

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
cursor:pointer;
}

.nav.left{left:10px}
.nav.right{right:10px}

/* buttons */

button{
padding:12px 26px;
border:none;
border-radius:30px;
background:#ff4d6d;
color:white;
font-size:16px;
cursor:pointer;
margin-top:20px;
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

<div id="loading">Preparing something special for Shreyu ❤️</div>

<!-- INTRO -->

<section class="glass">
<h1 onclick="secretTap()">Shreyu ❤️</h1>
<p>Sahil made something special for you</p>
</section>

<!-- TIMER -->

<section class="glass">
<h2>You've been my world for</h2>
<div id="timer"></div>
</section>

<!-- PHOTO CAROUSEL -->

<section class="glass">

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

</section>

<!-- REASONS -->

<section class="glass">

<h2>Reasons I Love You ❤️</h2>

<button onclick="showReason()">What more?</button>

<div id="reasons"></div>

</section>

<!-- QUIZ -->

<section class="glass">

<h2>Memory Quiz 😄</h2>

<p>Our favourite activity?</p>

<button onclick="quiz()">Talking nonsense</button>
<button onclick="quiz()">Fighting</button>
<button onclick="quiz()">Both</button>

</section>

<!-- GIFT -->

<section class="glass">

<h2>Open Your Gift 🎁</h2>

<button onclick="openGift()">Tap to open</button>

<p id="giftText" class="hidden">
The best gift in my life was meeting you ❤️
</p>

</section>

<!-- MESSAGE -->

<section class="glass">

<h2>A Message For You 💌</h2>

<p id="typeText"></p>

</section>

<!-- CAKE -->

<section class="glass">

<h2>Make a Birthday Wish 🎂</h2>

<div class="cake" onclick="blowCandle()">🎂</div>

<p id="cakeText" class="hidden">Happy Birthday Shreyu ❤️</p>

</section>

<!-- HOLD HAND -->

<section class="glass">

<button onclick="final()">Hold my hand ✋</button>

</section>

<!-- FINAL -->

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
music.play()
},2000)

/* timer */

const start=new Date("Dec 3 2023 19:00")

setInterval(()=>{
const diff=new Date()-start
const d=Math.floor(diff/86400000)
timer.innerHTML=d+" days together ❤️"
},1000)

/* stars */

for(let i=0;i<60;i++){
let s=document.createElement("div")
s.className="star"
s.style.width=Math.random()*3+"px"
s.style.height=s.style.width
s.style.top=Math.random()*100+"vh"
s.style.left=Math.random()*100+"vw"
document.body.appendChild(s)
}

/* floating hearts */

setInterval(()=>{
let h=document.createElement("div")
h.className="heart"
h.innerHTML="❤️"
h.style.left=Math.random()*100+"vw"
document.body.appendChild(h)
setTimeout(()=>h.remove(),6000)
},300)

/* carousel */

let slide=0
const slides=document.querySelectorAll(".slide")

function showSlides(){
slides.forEach(s=>s.classList.remove("active"))
slides[slide].classList.add("active")
slide=(slide+1)%slides.length
}

setInterval(showSlides,4000)
showSlides()

function moveSlide(d){
slide+=d
if(slide<0)slide=slides.length-1
if(slide>=slides.length)slide=0
showSlides()
}

/* reasons */

const reasonList=[
"Your smile",
"Your madness",
"How you care",
"How you make normal days fun",
"Because life is better with you"
]

let r=0

function showReason(){

if(r<reasonList.length){

let div=document.createElement("div")
div.innerText=reasonList[r]
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

/* typing message */

const text=`Dear Shreyu ❤️ First of all… Happy Birthday to the cutest troublemaker in my life. I honestly didn’t expect that one person could become such an important part of my life so quickly, but somehow you did it. Now you’re the person I talk to the most, think about the most, and the one who makes even normal days feel special. You have this amazing ability to make me laugh, irritate me a little, and still make me smile at the same time. Life with you is never boring, and I wouldn’t want it any other way. Every random conversation, every joke, every small moment we share means more to me than you probably realize. Being with you just feels easy and comfortable, like things are exactly the way they should be. So on your birthday, I just want you to know that I’m really lucky to have you in my life. Thank you for being you — for your smile, your madness, your kindness, and for making my life a lot more fun. I hope today makes you as happy as you make me. Happy Birthday, Shreyu ❤️ Now enjoy your day… but remember, I’m still your favorite person.`

let i=0

function typeWriter(){
if(i<text.length){
typeText.innerHTML+=text.charAt(i)
i++
setTimeout(typeWriter,20)
}
}

typeWriter()

/* cake */

function blowCandle(){

cakeText.classList.remove("hidden")

for(let i=0;i<40;i++){

let c=document.createElement("div")
c.style.position="fixed"
c.style.width="6px"
c.style.height="6px"
c.style.background="white"
c.style.top=Math.random()*100+"vh"
c.style.left=Math.random()*100+"vw"

document.body.appendChild(c)

setTimeout(()=>c.remove(),2000)

}

}

/* final */

function final(){
finalPage.classList.remove("hidden")
window.scrollTo(0,document.body.scrollHeight)
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
