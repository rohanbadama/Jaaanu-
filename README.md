<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Queen 👑🌹</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@400;600&family=Great+Vibes&display=swap');

        :root {
            --bg-pink: #ffccd5;
            --accent-pink: #ff4d6d;
            --rose-red: #c9184a;
            --card-white: #fffafa;
        }

        body {
            margin: 0; padding: 0;
            background-color: var(--bg-pink);
            font-family: 'Poppins', sans-serif;
            display: flex; justify-content: center; align-items: center;
            height: 100vh; overflow: hidden;
        }

        /* Fixed Animations: Falling Hearts & Sparkles */
        .decoration {
            position: absolute; pointer-events: none;
            animation: fallAnimation 5s linear infinite; z-index: 1;
            font-size: 20px;
        }
        @keyframes fallAnimation {
            0% { transform: translateY(-10vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
        }

        .container {
            background: var(--card-white);
            border-radius: 30px;
            box-shadow: 0 10px 40px rgba(255, 77, 109, 0.2);
            width: 90%; max-width: 380px;
            padding: 30px 20px;
            display: none; text-align: center;
            position: relative; z-index: 10;
            animation: popIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            max-height: 90vh; overflow-y: auto;
        }

        .active { display: block; }
        @keyframes popIn { from { transform: scale(0.8); opacity: 0; } to { transform: scale(1); opacity: 1; } }

        .ribbon { position: absolute; top: 15px; right: 20px; font-size: 24px; color: #ff8fa3; }
        h1 { font-family: 'Dancing Script', cursive; color: var(--accent-pink); font-size: 2rem; margin: 10px 0; }
        .main-gif { width: 120px; margin: 15px auto; display: block; border-radius: 10px; }
        .sub-text { font-size: 0.9rem; color: #555; line-height: 1.6; }

        .btn {
            background: var(--accent-pink); color: white; border: none;
            padding: 12px 25px; border-radius: 50px; cursor: pointer;
            font-weight: 600; transition: 0.3s; margin-top: 15px;
        }
        .btn:hover { transform: scale(1.05); background: var(--rose-red); }

        /* Game 1: Catch the Hearts */
        #game-area { width: 100%; height: 200px; background: #fff0f3; border-radius: 15px; position: relative; overflow: hidden; border: 2px dashed var(--accent-pink); }
        .catch-heart { position: absolute; cursor: pointer; font-size: 25px; transition: 0.1s; }

        /* Game 2: Scratch Card */
        .scratch-container { position: relative; width: 200px; height: 100px; margin: 0 auto; background: #ff4d6d; border-radius: 10px; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; cursor: crosshair; overflow: hidden; }
        .scratch-overlay { position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: #ccc; transition: 0.5s; }

        /* Game 3: Compliment Puzzle */
        .puzzle-btn { margin: 5px; padding: 8px 15px; background: white; border: 2px solid var(--accent-pink); border-radius: 20px; cursor: pointer; font-size: 0.8rem; }
        .puzzle-btn.selected { background: var(--accent-pink); color: white; }

        .video-wrapper { width: 100%; border-radius: 20px; overflow: hidden; border: 3px solid var(--accent-pink); margin: 15px 0; background: #000; }
        video { width: 100%; display: block; }

        .letter-box { background: #fffef0; border-left: 4px solid var(--accent-pink); padding: 20px; text-align: left; font-family: 'Great Vibes', cursive; font-size: 1.3rem; line-height: 1.8; border-radius: 10px; max-height: 300px; overflow-y: auto; }
    </style>
</head>
<body>

    <div id="animation-layer"></div>

    <div style="display:none"><div id="player"></div></div>

    <div id="page1" class="container active">
        <span class="ribbon">🎀</span>
        <h1>Hi Gorgeous! ❤️</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="main-gif">
        <p class="sub-text">Maine tumhare liye kuch games aur surprises taiyar kiye hain. Let's play? ✨</p>
        <button class="btn" onclick="startFlow()">Yes, Let's Go! 🫶🏻</button>
    </div>

    <div id="page2" class="container">
        <h1>Catch My Love! ❤️</h1>
        <p class="sub-text">Inhe catch karo, har heart mein ek tareef hai!</p>
        <div id="game-area"></div>
        <p id="game-msg" style="color:var(--rose-red); font-weight:bold; margin-top:10px;">Hearts pakdo!</p>
        <button id="btn2" class="btn" style="display:none;" onclick="nextPage(3)">Next Game ➡️</button>
    </div>

    <div id="page3" class="container">
        <h1>Solve the Truth 🧩</h1>
        <p class="sub-text">Sahi tareef ko select karo!</p>
        <div id="puzzle-area">
            <button class="puzzle-btn" onclick="checkPuzzle(this, 'wrong')">Ordinary</button>
            <button class="puzzle-btn" onclick="checkPuzzle(this, 'correct')">The Most Beautiful Girl 🌸</button>
            <button class="puzzle-btn" onclick="checkPuzzle(this, 'wrong')">Just Okay</button>
            <button class="puzzle-btn" onclick="checkPuzzle(this, 'correct')">My Life Line ❤️</button>
            <button class="puzzle-btn" onclick="checkPuzzle(this, 'correct')">Cutest Smile Ever 😊</button>
        </div>
        <p id="puzzle-msg" style="min-height: 40px; margin-top:10px;"></p>
        <button id="btn3" class="btn" style="display:none;" onclick="nextPage(4)">Surprise Dekho! 🎬</button>
    </div>

    <div id="page4" class="container">
        <h1>For you 🫶🏻🎀</h1>
        <div class="video-wrapper">
            <video id="mainVideo" onended="showLetterBtn()">
                <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
            </video>
        </div>
        <button id="btn4" class="btn" style="display:none;" onclick="nextPage(5)">Read My Deep Feelings 💌</button>
    </div>

    <div id="page5" class="container">
        <h1>From My Heart ❤️</h1>
        <div class="letter-box">
            My Dearest,<br><br>
            Tumhe pata hai, jab bhi main games khelta hoon ya life ki bhag-daur mein hota hoon, mera sukoon sirf tumhare paas milta hai. Tumhari aankhein, tumhari smile, aur tumhara mujhse baat karne ka tarika... ye sab milkar meri duniya ko jannat banate hain. <br><br>
            Main shayad har roz nahi keh pata, par tum sach mein is poori duniya ki sabse pyari ladki ho. Tumhare saath har pal ek game jaisa exciting aur har subah ek rose jaisi fresh lagti hai. Main hamesha tumhara saath nibhaunga, chahe life koi bhi level throw kare.<br><br>
            Happy Rose Day, My Queen! You are my forever winner. ❤️
        </div>
        <button class="btn" style="margin-top:20px;" onclick="location.reload()">Replay Love ❤️</button>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let player;
        function onYouTubeIframeAPIReady() {
            player = new YT.Player('player', {
                height: '0', width: '0', videoId: 'l6E16JAk_Fs',
                playerVars: { 'autoplay': 1, 'loop': 1, 'playlist': 'l6E16JAk_Fs' }
            });
        }

        function startFlow() {
            if(player) player.unMute();
            nextPage(2);
            spawnHearts();
        }

        function nextPage(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
            const v = document.getElementById('mainVideo');
            if(n === 4) { if(player) player.pauseVideo(); v.play(); } 
            else { v.pause(); if(player) player.playVideo(); }
        }

        // --- GAME 1 LOGIC ---
        let caught = 0;
        const compliments = ["Tumhari smile qatal hai! 😍", "Sabse sundar aankhein! ✨", "Mera sukoon ho tum! ❤️", "Cutest person ever! 🎀"];
        function spawnHearts() {
            const area = document.getElementById('game-area');
            const h = document.createElement('div');
            h.className = 'catch-heart';
            h.innerHTML = '❤️';
            h.style.left = Math.random() * 80 + '%';
            h.style.top = Math.random() * 80 + '%';
            h.onclick = function() {
                document.getElementById('game-msg').innerText = compliments[Math.floor(Math.random()*compliments.length)];
                this.remove();
                caught++;
                if(caught >= 5) {
                    document.getElementById('game-msg').innerText = "Winner! Tum sach mein sabse pyari ho! 🏆";
                    document.getElementById('btn2').style.display = 'inline-block';
                } else { spawnHearts(); }
            };
            area.appendChild(h);
        }

        // --- GAME 2 LOGIC ---
        let puzzleCount = 0;
        function checkPuzzle(btn, type) {
            if(type === 'correct') {
                btn.classList.add('selected');
                btn.onclick = null;
                puzzleCount++;
                document.getElementById('puzzle-msg').innerHTML = "<span style='color:green'>Sach kaha! Tum hi toh ho! 😍</span>";
                if(puzzleCount >= 3) document.getElementById('btn3').style.display = 'inline-block';
            } else {
                document.getElementById('puzzle-msg').innerHTML = "<span style='color:red'>Bilkul nahi! Tum isse 1000x zyada ho! 😡❤️</span>";
            }
        }

        function showLetterBtn() { 
            document.getElementById('btn4').style.display = 'inline-block'; 
            if(player) player.playVideo();
        }

        // CSS Animations Creator
        setInterval(() => {
            const d = document.createElement('div');
            d.className = 'decoration';
            d.innerHTML = ['❤️','🌸','✨','🌹'][Math.floor(Math.random()*4)];
            d.style.left = Math.random() * 100 + 'vw';
            d.style.animationDuration = (Math.random()*3 + 2) + 's';
            document.getElementById('animation-layer').appendChild(d);
            setTimeout(() => d.remove(), 5000);
        }, 300);
    </script>
</body>
</html>
