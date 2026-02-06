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
  background:#fff;
  border-radius:24px;
  padding:18px;
  box-shadow:0 15px 35px rgba(0,0,0,0.15);
  text-align:center;
}

.hidden{display:none;}

h2,h3{color:#d6336c;margin:10px 0;}
p{font-size:14px;color:#555;}

button{
  background:#ff4d6d;
  color:#fff;
  border:none;
  padding:10px 24px;
  border-radius:24px;
  font-size:14px;
  margin-top:14px;
}

/* GIF BOX */
.gif-box{
  width:110px;
  height:110px;
  margin:0 auto 12px;
  border-radius:18px;
  overflow:hidden;
}
.gif-box img{
  width:100%;
  height:100%;
  object-fit:cover;
}

/* ROSE GAME */
.roses{
  display:flex;
  justify-content:center;
  gap:20px;
  font-size:42px;
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
    <img src="http://tmpfiles.org/dl/22876715/fromklickpincftkthao219bubududugif-tkthao219bubududupanda-discoversharegifs_cutecartoonquotescuteanimecatcutebeardrawings1.gif">
  </div>
  <h2>Happy Rose Day 🌹</h2>
  <p>For someone very special</p>
  <button onclick="openPage('game')">Tap a Rose 🌹</button>
</div>

<!-- GAME -->
<div id="game" class="hidden">
  <div class="gif-box">
    <img src="http://tmpfiles.org/dl/22876666/fromklickpincfpinvonelizavetapauesovaaufenrgy_gifbilderlustigniedlicheliebeszeichentrickliebegifthealeni.gif">
  </div>

  <h3>Tap a Rose 🌹</h3>

  <div class="roses">
    <span onclick="pickRose()">🌹</span>
    <span onclick="pickRose()">🌹</span>
    <span onclick="pickRose()">🌹</span>
  </div>

  <div id="roseMessage"></div>

  <button onclick="openPage('photos')">Our Memories 🎀🧿</button>
</div>

<!-- PHOTOS (NO GIF HERE) -->
<div id="photos" class="hidden">
  <h3>Our Memories 🎀🧿</h3>

  <div class="photo-grid">
    <img src="https://i.postimg.cc/yNqkyd81/IMG_20260206_190532.png">
    <img src="https://i.postimg.cc/s2Fv4Xg3/IMG_20260206_190558.png">
    <img src="https://i.postimg.cc/K831TLx4/IMG_20260206_190630.png">
    <img src="https://i.postimg.cc/rp6KNmw8/IMG_20260206_190726.png">
    <img src="https://i.postimg.cc/XNxB64s3/IMG_20260206_190744.png">
    <img src="https://i.postimg.cc/MGkvmTpR/IMG_20260206_190444.png">
    <img src="https://i.postimg.cc/k5rBv4gN/IMG_20260206_190512.png">
    <img src="https://i.postimg.cc/xdrc3C16/IMG_20260206_190418.png">
  </div>

  <button onclick="openPage('videos')">For You 🫶🏻💗</button>
</div>

<!-- VIDEOS (NO GIF HERE) -->
<div id="videos" class="hidden">
  <h3>For You 🫶🏻💗</h3>

  <video controls muted playsinline src="https://files.catbox.moe/mw3f2q.mp4"></video>
  <video controls muted playsinline src="https://files.catbox.moe/ggbrik.mp4"></video>
  <video controls muted playsinline src="https://files.catbox.moe/sfk5b8.mp4"></video>
  <video controls muted playsinline src="https://files.catbox.moe/p150ss.mp4"></video>
  <video controls muted playsinline src="https://files.catbox.moe/3ju0zb.mp4"></video>
  <video controls muted playsinline src="https://files.catbox.moe/6kf2dd.mp4"></video>

  <button onclick="openPage('letter')">From My Heart 💌</button>
</div>

<!-- LETTER -->
<div id="letter" class="hidden">
  <div class="gif-box">
    <img src="http://tmpfiles.org/dl/22876616/fromklickpincfpinbyceciliadelpantaongif_cutegifcutelovecartoonscutelovepictures.gif">
  </div>

  <h3>From My Heart 💌</h3>

  <div class="letter">
Happy Rose Day, meri zindagi ke sabse khoobsurat ehsaas 🌹
Aaj Rose Day hai, aur jab bhi rose ka naam aata hai na, mujhe aap yaad aa jaate ho. Kyunki jaise ek rose simple hoke bhi special hota hai, waise hi aap meri life me aaye bina koi shor machaye… par dheere dheere sabse important ban gaye. Aapke saath hone ka ehsaas hi alag hai — bina zyada bole, bina zyada dikhaye, bas ek sukoon sa. Jaise kisi thake hue din ke baad achanak thandi hawa mil jaaye.
Mujhe aapki woh chhoti chhoti baatein bohot pasand hain, jinhe shayad duniya notice bhi na kare, par mere liye wahi sabse important hoti hain. Aapka mood, aapki khamoshi, aapki hasi, aur kabhi kabhi aapka bina wajah gussa hona — sab kuch. Aap perfect isliye nahi ho kyunki aap kabhi galat nahi hote, balki isliye ho kyunki aap real ho. Aur mujhe real cheezein hi sabse zyada apni lagti hain.
Rose ki tarah hi pyaar bhi hota hai — thoda soft, thoda strong, kabhi khushboo se bhara, kabhi thoda sa dard bhi deta hai. Par phir bhi koi rose ko chhodta nahi, kyunki uski khoobsurti uske saath aane wale har ehsaas ke layak hoti hai. Bilkul waise hi, aap bhi. Aapke saath har moment easy nahi hota, par har moment worth it hota hai.
Aapko shayad andaza bhi nahi hai ki aapki presence mere liye kya maayne rakhti hai. Jab aap theek hote ho, mujhe lagta hai sab theek hai. Aur jab aap thode low feel karte ho, to dil karta hai bas itna kar paun ki aapko thoda sa halka feel kara saku. Kyunki pyaar ka matlab sirf saath rehna nahi hota, balki ek dusre ki care bina shart ke karna hota hai.
Aaj Rose Day pe main koi wada nahi kar raha, koi badi baat nahi keh raha. Bas itna kehna chahta hoon ki aap meri life ka woh rose ho jo main sambhaal ke rakhna chahta hoon — bina todhe, bina force kiye, bas respect aur care ke saath. Aap jaisa ho, jaise bhi ho, wahi mere liye kaafi hai.
Is Rose Day pe agar main aapko ek rose deta, to uske saath sirf ek hi baat likhta —
“Aap meri life me ho, wahi mere liye sabse badi khushi hai.” 🌹
Happy Rose Day 🤍
Hamesha muskurate rahiye… kyunki aapki muskurahat kisi ke liye bohot special hai.
  </div>

  <button onclick="openPage('end')">One Last Thing 🤍</button>
</div>

<!-- END -->
<div id="end" class="hidden">
  <div class="gif-box">
    <img src="http://tmpfiles.org/dl/22876413/fromklickpincfbunnysticker-bunny-discoversharegifs_cutelovegifcutegifloveyougif.gif">
  </div>

  <h3>Thank You 🤍</h3>
  <p>
    Agar yahan tak aaye ho,  
    to bas itna samajh lena —  
    yeh sab sirf ek din ke liye nahi tha 🌹
  </p>
</div>

</div>

<script>
function openPage(id){
  document.querySelectorAll('.card > div').forEach(d=>d.classList.add('hidden'));
  document.getElementById(id).classList.remove('hidden');
}

var roseMessages=[
  "You are my favourite feeling ❤️",
  "Life feels softer with you 🌸",
  "I choose you, every single day 🫶🏻",
  "You matter more than you know 🤍"
];

function pickRose(){
  document.getElementById("roseMessage").innerText =
    roseMessages[Math.floor(Math.random()*roseMessages.length)];
}
</script>

</body>
</html>
