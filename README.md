<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Safar Humara ❤️</title>
    <style>
        body { margin: 0; background: #fff0f3; font-family: sans-serif; text-align: center; color: #333; }
        .page { display: none; padding: 20px; min-height: 100vh; flex-direction: column; align-items: center; justify-content: center; }
        .active { display: flex; animation: fadeIn 0.5s; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        h1 { color: #ff4d6d; font-size: 24px; }
        .gif-img { width: 80%; max-width: 250px; border-radius: 15px; margin: 20px 0; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        .btn { background: #ff4d6d; color: white; border: none; padding: 15px 30px; border-radius: 25px; font-weight: bold; width: 80%; margin: 10px 0; cursor: pointer; }
        .box { background: white; padding: 15px; border-radius: 20px; width: 90%; max-width: 320px; border: 2px solid #ffccd5; }
        video { width: 100%; border-radius: 15px; background: black; }
        .scroll-box { height: 150px; overflow-y: auto; text-align: left; padding: 10px; background: #fffdf5; border-radius: 10px; }
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
    </audio>

    <div id="p1" class="page active">
        <div class="box">
            <h1>Hello Jaan ❤️</h1>
            <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif" class="gif-img">
            <p>Aapke liye kuch special hai...</p>
            <button class="btn" onclick="start()">Shuru Karein 🎵</button>
        </div>
    </div>

    <div id="p2" class="page">
        <div class="box">
            <h1>Pehli Yaad 📞</h1>
            <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399976555941918/From_KlickPin_CF_Love_You_Lots_Kiss_GIF_-_LoveYouLots_Kiss_Peachcatmatheodelanoe12.gif" class="gif-img">
            <p>Humari pehli call ki duration?</p>
            <button class="btn" onclick="alert('Thoda aur socho!')">08:45</button>
            <button class="btn" onclick="go(3)">10:53</button>
        </div>
    </div>

    <div id="p3" class="page">
        <div class="box">
            <h1>Catch My Love ❤️</h1>
            <img id="gif3" src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399976903933982/From_KlickPin_CF_Pin_de_Milly_Millo_en_Manga___Gif_lindos_Hermosa_pareja_de_dibujos_animados_Imagenes_de_lindos_dibujos_animados.gif" class="gif-img">
            <p>Kya aap mujhse pyar karti ho?</p>
            <button class="btn" onclick="go(4)">Bohot Zyada! ❤️</button>
        </div>
    </div>

    <div id="p4" class="page">
        <div class="box">
            <h1>Reasons ❤️</h1>
            <div class="scroll-box">
                <p>1. Aapki smile...</p>
                <p>2. Aapka care karna...</p>
                <p>3. Aapka gussa...</p>
                <p>4. Bas aap! ❤️</p>
                <p>--- Scroll Down ---</p>
                <p>Hamesha mere sath rehna.</p>
            </div>
            <button class="btn" onclick="go(5)">Next 🎬</button>
        </div>
    </div>

    <div id="p5" class="page">
        <div class="box">
            <h1>Yaadein 🎬</h1>
            <video id="vid" controls onplay="pauseM()" onended="playM()">
                <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4" type="video/mp4">
            </video>
            <button id="nextBtn" class="btn" style="display:none;" onclick="go(6)">Last Message 💌</button>
        </div>
    </div>

    <div id="p6" class="page">
        <div class="box">
            <h1>I Love You ❤️</h1>
            <p>Aap meri duniya ho.</p>
            <button class="btn" onclick="location.reload()">Replay ❤️</button>
        </div>
    </div>

    <script>
        const music = document.getElementById('bgMusic');
        
        function start() {
            music.play().catch(e => console.log("Music error"));
            go(2);
        }

        function go(n) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('p' + n).classList.add('active');
            
            // GIF reload hack for 3rd gif
            if(n === 3) {
                const g = document.getElementById('gif3');
                g.src = g.src.split('?')[0] + '?t=' + new Date().getTime();
            }
        }

        function pauseM() { music.pause(); }
        function playM() { music.play(); document.getElementById('nextBtn').style.display = 'block'; }
    </script>
</body>
</html>
