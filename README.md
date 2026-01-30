<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>365 Days With You ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&family=Great+Vibes&display=swap" rel="stylesheet">

<style>
  :root { --pink: #ff4d88; --dark-pink: #d63384; }
  body { margin: 0; font-family: 'Poppins', sans-serif; background: #fff0f5; overflow-x: hidden; text-align: center; color: #333; }
  
  section { min-height: 100vh; padding: 20px 15px; display: none; animation: fade 0.8s ease; box-sizing: border-box; }
  section.active { display: flex; flex-direction: column; align-items: center; justify-content: center; }
  
  @keyframes fade { from {opacity:0; transform:scale(0.95);} to {opacity:1; transform:scale(1);} }

  h1 { font-family: 'Great Vibes', cursive; font-size: 3rem; color: var(--dark-pink); margin-bottom: 10px; }
  p { font-size: 1.1rem; max-width: 600px; margin: 10px auto; }

  /* Glass Cards */
  .glass { background: rgba(255, 255, 255, 0.7); backdrop-filter: blur(10px); border-radius: 20px; padding: 20px; box-shadow: 0 10px 25px rgba(214, 51, 132, 0.1); width: 100%; max-width: 500px; }

  button { padding: 14px 30px; margin: 15px; border: none; border-radius: 50px; background: var(--pink); color: white; font-size: 18px; font-weight: bold; cursor: pointer; transition: 0.3s; box-shadow: 0 5px 15px rgba(255, 77, 136, 0.3); }
  button:hover { background: var(--dark-pink); transform: translateY(-3px); }

  .gif { width: 180px; border-radius: 15px; margin-bottom: 15px; }
  .gallery img { width: 100px; height: 100px; object-fit: cover; margin: 5px; border-radius: 10px; border: 2px solid white; }
  
  video { width: 100%; max-width: 450px; border-radius: 15px; margin: 10px 0; border: 3px solid white; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }

  /* Game Canvas */
  canvas { background: white; border: 5px solid var(--pink); border-radius: 15px; max-width: 100%; height: auto; cursor: crosshair; touch-action: none; }

  /* Fast Letter Styling */
  .letter-box { text-align: left; height: 400px; overflow-y: auto; background: white; padding: 20px; border-radius: 15px; font-size: 16px; line-height: 1.8; border: 1px solid #ffc1d6; white-space: pre-wrap; box-shadow: inset 0 0 10px rgba(0,0,0,0.05); }
</style>
</head>
<body>

<div id="player" style="position:absolute; top:-9999px;"></div>

<section id="home" class="active">
  <div class="glass">
    <h1>365 Days With You ❤️</h1>
    <img class="gif" src="https://media.giphy.com/media/v1.Y2lkPTZjMDliOTUyc3R1am8wY2k4MW9zMTBhZGdnM2QxYXM4YmhxZnB5ZGRoYmlscTh1MiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/vFKqnCdLPNOKc/giphy.gif">
    <p>One year. One us. Forever to go. <br> Main tumhare liye kuch khaas banaya hai...</p>
    <button onclick="startExperience()">Start Our Journey 🎮</button>
  </div>
</section>

<section id="game">
  <h1>Collect My Love ❤️</h1>
  <p>Canvas par touch/click karke hearts pakdo!</p>
  <canvas id="gameCanvas" width="400" height="400"></canvas>
  <div id="winMessage" style="display:none; margin-top:15px;">
    <h2>You found it all! ❤️</h2>
    <img class="gif" src="https://media.giphy.com/media/v1.Y2lkPTZjMDliOTUyajZ0YWN6enhkMzdjYTZqb3h6emk4N2c0M2c0MXpmYTA1Ynd0NnNpaSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/TjSPQgowhhJdHgvnwA/giphy.gif">
    <br>
    <button onclick="showSection('memories')">Continue 💌</button>
  </div>
</section>

<section id="memories">
  <h1>Our Memories 📸</h1>
  <div class="glass">
    <div class="gallery">
      <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png">
      <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png">
      <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg">
      <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png">
      <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032864981164/FreeFire_10_20_2025_19_46_49.png">
      <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436033343262720/FreeFire_11_06_2025_17_43_23.png">
    </div>
    <button onclick="showSection('videos')">See Our Videos ▶️</button>
  </div>
</section>

<section id="videos">
  <h1>Our Videos 🎥</h1>
  <div class="glass">
    <video id="v1" controls class="vid"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448687809954058/lv_7555554315964878141_20260117212840.mp4"></video>
    <video id="v2" controls class="vid"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448576363233361/lv_7572376034872478993_20260129201229.mp4"></video>
    <button onclick="showSection('letter'); startFastTyping();">Final Surprise 💖</button>
  </div>
</section>

<section id="letter">
  <h1>To My Forever 🫶🏻</h1>
  <div class="glass" style="max-width: 600px;">
    <div id="letterBox" class="letter-box"></div>
    <p style="margin-top:20px; font-weight:bold; color:var(--dark-pink);">I Love You Endlessly! 😚💖</p>
  </div>
</section>

<script src="https://www.youtube.com/iframe_api"></script>
<script>
const fullText = `Happy 1 year anniversary meri FOREVER 🫶🏻 💖 \n\nAaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai, kyunki ye sirf dates ka guzar jana nahi tha, balki do alag zindagiyon ka dheere dheere ek doosre ki aadat ban jana tha. Shuruaat shayad simple thi, thodi awkward, thodi hasi mazaak wali, thodi confusion se bhari hui, lekin usi shuruaat me ek sachchai thi — baat karne ka mann, ek doosre ko samajhne ki koshish, aur bina mile bhi ek connection mehsoos hona. Dheere dheere hamari baatein routine nahi rahi, zarurat ban gayi; din kaisa gaya, kya khaya, kis baat pe hansi aayi, kis baat ne pareshan kiya — ye sab share karte karte hum sirf lovers nahi, balki ek doosre ke safe place ban gaye. Is ek saal me humne sirf achhe din hi nahi dekhe, balki misunderstandings, mood swings, overthinking, gussa, rona, dooriyan aur wapas paas aane ki koshish bhi dekhi, aur shayad isi wajah se ye rishta aur real lagta hai, kyunki ye perfect nahi tha, par sachcha tha. Aapne mujhe patience sikhaya, sikhaya ki har baat ka turant jawab nahi hota, kuch baatein samajhne me waqt lagta hai; aapne mujhe care ka matlab samjhaya, ki pyaar sirf “I love you” bolne me nahi, balki “khana khaya?” “thak gaye ho kya?” jaisi chhoti chhoti baaton me hota hai. Maine bhi apni taraf se ye seekha ki kisi ko apni life me rakhna sirf khushi baantna nahi, balki uske dard ko bhi samajhna hota hai, chahe wo hamesha shabdon me na bataya ja sake. Kabhi kabhi main galat samjha, kabhi aap hurt hui, kabhi maine overthink kiya, kabhi aap chup ho gayi — par phir bhi humne poori tarah haath nahi chhoda, aur shayad isi me is rishte ki asli taqat hai. Aap meri life me sirf ek insaan ki tarah nahi, balki ek ehsaas ki tarah aayi — aisi aadat jo din me kai baar yaad aati hai, aisi fikr jo bina wajah bhi hoti rehti hai, aisi muskurahat jo sirf aapki ek simple si line se aa jaati hai. Is ek saal me maine ye bhi samjha ki pyaar ka matlab control nahi, samajhna hota hai; possess karna nahi, appreciate karna hota hai; har waqt perfect rehna nahi, balki galti hone par maan lena hota hai. Aage ka safar kaisa hoga, ye shayad hum dono aaj poori tarah nahi jaante, par main itna zaroor jaanta hoon ki main aapke saath grow karna chahta hoon — zyada samajhdaar banke, zyada shaant banke, zyada supportive banke. Main chahta hoon ki jab aap thaki ho to aapko sukoon mile, jab aap khush ho to wo khushi dugni ho, jab aap pareshan ho to aapko lage ki koi bina judge kiye sunne wala hai. Main promise perfect hone ka nahi kar sakta, par ye zaroor keh sakta hoon ki main har din koshish karunga ki kal se thoda better insaan ban paun — aapke liye nahi sirf, balki humare liye. Ye ek saal sirf memories ka collection nahi, balki ek foundation tha — trust ka, care ka, emotional connection ka. Aage bhi misunderstandings aayengi, mood swings aayenge, busy din aayenge, par agar hum baat karna nahi chhodenge aur ek doosre ko enemy nahi samjhenge, to koi bhi problem humse badi nahi hogi. Aap meri zindagi me ek chapter nahi, balki ek aisi kahani ho jo abhi likhi ja rahi hai, dheere dheere, patience ke saath, feelings ke saath. Aaj ke din bas itna kehna hai ki jo bhi tha, jaisa bhi tha, ye saal mere liye special tha kyunki isme aap thi — aapki awaaz, aapka tareeka, aapka gussa, aapka care, sab kuch. Aur agar aap saath ho, to main aage ke saalon ko bhi isi tarah sambhal ke chalna chahta hoon — respect ke saath, loyalty ke saath, aur us pyaar ke saath jo shor se nahi, par ehsaas se mehsoos hota hai.\n\nJab main aapke baare me sochta hoon na, to mujhe sabse pehle ye feel hota hai ki meri zindagi me jo bhi softness, jo bhi emotional depth, jo bhi sachcha care aaya hai, wo kahin na kahin aapse hi shuru hota hai, kyunki aap sirf ek insaan nahi ho, aap ek feeling ho jo dheere dheere meri aadat ban gayi. Aapki baat karne ka tareeka, aapka hasna, aapka gussa hona, aapka chup ho jana, even aapka “thik hu” bolne ka andaaz bhi mere liye alag hi importance rakhta hai, kyunki main aapko sirf sunta nahi, mehsoos karta hoon. Aap shayad realize bhi nahi karti ki aapki choti choti cheezein mere din pe kitna effect dalti hain — aapka ek normal sa message bhi mere mood ko theek kar deta hai, aapka thoda sa upset tone mujhe andar se restless kar deta hai, aur aapki khushi genuinely mere liye relief jaisi hoti hai. Mujhe aapse baat karne ke liye kisi special topic ki zarurat nahi hoti, kyunki aap khud hi mere liye topic ho, aapki presence hi kaafi hoti hai. Aapne shayad casually meri life me entry li hogi, par aaj aap meri life ka sabse serious, sabse real, aur sabse precious part ho. Mujhe aapke alawa kisi aur se koi matlab nahi hai, na emotionally, na mentally, kyunki jo connection mujhe aapse feel hota hai wo na replace ho sakta hai na compare. Aapki problems mere liye “aapki” nahi rehti, wo automatically “hamari” lagne lagti hain; aapka stress mujhe disturb karta hai, aapki health ki tension mujhe apni lagti hai, aur aapki thakan dekh ke dil karta hai kaash main kisi tarah aapko thoda sa sukoon de paun. Aap strong ho, par phir bhi aapki vulnerability mujhe aur zyada close feel karwati hai, kyunki mujhe lagta hai ki mujhe aapka khayal rakhna hai, bina aapko change kiye, bina aapko control kiye, bas aapke saath khade rehkar. Aap perfect nahi ho — aur shayad isi liye itni real ho, itni apni lagti ho. Aap jab overthink karti ho, jab mood swing hota hai, jab bina wajah irritate ho jati ho, tab bhi main aapko kam nahi, aur zyada pyaar karta hoon, kyunki wo sab aapka part hai, aur mujhe aap poori chahiye, sirf aapke easy wale din nahi. Aapne mujhe care ka actual matlab samjhaya — bina bade gestures ke, bina show off ke, bas presence se, bas is ehsaas se ki koi hai jo sach me matter karta hai. Aapki respect mere dil me itni naturally hai ki mujhe kabhi force nahi karna padta aapko value dene ke liye, wo khud hi feel hoti hai, har baat me, har soch me. Main jab future ke baare me sochta hoon to mujhe koi perfect picture nahi dikhti, mujhe bas aap dikhti ho — kabhi haste hue, kabhi thodi si naraz, kabhi thaki hui, par mere saath. Mujhe aapki aadat si ho gayi hai, par ye aadat unhealthy nahi lagti, ye sukoon wali aadat lagti hai, jaise din ke end me ghar wapas aana. Aap meri life me ho isliye main apne aap ko thoda better banana chahta hoon, thoda zyada patient, thoda zyada samajhdaar, thoda zyada worthy of you. Mujhe aapki har choti baat important lagti hai — aapne khana khaya ya nahi, aaj aapka mood kaisa hai, aap thak to nahi gayi, aapko kis baat ne hasaaya — ye sab mere liye random details nahi, ye sab meri care ke reasons hain. Aap meri priority ho bina mujhe loud hone ki zarurat pade, bina mujhe duniya ko prove karne ki zarurat pade. Jo jagah aapne meri life me le li hai na, waha ab koi aur aa bhi nahi sakta, kyunki wo jagah banayi hi aapne hai, apne tareeke se, apni presence se, apni reality se. Main aapko sirf isliye pyaar nahi karta kyunki aap meri ho, main aapko isliye pyaar karta hoon kyunki aap “aap” ho — jaisi ho waisi, bina filter ke, bina pretend kiye. Aur aaj main bas itna kehna chahta hoon ki chahe din simple ho ya complicated, baatein zyada ho ya kam, mood acha ho ya off, meri feelings aapke liye constant hain, steady hain, aur dil se hain. Aap meri choice nahi, meri clarity ho. I love you endlessly meri jaaaaaneman 😚💖.`;

let playerYT;
function onYouTubeIframeAPIReady(){
  playerYT = new YT.Player('player', {
    videoId: 'fPii4hwD7Zc',
    playerVars: { 'autoplay': 0, 'loop': 1, 'playlist': 'fPii4hwD7Zc' }
  });
}

function startExperience() {
  if(playerYT) playerYT.playVideo();
  showSection('game');
}

function showSection(id){
  document.querySelectorAll("section").forEach(s=>s.classList.remove("active"));
  document.getElementById(id).classList.add("active");
}

// GAME LOGIC (Touch & Click)
const canvas=document.getElementById("gameCanvas");
const ctx=canvas.getContext("2d");
let player={x:180,y:180,size:30};
let hearts=[],collected=0,total=5;

function initHearts() {
  hearts = [];
  for(let i=0;i<total;i++) hearts.push({x:Math.random()*340+20,y:Math.random()*340+20,s:15,c:false});
}
initHearts();

function handleInput(e) {
  let rect = canvas.getBoundingClientRect();
  let x = (e.clientX || e.touches[0].clientX) - rect.left;
  let y = (e.clientY || e.touches[0].clientY) - rect.top;
  player.x = x - player.size/2;
  player.y = y - player.size/2;
}
canvas.addEventListener("mousemove", handleInput);
canvas.addEventListener("touchmove", (e) => { e.preventDefault(); handleInput(e); }, {passive: false});

function drawHeart(x,y,s){
  ctx.fillStyle="#ff4d88"; ctx.beginPath();
  ctx.moveTo(x,y);
  ctx.bezierCurveTo(x,y-s/2,x-s,y-s/2,x-s,y);
  ctx.bezierCurveTo(x-s,y+s/2,x,y+s,x,y+s);
  ctx.bezierCurveTo(x,y+s,x+s,y+s/2,x+s,y);
  ctx.bezierCurveTo(x+s,y-s/2,x,y-s/2,x,y);
  ctx.fill();
}

function loop(){
  ctx.clearRect(0,0,400,400);
  ctx.font = "30px Arial"; ctx.fillText("👤", player.x, player.y + 25);
  hearts.forEach(h=>{
    if(!h.c && player.x < h.x+h.s && player.x+player.size > h.x-h.s && player.y < h.y+h.s && player.y+player.size > h.y-h.s){
      h.c=true; collected++;
    }
    if(!h.c) drawHeart(h.x, h.y, h.s);
  });
  if(collected === total) document.getElementById("winMessage").style.display="block";
  requestAnimationFrame(loop);
}
loop();

// FAST TYPING LOGIC (2 SECONDS)
function startFastTyping() {
  const box = document.getElementById("letterBox");
  box.innerHTML = "";
  let i = 0;
  const speed = 2000 / fullText.length; // 2000ms = 2 seconds
  const timer = setInterval(() => {
    if (i < fullText.length) {
      box.innerHTML += fullText.charAt(i);
      i++;
      box.scrollTop = box.scrollHeight;
    } else {
      clearInterval(timer);
    }
  }, speed);
}

// Music Pause/Play during videos
document.querySelectorAll("video").forEach(v=>{
  v.addEventListener("play",()=>{ if(playerYT) playerYT.pauseVideo(); });
  v.addEventListener("ended",()=>{ if(playerYT) playerYT.playVideo(); });
});
</script>
</body>
</html>
