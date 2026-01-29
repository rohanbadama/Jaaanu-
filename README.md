<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Forever Valentine ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap');

        :root {
            --pink-bg: #fff0f3;
            --dark-pink: #ff4d6d;
            --rose-red: #c9184a;
        }

        body {
            margin: 0; padding: 0;
            background-color: var(--pink-bg);
            font-family: 'Poppins', sans-serif;
            display: flex; justify-content: center; align-items: center;
            height: 100vh; overflow: hidden;
        }

        /* Floating Hearts Animation */
        .heart {
            position: absolute; color: rgba(255, 77, 109, 0.3);
            animation: float 4s linear infinite; font-size: 20px;
        }
        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        .container {
            background: rgba(255, 255, 255, 0.95);
            padding: 25px; border-radius: 30px;
            box-shadow: 0 15px 50px rgba(255, 77, 109, 0.25);
            width: 90%; max-width: 400px;
            display: none; text-align: center;
            position: relative; z-index: 10;
            animation: scaleIn 0.5s ease;
            max-height: 85vh; overflow-y: auto;
        }

        .active { display: block; }

        @keyframes scaleIn { from { transform: scale(0.8); opacity: 0; } to { transform: scale(1); opacity: 1; } }

        h1 { color: var(--dark-pink); font-family: 'Dancing Script', cursive; font-size: 2.2rem; }
        
        /* Video Styling */
        .video-box { position: relative; width: 100%; border-radius: 20px; overflow: hidden; border: 3px solid var(--dark-pink); }
        video { width: 100%; display: block; }
        
        .replay-btn {
            position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
            background: rgba(255, 77, 109, 0.8); color: white; padding: 10px 20px;
            border-radius: 20px; cursor: pointer; display: none; border: none; font-weight: bold;
        }

        button {
            background: var(--dark-pink); color: white; border: none;
            padding: 12px 30px; border-radius: 50px; cursor: pointer;
            font-weight: bold; transition: 0.3s; margin-top: 15px;
            box-shadow: 0 5px 15px rgba(255, 77, 109, 0.4);
        }

        button:hover { background: var(--rose-red); transform: translateY(-2px); }

        .rose-box { display: flex; justify-content: center; gap: 15px; font-size: 45px; margin: 20px 0; }
        .rose { cursor: pointer; transition: 0.3s; filter: drop-shadow(0 4px 4px rgba(0,0,0,0.1)); }

        .letter-content {
            text-align: left; background: #fffcf2; border: 1px dashed var(--dark-pink);
            padding: 20px; font-style: italic; color: #444; line-height: 1.7;
            font-size: 0.95rem; border-radius: 15px;
        }

        .cat-gif { width: 140px; margin-bottom: 10px; border-radius: 10px; }
        #msg-display { color: var(--rose-red); font-weight: 600; min-height: 40px; margin: 10px 0; font-size: 0.9rem;}
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="https://www.chosic.com/wp-content/uploads/2021/04/Warm-Memories-Emotional-Inspiring-Piano.mp3" type="audio/mp3">
    </audio>

    <div id="page1" class="container active">
        <img src="https://media.tenor.com/On7tBy_9mS0AAAAi/peach-goma-love.gif" class="cat-gif">
        <h1>Hey Gorgeous! 🌹</h1>
        <p>Before we start, turn up the volume... I have something special for you.</p>
        <button onclick="startExperience()">Open Your Surprise ❤️</button>
    </div>

    <div id="page2" class="container">
        <h1>This is for you... ❤️</h1>
        <div class="video-box">
            <video id="mainVideo" onended="videoEnded()">
                <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
            </video>
            <button class="replay-btn" id="replayBtn" onclick="replayVideo()">Replay Video 🔄</button>
        </div>
        <p id="videoDesc">Every moment with you is a treasure.</p>
        <button onclick="nextPage(3)">Continue... ✨</button>
    </div>

    <div id="page3" class="container">
        <h1>Pick a Rose</h1>
        <img src="https://media.tenor.com/X9S79Uu3v7MAAAAi/mochi-mochi-peach-cat-cat.gif" class="cat-gif" style="width: 100px;">
        <div class="rose-box">
            <span class="rose" onclick="reveal('You are the most beautiful person I have ever known, inside and out. 💖')">🌹</span>
            <span class="rose" onclick="reveal('Thank you for choosing me every single day. I am so lucky! 🍀')">🌹</span>
            <span class="rose" onclick="reveal('My love for you grows stronger with every heartbeat. 💓')">🌹</span>
        </div>
        <div id="msg-display"></div>
        <button id="nxt-btn" style="display:none;" onclick="nextPage(4)">Read My Message 💌</button>
    </div>

    <div id="page4" class="container">
        <h1>Deep From My Heart</h1>
        <div class="letter-content">
            My Dearest Love, <br><br>
            I tried to find the perfect words to tell you how much you mean to me, but I realized that no language has enough beauty to describe you. You are the light that guide me through my darkest days and the joy that completes my happiest ones. <br><br>
            Watching the video we made, I am reminded of how lucky I am to have you by my side. Every smile you give me feels like a thousand roses blooming at once. You are my soulmate, my best friend, and my forever. <br><br>
            On this Rose Day, I promise to protect your smile, to cherish our memories, and to love you more than I did yesterday. I am yours, today and for all the tomorrows to come. <br><br>
            <b>Forever & Always, ❤️</b>
        </div>
        <button onclick="nextPage(5)">Final Page 🌸</button>
    </div>

    <div id="page5" class="container">
        <h1>I Love You To Infinity!</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="cat-gif">
        <p style="font-size: 1.1rem; color: var(--rose-red); font-weight: bold;">Happy Rose Day, My Queen! 🌹</p>
        <button onclick="location.reload()">Start Over ❤️</button>
    </div>

    <script>
        const bgMusic = document.getElementById('bgMusic');
        const mainVideo = document.getElementById('mainVideo');
        const replayBtn = document.getElementById('replayBtn');

        function startExperience() {
            bgMusic.play();
            nextPage(2);
            // Switch audio
            bgMusic.volume = 0.2; 
            mainVideo.play();
            mainVideo.volume = 1.0;
            bgMusic.pause(); // Pause bg music while video plays
        }

        function videoEnded() {
            replayBtn.style.display = 'block';
            bgMusic.play(); // Restart bg music
            bgMusic.volume = 0.5;
        }

        function replayVideo() {
            replayBtn.style.display = 'none';
            bgMusic.pause();
            mainVideo.currentTime = 0;
            mainVideo.play();
        }

        let count = 0;
        function nextPage(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
            if(n !== 2) {
                mainVideo.pause();
                bgMusic.play();
            }
        }

        function reveal(m) {
            document.getElementById('msg-display').innerText = m;
            count++;
            if(count >= 3) document.getElementById('nxt-btn').style.display = 'inline-block';
        }

        // Generate Floating Hearts
        setInterval(() => {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 4000);
        }, 500);
    </script>
</body>
</html>
