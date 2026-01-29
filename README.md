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
            --soft-white: rgba(255, 255, 255, 0.94);
        }

        body {
            margin: 0; padding: 0;
            background: radial-gradient(circle, #fff0f3 0%, #ffccd5 100%);
            font-family: 'Poppins', sans-serif;
            display: flex; justify-content: center; align-items: center;
            height: 100vh; overflow: hidden;
        }

        /* Floating Rose Petals & Hearts */
        .decoration {
            position: absolute; pointer-events: none;
            animation: fall linear infinite; z-index: 1;
        }
        @keyframes fall {
            0% { transform: translateY(-10vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
        }

        .container {
            background: var(--soft-white);
            backdrop-filter: blur(12px);
            padding: 25px; border-radius: 40px;
            box-shadow: 0 25px 70px rgba(255, 77, 109, 0.35);
            width: 85%; max-width: 450px;
            display: none; text-align: center;
            position: relative; z-index: 10;
            animation: slideUp 0.7s ease-out;
            max-height: 88vh; overflow-y: auto;
            border: 2px solid white;
        }

        .active { display: block; }
        @keyframes slideUp { from { transform: translateY(50px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }

        h1 { color: var(--dark-pink); font-family: 'Dancing Script', cursive; font-size: 2.3rem; margin: 10px 0; }
        p { font-size: 0.95rem; color: #555; line-height: 1.5; }

        /* Video Section */
        .video-box { 
            position: relative; width: 100%; border-radius: 25px; 
            overflow: hidden; border: 4px solid var(--dark-pink); background: #000; margin: 20px 0;
        }
        video { width: 100%; display: block; max-height: 400px; }
        
        .replay-overlay {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.65); display: none;
            justify-content: center; align-items: center;
        }

        button {
            background: linear-gradient(45deg, var(--dark-pink), var(--rose-red));
            color: white; border: none; padding: 14px 35px; border-radius: 50px;
            cursor: pointer; font-weight: 600; transition: 0.3s; margin-top: 15px;
            box-shadow: 0 8px 20px rgba(255, 77, 109, 0.3);
            text-transform: uppercase; font-size: 0.85rem; letter-spacing: 1px;
        }
        button:hover { transform: translateY(-3px); box-shadow: 0 12px 25px rgba(255, 77, 109, 0.5); }

        .rose-box { display: flex; justify-content: center; gap: 20px; font-size: 55px; margin: 25px 0; }
        .rose { cursor: pointer; transition: 0.4s; filter: drop-shadow(0 5px 8px rgba(0,0,0,0.1)); }
        .rose:hover { transform: scale(1.2) rotate(10deg); }

        .letter-content {
            text-align: left; background: #fffdf5; border-left: 5px solid var(--dark-pink);
            padding: 30px; color: #333; line-height: 2; font-family: 'Great Vibes', cursive;
            font-size: 1.5rem; border-radius: 10px; max-height: 400px; overflow-y: auto;
            box-shadow: inset 0 0 15px rgba(0,0,0,0.05);
        }

        .cat-gif { width: 130px; margin-bottom: 10px; border-radius: 15px; }
        #msg-display { color: var(--rose-red); font-weight: 600; min-height: 55px; margin-top: 10px; font-style: italic; }
    </style>
</head>
<body>

    <div id="decorations-container"></div>

    <div style="position: absolute; top: -1000px;">
        <div id="player"></div>
    </div>

    <div id="page1" class="container active">
        <img src="https://media.tenor.com/On7tBy_9mS0AAAAi/peach-goma-love.gif" class="cat-gif">
        <h1>For My Special One 🎀</h1>
        <p>I have designed this little world just for you. Turn up your volume and step inside...</p>
        <button onclick="startExperience()">Start the Magic 🫶🏻</button>
    </div>

    <div id="page2" class="container">
        <h1>Pick Your Roses 🌹</h1>
        <p>Tap each rose to unlock a secret message...</p>
        <div class="rose-box">
            <span class="rose" onclick="reveal('The moment you smile, my whole world lights up. Never lose that glow! ✨')">🌹</span>
            <span class="rose" onclick="reveal('You are the answer to every prayer I ever made. I am so lucky to have you. ❤️')">🌹</span>
            <span class="rose" onclick="reveal('I promise to cherish you today, tomorrow, and for all the lifetimes to come. 💍')">🌹</span>
        </div>
        <div id="msg-display"></div>
        <button id="nxt-btn" style="display:none;" onclick="nextPage(3)">Watch This... 🎬</button>
    </div>

    <div id="page3" class="container">
        <h1>Just for you 🫶🏻🎀</h1>
        <div class="video-box">
            <video id="mainVideo" onended="videoEnded()">
                <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
            </video>
            <div class="replay-overlay" id="replayOverlay">
                <button onclick="replayVideo()">Replay 🔄</button>
            </div>
        </div>
        <p>Every memory with you is my favorite memory.</p>
        <button onclick="nextPage(4)">Open My Letter 💌</button>
    </div>

    <div id="page4" class="container">
        <h1>My Heart on Paper...</h1>
        <div class="letter-content">
            My Dearest Love,

            As I sit here trying to put my feelings into words, I realize that even a thousand pages wouldn't be enough to explain how much you mean to me. You are the rhythm in my heartbeat and the peace in my chaos. Every single day, I wake up feeling like the luckiest person in the world simply because I know you are mine.

            Meeting you was the turning point of my life. Before you, everything seemed like a black-and-white movie, but you brought a burst of color that changed my world forever. You taught me what it truly means to be loved and to love someone without any conditions. Your smile is my daily dose of happiness, and your eyes are the only place where I truly feel at home. I cherish the way you laugh at my silly jokes and the way you hold my hand like you never want to let go.

            I remember the clips we just watched in the video; they aren't just videos for me. They are proof of a beautiful journey we started together. Every smile, every glance, and every second shared is a treasure I will keep locked in my heart forever. I want to build a mountain of such memories with you, where we can look back and smile even when we are old and gray.

            You are my soulmate, my best friend, and my greatest adventure. Your kindness inspires me to be a better person, and your strength gives me the courage to face anything life throws at us. I promise to be the shoulder you lean on when you’re tired, the listener when you need to vent, and the one who celebrates your smallest wins with the loudest cheers. I want to grow with you, learn with you, and build a future that is as bright and beautiful as your soul.

            On this Rose Day, I am not just giving you a digital flower; I am giving you a piece of my soul. I promise to protect our love like the most delicate rose and to make sure it blooms even in the toughest seasons. I will be your rock when you feel weak and your wings when you want to fly. My love for you is not a feeling; it is a choice I make every morning when I wake up, and a promise I keep every night before I sleep.

            Thank you for being my constant. Thank you for staying. Thank you for being the most amazing person I have ever known. I love you more than words can express, more than distance can divide, and more than time can measure. Our story is my favorite story, and I can’t wait to see what the next chapters hold for us. You are my forever, my always, and my everything.

            With all my love, always. ❤️
        </div>
        <button onclick="nextPage(5)">Final Surprise 🌸</button>
    </div>

    <div id="page5" class="container">
        <h1>Forever & Always!</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="cat-gif">
        <p style="font-size: 1.4rem; color: var(--rose-red); font-weight: bold; font-family: 'Great Vibes';">Happy Rose Day, My Queen! 🌹</p>
        <p>May our love continue to bloom for an eternity.</p>
        <button onclick="location.reload()">Re-live the Love ❤️</button>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let player;
        function onYouTubeIframeAPIReady() {
            player = new YT.Player('player', {
                height: '0', width: '0', videoId: 'l6E16JAk_Fs',
                playerVars: { 'autoplay': 1, 'loop': 1, 'playlist': 'l6E16JAk_Fs' },
                events: { 'onReady': (e) => e.target.mute() }
            });
        }

        const mainVideo = document.getElementById('mainVideo');
        const replayOverlay = document.getElementById('replayOverlay');

        function startExperience() {
            if (player) { player.unMute(); player.playVideo(); }
            nextPage(2);
        }

        function videoEnded() {
            replayOverlay.style.display = 'flex';
            if (player) player.playVideo(); 
        }

        function replayVideo() {
            replayOverlay.style.display = 'none';
            if (player) player.pauseVideo();
            mainVideo.currentTime = 0;
            mainVideo.play();
        }

        function nextPage(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
            
            if(n === 3) {
                if (player) player.pauseVideo(); // Music stops for video
                mainVideo.play();
            } else {
                mainVideo.pause();
                if (player) player.playVideo(); // Music resumes
            }
        }

        let count = 0;
        function reveal(m) {
            document.getElementById('msg-display').innerText = m;
            count++;
            if(count >= 3) document.getElementById('nxt-btn').style.display = 'inline-block';
        }

        // Background Decorations (Hearts and Petals)
        const decoContainer = document.getElementById('decorations-container');
        const symbols = ['❤️', '🌹', '🌸', '✨'];
        setInterval(() => {
            const el = document.createElement('div');
            el.className = 'decoration';
            el.innerText = symbols[Math.floor(Math.random() * symbols.length)];
            el.style.left = Math.random() * 100 + 'vw';
            el.style.fontSize = Math.random() * 20 + 10 + 'px';
            el.style.animationDuration = Math.random() * 3 + 4 + 's';
            decoContainer.appendChild(el);
            setTimeout(() => el.remove(), 7000);
        }, 500);
    </script>
</body>
</html>
