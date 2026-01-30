<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>365 Days With You ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  background: linear-gradient(135deg, #ffd6e7, #fff);
  overflow-x: hidden;
  text-align: center;
}
section {
  min-height: 100vh;
  padding: 40px 15px;
  display: none;
  animation: fade 1s ease;
}
section.active { display: block; }
@keyframes fade {
  from {opacity:0; transform:translateY(20px);}
  to {opacity:1; transform:translateY(0);}
}
h1 { color:#d63384; }
button {
  padding:12px 25px;
  margin:15px;
  border:none;
  border-radius:25px;
  background:#ff4d88;
  color:white;
  font-size:16px;
  cursor:pointer;
}
button:hover { background:#e6005c; }
.gif { width:200px; border-radius:15px; margin:10px; }
.gallery img { width:170px; margin:8px; border-radius:12px; }
video { width:90%; max-width:500px; margin:15px 0; border-radius:15px; }
canvas { background:white; border:3px solid pink; margin-top:15px; }
</style>
</head>
<body>

<div id="player" style="display:none;"></div>

<section id="home" class="active">
  <h1>365 Days With You ❤️</h1>
  <img class="gif" src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif">
  <p>One year. One us. Forever to go.</p>
  <button onclick="showSection('game')">Start Our Journey 🎮</button>
</section>

<section id="game">
  <h1>Collect All My Love ❤️</h1>
  <canvas id="gameCanvas" width="600" height="400"></canvas>
  <div id="winMessage" style="display:none;">
    <h2>You found all my love ❤️</h2>
    <img class="gif" src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399975205376052/From_KlickPin_CF_Resultado_de_imagen_para_Milk__Mocha_STICKERS___Hug_gif_Cute_gif_Cute_love_gif.gif">
    <br>
    <button onclick="showSection('memories')">Continue 💌</button>
  </div>
</section>

<section id="memories">
  <h1>Our Memories 📸</h1>
  <div class="gallery">
    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png">
    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png">
    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg">
    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png">
    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032864981164/FreeFire_10_20_2025_19_46_49.png">
    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436033343262720/FreeFire_11_06_2025_17_43_23.png">
    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436033917747447/FreeFire_12_15_2025_18_05_48.png">
    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436034366799882/FreeFire_12_22_2025_10_44_53.png">
    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032407933071/Screenshot_2025-10-30-17-57-27-678_com.instagram.android.jpg">
  </div>
  <button onclick="showSection('videos')">Next ▶️</button>
</section>

<section id="videos">
  <h1>Our Videos 🎥</h1>
  <video controls class="vid"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448687809954058/lv_7555554315964878141_20260117212840.mp4"></video>
  <video controls class="vid"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448576363233361/lv_7572376034872478993_20260129201229.mp4"></video>
  <video controls class="vid"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448578389217290/lv_7596206565158423861_20260129200129.mp4"></video>
  <video controls class="vid"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577013354598/lv_7591172117144587573_20260129201020.mp4"></video>
  <video controls class="vid"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4"></video>
  <button onclick="showSection('letter')">Final Surprise 💖</button>
</section>

<section id="letter">
  <h1>Happy 1year anniversary meri FOREVER 🫶🏻💖</h1>
  <p style="max-width:900px;margin:auto;font-size:18px;line-height:1.8;white-space:pre-line;">
Aaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai, kyunki ye sirf dates ka guzar jana nahi tha, balki do alag zindagiyon ka dheere dheere ek doosre ki aadat ban jana tha. Shuruaat shayad simple thi, thodi awkward, thodi hasi mazaak wali, thodi confusion se bhari hui, lekin usi shuruaat me ek sachchai thi — baat karne ka mann, ek doosre ko samajhne ki koshish, aur bina mile bhi ek connection mehsoos hona. Dheere dheere hamari baatein routine nahi rahi, zarurat ban gayi; din kaisa gaya, kya khaya, kis baat pe hansi aayi, kis baat ne pareshan kiya — ye sab share karte karte hum sirf lovers nahi, balki ek doosre ke safe place ban gaye. Is ek saal me humne sirf achhe din hi nahi dekhe, balki misunderstandings, mood swings, overthinking, gussa, rona, dooriyan aur wapas paas aane ki koshish bhi dekhi, aur shayad isi wajah se ye rishta aur real lagta hai, kyunki ye perfect nahi tha, par sachcha tha. Aapne mujhe patience sikhaya, sikhaya ki har baat ka turant jawab nahi hota, kuch baatein samajhne me waqt lagta hai; aapne mujhe care ka matlab samjhaya, ki pyaar sirf “I love you” bolne me nahi, balki “khana khaya?” “thak gaye ho kya?” jaisi chhoti chhoti baaton me hota hai. Maine bhi apni taraf se ye seekha ki kisi ko apni life me rakhna sirf khushi baantna nahi, balki uske dard ko bhi samajhna hota hai, chahe wo hamesha shabdon me na bataya ja sake. Kabhi kabhi main galat samjha, kabhi aap hurt hui, kabhi maine overthink kiya, kabhi aap chup ho gayi — par phir bhi humne poori tarah haath nahi chhoda, aur shayad isi me is rishte ki asli taqat hai. Aap meri life me sirf ek insaan ki tarah nahi, balki ek ehsaas ki tarah aayi — aisi aadat jo din me kai baar yaad aati hai, aisi fikr jo bina wajah bhi hoti rehti hai, aisi muskurahat jo sirf aapki ek simple si line se aa jaati hai. Is ek saal me maine ye bhi samjha ki pyaar ka matlab control nahi, samajhna hota hai; possess karna nahi, appreciate karna hota hai; har waqt perfect rehna nahi, balki galti hone par maan lena hota hai. Aage ka safar kaisa hoga, ye shayad hum dono aaj poori tarah nahi jaante, par main itna zaroor jaanta hoon ki main aapke saath grow karna chahta hoon — zyada samajhdaar banke, zyada shaant banke, zyada supportive banke. Main chahta hoon ki jab aap thaki ho to aapko sukoon mile, jab aap khush ho to wo khushi dugni ho, jab aap pareshan ho to aapko lage ki koi bina judge kiye sunne wala hai. Main promise perfect hone ka nahi kar sakta, par ye zaroor keh sakta hoon ki main har din koshish karunga ki kal se thoda better insaan ban paun — aapke liye nahi sirf, balki humare liye. Ye ek saal sirf memories ka collection nahi, balki ek foundation tha — trust ka, care ka, emotional connection ka. Aage bhi misunderstandings aayengi, mood swings aayenge, busy din aayenge, par agar hum baat karna nahi chhodenge aur ek doosre ko enemy nahi samjhenge, to koi bhi problem humse badi nahi hogi. Aap meri zindagi me ek chapter nahi, balki ek aisi kahani ho jo abhi likhi ja rahi hai, dheere dheere, patience ke saath, feelings ke saath. Aaj ke din bas itna kehna hai ki jo bhi tha, jaisa bhi tha, ye saal mere liye special tha kyunki isme aap thi — aapki awaaz, aapka tareeka, aapka gussa, aapki care, sab kuch. Aur agar aap saath ho, to main aage ke saalon ko bhi isi tarah sambhal ke chalna chahta hoon — respect ke saath, loyalty ke saath, aur us pyaar ke saath jo shor se nahi, par ehsaas se mehsoos hota hai.
Jab main aapke baare me sochta hoon na, to mujhe sabse pehle ye feel hota hai ki meri zindagi me jo bhi softness, jo bhi emotional depth, jo bhi sachcha care aaya hai, wo kahin na kahin aapse hi shuru hota hai, kyunki aap sirf ek insaan nahi ho, aap ek feeling ho jo dheere dheere meri aadat ban gayi. Aapki baat karne ka tareeka, aapka hasna, aapka gussa hona, aapka chup ho jana, even aapka “thik hu” bolne ka andaaz bhi mere liye alag hi importance rakhta hai, kyunki main aapko sirf sunta nahi, mehsoos karta hoon. Aap shayad realize bhi nahi karti ki aapki choti choti cheezein mere din pe kitna effect dalti hain — aapka ek normal sa message bhi mere mood ko theek kar deta hai, aapka thoda sa upset tone mujhe andar se restless kar deta hai, aur aapki khushi genuinely mere liye relief jaisi hoti hai. Mujhe aapse baat karne ke liye kisi special topic ki zarurat nahi hoti, kyunki aap khud hi mere liye topic ho, aapki presence hi kaafi hoti hai. Aapne shayad casually meri life me entry li hogi, par aaj aap meri life ka sabse serious, sabse real, aur sabse precious part ho. Mujhe aapke alawa kisi aur se koi matlab nahi hai, na emotionally, na mentally, kyunki jo connection mujhe aapse feel hota hai wo na replace ho sakta hai na compare. Aapki problems mere liye “aapki” nahi rehti, wo automatically “hamari” lagne lagti hain; aapka stress mujhe disturb karta hai, aapki health ki tension mujhe apni lagti hai, aur aapki thakan dekh ke dil karta hai kaash main kisi tarah aapko thoda sa sukoon de paun. Aap strong ho, par phir bhi aapki vulnerability mujhe aur zyada close feel karwati hai, kyunki mujhe lagta hai ki mujhe aapka khayal rakhna hai, bina aapko change kiye, bina aapko control kiye, bas aapke saath khade rehkar. Aap perfect nahi ho — aur shayad isi liye itni real ho, itni apni lagti ho. Aap jab overthink karti ho, jab mood swing hota hai, jab bina wajah irritate ho jati ho, tab bhi main aapko kam nahi, aur zyada pyaar karta hoon, kyunki wo sab aapka part hai, aur mujhe aap poori chahiye, sirf aapke easy wale din nahi. Aapne mujhe care ka actual matlab samjhaya — bina bade gestures ke, bina show off ke, bas presence se, bas is ehsaas se ki koi hai jo sach me matter karta hai. Aapki respect mere dil me itni naturally hai ki mujhe kabhi force nahi karna padta aapko value dene ke liye, wo khud hi feel hoti hai, har baat me, har soch me. Main jab future ke baare me sochta hoon to mujhe koi perfect picture nahi dikhti, mujhe bas aap dikhti ho — kabhi haste hue, kabhi thodi si naraz, kabhi thaki hui, par mere saath. Mujhe aapki aadat si ho gayi hai, par ye aadat unhealthy nahi lagti, ye sukoon wali aadat lagti hai, jaise din ke end me ghar wapas aana. Aap meri life me ho isliye main apne aap ko thoda better banana chahta hoon, thoda zyada patient, thoda zyada samajhdaar, thoda zyada worthy of you. Mujhe aapki har choti baat important lagti hai — aapne khana khaya ya nahi, aaj aapka mood kaisa hai, aap thak to nahi gayi, aapko kis baat ne hasaaya — ye sab mere liye random details nahi, ye sab meri care ke reasons hain. Aap meri priority ho bina mujhe loud hone ki zarurat pade, bina mujhe duniya ko prove karne ki zarurat pade. Jo jagah aapne meri life me le li hai na, waha ab koi aur aa bhi nahi sakta, kyunki wo jagah banayi hi aapne hai, apne tareeke se, apni presence se, apni reality se. Main aapko sirf isliye pyaar nahi karta kyunki aap meri ho, main aapko isliye pyaar karta hoon kyunki aap “aap” ho — jaisi ho waisi, bina filter ke, bina pretend kiye. Aur aaj main bas itna kehna chahta hoon ki chahe din simple ho ya complicated, baatein zyada ho ya kam, mood acha ho ya off, meri feelings aapke liye constant hain, steady hain, aur dil se hain. Aap meri choice nahi, meri clarity ho. I love you endlessly meri jaaaaaneman 😚💖.
  </p>
</section>

<script>
function showSection(id){
  document.querySelectorAll("section").forEach(s=>s.classList.remove("active"));
  document.getElementById(id).classList.add("active");
}

/* GAME */
const canvas=document.getElementById("gameCanvas");
const ctx=canvas.getContext("2d");
let player={x:50,y:200,size:20};
let hearts=[],keys={},collected=0,totalHearts=5;
for(let i=0;i<totalHearts;i++){
  hearts.push({x:Math.random()*550+20,y:Math.random()*350+20,size:15,collected:false});
}
document.addEventListener("keydown",e=>keys[e.key]=true);
document.addEventListener("keyup",e=>keys[e.key]=false);
function update(){
  if(keys["ArrowUp"])player.y-=3;
  if(keys["ArrowDown"])player.y+=3;
  if(keys["ArrowLeft"])player.x-=3;
  if(keys["ArrowRight"])player.x+=3;
  player.x=Math.max(0,Math.min(canvas.width-player.size,player.x));
  player.y=Math.max(0,Math.min(canvas.height-player.size,player.y));
  hearts.forEach(h=>{
    if(!h.collected && player.x<h.x+h.size && player.x+player.size>h.x && player.y<h.y+h.size && player.y+player.size>h.y){
      h.collected=true; collected++;
    }
  });
  if(collected===totalHearts){
    document.getElementById("winMessage").style.display="block";
  }
}
function drawHeart(x,y,s){
  ctx.fillStyle="pink";
  ctx.beginPath();
  ctx.moveTo(x,y);
  ctx.bezierCurveTo(x,y-s/2,x-s,y-s/2,x-s,y);
  ctx.bezierCurveTo(x-s,y+s/2,x,y+s,x,y+s);
  ctx.bezierCurveTo(x,y+s,x+s,y+s/2,x+s,y);
  ctx.bezierCurveTo(x+s,y-s/2,x,y-s/2,x,y);
  ctx.fill();
}
function draw(){
  ctx.clearRect(0,0,canvas.width,canvas.height);
  ctx.fillStyle="red";
  ctx.fillRect(player.x,player.y,player.size,player.size);
  hearts.forEach(h=>{if(!h.collected)drawHeart(h.x,h.y,h.size);});
}
function loop(){update();draw();requestAnimationFrame(loop);} loop();

/* YOUTUBE MUSIC */
var tag=document.createElement('script');
tag.src="https://www.youtube.com/iframe_api";
document.body.appendChild(tag);
var playerYT;
function onYouTubeIframeAPIReady(){
  playerYT=new YT.Player('player',{
    videoId:'fPii4kwD7Zc',
    playerVars:{autoplay:1,loop:1,playlist:'fPii4kwD7Zc'},
    events:{onReady:e=>e.target.setVolume(40)}
  });
}
document.querySelectorAll("video").forEach(v=>{
  v.addEventListener("play",()=>{ if(playerYT) playerYT.pauseVideo(); });
  v.addEventListener("ended",()=>{ if(playerYT) playerYT.playVideo(); });
});
</script>
</body>
</html>
