<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Just For You 🫶🏻🎀</title>
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
            position: absolute; color: rgba(255, 77, 109, 0.4);
            animation: float 4s linear infinite; font-size: 20px; z-index: 1;
        }
        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        .container {
            background: rgba(255, 255, 255, 0.98);
            padding: 25px; border-radius: 30px;
            box-shadow: 0 15px 50px rgba(255, 77, 109, 0.3);
            width: 90%; max-width: 400px;
            display: none; text-align: center;
            position: relative; z-index: 10;
            animation: scaleIn 0.5s ease;
            max-height: 85vh; overflow-y: auto;
        }

        .active { display: block; }

        @keyframes scaleIn { from { transform: scale(0.9); opacity: 0; } to { transform: scale(1); opacity: 1; } }

        h1 { color: var(--dark-pink); font-family: 'Dancing Script', cursive; font-size: 2.2rem; margin-top: 5px; }
        
        /* Video Container */
        .video-box { 
            position: relative; 
            width: 100%; 
            border-radius: 20px; 
            overflow: hidden; 
            border: 4px solid var(--dark-pink);
            background: #000;
            margin: 15px 0;
        }
        video { width: 100%; display: block; max-height: 400px; }
        
        .replay-overlay {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.6); display: none;
            justify-content: center; align-items: center; flex-direction: column;
        }

        button {
            background: var(--dark-pink); color: white; border: none;
            padding: 12px 30px; border-radius: 50px; cursor: pointer;
            font-weight: bold; transition: 0.3s; margin-top: 15px;
            box-shadow: 0 5px 15px rgba(255, 77, 109, 0.4);
            font-size: 1rem;
        }

        button:hover { background: var(--rose-red); transform: translateY(-2px); }

        .rose-box { display: flex; justify-content: center; gap: 15px; font-size: 50px; margin: 20px 0; }
        .rose { cursor: pointer; transition: 0.3s; filter: drop-shadow(0 4px 4px rgba(0,0,0,0.1)); }
        .rose:hover { transform: scale(1.2); }

        .letter-content {
            text-align: left; background: #fffcf2; border: 1px dashed var(--dark-pink);
            padding: 25px; font-style: italic; color: #444; line-height: 1.8;
            font-size: 0.95rem; border-radius: 15px; white-space: pre-line;
        }

        .cat-gif { width: 130px; margin-bottom: 10px; }
        #msg-display { color: var(--rose-red); font-weight: 600; min-height: 50px; margin: 10px 0; }
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="https://www.chosic.com/wp-content/uploads/2021/04/Warm-Memories-Emotional-Inspiring-Piano.mp3" type="audio/mp3">
    </audio>

    <div id="page1" class="container active">
        <img src="https://media.tenor.com/On7tBy_9mS0AAAAi/peach-goma-love.gif" class="cat-gif">
        <h1>For My Favorite Person 🎀</h1>
        <p>I have made something special for you. Please turn up your volume for the best experience.</p>
        <button onclick="startExperience()">Start Here ❤️</button>
    </div>

    <div id="page2" class="container">
        <h1>Just for you 🫶🏻🎀</h1>
        <div class="video-box">
            <video id="mainVideo" onended="videoEnded()">
                <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
            </video>
            <div class="replay-overlay" id="replayOverlay">
                <button onclick="replayVideo()">Watch Again 🔄</button>
            </div>
        </div>
        <p>Every second in this video is a memory I'll cherish forever.</p>
        <button onclick="nextPage(3)">Continue... ✨</button>
    </div>

    <div id="page3" class="container">
        <h1>A Rose for You</h1>
        <img src="https://media.tenor.com/X9S79Uu3v7MAAAAi/mochi-mochi-peach-cat-cat.gif" class="cat-gif" style="width: 100px;">
        <div class="rose-box">
            <span class="rose" onclick="reveal('You are the most beautiful chapter in my life story. 📖❤️')">🌹</span>
            <span class="rose" onclick="reveal('My life became a thousand times better the day you walked into it. 🌟')">🌹</span>
            <span class="rose" onclick="reveal('I promise to hold your hand through every high and every low. 💍')">🌹</span>
        </div>
        <div id="msg-display"></div>
        <button id="nxt-btn" style="display:none;" onclick="nextPage(4)">Read My Heart 💌</button>
    </div>

    <div id="page4" class="container">
        <h1>My Dearest...</h1>
        <div class="letter-content">
            To the one who holds my heart,

            Words often fail to capture how deeply I feel for you. You aren't just a part of my life; you are the light that makes everything clearer and the warmth that makes everything better.

            Seeing your face and hearing your laughter is the highlight of my every day. I cherish the way you understand me without a word, and the way you make me want to be the best version of myself. 

            On this Rose Day, I want to give you not just a flower, but a promise. A promise to be your constant, your listener, and your biggest supporter. Thank you for being my peace in this chaotic world. 

            I love you more than words could ever say, and I look forward to spending every single Rose Day for the rest of our lives together.

            <b>Forever Yours, ❤️</b>
        </div>
        <button onclick="nextPage(5)">One Last Thing 🌸</button>
    </div>

    <div id="page5" class="container">
        <h1>I Love You So Much!</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="cat-gif">
        <p style="font-size: 1.1rem; color: var(--rose-red); font-weight: bold;">Happy Rose Day, My Queen! 🌹</p>
        <button onclick="location.reload()">Start Again ❤️</button>
    </div>

    <script>
        const bgMusic = document.getElementById('bgMusic');
        const mainVideo = document.getElementById('mainVideo');
        const replayOverlay = document.getElementById('replayOverlay');

        function startExperience() {
            nextPage(2);
            mainVideo.play();
            bgMusic.pause(); // Music stops when video plays
        }

        function videoEnded() {
            replayOverlay.style.display = 'flex';
            bgMusic.play(); // Music resumes when video ends
            bgMusic.volume = 0.5;
        }

        function replayVideo() {
            replayOverlay.style.display = 'none';
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

        // Floating Hearts Background
        setInterval(() => {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 4000);
        }, 600);
    </script>
</body>
</html>
