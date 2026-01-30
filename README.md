<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>365 Days With You ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
  body { margin: 0; font-family: 'Arial', sans-serif; background: #fff0f5; text-align: center; overflow-x: hidden; }
  section { min-height: 100vh; display: none; flex-direction: column; align-items: center; justify-content: center; padding: 20px; box-sizing: border-box; }
  .active { display: flex; animation: fadeIn 0.5s; }
  @keyframes fadeIn { from {opacity:0;} to {opacity:1;} }
  
  .card { background: white; padding: 25px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); width: 100%; max-width: 450px; }
  h1 { color: #d63384; font-size: 2rem; }
  
  /* Game Area */
  #game-zone { width: 300px; height: 300px; background: #ffeef2; border: 3px dashed #ff4d88; position: relative; margin: 20px auto; overflow: hidden; border-radius: 15px; touch-action: none; }
  .heart-target { position: absolute; font-size: 30px; cursor: pointer; user-select: none; }

  button { background: #ff4d88; color: white; border: none; padding: 15px 30px; border-radius: 50px; font-size: 18px; cursor: pointer; margin-top: 15px; width: 80%; }
  
  .letter-box { text-align: left; height: 300px; overflow-y: auto; background: #fdfdfd; padding: 15px; border-radius: 10px; border: 1px solid #eee; font-size: 14px; line-height: 1.6; white-space: pre-wrap; margin-top: 10px; }
  
  video { width: 100%; border-radius: 10px; margin: 10px 0; background: #000; }
  .gif { width: 150px; margin-bottom: 15px; }
</style>
</head>
<body>

<audio id="bgMusic" loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<section id="s1" class="active">
  <div class="card">
    <img class="gif" src="https://media.giphy.com/media/vFKqnCdLPNOKc/giphy.gif">
    <h1>365 Days With You ❤️</h1>
    <p>Music aur Games ke saath journey shuru karein?</p>
    <button onclick="startApp()">Yes, Start! ✨</button>
  </div>
</section>

<section id="s2">
  <div class="card">
    <h1>Catch 5 Hearts! ❤️</h1>
    <p>Hearts par tap karo aage badhne ke liye!</p>
    <div id="game-zone"></div>
    <p id="scoreText">Found: 0/5</p>
  </div>
</section>

<section id="s3">
  <div class="card">
    <h1>Our Memories 🎥</h1>
    <video id="vidPlayer" controls>
       <source src="https://www.dropbox.com/scl/fi/o9usm8k2p2kuuk7mx6bl7/lv_7519771999514676541_20260129202958.mp4?rlkey=65vejp4ckxe7ydmn71u0s5c4j&st=ukezepjh&raw=1" type="video/mp4">
    </video>
    <button onclick="goLetter()">Skip to Final Letter ✉️</button>
  </div>
</section>

<section id="s4">
  <div class="card" style="max-width: 600px;">
    <h1>To My Forever 🫶🏻</h1>
    <div id="typingBox" class="letter-box"></div>
    <p style="color: #ff4d88; font-weight: bold; margin-top: 10px;">Happy Anniversary Jaan! ❤️</p>
  </div>
</section>

<script>
const msg = `Happy 1 year anniversary meri FOREVER 🫶🏻 💖 \nAaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon... (Yahan aapka pura message load hoga)... I love you endlessly!`;

let score = 0;
const music = document.getElementById('bgMusic');

function show(id) {
  document.querySelectorAll('section').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}

function startApp() {
  music.play().catch(() => console.log("Music needs interaction"));
  show('s2');
  spawnHeart();
}

function spawnHeart() {
  if(score >= 5) {
    show('s3');
    return;
  }
  const zone = document.getElementById('game-zone');
  const h = document.createElement('div');
  h.className = 'heart-target';
  h.innerHTML = '❤️';
  h.style.left = Math.random() * 250 + 'px';
  h.style.top = Math.random() * 250 + 'px';
  h.onclick = () => {
    score++;
    document.getElementById('scoreText').innerText = `Found: ${score}/5`;
    zone.removeChild(h);
    spawnHeart();
  };
  zone.appendChild(h);
}

function goLetter() {
  show('s4');
  const box = document.getElementById('typingBox');
  let i = 0;
  // Speed calculation for 2 seconds
  const speed = 2000 / msg.length;
  const interval = setInterval(() => {
    box.innerHTML += msg.charAt(i);
    i++;
    box.scrollTop = box.scrollHeight;
    if(i >= msg.length) clearInterval(interval);
  }, speed);
}
</script>
</body>
</html>
