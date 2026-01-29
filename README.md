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
        h1 { font-family: 'Dancing Script', cursive; color: var(--primary); font-size: 1.8rem; margin-bottom: 10px; }
        .gif-img { width: 100%; max-width: 220px; border-radius: 15px; margin: 10px 0; display: block; margin-left: auto; margin-right: auto; }
        .btn { background: var(--primary); color: white; border: none; padding: 12px 20px; border-radius: 50px; cursor: pointer; margin-top: 15px; width: 85%; font-weight: 600; }
        
        #maze { width: 250px; height: 200px; background: #fffdf5; margin: 10px auto; position: relative; border: 2px solid var(--primary); border-radius: 10px; overflow: hidden; }
        #player-heart { position: absolute; top: 5px; left: 5px; font-size: 22px; transition: 0.1s; z-index: 10; }
        #goal { position: absolute; bottom: 5px; right: 5px; font-size: 22px; }

        #reasons-box { height: 250px; overflow-y: scroll; border: 1px solid #ffccd5; padding: 15px; background: #fffdf5; border-radius: 15px; text-align: left; }
        .reason-item { padding: 10px 0; border-bottom: 1px solid #eee; font-size: 0.95rem; color: #444; line-height: 1.4; }

        video { width: 100%; border-radius: 15px; margin-top: 10px; border: 2px solid var(--primary); background: #000; }
        .letter-text { text-align: left; font-family: 'Great Vibes', cursive; font-size: 1.5rem; line-height: 1.6; color: #333; white-space: pre-wrap; background: #fffdf5; padding: 15px; border-radius: 15px; }
    </style>
</head>
<body>

    <div id="yt-audio-container" style="position: absolute; top: -9999px;"><div id="yt-audio"></div></div>

    <div id="page1" class="container active">
        <h1>Welcome Jaan ❤️</h1>
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif?ex=697c9b75&is=697b49f5&hm=baab3586965ae954eaf7d16ad28925e97981fd3fa3ae13ab7970362d2b7ebe04&" class="gif-img">
        <p>Aapke liye ek pyara sa safar... Ise music ke saath shuru karein?</p>
        <button class="btn" onclick="startEverything()">Haan, Music Shuru Karein! 🎵</button>
    </div>

    <div id="page2" class="container">
        <h1>Pehli Yaad 📞</h1>
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399976555941918/From_KlickPin_CF_Love_You_Lots_Kiss_GIF_-_LoveYouLots_Kiss_Peachcatmatheodelanoe12.gif?ex=697c9ae6&is=697b4966&hm=b4c6fead8ca9c4dfa5fb38b1f9b66b6f27ee1dc8cd0dd0a60b3615854c53d603&" class="gif-img">
        <p>Hamari sabse pehli call kitni der chali thi?</p>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="alert('Nahi, itni kam nahi thi!')">08:45</button>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="showNext(3)">10:53</button>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="alert('Thoda aur socho!')">12:10</button>
    </div>

    <div id="page3" class="container">
        <h1>Love Maze 🧭</h1>
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399976903933982/From_KlickPin_CF_Pin_de_Milly_Millo_en_Manga___Gif_lindos_Hermosa_pareja_de_dibujos_animados_Imagenes_de_lindos_dibujos_animados.gif?ex=697c9ae6&is=697b4966&hm=66f3a445baf93d4ba9341837b60f040eb041e7d75d4eee20fbb48f4eb327fb92&" class="gif-img" style="max-width: 120px;">
        <p>Dil ❤️ ko mere ghar 🏠 tak pahunchaiye!</p>
        <div id="maze"><div id="player-heart">❤️</div><div id="goal">🏠</div></div>
        <div style="margin-top:10px;">
            <button class="btn" style="width:50px; padding:10px;" onclick="move('U')">⬆️</button><br>
            <button class="btn" style="width:50px; padding:10px;" onclick="move('L')">⬅️</button>
            <button class="btn" style="width:50px; padding:10px;" onclick="move('D')">⬇️</button>
            <button class="btn" style="width:50px; padding:10px;" onclick="move('R')">➡️</button>
        </div>
        <button id="maze-btn" class="btn" style="display:none" onclick="showNext(4)">Aage Badhein ✨</button>
    </div>

    <div id="page4" class="container">
        <h1>Kyun Itna Pyar Hai? ❤️</h1>
        <div id="reasons-box">
            <div class="reason-item">1. Aapki smile jo meri duniya roshan kar deti hai.</div>
            <div class="reason-item">2. Aapka mujhe har halat mein support karna.</div>
            <div class="reason-item">3. Aapka wo gussa jo sirf mujhpar nikalta hai.</div>
            <div class="reason-item">4. Humari wo pehli call ki lambi guftagu.</div>
            <div class="reason-item">5. Aapka mere liye itna care dikhana.</div>
            <div class="reason-item">6. Aapki aankhein jo sab keh deti hain.</div>
            <div class="reason-item">7. Aapka mujhe har baar maaf kar dena.</div>
            <div class="reason-item">8. Aapka mere sath budha hone ka khwab.</div>
            <div class="reason-item">9. Aapka har ek promise dil se nibhana.</div>
            <div class="reason-item">10. Bas aap, kyunki aap jaisa koi aur nahi.</div>
        </div>
        <button id="reason-btn" class="btn" style="display:none" onclick="showNext(5)">Ab Kuch Yaadein... 🎬</button>
    </div>

    <div id="page5" class="container">
        <h1>For you 🫶🏻🎀</h1>
        <video id="myVideo" controls onplay="pauseYT()" onended="resumeYT()">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
        </video>
        <button id="v-btn" class="btn" style="display:none" onclick="showNext(6)">Mera Akhri Khat 💌</button>
    </div>

    <div id="page6" class="container">
        <h1>Mera Dil ❤️</h1>
        <div class="letter-text">
Meri Sabse Pyaari Jaan,

Aapne is safar mein jo waqt bitaya, wo mere liye bahut mayne rakhta hai. Main chahta hoon ki hum hamesha aise hi sath rahein. Aap meri life ki sabse khoobsurat haqiqat ho.

I love you forever! ❤️
        </div>
        <button class="btn" onclick="location.reload()">Replay ❤️</button>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let ytPlayer;
        let isYTReady = false;

        function onYouTubeIframeAPIReady() {
            ytPlayer = new YT.Player('yt-audio', {
                height: '0', width: '0', videoId: 'l6E16JAk_Fs',
                playerVars: { 'autoplay': 0, 'loop': 1, 'playlist': 'l6E16JAk_Fs', 'playsinline': 1 },
                events: { 'onReady': () => { isYTReady = true; } }
            });
        }

        function startEverything() {
            if(isYTReady) {
                ytPlayer.unMute();
                ytPlayer.setVolume(100);
                ytPlayer.playVideo();
            }
            showNext(2);
        }

        function pauseYT() { if(isYTReady) ytPlayer.pauseVideo(); }
        function resumeYT() { 
            if(isYTReady) ytPlayer.playVideo(); 
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
            document.getElementById('player-heart').style.top = pos.y + 'px';
            document.getElementById('player-heart').style.left = pos.x + 'px';
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
