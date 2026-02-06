<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For You 🫶🏻💗</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  background: #ffe6ef;
  color: #333;
  text-align: center;
}

section {
  display: none;
  min-height: 100vh;
  padding: 20px;
}

section.active {
  display: block;
}

button {
  padding: 12px 22px;
  border: none;
  border-radius: 25px;
  background: #ff4d88;
  color: white;
  font-size: 16px;
  cursor: pointer;
  margin-top: 20px;
}

h1, h2 {
  color: #ff2f73;
}

.gif-bg {
  background-size: cover;
  background-position: center;
}

/* Roses */
.roses {
  display: flex;
  justify-content: center;
  gap: 15px;
  flex-wrap: wrap;
}
.rose {
  font-size: 40px;
  cursor: pointer;
}

/* Photos */
.gallery img {
  width: 90%;
  max-width: 300px;
  border-radius: 15px;
  margin: 10px;
}

/* Videos */
video {
  width: 95%;
  max-width: 500px;
  border-radius: 15px;
}

/* Game */
.game-box {
  font-size: 40px;
  cursor: pointer;
}

/* Letter */
.letter {
  background: #fff;
  padding: 20px;
  border-radius: 15px;
  text-align: left;
  white-space: pre-wrap;
}
</style>
</head>

<body>

<!-- LANDING -->
<section id="landing" class="active gif-bg"
style="background-image:url('http://tmpfiles.org/dl/22876715/fromklickpincftkthao219bubududugif-tkthao219bubududupanda-discoversharegifs_cutecartoonquotescuteanimecatcutebeardrawings1.gif')">
<h1>Happy Rose Day 🌹</h1>
<button onclick="go('roses')">Tap to Begin</button>
</section>

<!-- ROSE PAGE -->
<section id="roses" class="gif-bg"
style="background-image:url('http://tmpfiles.org/dl/22876666/fromklickpincfpinvonelizavetapauesovaaufenrgy_gifbilderlustigniedlicheliebeszeichentrickliebegifthealeni.gif')">
<h2>Tap a Rose for a Message 🌸</h2>

<div class="roses">
  <div class="rose" onclick="alert('You are my favorite feeling 🫶🏻')">🌹</div>
  <div class="rose" onclick="alert('Your smile makes everything softer 💗')">🌹</div>
  <div class="rose" onclick="alert('With you, even silence feels beautiful 🤍')">🌹</div>
  <div class="rose" onclick="alert('You are home to my heart 🏡❤️')">🌹</div>
  <div class="rose" onclick="alert('I choose you, every single day 🌹')">🌹</div>
</div>

<button onclick="go('photos')">Next 💞</button>
</section>

<!-- PHOTOS -->
<section id="photos">
<h2>Our Memories 🎀🧿</h2>

<div class="gallery">
<img src="https://i.postimg.cc/yNqkyd81/IMG_20260206_190532.png">
<img src="https://i.postimg.cc/s2Fv4Xg3/IMG_20260206_190558.png">
<img src="https://i.postimg.cc/K831TLx4/IMG_20260206_190630.png">
<img src="https://i.postimg.cc/rp6KNmw8/IMG_20260206_190726.png">
<img src="https://i.postimg.cc/XNxB64s3/IMG_20260206_190744.png">
<img src="https://i.postimg.cc/MGkvmTpR/IMG_20260206_190444.png">
<img src="https://i.postimg.cc/k5rBv4gN/IMG_20260206_190512.png">
<img src="https://i.postimg.cc/xdrc3C16/IMG_20260206_190418.png">
</div>

<button onclick="go('videos')">Next 💗</button>
</section>

<!-- VIDEOS -->
<section id="videos">
<h2>For You 🫶🏻💗</h2>

<video controls src="https://files.catbox.moe/mw3f2q.mp4"></video><br><br>
<video controls src="https://files.catbox.moe/ggbrik.mp4"></video><br><br>
<video controls src="https://files.catbox.moe/sfk5b8.mp4"></video><br><br>
<video controls src="https://files.catbox.moe/p150ss.mp4"></video><br><br>
<video controls src="https://files.catbox.moe/3ju0zb.mp4"></video><br><br>
<video controls src="https://files.catbox.moe/6kf2dd.mp4"></video>

<button onclick="go('games')">Next 🎮</button>
</section>

<!-- GAMES -->
<section id="games" class="gif-bg"
style="background-image:url('http://tmpfiles.org/dl/22876616/fromklickpincfpinbyceciliadelpantaongif_cutegifcutelovecartoonscutelovepictures.gif')">
<h2>Little Games 💕</h2>

<p>Tap the heart 💖</p>
<div class="game-box" onclick="alert('You won my heart already 🫶🏻')">💖</div>

<br><br>
<p>Choose one:</p>
<button onclick="alert('Forever us 🤍')">You & Me</button>
<button onclick="alert('Still You 🫶🏻')">Only You</button>

<button onclick="go('letter')">Next ✉️</button>
</section>

<!-- LETTER -->
<section id="letter" class="gif-bg"
style="background-image:url('http://tmpfiles.org/dl/22876413/fromklickpincfbunnysticker-bunny-discoversharegifs_cutelovegifcutegifloveyougif.gif')">
<h2>From My Heart 🤍</h2>

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

</section>

<script>
function go(id){
  document.querySelectorAll('section').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}
</script>

</body>
</html>
