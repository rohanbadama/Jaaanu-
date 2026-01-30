<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>365 Days With You ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
  margin:0;
  font-family:sans-serif;
  background:linear-gradient(135deg,#ffd6e7,#fff);
  text-align:center;
}
section {display:none; padding:30px 15px; min-height:100vh;}
section.active {display:block;}

h1 {color:#d63384;}

button {
  padding:12px 22px;
  border:none;
  border-radius:25px;
  background:#ff4d88;
  color:white;
  font-size:16px;
  margin:15px;
}

img, video {
  width:90%;
  max-width:500px;
  border-radius:15px;
  margin:10px 0;
}

canvas {
  background:white;
  border:3px solid pink;
  border-radius:10px;
  width:95%;
  max-width:500px;
  height:300px;
}
</style>
</head>
<body>

<!-- Background Music -->
<audio id="bgMusic" loop>
  <source src="https://docs.google.com/uc?export=download&id=1B9musicfileexample" type="audio/mp3">
</audio>

<section id="home" class="active">
  <h1>365 Days With You ❤️</h1>
  <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif">
  <p>One year. One us. Forever to go.</p>
  <button onclick="startSite()">Enter ❤️</button>
</section>

<section id="game">
  <h1>Collect All My Love ❤️</h1>
  <canvas id="gameCanvas"></canvas>
  <div id="winMessage" style="display:none;">
    <h2>You found all my love ❤️</h2>
    <button onclick="showSection('memories')">Continue 💌</button>
  </div>
</section>

<section id="memories">
  <h1>Our Memories 📸</h1>
  <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399976555941918/From_KlickPin_CF_Love_You_Lots_Kiss_GIF_-_LoveYouLots_Kiss_Peachcatmatheodelanoe12.gif">
  <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png">
  <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg">
  <button onclick="showSection('videos')">Next ▶️</button>
</section>

<section id="videos">
  <h1>Our Videos 🎥</h1>
  <video controls class="vid"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448687809954058/lv_7555554315964878141_20260117212840.mp4"></video>
  <video controls class="vid"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448576363233361/lv_7572376034872478993_20260129201229.mp4"></video>
  <button onclick="showSection('letter')">Final Surprise 💖</button>
</section>

<section id="letter">
  <h1>Happy 1year anniversary meri FOREVER 🫶🏻💖</h1>
  <p style="white-space:pre-line; max-width:900px; margin:auto; font-size:18px; line-height:1.8;">
YAHAN TUM APNA FULL LETTER PASTE KARO (same jo bheja tha)
  </p>
</section>

<script>
let music = document.getElementById("bgMusic");

function startSite(){
  music.play().catch(()=>{});
  showSection('game');
}

function showSection(id){
  document.querySelectorAll("section").forEach(s=>s.classList.remove("active"));
  document.getElementById(id).classList.add("active");
}

/* Pause music when videos play */
document.querySelectorAll("video").forEach(v=>{
  v.addEventListener("play",()=>music.pause());
  v.addEventListener("pause",()=>music.play());
  v.addEventListener("ended",()=>music.play());
});

/* SIMPLE MOBILE GAME */
const canvas=document.getElementById("gameCanvas");
const ctx=canvas.getContext("2d");

function resizeCanvas(){
  canvas.width=canvas.offsetWidth;
  canvas.height=300;
}
resizeCanvas();
window.addEventListener("resize",resizeCanvas);

let player={x:20,y:150,size:20};
let heart={x:250,y:150,size:15};

document.addEventListener("touchmove",e=>{
  player.x=e.touches[0].clientX-20;
  player.y=e.touches[0].clientY-100;
});

function loop(){
  ctx.clearRect(0,0,canvas.width,canvas.height);
  ctx.fillStyle="red";
  ctx.fillRect(player.x,player.y,player.size,player.size);

  ctx.fillStyle="pink";
  ctx.beginPath();
  ctx.arc(heart.x,heart.y,heart.size,0,Math.PI*2);
  ctx.fill();

  if(Math.abs(player.x-heart.x)<20 && Math.abs(player.y-heart.y)<20){
    document.getElementById("winMessage").style.display="block";
  }

  requestAnimationFrame(loop);
}
loop();
</script>

</body>
</html>
