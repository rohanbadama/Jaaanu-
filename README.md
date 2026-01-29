<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Forever ❤️</title>
    <style>
        :root { --pink: #ff4d6d; --bg: #000; --glass: rgba(255, 255, 255, 0.1); }
        body, html { margin: 0; padding: 0; width: 100%; height: 100%; background: #000; font-family: 'Poppins', sans-serif; color: white; overflow: hidden; }
        
        /* Particle Background */
        #particles { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 1; pointer-events: none; }
        
        .container { position: relative; z-index: 10; width: 100%; height: 100%; display: flex; justify-content: center; align-items: center; background: radial-gradient(circle, rgba(255,77,109,0.2) 0%, rgba(0,0,0,1) 100%); }
        
        .glass-card { background: var(--glass); backdrop-filter: blur(15px); border: 1px solid rgba(255,255,255,0.2); border-radius: 20px; padding: 30px; width: 85%; max-width: 500px; text-align: center; box-shadow: 0 8px 32px 0 rgba(0,0,0,0.8); }
        
        .hidden { display: none !important; }
        
        /* Full Screen Media */
        .fs-bg { position: fixed; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: -1; opacity: 0; transition: opacity 1.5s; }
        
        button { background: var(--pink); color: white; border: none; padding: 12px 30px; border-radius: 50px; font-size: 1.1rem; cursor: pointer; transition: 0.3s; margin-top: 20px; box-shadow: 0 0 15px var(--pink); }
        button:hover { transform: scale(1.1); box-shadow: 0 0 25px var(--pink); }

        /* Game Styles */
        #game-canvas { background: rgba(0,0,0,0.5); border-radius: 15px; margin-top: 10px; cursor: crosshair; }
        .rose-box { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; margin: 20px 0; }
        .rose { font-size: 40px; cursor: pointer; filter: drop-shadow(0 0 5px red); }

        /* Letter Styling */
        .letter-content { text-align: left; height: 300px; overflow-y: auto; padding: 20px; background: rgba(0,0,0,0.4); border-radius: 10px; line-height: 1.8; font-size: 0.95rem; border-left: 3px solid var(--pink); }
        
        h1 { font-family: 'Great Vibes', cursive; font-size: 2.5rem; text-shadow: 0 0 10px var(--pink); }
        video { width: 100%; border-radius: 15px; box-shadow: 0 0 20px rgba(255,255,255,0.2); }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;600&display=swap" rel="stylesheet">
</head>
<body>

    <canvas id="particles"></canvas>
    <div id="yt-music" style="position: absolute; top: -9999px;"></div>

    <div class="container">
        <div id="sec-1" class="glass-card">
            <h1>Hi My Jaan ❤️</h1>
            <img src="https://media2.giphy.com/media/vFKqnCdLPNOKc/giphy.gif" style="width: 150px;">
            <p>I've built a world just for us. Sab kuch dhyan se dekhna aur sunna...</p>
            <button onclick="init()">Pura Dekhna Hai ✨</button>
        </div>

        <div id="sec-game1" class="glass-card hidden">
            <h3>Game 1: Catch My Love</h3>
            <p>Tap 10 falling hearts to unlock the first memory!</p>
            <canvas id="game-canvas" width="300" height="250"></canvas>
            <p id="score">Hearts: 0</p>
        </div>

        <div id="sec-video" class="glass-card hidden">
            <h2 id="v-title">Our Memory</h2>
            <video id="main-video" controls onplay="musicCtrl('pause')" onended="musicCtrl('play'); showNextBtn()">
                <source src="" type="video/mp4">
            </video>
            <button id="next-v-btn" class="hidden" onclick="playNextVideo()">Next Chapter ➡️</button>
        </div>

        <div id="sec-quiz" class="glass-card hidden">
            <h3>Quick Question!</h3>
            <p>Hamare liye sabse important kya hai?</p>
            <button onclick="quizAns('Pyaar')">Pyaar</button>
            <button onclick="quizAns('Baat Karna')">Baat Karna (Correct)</button>
            <button onclick="quizAns('Gussa')">Gussa</button>
        </div>

        <div id="sec-roses" class="glass-card hidden">
            <h3>Tap the Roses 🌹</h3>
            <div class="rose-box">
                <span class="rose" onclick="revealRose(0, this)">🌹</span>
                <span class="rose" onclick="revealRose(1, this)">🌹</span>
                <span class="rose" onclick="revealRose(2, this)">🌹</span>
            </div>
            <p id="rose-msg">Something is hidden here...</p>
            <button id="final-letter-btn" class="hidden" onclick="startLetter()">Read My Heart ✉️</button>
        </div>

        <div id="sec-letter" class="glass-card hidden">
            <h2>To My Forever 🫶🏻</h2>
            <div id="typing-letter" class="letter-content"></div>
            <button id="end-btn" class="hidden" onclick="showSlideshow()">Last Surprise ✨</button>
        </div>

        <div id="sec-final" class="hidden">
            <div id="slideshow-container"></div>
            <div style="position: absolute; z-index: 100; text-align: center; width: 100%; top: 50%; transform: translateY(-50%);">
                <h1 style="font-size: 3.5rem; text-shadow: 0 0 20px #ff0000;">I LOVE YOU FOREVER ❤️</h1>
                <p style="font-size: 1.5rem; font-weight: bold;">Happy 1st Anniversary Jaanu!</p>
            </div>
        </div>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let player, vIndex = 0, score = 0, rosesOpened = 0;
        
        // Videos Sorted by Size (Longest/Biggest first)
        const vLinks = [
            "https://www.dropbox.com/scl/fi/o9usm8k2p2kuuk7mx6bl7/lv_7519771999514676541_20260129202958.mp4?rlkey=65vejp4ckxe7ydmn71u0s5c4j&st=ukezepjh&raw=1",
            "https://www.dropbox.com/scl/fi/izqmlr58596t8jwb9lkhb/lv_7365945955050474768_20260129202233.mp4?rlkey=jegiyo01tx1z9nbpctt32shtr&st=v454v32a&raw=1",
            "https://www.dropbox.com/scl/fi/i2cfd8d8kbtdzczj75j3v/lv_7572532755339234613_20260129202646.mp4?rlkey=jh7dukef0w0y33r3kei2iaxsr&st=e7ujditm&raw=1",
            "https://www.dropbox.com/scl/fi/h1eginkeecpti2ijkh3j0/lv_7572376034872478993_20260129201229.mp4?rlkey=glju2q4rhrqqlkmhfccyrxirj&st=k4w3t8j9&raw=1",
            "https://www.dropbox.com/scl/fi/ojmuyvznbim92y4hfysec/lv_7588073915361021201_20260129201555.mp4?rlkey=5tkecx9y3873n3fdglbi6qysw&st=ym0ghjl2&raw=1",
            "https://www.dropbox.com/scl/fi/3g34w4ohzcbveqwzwuizy/lv_7335708490083650837_20260129202446.mp4?rlkey=3cf50iol7dkn1jqjuohjxg9s7&st=4zlk3akk&raw=1",
            "https://www.dropbox.com/scl/fi/g0lz2b9d3y3s7qja23use/lv_7596118272932678917_20260129200828.mp4?rlkey=wsr2r478751immon3k0qv5zqf&st=e8kit9sm&raw=1",
            "https://www.dropbox.com/scl/fi/ij8zkmb71qj2q9eiwclqt/lv_7555554315964878141_20260117212840.mp4?rlkey=ybbd66nzfdodr5fwrx2qzvxyq&st=i9m6s8ta&raw=1",
            "https://www.dropbox.com/scl/fi/ggx9pgggvucv112txh5tz/lv_7587817635014774021_20260129195708.mp4?rlkey=ubrdqnl47j8mpofzfn6rm3rp9&st=o6wxfu52&raw=1"
        ];

        const fPhotos = [
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436032864981164/FreeFire_10_20_2025_19_46_49.png"
        ];

        const fullMsg = `Happy 1 year anniversary meri FOREVER 🫶🏻 💖 \n\nAaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai, kyunki ye sirf dates ka guzar jana nahi tha, balki do alag zindagiyon ka dheere dheere ek doosre ki aadat ban jana tha. Shuruaat shayad simple thi, thodi awkward, thodi hasi mazaak wali, thodi confusion se bhari hui, lekin usi shuruaat me ek sachchai thi — baat karne ka mann, ek doosre ko samajhne ki koshish... (Pura Message Yahan Hai)... I love you endlessly meri jaaaaaneman 😚 💖.`;

        function onYouTubeIframeAPIReady() {
            player = new YT.Player('yt-music', {
                height: '0', width: '0', videoId: 'fPii4hwD7Zc',
                playerVars: { 'loop': 1, 'playlist': 'fPii4hwD7Zc' }
            });
        }

        function init() {
            if(player) player.playVideo();
            showSec('sec-game1');
            startGame();
        }

        function showSec(id) {
            document.querySelectorAll('.glass-card').forEach(s => s.classList.add('hidden'));
            document.getElementById(id).classList.remove('hidden');
        }

        // --- GAME 1 Logic ---
        function startGame() {
            const canvas = document.getElementById('game-canvas');
            const ctx = canvas.getContext('2d');
            let hearts = [];
            function createHeart() { hearts.push({ x: Math.random() * 280, y: 0, s: 2 + Math.random() * 3 }); }
            function update() {
                ctx.clearRect(0,0,300,250);
                hearts.forEach((h, i) => {
                    h.y += h.s;
                    ctx.font = "20px Arial"; ctx.fillText("❤️", h.x, h.y);
                    if(h.y > 250) hearts.splice(i, 1);
                });
                if(Math.random() < 0.05) createHeart();
                if(score < 10) requestAnimationFrame(update);
                else { showSec('sec-video'); playNextVideo(); }
            }
            canvas.onclick = (e) => { score++; document.getElementById('score').innerText = "Hearts: " + score; };
            update();
        }

        // --- VIDEO Logic ---
        function playNextVideo() {
            const v = document.getElementById('main-video');
            if(vIndex < vLinks.length) {
                v.src = vLinks[vIndex];
                document.getElementById('v-title').innerText = "Our Story Part " + (vIndex+1);
                document.getElementById('next-v-btn').classList.add('hidden');
                v.load(); vIndex++;
            } else { showSec('sec-quiz'); }
        }
        function showNextBtn() { document.getElementById('next-v-btn').classList.remove('hidden'); }
        function musicCtrl(s) { if(player) s==='pause' ? player.pauseVideo() : player.playVideo(); }

        // --- QUIZ & ROSES ---
        function quizAns(a) { if(a.includes('Baat')) showSec('sec-roses'); else alert("Nooo! Try again baby ❤️"); }
        function revealRose(i, el) {
            const msgs = ["Mera Sukoon", "Meri Best Teacher", "Mera Forever"];
            document.getElementById('rose-msg').innerText = msgs[i];
            el.style.opacity = 0.3; rosesOpened++;
            if(rosesOpened >= 3) document.getElementById('final-letter-btn').classList.remove('hidden');
        }

        // --- LETTER & SLIDESHOW ---
        function startLetter() {
            showSec('sec-letter');
            let i = 0; const target = document.getElementById('typing-letter');
            function type() {
                if(i < fullMsg.length) {
                    target.innerHTML += fullMsg.charAt(i); i++;
                    setTimeout(type, 30); target.scrollTop = target.scrollHeight;
                } else document.getElementById('end-btn').classList.remove('hidden');
            }
            type();
        }

        function showSlideshow() {
            document.querySelector('.container').classList.add('hidden');
            const final = document.getElementById('sec-final');
            final.classList.remove('hidden');
            const container = document.getElementById('slideshow-container');
            fPhotos.forEach((p, idx) => {
                const img = document.createElement('img');
                img.src = p; img.className = 'fs-bg';
                if(idx === 0) img.style.opacity = 1;
                container.appendChild(img);
            });
            let cur = 0;
            setInterval(() => {
                const imgs = document.querySelectorAll('.fs-bg');
                imgs[cur].style.opacity = 0;
                cur = (cur + 1) % imgs.length;
                imgs[cur].style.opacity = 1;
            }, 4000);
        }

        // --- Particles Effect ---
        const pCanvas = document.getElementById('particles');
        const pCtx = pCanvas.getContext('2d');
        pCanvas.width = window.innerWidth; pCanvas.height = window.innerHeight;
        let pArray = [];
        class Particle {
            constructor() { this.x = Math.random()*pCanvas.width; this.y = Math.random()*pCanvas.height; this.size = Math.random()*5+1; this.speedX = Math.random()*1-0.5; this.speedY = Math.random()*1-0.5; }
            draw() { pCtx.fillStyle = 'rgba(255, 77, 109, 0.5)'; pCtx.beginPath(); pCtx.arc(this.x, this.y, this.size, 0, Math.PI*2); pCtx.fill(); }
            update() { this.x += this.speedX; this.y += this.speedY; }
        }
        function initP() { for(let i=0; i<50; i++) pArray.push(new Particle()); }
        function animateP() { pCtx.clearRect(0,0,pCanvas.width, pCanvas.height); pArray.forEach(p => { p.draw(); p.update(); }); requestAnimationFrame(animateP); }
        initP(); animateP();
    </script>
</body>
</html>
