<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Rose Day 🌹</title>

<style>
body{
  margin:0;
  min-height:100vh;
  background:linear-gradient(135deg,#ffd6e8,#ffeef5);
  font-family:Arial,Helvetica,sans-serif;
  display:flex;
  justify-content:center;
  align-items:center;
}

.card{
  width:92%;
  max-width:380px;
  background:#ffffff;
  border-radius:24px;
  padding:18px;
  box-shadow:0 15px 35px rgba(0,0,0,0.15);
  text-align:center;
}

.hidden{display:none;}

h2,h3{
  color:#d6336c;
  margin:10px 0;
}

p{
  font-size:14px;
  color:#555;
}

/* GIF BOX */
.gif-box{
  width:120px;
  height:120px;
  margin:0 auto 12px;
  border-radius:18px;
  overflow:hidden;
}
.gif-box img{
  width:100%;
  height:100%;
  object-fit:cover;
}

/* BUTTON */
button{
  background:#ff4d6d;
  color:#fff;
  border:none;
  padding:10px 24px;
  border-radius:24px;
  font-size:14px;
  margin-top:14px;
}

/* ROSE GAME */
.roses{
  display:flex;
  justify-content:center;
  gap:20px;
  font-size:42px;
  cursor:pointer;
}
#roseMessage{
  margin-top:12px;
  min-height:48px;
  font-size:15px;
  color:#b0004e;
}

/* PHOTOS */
.photo-grid{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
}
.photo-grid img{
  width:100%;
  border-radius:14px;
}

/* VIDEOS */
video{
  width:100%;
  border-radius:14px;
  margin-bottom:10px;
}

/* LETTER */
.letter{
  background:#fff5fa;
  padding:14px;
  border-radius:16px;
  text-align:left;
  font-size:13px;
  color:#444;
  max-height:300px;
  overflow-y:auto;
}
</style>
</head>

<body>

<div class="card">

<!-- HOME -->
<div id="home">
  <div class="gif-box">
    <img src="https://files.catbox.moe/example.gif" alt="">
  </div>
  <h2>Happy Rose Day 🌹</h2>
  <p>For the one who makes my world softer</p>
  <button onclick="openPage('game')">Tap a Rose 🌹</button>
</div>

<!-- GAME -->
<div id="game" class="hidden">
  <h3>Tap a Rose 🌹</h3>
  <p>Har rose ke niche ek feeling hai</p>

  <div class="roses">
    <span onclick="pickRose()">🌹</span>
    <span onclick="pickRose()">🌹</span>
    <span onclick="pickRose()">🌹</span>
  </div>

  <div id="roseMessage"></div>

  <button onclick="openPage('photos')">Our Memories 🎀🧿</button>
</div>

<!-- PHOTOS -->
<div id="photos" class="hidden">
  <h3>Our Memories 🎀🧿</h3>

  <div class="photo-grid">
    <img src="https://i.postimg.cc/yNqkyd81/IMG_20260206_190532.png">
    <img src="https://i.postimg.cc/s2Fv4Xg3/IMG_20260206_190558.png">
    <img src="https://i.postimg.cc/K831TLx4/IMG_20260206_190630.png">
    <img src="https://i.postimg.cc/rp6KNmw8/IMG_20260206_190726.png">
  </div>

  <button onclick="openPage('videos')">For You 🫶🏻💗</button>
</div>

<!-- VIDEOS -->
<div id="videos" class="hidden">
  <h3>For You 🫶🏻💗</h3>

  <video controls muted playsinline src="https://files.catbox.moe/mw3f2q.mp4"></video>
  <video controls muted playsinline src="https://files.catbox.moe/ggbrik.mp4"></video>
  <video controls muted playsinline src="https://files.catbox.moe/sfk5b8.mp4"></video>

  <button onclick="openPage('letter')">From My Heart 💌</button>
</div>

<!-- LETTER -->
<div id="letter" class="hidden">
  <h3>From My Heart 💌</h3>

  <div class="letter">
Happy Rose Day, meri zindagi ke sabse khoobsurat ehsaas 🌹  
Aaj Rose Day hai, aur jab bhi rose ka naam aata hai na, mujhe aap yaad aa jaate ho. Kyunki jaise ek rose simple hoke bhi special hota hai, waise hi aap meri life me aaye bina koi shor machaye… par dheere dheere sabse important ban gaye. Aapke saath hone ka ehsaas hi alag hai — bina zyada bole, bina zyada dikhaye, bas ek sukoon sa. Jaise kisi thake hue din ke baad achanak thandi hawa mil jaaye.  

Mujhe aapki woh chhoti chhoti baatein bohot pasand hain, jinhe shayad duniya notice bhi na kare, par mere liye wahi sabse important hoti hain. Aapka mood, aapki khamoshi, aapki hasi, aur kabhi kabhi aapka bina wajah gussa hona — sab kuch. Aap perfect isliye nahi ho kyunki aap kabhi galat nahi hote, balki isliye ho kyunki aap real ho. Aur mujhe real cheezein hi sabse zyada apni lagti hain.  

Rose ki tarah hi pyaar bhi hota hai — thoda soft, thoda strong, kabhi khushboo se bhara, kabhi thoda sa dard bhi deta hai. Par phir bhi koi rose ko chhodta nahi… bilkul waise hi, aap bhi.  

Aaj Rose Day pe bas itna kehna chahta hoon ki aap meri life ka woh rose ho jo main sambhaal ke rakhna chahta hoon — bina todhe, bina force kiye, bas respect aur care ke saath.  

“Aap meri life me ho, wahi mere liye sabse badi khushi hai.” 🌹  
Happy Rose Day 🤍
  </div>

  <button onclick="openPage('end')">One Last Thing 🤍</button>
</div>

<!-- END -->
<div id="end" class="hidden">
  <h3>Thank You 🤍</h3>
  <p>
    Is chhoti si duniya ka hissa banne ke liye  
    shukriya…  
    Agar aap muskuraye ho,  
    to mera purpose complete ho gaya 🌹
  </p>
  <p>
    Always stay the way you are.  
    Someone out there cares — deeply.
  </p>
</div>

</div>

<script>
function openPage(id){
  var pages=document.querySelectorAll('.card > div');
  pages.forEach(function(p){p.classList.add('hidden');});
  document.getElementById(id).classList.remove('hidden');
}

var roseMessages=[
  "You are my calm in chaos ❤️",
  "Life feels softer with you 🌸",
  "I choose you, every single day 🫶🏻",
  "You are my safe place 🤍"
];

function pickRose(){
  var msg=roseMessages[Math.floor(Math.random()*roseMessages.length)];
  document.getElementById("roseMessage").innerText=msg;
}
</script>

</body>
</html>
