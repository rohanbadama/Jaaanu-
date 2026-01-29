<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Forever ❤️</title>
    <style>
        body { background: #fff5f7; font-family: 'Segoe UI', sans-serif; margin: 0; overflow: hidden; }
        .page { display: none; width: 100vw; height: 100vh; flex-direction: column; align-items: center; justify-content: center; text-align: center; padding: 20px; box-sizing: border-box; }
        .active { display: flex; }
        
        /* Media Styling */
        .media-box { width: 90%; max-width: 320px; border: 8px solid white; border-radius: 20px; box-shadow: 0 10px 20px rgba(0,0,0,0.1); margin: 15px 0; overflow: hidden; }
        img, video { width: 100%; display: block; }
        
        /* Text Styling */
        h1 { color: #ff4d6d; font-size: 24px; margin: 10px 0; }
        p { color: #4a0e0e; font-size: 16px; margin: 5px 0; }
        .letter { background: white; padding: 20px; border-radius: 15px; height: 300px; overflow-y: auto; text-align: left; line-height: 1.6; border: 1px solid #ffccd5; }

        /* Buttons */
        .btn { background: #ff4d6d; color: white; border: none; padding: 15px 40px; border-radius: 50px; font-weight: bold; cursor: pointer; margin-top: 20px; }
        .btn:active { transform: scale(0.9); }
        
        .game-input { width: 80%; padding: 12px; border-radius: 10px; border: 2px solid #ffccd5; margin-top: 10px; }
    </style>
</head>
<body>

<audio id="bgMusic" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<div class="page active" id="p1">
    <div class="media-box"><img src="https://media.tenor.com/7S8YgN_Gv98AAAAi/cute-cat.gif"></div>
    <h1>Happy Anniversary My Jaan! ❤️</h1>
    <button class="btn" onclick="start()">Surprise Dekho ✨</button>
</div>

<div class="page" id="p2">
    <h1>Game 1 🎮</h1>
    <div class="media-box"><img src="https://media.tenor.com/gYf_65_AclAAAAAi/milk-and-mocha.gif"></div>
    <p>Hamari pehli baat kab hui thi?</p>
    <input type="text" class="game-input" placeholder="Yahan likho...">
    <button class="btn" onclick="go(3)">Next</button>
</div>
<div class="page" id="p3">
    <h1>Game 2 🎮</h1>
    <div class="media-box"><img src="https://media.tenor.com/X-1M5qC6v3QAAAAi/hug.gif"></div>
    <p>Mera favorite song?</p>
    <input type="text" class="game-input" placeholder="Type here...">
    <button class="btn" onclick="go(4)">Next</button>
</div>
<div class="page" id="p4">
    <h1>Game 3 🎮</h1>
    <div class="media-box"><img src="https://media.tenor.com/vH95e5vW6EIAAAAi/mocha.gif"></div>
    <p>Hum pehli baar kahan mile the?</p>
    <input type="text" class="game-input" placeholder="...">
    <button class="btn" onclick="go(5)">Next</button>
</div>
<div class="page" id="p5">
    <h1>Game 4 🎮</h1>
    <div class="media-box"><img src="https://media.tenor.com/9-C-S-kKzG8AAAAi/cute.gif"></div>
    <p>Mera bday kab aata hai?</p>
    <input type="text" class="game-input" placeholder="...">
    <button class="btn" onclick="go(6)">Next</button>
</div>

<div class="page" id="p6">
    <h1>For You... 🎁</h1>
    <div class="media-box"><video controls onplay="m(0)" onpause="m(1)"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4"></video></div>
    <button class="btn" onclick="go(7)">Next Video</button>
</div>
<div class="page" id="p11">
    <h1>My Heart 💌</h1>
    <div class="letter">
        <p><b>Jaaneman,</b></p>
        <p>Happy 1st Anniversary! (Message 1 yahan aayega jo tune diya tha). Main kitna lucky hoon ki tum meri life mein ho. Tumhare bina meri duniya adhuri hai. I love you so much!</p>
    </div>
    <button class="btn" onclick="go(12)">Next ✨</button>
</div>

<div class="page" id="p12">
    <div class="media-box"><img src="https://media.tenor.com/v8tT9oV7jPAAAAAi/cute.gif"></div>
    <p>You're My World! ❤️</p>
    <button class="btn" onclick="go(13)">Next</button>
</div>
<div class="page" id="p17">
    <h1>Our Memories 📸</h1>
    <div class="media-box" onclick="nextPic()">
        <img id="slideImg" src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png">
    </div>
    <p>Tap photo to swipe</p>
    <button class="btn" onclick="go(18)">Maja Aaya? 😍</button>
</div>

<div class="page" id="p18">
    <h1>Maja Aaya? 😍</h1>
    <button class="btn" onclick="go(19)">Haa! ❤️ (Phase 2)</button>
    <button class="btn" style="background:gray" onmouseover="move(this)">Naa 😤</button>
</div>

<div class="page" id="p19">
    <h1>Phase 2 Starts... 🌹</h1>
    <div class="media-box"><img src="https://media.tenor.com/fM-p64f5_78AAAAi/cute-mocha.gif"></div>
    <button class="btn" onclick="go(20)">Chalo Dekhte Hai ➡</button>
</div>

<script>
    const music = document.getElementById('bgMusic');
    const pics = [
        "https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png",
        "https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png",
        "https://cdn.discordapp.com/attachments/1421877888877203559/1466437297821192326/Screenshot_2025-07-21-03-45-44-645_com.instagram.android.jpg"
    ];
    let pIdx = 0;

    function start() { music.play(); go(2); }
    function m(s) { s ? music.play() : music.pause(); }
    
    function go(n) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        document.getElementById('p'+n).classList.add('active');
        document.querySelectorAll('video').forEach(v => v.pause());
        m(1);
    }

    function nextPic() {
        pIdx = (pIdx + 1) % pics.length;
        document.getElementById('slideImg').src = pics[pIdx];
    }

    function move(b) {
        b.style.position='absolute'; b.style.left=Math.random()*80+'%'; b.style.top=Math.random()*80+'%';
    }
</script>
</body>
</html>
