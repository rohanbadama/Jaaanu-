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
        .gif-container { width: 100%; display: flex; justify-content: center; margin: 10px 0; }
        .gif-img { width: 100%; max-width: 220px; border-radius: 15px; display: block; }
        .btn { background: var(--primary); color: white; border: none; padding: 12px 20px; border-radius: 50px; cursor: pointer; margin-top: 15px; width: 85%; font-weight: 600; }
        
        #maze { width: 250px; height: 200px; background: #fffdf5; margin: 10px auto; position: relative; border: 2px solid var(--primary); border-radius: 10px; }
        #player-heart { position: absolute; top: 5px; left: 5px; font-size: 22px; transition: 0.1s; z-index: 10; }
        #goal { position: absolute; bottom: 5px; right: 5px; font-size: 22px; }

        #reasons-box { height: 250px; overflow-y: scroll; border: 1px solid #ffccd5; padding: 15px; background: #fffdf5; border-radius: 15px; text-align: left; }
        .reason-item { padding: 10px 0; border-bottom: 1px solid #eee; font-size: 0.95rem; color: #444; }

        video { width: 100%; border-radius: 15px; margin-top: 10px; border: 2px solid var(--primary); background: #000; }
        .letter-text { text-align: left; font-family: 'Great Vibes', cursive; font-size: 1.5rem; line-height: 1.6; white-space: pre-wrap; background: #fffdf5; padding: 15px; border-radius: 15px; }
    </style>
</head>
<body>

    <div id="yt-player-div" style="position: absolute; top: -9999px;"><div id="player"></div></div>

    <div id="page1" class="container active">
        <h1>Welcome Jaan ❤️</h1>
        <div class="gif-container">
            <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif" class="gif-img">
        </div>
        <p>Aapke liye kuch special hai. Kya hum music ke saath shuru karein?</p>
        <button class="btn" onclick="startExperience()">Haan, Shuru Karein! 🎵</button>
    </div>

    <div id="page2" class="container">
        <h1>Pehli Yaad 📞</h1>
        <div class="gif-container">
            <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399976555941918/From_KlickPin_CF_Love_You_Lots_Kiss_GIF_-_LoveYouLots_Kiss_Peachcatmatheodelanoe12.gif" class="gif-img">
        </div>
        <p>Hamari pehli call kitni der chali thi?</p>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="alert('Nahi!')">08:45</button>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="showNext(3)">10:53</button>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="alert('Try again!')">12:10</button>
    </div>

    <div id="page3" class="container">
        <h1>Love Maze 🧭</h1>
        <div class="gif-container">
            <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399976903933982/From_KlickPin_CF_Pin_de_Milly_Millo_en_Manga___Gif_lindos_Hermosa_pareja_de_dibujos_animados_Imagenes_de_lindos_dibujos_animados.gif" class="gif-img" style="max-width:100px;">
        </div>
        <div id="maze"><div id="player-heart">❤️</div><div id="goal">🏠</div></div>
        <div style="margin-top:10px;">
            <button class="btn" style="width:50px" onclick="move('U')">⬆️</button><br>
            <button class="btn" style="width:50px" onclick="move('L')">⬅️</button>
            <button class="btn" style="width:50px" onclick="move('D')">⬇️</button>
            <button class="btn" style="width:50px" onclick="move('R')">➡️</button>
        </div>
        <button id="maze-btn" class="btn" style="display:none" onclick="showNext(4)">Aage Badhein ✨</button>
    </div>

    <div id="page4" class="container">
        <h1>Reasons ❤️</h1>
        <div id="reasons-box">
            <div class="reason-item">1. Aapki smile jo sab theek kar deti hai.</div>
            <div class="reason-item">2. Aapka bina kahe sab samajh jaana.</div>
            <div class="reason-item">3. Hamari lambi calls.</div>
            <div class="reason-item">4. Aapka mere liye itna fikar karna.</div>
            <div class="reason-item">5. Aap jaisa koi aur nahi hai. ❤️</div>
        </div>
        <button id="reason-btn" class="btn" style="display:none" onclick="showNext(5)">Video 🎬</button>
    </div>

    <div id="page5" class="container">
        <h1>Humari Yaadein 🎬</h1>
        <video id="personalVideo" controls onplay="stopMusic()" onended="playMusic()">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
        </video>
        <button id="v-btn" class="btn" style="display:none" onclick="showNext(6)">Mera Khat 💌</button>
    </div>

    <div id="page6" class="container">
        <h1>I Love You ❤️</h1>
        <div class="letter-text">Aap meri zindagi ka sabse khoobsurat hissa ho. Hamesha mere sath rehna. ❤️</div>
        <button class="btn" onclick="location.reload()">Replay ❤️</button>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let yt;
        function onYouTubeIframeAPIReady() {
            yt = new YT.Player('player', {
                height: '0', width: '0', videoId: 'l6E16JAk_Fs',
                playerVars: { 'autoplay': 1, 'loop': 1, 'playlist': 'l6E16JAk_Fs', 'playsinline': 1 },
                events: { 'onReady': (e) => { e.target.mute(); e.target.playVideo(); } }
            });
        }

        function startExperience() {
            if(yt) { yt.unMute(); yt.setVolume(100); yt.playVideo(); }
            showNext(2);
        }

        function stopMusic() { if(yt) yt.pauseVideo(); }
        function playMusic() { if(yt) yt.playVideo(); document.getElementById('v-btn').style.display='block'; }

        function showNext(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
        }

        let p = { x: 5, y: 5 };
        function move(d) {
            if(d=='U' && p.y > 5) p.y -= 25; if(d=='D' && p.y < 165) p.y += 25;
            if(d=='L' && p.x > 5) p.x -= 25; if(d=='R' && p.x < 225) p.x += 25;
            document.getElementById('player-heart').style.top = p.y + 'px';
            document.getElementById('player-heart').style.left = p.x + 'px';
            if(p.x >= 210 && p.y >= 150) document.getElementById('maze-btn').style.display='block';
        }

        document.getElementById('reasons-box').onscroll = function() {
            let b = this; if(b.scrollHeight - b.scrollTop <= b.clientHeight + 10) document.getElementById('reason-btn').style.display='block';
        };
    </script>
</body>
</html>
