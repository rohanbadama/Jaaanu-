<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Forever Love 🫶🏻🎀</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&family=Great+Vibes&display=swap');

        :root {
            --pink-bg: #fff0f3;
            --dark-pink: #ff4d6d;
            --rose-red: #c9184a;
            --gold: #d4af37;
        }

        body {
            margin: 0; padding: 0;
            background: radial-gradient(circle, #fff0f3 0%, #ffccd5 100%);
            font-family: 'Poppins', sans-serif;
            display: flex; justify-content: center; align-items: center;
            height: 100vh; overflow: hidden;
        }

        /* Decoration: Floating Rose Petals */
        .petal {
            position: absolute; background: #ff4d6d;
            border-radius: 150% 0 150% 0;
            animation: animate 10s linear infinite;
            z-index: 1; opacity: 0.7;
        }
        @keyframes animate {
            0% { transform: translateY(-10%) rotate(0deg); left: 0; }
            100% { transform: translateY(110vh) rotate(360deg); left: 100%; }
        }

        /* Decoration: Sparkling Stars */
        .star {
            position: absolute; background: white; border-radius: 50%;
            animation: twinkle 2s infinite; z-index: 1;
        }
        @keyframes twinkle { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }

        .container {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            padding: 30px; border-radius: 40px;
            border: 2px solid rgba(255, 255, 255, 0.5);
            box-shadow: 0 20px 60px rgba(255, 77, 109, 0.4);
            width: 85%; max-width: 450px;
            display: none; text-align: center;
            position: relative; z-index: 10;
            animation: fadeInContainer 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            max-height: 85vh; overflow-y: auto;
        }

        .active { display: block; }

        @keyframes fadeInContainer { from { transform: scale(0.8) translateY(30px); opacity: 0; } to { transform: scale(1) translateY(0); opacity: 1; } }

        h1 { color: var(--dark-pink); font-family: 'Dancing Script', cursive; font-size: 2.5rem; text-shadow: 2px 2px 4px rgba(0,0,0,0.1); }
        
        /* Interactive Animation: Heartbeat */
        .heart-loader {
            width: 100px; height: 100px; margin: 0 auto 20px;
            background-color: var(--dark-pink);
            display: inline-block; position: relative;
            transform: rotate(-45deg);
            animation: heartbeat 1.2s infinite;
        }
        .heart-loader::before, .heart-loader::after {
            content: ""; width: 100px; height: 100px;
            background-color: var(--dark-pink);
            border-radius: 50%; position: absolute;
        }
        .heart-loader::before { top: -50px; left: 0; }
        .heart-loader::after { top: 0; left: 50px; }
        @keyframes heartbeat { 0% { transform: rotate(-45deg) scale(0.8); } 5% { transform: rotate(-45deg) scale(0.9); } 10% { transform: rotate(-45deg) scale(0.8); } 15% { transform: rotate(-45deg) scale(1); } 50% { transform: rotate(-45deg) scale(0.8); } 100% { transform: rotate(-45deg) scale(0.8); } }

        /* Video Section */
        .video-box { 
            position: relative; width: 100%; border-radius: 25px; 
            overflow: hidden; border: 5px solid white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2); background: #000; margin: 20px 0;
        }
        video { width: 100%; display: block; }
        
        .replay-btn {
            position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
            background: var(--dark-pink); color: white; padding: 15px 25px;
            border-radius: 30px; cursor: pointer; display: none; border: none; font-weight: bold;
        }

        button {
            background: linear-gradient(45deg, var(--dark-pink), var(--rose-red));
            color: white; border: none; padding: 14px 35px; border-radius: 50px;
            cursor: pointer; font-weight: 600; transition: 0.4s; margin-top: 20px;
            box-shadow: 0 8px 20px rgba(255, 77, 109, 0.4); text-transform: uppercase; letter-spacing: 1px;
        }
        button:hover { transform: translateY(-5px) scale(1.05); box-shadow: 0 12px 25px rgba(255, 77, 109, 0.6); }

        .rose-box { display: flex; justify-content: center; gap: 20px; font-size: 55px; margin: 25px 0; }
        .rose { cursor: pointer; transition: 0.4s; filter: drop-shadow(0 5px 10px rgba(0,0,0,0.15)); }
        .rose:hover { transform: rotate(15deg) scale(1.3); }

        .letter-content {
            text-align: left; background: #fffdf5; border: 2px solid #f0e6d2;
            padding: 30px; color: #333; line-height: 2; font-family: 'Great Vibes', cursive;
            font-size: 1.4rem; border-radius: 20px; box-shadow: inset 0 0 20px rgba(0,0,0,0.05);
            max-height: 400px; overflow-y: scroll;
        }

        #msg-display { color: var(--rose-red); font-weight: 600; min-height: 60px; margin-top: 15px; font-size: 1.1rem; }
    </style>
</head>
<body>

    <div id="bg-elements"></div>

    <div style="display:none">
        <iframe id="ytPlayer" width="0" height="0" src="https://www.youtube.com/embed/l6E16JAk_Fs?enablejsapi=1&autoplay=1&mute=1&loop=1&playlist=l6E16JAk_Fs" frameborder="0"></iframe>
    </div>

    <div id="page1" class="container active">
        <div class="heart-loader"></div>
        <h1>Welcome, My Love ❤️</h1>
        <p>You are about to enter a world made only for you. Please turn up your volume for the music...</p>
        <button onclick="startExperience()">Enter My Heart 🫶🏻</button>
    </div>

    <div id="page2" class="container">
        <h1>Just for you 🫶🏻🎀</h1>
        <div class="video-box">
            <video id="mainVideo" onended="videoEnded()">
                <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
            </video>
            <button class="replay-btn" id="replayBtn" onclick="replayVideo()">Watch Again 🔄</button>
        </div>
        <p>These are the moments that define my happiness.</p>
        <button onclick="nextPage(3)">Continue... ✨</button>
    </div>

    <div id="page3" class="container">
        <h1>The Petals of Love</h1>
        <p>Tap each rose to see my promises to you...</p>
        <div class="rose-box">
            <span class="rose" onclick="reveal('I promise to hold your hand through every high and every low. Forever. 💍')">🌹</span>
            <span class="rose" onclick="reveal('I promise to be your safest place, your biggest fan, and your home. 🏠❤️')">🌹</span>
            <span class="rose" onclick="reveal('I promise to love you more with every single sunset we see together. 🌅')">🌹</span>
        </div>
        <div id="msg-display"></div>
        <button id="nxt-btn" style="display:none;" onclick="nextPage(4)">Open My Letter 💌</button>
    </div>

    <div id="page4" class="container">
        <h1>My Forever Promise...</h1>
        <div class="letter-content">
            My Dearest,

            As I sit here trying to put my feelings into words, I realize that even 500 words wouldn't be enough to explain how much you mean to me. But I'll try, because you deserve to know every single thought that crosses my mind when I think of you.

            Meeting you was like finding a piece of myself that I didn't even know was missing. You aren't just a part of my life; you are the very rhythm of my heartbeat. Every morning I wake up, my first thought is of you, and every night before I sleep, I thank the universe for bringing us together. You have this magical way of making the ordinary feel extraordinary. 

            Your smile is my favorite sun—it lights up my world even on the darkest days. Your laughter is the music I could listen to for the rest of my life. I remember the video we just watched, and it makes me realize how far we've come and how many more memories we are yet to build. Every second in those clips is a testament to the love that we share—a love that is pure, deep, and unbreakable.

            I want you to know that I see you. I see the kindness in your eyes, the strength in your soul, and the beauty in your heart. You make me want to be a better person, not because I have to, but because I want to be worthy of someone as incredible as you. You are my peace in a chaotic world, my calm in the middle of a storm, and my home wherever we may be.

            On this Rose Day, I'm not just giving you a digital flower; I'm giving you my soul. I promise to cherish you, to respect you, and to never let a day pass without telling you how beautiful you are. I promise to be the shoulder you cry on and the person you celebrate with. I will be your rock when you feel weak and your wings when you want to fly.

            Our love is like a rose—it started as a small bud and has grown into a magnificent bloom. And just like a rose, I will protect it with everything I have. No matter what life throws at us, no matter the distance or the difficulties, I will always be here, standing by your side. You are my soulmate, my best friend, and my greatest adventure. 

            Thank you for choosing me. Thank you for staying. Thank you for being exactly who you are. I love you more than words, more than distance, and more than time itself. 

            Forever and always, your one and only. ❤️
        </div>
        <button onclick="nextPage(5)">Final Surprise 🌸</button>
    </div>

    <div id="page5" class="container">
        <div class="heart-loader"></div>
        <h1>I Love You To Infinity!</h1>
        <p style="font-size: 1.3rem; color: var(--rose-red); font-weight: bold; font-family: 'Great Vibes';">Happy Rose Day, My Queen! 🌹</p>
        <p>May our love continue to bloom forever.</p>
        <button onclick="location.reload()">Re-live the Magic ❤️</button>
    </div>

    <script>
        const mainVideo = document.getElementById('mainVideo');
        const replayBtn = document.getElementById('replayBtn');
        const ytPlayer = document.getElementById('ytPlayer');

        // Background Decorations
        const bgContainer = document.getElementById('bg-elements');
        function createDecorations() {
            for(let i=0; i<15; i++) {
                let petal = document.createElement('div');
                petal.className = 'petal';
                petal.style.width = Math.random() * 15 + 10 + 'px';
                petal.style.height = petal.style.width;
                petal.style.left = Math.random() * 100 + 'vw';
                petal.style.animationDelay = Math.random() * 5 + 's';
                bgContainer.appendChild(petal);
            }
            for(let i=0; i<30; i++) {
                let star = document.createElement('div');
                star.className = 'star';
                star.style.width = '2px'; star.style.height = '2px';
                star.style.left = Math.random() * 100 + 'vw';
                star.style.top = Math.random() * 100 + 'vh';
                star.style.animationDelay = Math.random() * 2 + 's';
                bgContainer.appendChild(star);
            }
        }
        createDecorations();

        function startExperience() {
            // Unmute YouTube Player via API if possible, otherwise it plays hidden
            ytPlayer.src = ytPlayer.src.replace("mute=1", "mute=0");
            nextPage(2);
            mainVideo.play();
        }

        function videoEnded() {
            replayBtn.style.display = 'block';
            ytPlayer.contentWindow.postMessage('{"event":"command","func":"playVideo","args":""}', '*');
        }

        function replayVideo() {
            replayBtn.style.display = 'none';
            ytPlayer.contentWindow.postMessage('{"event":"command","func":"pauseVideo","args":""}', '*');
            mainVideo.currentTime = 0;
            mainVideo.play();
        }

        let count = 0;
        function nextPage(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
            if(n !== 2) {
                mainVideo.pause();
                ytPlayer.contentWindow.postMessage('{"event":"command","func":"playVideo","args":""}', '*');
            } else {
                ytPlayer.contentWindow.postMessage('{"event":"command","func":"pauseVideo","args":""}', '*');
            }
        }

        function reveal(m) {
            document.getElementById('msg-display').innerHTML = `<p style="animation: fadeIn 0.5s;">${m}</p>`;
            count++;
            if(count >= 3) document.getElementById('nxt-btn').style.display = 'inline-block';
        }
    </script>
</body>
</html>
