<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Safar Humara ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&family=Great+Vibes&display=swap');
        :root { --primary: #ff4d6d; --bg: #fff0f3; }
        body { margin: 0; background: var(--bg); font-family: 'Poppins', sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; overflow: hidden; }
        .container { background: #fff; width: 90%; max-width: 400px; padding: 20px; border-radius: 25px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); text-align: center; display: none; position: relative; max-height: 80vh; overflow-y: auto; border: 2px solid #ffccd5; }
        .active { display: block; animation: fadeIn 0.4s ease-in; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        h1 { font-family: 'Dancing Script', cursive; color: var(--primary); font-size: 1.8rem; }
        .gif-img { width: 100%; max-width: 200px; border-radius: 15px; margin: 10px 0; }
        .btn { background: var(--primary); color: white; border: none; padding: 12px 20px; border-radius: 50px; cursor: pointer; margin-top: 15px; width: 85%; font-weight: 600; }
        
        #maze { width: 250px; height: 200px; background: #fffdf5; margin: 10px auto; position: relative; border: 2px solid var(--primary); border-radius: 10px; }
        #player { position: absolute; top: 5px; left: 5px; font-size: 22px; transition: 0.1s; z-index: 10; }
        #goal { position: absolute; bottom: 5px; right: 5px; font-size: 22px; }

        #reasons-box { height: 250px; overflow-y: scroll; border: 1px solid #ffccd5; padding: 15px; background: #fffdf5; border-radius: 15px; text-align: left; }
        .reason-item { padding: 10px 0; border-bottom: 1px solid #eee; font-size: 0.95rem; color: #444; line-height: 1.4; }

        video { width: 100%; border-radius: 15px; margin-top: 10px; border: 2px solid var(--primary); background: #000; }
        .letter-text { text-align: left; font-family: 'Great Vibes', cursive; font-size: 1.5rem; line-height: 1.6; color: #333; white-space: pre-wrap; background: #fffdf5; padding: 15px; border-radius: 15px; }
    </style>
</head>
<body>

    <div id="yt-audio-container" style="position: absolute; top: -9999px; left: -9999px;">
        <div id="yt-audio"></div>
    </div>

    <div id="page1" class="container active">
        <h1>Welcome Jaan ❤️</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="gif-img">
        <p>Aapke liye ek chota sa tohfa... kya aap taiyar hain hamari yaadon mein dubne ke liye?</p>
        <button class="btn" onclick="startJourney()">Haan, Shuru Karein! 🎵</button>
    </div>

    <div id="page2" class="container">
        <h1>Pehli Yaad 📞</h1>
        <img src="https://media.tenor.com/X9S79Uu3v7MAAAAi/mochi-mochi-peach-cat-cat.gif" class="gif-img">
        <p>Hamari sabse pehli call kitni der chali thi?</p>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="alert('Nahi, itni kam nahi thi!')">08:45</button>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="showNext(3)">10:53</button>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="alert('Itni lambi bhi nahi thi!')">12:10</button>
    </div>

    <div id="page3" class="container">
        <h1>Love Maze 🧭</h1>
        <p>Dil ❤️ ko mere ghar 🏠 tak pahunchaiye!</p>
        <div id="maze"><div id="player">❤️</div><div id="goal">🏠</div></div>
        <div style="margin-top:10px;">
            <button class="btn" style="width:50px; padding:10px;" onclick="move('U')">⬆️</button><br>
            <button class="btn" style="width:50px; padding:10px;" onclick="move('L')">⬅️</button>
            <button class="btn" style="width:50px; padding:10px;" onclick="move('D')">⬇️</button>
            <button class="btn" style="width:50px; padding:10px;" onclick="move('R')">➡️</button>
        </div>
        <button id="maze-btn" class="btn" style="display:none" onclick="showNext(4)">Level Clear! Aage Badhein ✨</button>
    </div>

    <div id="page4" class="container">
        <h1>Kyun Itna Pyar Hai? ❤️</h1>
        <p>Ise poora niche tak scroll karke padhiye...</p>
        <div id="reasons-box">
            <div class="reason-item">1. Aapki wo masoom si smile jo mera din bana deti hai.</div>
            <div class="reason-item">2. Jis tarah aap meri fikar karte ho, koi nahi kar sakta.</div>
            <div class="reason-item">3. Aapka wo gussa, jo thodi der mein pyar mein badal jata hai.</div>
            <div class="reason-item">4. Humari wo pehli call jo hamesha yaad rahegi.</div>
            <div class="reason-item">5. Aapka mere bure jokes par bhi dil se hasna.</div>
            <div class="reason-item">6. Aapki aankhein jo bina bole sab keh deti hain.</div>
            <div class="reason-item">7. Aapka mere liye itna waqt nikalna.</div>
            <div class="reason-item">8. Aapka mujhe har baar maaf kar dena.</div>
            <div class="reason-item">9. Aapka mere sath budha hone ka sapna dekhna.</div>
            <div class="reason-item">10. Bas aap, kyunki aap jaisa koi aur nahi hai. ❤️</div>
        </div>
        <button id="reason-btn" class="btn" style="display:none" onclick="showNext(5)">Video Time 🎬</button>
    </div>

    <div id="page5" class="container">
        <h1>Hamari Yaadein 🎬</h1>
        <video id="myVideo" controls onplay="pauseMusic()" onended="resumeMusicAndShowBtn()">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
        </video>
        <button id="v-btn" class="btn" style="display:none" onclick="showNext(6)">Mera Khat 💌</button>
    </div>

    <div id="page6" class="container">
        <h1>Mera Dil Aapke Liye ❤️</h1>
        <div class="letter-text">
Meri Sabse Pyaari Jaan,

Aapne is safar mein jo waqt bitaya, wo dikhata hai ki aap mujhse kitna pyar karti hain. Main waada karta hoon ki main hamesha aapka sath nibhaunga. 

Aap meri zindagi ka wo sukoon ho jo mujhe kahin aur nahi milta. Hum milkar apne har sapne ko pura karenge. I love you more than words can say. ❤️
        </div>
        <button class="btn" onclick="location.reload()">Replay ❤️</button>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let ytPlayer;
        let isPlayerReady = false;

        function onYouTubeIframeAPIReady() {
            ytPlayer = new YT.Player('yt-audio', {
                height: '0', width: '0', videoId: 'l6E16JAk_Fs',
                playerVars: { 
                    'autoplay': 1, 
                    'loop': 1, 
                    'playlist': 'l6E16JAk_Fs',
                    'playsinline': 1 
                },
                events: {
                    'onReady': function(event) {
                        isPlayerReady = true;
                        event.target.mute(); // Pehle mute karna padta hai autoplay ke liye
                        event.target.playVideo();
                    }
                }
            });
        }

        function startJourney() {
            if(isPlayerReady) {
                ytPlayer.unMute(); // User click par unmute
                ytPlayer.setVolume(100);
                ytPlayer.playVideo();
            }
            showNext(2);
        }

        function pauseMusic() { if(isPlayerReady) ytPlayer.pauseVideo(); }
        function resumeMusicAndShowBtn() { 
            if(isPlayerReady) ytPlayer.playVideo(); 
            document.getElementById('v-btn').style.display = 'block';
        }

        function showNext(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
        }

        let pos = { x: 5, y: 5 };
        function move(dir) {
            if(dir=='U' && pos.y > 5) pos.y -= 25;
            if(dir=='D' && pos.y < 165) pos.y += 25;
            if(dir=='L' && pos.x > 5) pos.x -= 25;
            if(dir=='R' && pos.x < 225) pos.x += 25;
            document.getElementById('player').style.top = pos.y + 'px';
            document.getElementById('player').style.left = pos.x + 'px';
            if(pos.x >= 210 && pos.y >= 150) document.getElementById('maze-btn').style.display='block';
        }

        document.getElementById('reasons-box').onscroll = function() {
            let b = document.getElementById('reasons-box');
            if(b.scrollHeight - b.scrollTop <= b.clientHeight + 10) {
                document.getElementById('reason-btn').style.display = 'block';
            }
        };
    </script>
</body>
</html>
