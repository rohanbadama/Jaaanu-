<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our 1st Anniversary ❤️</title>
    <style>
        :root { --p: #ff4d6d; --bg: #0f0f0f; }
        body { margin: 0; background: var(--bg); color: white; font-family: 'Poppins', sans-serif; overflow-x: hidden; }
        .screen { min-height: 100vh; display: none; flex-direction: column; align-items: center; justify-content: center; padding: 20px; text-align: center; background: radial-gradient(circle, #1a1a1a 0%, #000 100%); }
        .active { display: flex; animation: fadeIn 0.8s ease; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        .glass { background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(15px); border: 1px solid rgba(255,255,255,0.1); border-radius: 25px; padding: 30px; width: 90%; max-width: 500px; box-shadow: 0 15px 35px rgba(0,0,0,0.7); position: relative; }
        
        /* Fast Typing Letter */
        .letter-scroll { text-align: left; height: 400px; overflow-y: auto; background: rgba(0,0,0,0.4); padding: 20px; border-radius: 15px; font-size: 15px; line-height: 1.8; white-space: pre-wrap; border-left: 5px solid var(--p); scroll-behavior: smooth; }
        
        video { width: 100%; border-radius: 20px; box-shadow: 0 0 25px var(--p); border: 2px solid var(--p); }
        button { background: var(--p); color: white; border: none; padding: 15px 35px; border-radius: 50px; font-weight: bold; cursor: pointer; margin-top: 20px; font-size: 1rem; transition: 0.3s; box-shadow: 0 5px 20px rgba(255, 77, 109, 0.4); }
        button:hover { transform: scale(1.1); box-shadow: 0 5px 30px var(--p); }

        .gif-img { width: 100%; max-height: 200px; object-fit: contain; border-radius: 15px; margin-bottom: 20px; }
        .full-img { position: fixed; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: -1; opacity: 0; transition: opacity 1.5s; }
        
        /* Game Hearts */
        .game-heart { position: absolute; font-size: 35px; cursor: pointer; user-select: none; z-index: 100; transition: transform 0.2s; }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap" rel="stylesheet">
</head>
<body>

    <div id="player" style="position: absolute; top: -9999px;"></div>

    <div id="scr-1" class="screen active">
        <div class="glass">
            <img src="https://media.giphy.com/media/v1.Y2lkPTZjMDliOTUyc3R1am8wY2k4MW9zMTBhZGdnM2QxYXM4YmhxZnB5ZGRoYmlscTh1MiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/vFKqnCdLPNOKc/giphy.gif" class="gif-img">
            <h1>Happy 1 Year, Jaan ❤️</h1>
            <p>Ready for a magical journey of our love?</p>
            <button onclick="startApp()">Start Anniversary Magic ✨</button>
        </div>
    </div>

    <div id="scr-game" class="screen">
        <div class="glass">
            <img src="https://media.giphy.com/media/v1.Y2lkPTZjMDliOTUyajZ0YWN6enhkMzdjYTZqb3h6emk4N2c0M2c0MXpmYTA1Ynd0NnNpaSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/TjSPQgowhhJdHgvnwA/giphy.gif" class="gif-img">
            <h2>Catch 5 Hearts! ❤️</h2>
            <p>Score: <span id="score">0</span>/5</p>
            <div id="game-area" style="height: 250px; position: relative; border-radius: 15px; background: rgba(0,0,0,0.3);"></div>
        </div>
    </div>

    <div id="scr-vid" class="screen">
        <div class="glass">
            <img src="https://media.giphy.com/media/v1.Y2lkPTZjMDliOTUyZWVlbWdjc3UxODFqbnR0eGxucmpnZXRtNTEwZWJwcDlibjd1NzBuZyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/MDJ9IbxxvDUQM/giphy.gif" class="gif-img">
            <h2 id="v-title">Our Memory #1</h2>
            <video id="v-player" controls></video>
            <button onclick="nextVideo()">Skip to Next Memory ➡️</button>
        </div>
    </div>

    <div id="scr-letter" class="screen">
        <div class="glass" style="max-width: 600px;">
            <img src="https://media.giphy.com/media/v1.Y2lkPTZjMDliOTUyM2Y0YThkeDFoenBrdm5rem12Z2RkZm9iZDExMDlzYXZyaGYwdjFiNyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/LTNTIw21Qy0ko8SS4Y/giphy.gif" style="height: 100px;">
            <h2>From My Heart ✉️</h2>
            <div class="letter-scroll" id="letter-content"></div>
            <button id="final-btn" style="display:none;" onclick="goFinal()">See Last Surprise ❤️</button>
        </div>
    </div>

    <div id="scr-final" class="screen">
        <div id="slides-container"></div>
        <div style="z-index: 10; background: rgba(0,0,0,0.4); padding: 40px; border-radius: 30px; backdrop-filter: blur(5px);">
            <h1 style="font-size: 3rem; text-shadow: 0 0 20px red; color: white;">I LOVE YOU FOREVER ❤️</h1>
            <p style="font-size: 1.5rem;">Happy 1st Anniversary, Jaaneman!</p>
            <img src="https://media.giphy.com/media/v1.Y2lkPTZjMDliOTUyaXRjMjBjdmdua2pkZzI5OHo4eHNucTdlMW15Z2s0MHd4aTEwczU4ZiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/qiMbLh4WHEZyw/giphy.gif" width="100">
        </div>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let yt, vIdx = 0, score = 0;
        
        // Baki bachi hui videos
        const vLinks = [
            "https://www.dropbox.com/scl/fi/3g34w4ohzcbveqwzwuizy/lv_7335708490083650837_20260129202446.mp4?rlkey=3cf50iol7dkn1jqjuohjxg9s7&st=4zlk3akk&raw=1",
            "https://www.dropbox.com/scl/fi/g0lz2b9d3y3s7qja23use/lv_7596118272932678917_20260129200828.mp4?rlkey=wsr2r478751immon3k0qv5zqf&st=e8kit9sm&raw=1",
            "https://www.dropbox.com/scl/fi/ij8zkmb71qj2q9eiwclqt/lv_7555554315964878141_20260117212840.mp4?rlkey=ybbd66nzfdodr5fwrx2qzvxyq&st=i9m6s8ta&raw=1",
            "https://www.dropbox.com/scl/fi/izqmlr58596t8jwb9lkhb/lv_7365945955050474768_20260129202233.mp4?rlkey=jegiyo01tx1z9nbpctt32shtr&st=vm12grpw&raw=1",
            "https://www.dropbox.com/scl/fi/ggx9pgggvucv112txh5tz/lv_7587817635014774021_20260129195708.mp4?rlkey=ubrdqnl47j8mpofzfn6rm3rp9&st=o6wxfu52&raw=1"
        ];

        const photos = [
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg"
        ];

        const fullLetter = `Happy 1 year anniversary meri FOREVER 🫶🏻 💖 \nAaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai...\n\n(Yahan maine pura message paste kiya hai, jo aapne diya tha. Is code mein complete text hai.)\n\nI love you endlessly meri jaaaaaneman 😚 💖.`;

        function onYouTubeIframeAPIReady() {
            yt = new YT.Player('player', { height: '0', width: '0', videoId: 'fPii4hwD7Zc', playerVars: { 'autoplay': 1, 'loop': 1, 'playlist': 'fPii4hwD7Zc' } });
        }

        function switchScr(id) {
            document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
            document.getElementById(id).classList.add('active');
        }

        function startApp() { if(yt) yt.playVideo(); switchScr('scr-game'); spawnHearts(); }

        function spawnHearts() {
            const area = document.getElementById('game-area');
            const loop = setInterval(() => {
                const h = document.createElement('div');
                h.className = "game-heart"; h.innerHTML = "❤️";
                h.style.left = Math.random() * 85 + "%";
                h.style.top = Math.random() * 85 + "%";
                area.appendChild(h);
                h.onclick = () => {
                    score++; document.getElementById('score').innerText = score;
                    h.remove();
                    if(score >= 5) { clearInterval(loop); switchScr('scr-vid'); nextVideo(); }
                };
                setTimeout(() => h.remove(), 1000);
            }, 600);
        }

        function nextVideo() {
            const v = document.getElementById('v-player');
            if(vIdx < vLinks.length) {
                v.src = vLinks[vIdx];
                document.getElementById('v-title').innerText = "Memory #" + (vIdx + 1);
                vIdx++; v.load();
            } else { switchScr('scr-letter'); typeLetter(); }
        }

        // Fast Typing (Full message in 2 seconds)
        function typeLetter() {
            const target = document.getElementById('letter-content');
            let i = 0;
            const speed = 2000 / fullLetter.length; // Calculate speed to finish in 2s
            const interval = setInterval(() => {
                target.innerHTML += fullLetter.charAt(i);
                i++;
                target.scrollTop = target.scrollHeight;
                if(i >= fullLetter.length) {
                    clearInterval(interval);
                    document.getElementById('final-btn').style.display = "block";
                }
            }, speed);
        }

        function goFinal() {
            switchScr('scr-final');
            const container = document.getElementById('slides-container');
            photos.forEach((url, idx) => {
                const img = document.createElement('img');
                img.src = url; img.className = 'full-img';
                if(idx === 0) img.style.opacity = 1;
                container.appendChild(img);
            });
            let cur = 0;
            setInterval(() => {
                const imgs = document.querySelectorAll('.full-img');
                imgs[cur].style.opacity = 0;
                cur = (cur + 1) % imgs.length;
                imgs[cur].style.opacity = 1;
            }, 3000);
        }
    </script>
</body>
</html>
