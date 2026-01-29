<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our 1st Anniversary ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap');
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { background: #fff0f3; font-family: 'Poppins', sans-serif; overflow: hidden; color: #590d22; }

        /* Page System */
        .page { 
            display: none; width: 100%; height: 100vh; 
            flex-direction: column; align-items: center; justify-content: center;
            padding: 20px; text-align: center; position: absolute;
            background: linear-gradient(135deg, #fff0f3 0%, #ffdde1 100%);
        }
        .active { display: flex !important; animation: fadeIn 0.8s ease; }
        @keyframes fadeIn { from { opacity: 0; transform: scale(0.9); } to { opacity: 1; transform: scale(1); } }

        h1 { font-family: 'Dancing Script', cursive; font-size: 2.5rem; color: #ff4d6d; text-shadow: 2px 2px 4px rgba(0,0,0,0.1); }
        .msg-text { font-size: 1.1rem; margin: 15px 0; font-weight: 400; max-width: 320px; }

        /* Elements */
        .gif-frame { width: 260px; border-radius: 20px; border: 6px solid white; box-shadow: 0 10px 25px rgba(255, 77, 109, 0.3); margin-bottom: 20px; }
        .video-container { width: 300px; border-radius: 20px; border: 8px solid white; box-shadow: 0 15px 35px rgba(0,0,0,0.2); overflow: hidden; }
        video { width: 100%; display: block; }
        
        .letter-scroll { 
            background: rgba(255, 255, 255, 0.9); width: 90%; max-width: 380px; height: 400px; 
            overflow-y: scroll; padding: 25px; border-radius: 25px; text-align: left; 
            line-height: 1.8; border: 2px solid #ffccd5; box-shadow: 0 10px 20px rgba(0,0,0,0.05);
        }

        .slider-box { width: 280px; height: 380px; border-radius: 20px; border: 6px solid white; position: relative; overflow: hidden; }
        .slider-box img { width: 100%; height: 100%; object-fit: cover; position: absolute; top:0; left:0; opacity:0; transition: 0.5s; }
        .slider-box img.active { opacity: 1; }

        .btn { 
            background: #ff4d6d; color: white; border: none; padding: 14px 35px; 
            border-radius: 50px; font-weight: 600; cursor: pointer; margin-top: 20px;
            box-shadow: 0 5px 15px rgba(255, 77, 109, 0.4); 
        }

        .game-card { background: white; padding: 20px; border-radius: 20px; width: 300px; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        input { width: 100%; padding: 10px; border-radius: 10px; border: 2px solid #ffccd5; margin-top: 10px; text-align: center; outline: none; }

        .heart { position: fixed; color: #ff4d6d; pointer-events: none; z-index: 99; animation: floatUp 4s linear forwards; }
        @keyframes floatUp { to { transform: translateY(-110vh) rotate(360deg); opacity: 0; } }
    </style>
</head>
<body>

<audio id="bgMusic" loop><source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg"></audio>

<div class="page active" id="p1">
    <h1>Hello My Jaan ❤️</h1>
    <img src="https://media.tenor.com/7S8YgN_Gv98AAAAi/cute-cat.gif" class="gif-frame">
    <button class="btn" onclick="start()">Click to Start ✨</button>
</div>

<div class="page" id="p2">
    <img src="https://media.tenor.com/gYf_65_AclAAAAAi/milk-and-mocha.gif" class="gif-frame">
    <div class="game-card"><p>Game 1: Guess our first hug date?</p><input type="text" placeholder="Answer here..."></div>
    <button class="btn" onclick="go(3)">Next ➡</button>
</div>
<div class="page" id="p6">
    <h1>For You... 🎁</h1>
    <div class="video-container">
        <video id="v1" controls onplay="m(0)" onpause="m(1)"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4" type="video/mp4"></video>
    </div>
    <button class="btn" onclick="go(7)">Next Video ➡</button>
</div>
<div class="page" id="p11">
    <h1>My First Letter 💌</h1>
    <div class="letter-scroll">
        <p><b>Meri Pyari Jaan,</b></p>
        <p>Happy 1st Anniversary! (Yahan tera pura 1st message aayega jo tune diya tha). Main kitna lucky hoon ki tum meri life mein ho. Hamari har choti khushi mere liye bohot badi hai...</p>
        <p>Scroll down to read more... I promise to love you forever and ever!</p>
    </div>
    <button class="btn" onclick="go(12)">Next ➡</button>
</div>

<div class="page" id="p12">
    <img src="https://media.tenor.com/v8tT9oV7jPAAAAAi/cute.gif" class="gif-frame">
    <p class="msg-text">You are the cutest person I know! ❤️</p>
    <button class="btn" onclick="go(13)">Next Card ➡</button>
</div>
<div class="page" id="p17">
    <h1>Our Best Memories 📸</h1>
    <div class="slider-box" onclick="nextSlide()">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png" class="active">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466437297821192326/Screenshot_2025-07-21-03-45-44-645_com.instagram.android.jpg">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032407933071/Screenshot_2025-10-30-17-57-27-678_com.instagram.android.jpg">
        </div>
    <button class="btn" onclick="go(18)">Check Feedback 😍</button>
</div>

<div class="page" id="p18">
    <h1>Maja Aaya? 😍</h1>
    <button class="btn" onclick="go(19)">Haa! ❤️ (Phase 2 Start)</button>
    <button class="btn" style="background:#888" onmouseover="move(this)">Naa 😤</button>
</div>

<div class="page" id="p19">
    <h1>Phase 2: More Love... 🌹</h1>
    <img src="https://media.tenor.com/fM-p64f5_78AAAAi/cute-mocha.gif" class="gif-frame">
    <button class="btn" onclick="go(20)">Continue ➡</button>
</div>

<div class="page" id="p20">
    <div class="game-card"><p>Game 5: My favorite color on you?</p><input type="text"></div>
    <button class="btn" onclick="go(21)">Next ➡</button>
</div>
<div class="page" id="p24">
    <h1>Something Special...</h1>
    <div class="video-container">
        <video id="v2" controls onplay="m(0)" onpause="m(1)"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448575633555579/lv_7335708490083650837_20260129202446.mp4" type="video/mp4"></video>
    </div>
    <button class="btn" onclick="go(25)">Next ➡</button>
</div>

<div class="page" id="p29">
    <h1>My Final Letter 💌</h1>
    <div class="letter-scroll">
        <p><b>Meri Jaaneman,</b></p>
        <p>(Yahan tera pura 2nd message aayega jo tune Jaaneman karke bhej tha). Tum meri poori duniya ho. Main tumhare bina ek pal nahi reh sakta. Thank you for this amazing year...</p>
        <p>I LOVE YOU SO MUCH! ❤️</p>
    </div>
    <button class="btn" onclick="go(30)">Finish ➡</button>
</div>

<div class="page" id="p30">
    <h1>Thank You & I Love You ❤️</h1>
    <img src="https://media.tenor.com/p_65_AclAAAAAi/love-mocha.gif" class="gif-frame">
    <p>Forever Yours!</p>
</div>

<script>
    let audio = document.getElementById('bgMusic');
    function start() { audio.play(); go(2); }
    function m(s) { if(s) audio.play(); else audio.pause(); }

    function go(n) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        document.getElementById('p'+n).classList.add('active');
        document.querySelectorAll('video').forEach(v => { v.pause(); v.currentTime = 0; });
        m(1);
    }

    let si = 0;
    function nextSlide() {
        let imgs = document.querySelectorAll('.slider-box img');
        imgs[si].classList.remove('active');
        si = (si + 1) % imgs.length;
        imgs[si].classList.add('active');
    }

    function move(b) {
        b.style.position='absolute'; b.style.left=Math.random()*80+'%'; b.style.top=Math.random()*80+'%';
    }

    setInterval(() => {
        let h = document.createElement('div'); h.innerHTML='❤️'; h.className='heart';
        h.style.left=Math.random()*100+'vw'; h.style.top='100vh';
        document.body.appendChild(h);
        setTimeout(() => h.remove(), 4000);
    }, 450);
</script>
</body>
</html>
