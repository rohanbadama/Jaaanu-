<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Anniversary My Jaan ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap');
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { background: #fff5f7; font-family: 'Poppins', sans-serif; overflow: hidden; color: #4a0e0e; }

        /* Page System */
        .page { 
            display: none; width: 100%; height: 100vh; flex-direction: column; 
            align-items: center; justify-content: center; padding: 20px; 
            text-align: center; position: absolute; background: white;
        }
        .active { display: flex !important; animation: fadeIn 0.6s ease; }
        @keyframes fadeIn { from { opacity: 0; transform: scale(0.95); } to { opacity: 1; transform: scale(1); } }

        h1 { font-family: 'Dancing Script', cursive; font-size: 2.8rem; color: #ff4d6d; margin-bottom: 10px; }
        h3 { font-size: 1.1rem; color: #c9184a; margin-bottom: 20px; font-weight: 500; }

        /* Media Elements */
        .gif-box { width: 280px; border-radius: 20px; border: 5px solid #ffccd5; margin-bottom: 20px; box-shadow: 0 10px 20px rgba(0,0,0,0.05); }
        .video-card { width: 310px; border-radius: 25px; border: 8px solid white; box-shadow: 0 15px 35px rgba(0,0,0,0.15); overflow: hidden; }
        video { width: 100%; display: block; }

        /* Letter Styling */
        .letter-scroll { 
            background: #fffafa; width: 90%; max-width: 380px; height: 420px; 
            overflow-y: auto; padding: 30px; border-radius: 25px; text-align: left; 
            line-height: 1.8; border: 2px solid #ffccd5; box-shadow: inset 0 0 15px rgba(0,0,0,0.03);
        }

        /* Photo Slider */
        .slider { width: 280px; height: 380px; border-radius: 20px; border: 6px solid white; position: relative; overflow: hidden; box-shadow: 0 10px 20px rgba(0,0,0,0.1); }
        .slider img { width: 100%; height: 100%; object-fit: cover; position: absolute; top:0; left:0; opacity:0; transition: 0.5s; }
        .slider img.active { opacity: 1; }

        /* Interaction Elements */
        .game-input { width: 100%; padding: 12px; border-radius: 12px; border: 2px solid #ffccd5; margin-top: 10px; text-align: center; outline: none; }
        .btn { background: #ff4d6d; color: white; border: none; padding: 14px 35px; border-radius: 50px; font-weight: 600; cursor: pointer; margin-top: 20px; box-shadow: 0 5px 15px rgba(255, 77, 109, 0.3); }
        .btn:active { transform: scale(0.95); }

        /* Background Effects */
        .heart { position: fixed; color: #ff4d6d; pointer-events: none; z-index: 99; animation: floatUp 4s linear forwards; }
        @keyframes floatUp { to { transform: translateY(-110vh) rotate(360deg); opacity: 0; } }

        /* Hidden YT Player for Background Music */
        #yt-bg { position: absolute; width: 0; height: 0; pointer-events: none; opacity: 0; }
    </style>
</head>
<body>

<div id="yt-bg">
    <iframe id="player" width="10" height="10" 
    src="https://www.youtube.com/embed/fPii4kwD7Zc?enablejsapi=1&autoplay=1&loop=1&playlist=fPii4kwD7Zc" 
    frameborder="0" allow="autoplay"></iframe>
</div>

<div class="page active" id="p1">
    <h1>Our Special Journey ❤️</h1>
    <img src="https://media.tenor.com/7S8YgN_Gv98AAAAi/cute-cat.gif" class="gif-box">
    <button class="btn" onclick="startApp()">Enter My World ✨</button>
</div>

<div class="page" id="p2">
    <img src="https://media.tenor.com/gYf_65_AclAAAAAi/milk-and-mocha.gif" class="gif-box">
    <h3>Game 1: Hamari pehli mulakat ki date?</h3>
    <input type="text" class="game-input" placeholder="Likho yahan...">
    <button class="btn" onclick="go(3)">Next ➡</button>
</div>
<div class="page" id="p3">
    <img src="https://media.tenor.com/X-1M5qC6v3QAAAAi/hug.gif" class="gif-box">
    <h3>Game 2: Mera sabse pasandida rang?</h3>
    <input type="text" class="game-input" placeholder="Guess karo...">
    <button class="btn" onclick="go(4)">Next ➡</button>
</div>
<div class="page" id="p4">
    <img src="https://media.tenor.com/vH95e5vW6EIAAAAi/mocha.gif" class="gif-box">
    <h3>Game 3: Hamari sabse pehli fight kis baat pe hui thi?</h3>
    <input type="text" class="game-input" placeholder="Yaad hai?">
    <button class="btn" onclick="go(5)">Next ➡</button>
</div>
<div class="page" id="p5">
    <img src="https://media.tenor.com/9-C-S-kKzG8AAAAi/cute.gif" class="gif-box">
    <h3>Game 4: Wo ek cheez jo mujhe aapme sabse pyaari lagti hai?</h3>
    <input type="text" class="game-input" placeholder="Batao...">
    <button class="btn" onclick="go(6)">Next ➡</button>
</div>

<div class="page" id="p6">
    <h3>A Gift for You... 🎁</h3>
    <div class="video-card">
        <video id="vid1" controls onplay="controlMusic('pause')" onpause="controlMusic('play')">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4" type="video/mp4">
        </video>
    </div>
    <button class="btn" onclick="go(7)">Next Video ➡</button>
</div>
<div class="page" id="p11">
    <h1>Message from My Heart 💌</h1>
    <div class="letter-scroll">
        <p><b>Meri Pyari Jaan,</b></p>
        <p>Happy 1st Anniversary! Ye ek saal mere liye kisi sapne se kam nahi tha. Maine har din tumse kuch naya seekha aur har pal tumse aur bhi zyada pyar kiya.</p>
        <p>Tumhara mere saath hona hi meri sabse badi taqat hai. Wo hamari baatein, wo lambi raatein, aur wo choti-choti khushiyan—main sab kuch hamesha ke liye sambhal kar rakhna chahta hoon.</p>
        <p>I promise to be with you in every situation. You are my world, my soulmate, and my forever. Love you infinitely! ❤️</p>
    </div>
    <button class="btn" onclick="go(12)">Next: A Surprise ➡</button>
</div>

<div class="page" id="p12">
    <img src="https://media.tenor.com/v8tT9oV7jPAAAAAi/cute.gif" class="gif-box">
    <h3>You're the sweetest thing ever!</h3>
    <button class="btn" onclick="go(13)">Next ➡</button>
</div>
<div class="page" id="p17">
    <h1>Our Best Memories 📸</h1>
    <div class="slider" onclick="nextSlide()">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png" class="active">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466437297821192326/Screenshot_2025-07-21-03-45-44-645_com.instagram.android.jpg">
    </div>
    <p style="margin-top:10px; font-size:0.8rem">Tap to swipe photos</p>
    <button class="btn" onclick="go(18)">Check Feedback 😍</button>
</div>

<div class="page" id="p18">
    <h1>Maja Aaya? 😍</h1>
    <button class="btn" onclick="go(19)">Haa! ❤️ (Phase 2 Start)</button>
    <button class="btn" style="background:#888" onmouseover="runAway(this)">Naa 😤</button>
</div>

<div class="page" id="p19">
    <h1>Phase 2: More Magic... ✨</h1>
    <img src="https://media.tenor.com/fM-p64f5_78AAAAi/cute-mocha.gif" class="gif-box">
    <button class="btn" onclick="go(20)">Continue ➡</button>
</div>

<div class="page" id="p30">
    <h1>Thank You Jaaneman ❤️</h1>
    <p>I LOVE YOU FOREVER AND EVER!</p>
    <img src="https://media.tenor.com/p_65_AclAAAAAi/love-mocha.gif" class="gif-box">
</div>

<script>
    // YouTube API Controller
    var player;
    function onYouTubeIframeAPIReady() {
        player = new YT.Player('player');
    }

    function controlMusic(action) {
        var iframe = document.getElementById('player').contentWindow;
        if (action === 'play') {
            iframe.postMessage('{"event":"command","func":"playVideo","args":""}', '*');
        } else {
            iframe.postMessage('{"event":"command","func":"pauseVideo","args":""}', '*');
        }
    }

    function startApp() {
        controlMusic('play');
        go(2);
    }

    function go(n) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        var nextPage = document.getElementById('p' + n);
        if(nextPage) nextPage.classList.add('active');
        
        // Stop all local videos
        document.querySelectorAll('video').forEach(v => { v.pause(); v.currentTime = 0; });
        controlMusic('play');
    }

    let si = 0;
    function nextSlide() {
        let imgs = document.querySelectorAll('.slider img');
        imgs[si].classList.remove('active');
        si = (si + 1) % imgs.length;
        imgs[si].classList.add('active');
    }

    function runAway(b) {
        b.style.position = 'absolute';
        b.style.left = Math.random() * 80 + '%';
        b.style.top = Math.random() * 80 + '%';
    }

    // Hearts Animation
    setInterval(() => {
        let h = document.createElement('div');
        h.innerHTML = '❤️'; h.className = 'heart';
        h.style.left = Math.random() * 100 + 'vw';
        h.style.top = '100vh';
        h.style.fontSize = (Math.random() * 20 + 10) + 'px';
        document.body.appendChild(h);
        setTimeout(() => h.remove(), 4000);
    }, 400);
</script>
<script src="https://www.youtube.com/iframe_api"></script>
</body>
</html>
