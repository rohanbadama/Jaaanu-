<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Safar Humara ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@400;600&family=Great+Vibes&display=swap');
        :root { --primary: #ff4d6d; --bg: #fff0f3; }
        body { margin: 0; background: var(--bg); font-family: 'Poppins', sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; overflow: hidden; }
        .container { background: #fff; width: 90%; max-width: 380px; padding: 20px; border-radius: 25px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); text-align: center; display: none; position: relative; max-height: 80vh; overflow-y: auto; border: 2px solid #ffccd5; }
        .active { display: block; animation: fadeIn 0.4s ease-in; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        h1 { font-family: 'Dancing Script', cursive; color: var(--primary); font-size: 1.8rem; }
        .gif-img { width: 100%; max-width: 220px; border-radius: 15px; margin: 10px auto; display: block; }
        .btn { background: var(--primary); color: white; border: none; padding: 12px 20px; border-radius: 50px; cursor: pointer; margin-top: 15px; width: 85%; font-weight: 600; }
        
        #maze { width: 240px; height: 180px; background: #fffdf5; margin: 10px auto; position: relative; border: 2px solid var(--primary); border-radius: 10px; }
        #player-heart { position: absolute; top: 5px; left: 5px; font-size: 22px; transition: 0.1s; z-index: 10; }
        #goal { position: absolute; bottom: 5px; right: 5px; font-size: 22px; }

        #reasons-box { height: 200px; overflow-y: scroll; border: 1px solid #ffccd5; padding: 15px; background: #fffdf5; border-radius: 15px; text-align: left; }
        .reason-item { padding: 10px 0; border-bottom: 1px solid #eee; font-size: 0.95rem; color: #444; }

        video { width: 100%; border-radius: 15px; margin-top: 10px; border: 2px solid var(--primary); background: #000; }
        .letter-text { text-align: left; font-family: 'Great Vibes', cursive; font-size: 1.5rem; line-height: 1.6; white-space: pre-wrap; background: #fffdf5; padding: 15px; border-radius: 15px; }
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
        </audio>

    <div id="page1" class="container active">
        <h1>Welcome Jaan ❤️</h1>
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif" class="gif-img">
        <p>Aapke liye kuch special hai. Ise music ke saath sunna...</p>
        <button class="btn" onclick="startExperience()">Haan, Music Shuru Karein! 🎵</button>
    </div>

    <div id="page2" class="container">
        <h1>Pehli Yaad 📞</h1>
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399976555941918/From_KlickPin_CF_Love_You_Lots_Kiss_GIF_-_LoveYouLots_Kiss_Peachcatmatheodelanoe12.gif" class="gif-img">
        <p>Hamari pehli call kitni der chali thi?</p>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="alert('Thoda aur socho!')">08:45</button>
        <button class="btn" style="background:white; color:#333; border:1px solid #ddd" onclick="showNext(3)">10:53</button>
    </div>

    <div id="page3" class="container">
        <h1>Love Maze 🧭</h1>
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399976903933982/From_KlickPin_CF_Pin_de_Milly_Millo_en_Manga___Gif_lindos_Hermosa_pareja_de_dibujos_animados_Imagenes_de_lindos_dibujos_animados.gif?t=123" class="gif-img" style="max-width:100px;">
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
            <div class="reason-item">3. Aapka mere liye itna fikar karna.</div>
            <div class="reason-item">4. Aap jaisa koi aur nahi hai. ❤️</div>
        </div>
        <button id="reason-btn" class="btn" style="display:none" onclick="showNext(5)">Video 🎬</button>
    </div>

    <div id="page5" class="container">
        <h1>Humari Yaadein 🎬</h1>
        <video id="personalVideo" controls onplay="document.getElementById('bgMusic').pause()" onended="document.getElementById('bgMusic').play(); document.getElementById('v-btn').style.display='block'">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
        </video>
        <button id="v-btn" class="btn" style="display:none" onclick="showNext(6)">Mera Khat 💌</button>
    </div>

    <div id="page6" class="container">
        <h1>Mera Khat ❤️</h1>
        <div class="letter-text">Aap meri zindagi ka sabse khoobsurat hissa ho. I love you! ❤️</div>
        <button class="btn" onclick="location.reload()">Replay ❤️</button>
    </div>

    <script>
        const bgMusic = document.getElementById('bgMusic');

        function startExperience() {
            // Instagram browser fix: play sound on user interaction
            bgMusic.play().catch(e => console.log("Audio play failed", e));
            showNext(2);
        }

        function showNext(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
        }

        // Maze logic
        let p = { x: 5, y: 5 };
        function move(d) {
            if(d=='U' && p.y > 5) p.y -= 25; if(d=='D' && p.y < 145) p.y += 25;
            if(d=='L' && p.x > 5) p.x -= 25; if(d=='R' && p.x < 215) p.x += 25;
            document.getElementById('player-heart').style.top = p.y + 'px';
            document.getElementById('player-heart').style.left = p.x + 'px';
            if(p.x >= 200 && p.y >= 130) document.getElementById('maze-btn').style.display='block';
        }

        document.getElementById('reasons-box').onscroll = function() {
            if(this.scrollHeight - this.scrollTop <= this.clientHeight + 10) 
                document.getElementById('reason-btn').style.display='block';
        };
    </script>
</body>
</html>
