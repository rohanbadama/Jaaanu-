<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Love Story ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&family=Great+Vibes&display=swap');

        :root { --primary: #ff4d6d; --secondary: #c9184a; --bg: #fff0f3; }
        body { margin: 0; background: var(--bg); font-family: 'Poppins', sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; overflow: hidden; }

        .container { background: #fff; width: 92%; max-width: 420px; padding: 25px 15px; border-radius: 30px; box-shadow: 0 15px 40px rgba(0,0,0,0.1); text-align: center; display: none; position: relative; max-height: 85vh; overflow-y: auto; border: 2px solid #ffccd5; }
        .active { display: block; animation: fadeIn 0.8s ease; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        h1 { font-family: 'Dancing Script', cursive; color: var(--primary); font-size: 1.8rem; margin: 10px 0; }
        .game-img { width: 140px; margin: 10px auto; display: block; border-radius: 15px; }
        .btn { background: var(--primary); color: white; border: none; padding: 12px 25px; border-radius: 50px; cursor: pointer; margin-top: 15px; width: 85%; font-weight: 600; }

        /* Hidden Message Style */
        .hunt-area { position: relative; width: 300px; height: 300px; margin: 0 auto; background: url('https://media.tenor.com/On7tBy_9mS0AAAAi/peach-goma-love.gif') center/cover; border-radius: 15px; border: 3px solid var(--primary); }
        .hotspot { position: absolute; width: 40px; height: 40px; border-radius: 50%; cursor: pointer; background: transparent; }

        /* Timeline Style */
        .timeline { text-align: left; padding: 20px 10px; border-left: 2px dashed var(--primary); margin-left: 20px; }
        .time-item { position: relative; margin-bottom: 30px; padding-left: 20px; }
        .time-item::before { content: '❤️'; position: absolute; left: -31px; top: 0; background: white; }

        /* Reason Scroller (Slower for time) */
        #reasons-box { height: 250px; overflow: hidden; border: 1px solid #ddd; padding: 10px; background: #fffdf5; border-radius: 15px; position: relative; }
        .reason-item { padding: 10px 0; border-bottom: 1px solid #eee; font-size: 0.95rem; }

        video { width: 100%; border-radius: 20px; border: 3px solid var(--primary); }
        .letter-content { text-align: left; font-family: 'Great Vibes', cursive; font-size: 1.5rem; line-height: 1.8; background: #fffdf5; padding: 25px; border-radius: 15px; white-space: pre-wrap; }
    </style>
</head>
<body>

    <div style="display:none"><div id="player"></div></div>

    <div id="page1" class="container active">
        <h1>Suno, Meri Jaan... ❤️</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Aapke liye maine kuch bahut gehra aur pyaara banaya hai. Ise araam se mehsoos kijiye...</p>
        <button class="btn" onclick="startExperience()">Ji, Bilkul ✨</button>
    </div>

    <div id="page2" class="container">
        <h1>Level 1: Memory Test 🧩</h1>
        <p>Aapko yaad hai hamari pehli call kitni der chali thi?</p>
        <button class="btn" style="background:white; color:#444; border:1px solid #ddd; margin:5px 0;" onclick="alert('Nahi, itni kam nahi thi!')">08 min 45 sec</button>
        <button class="btn" style="background:white; color:#444; border:1px solid #ddd; margin:5px 0;" onclick="nextPage(3)">10 min 53 sec</button>
        <button class="btn" style="background:white; color:#444; border:1px solid #ddd; margin:5px 0;" onclick="alert('Itni lambi bhi nahi thi ji!')">12 min 10 sec</button>
    </div>

    <div id="page3" class="container">
        <h1>Level 2: Hidden Messages 🔍</h1>
        <p>Is photo mein maine 4 jagah "Secret Words" chhupaye hain. Unhe dhoondh kar tap kijiye!</p>
        <div class="hunt-area">
            <div class="hotspot" style="top: 10%; left: 10%;" onclick="found(1, 'Hamesha')"></div>
            <div class="hotspot" style="top: 80%; left: 70%;" onclick="found(2, 'Sath')"></div>
            <div class="hotspot" style="top: 20%; left: 60%;" onclick="found(3, 'Rehna')"></div>
            <div class="hotspot" style="top: 70%; left: 10%;" onclick="found(4, 'Mere')"></div>
        </div>
        <p id="found-msg" style="color:var(--secondary); font-weight:bold; height:20px;"></p>
        <button id="hunt-nxt" class="btn" style="display:none" onclick="nextPage(4)">Level 3 Par Chalein ➡️</button>
    </div>

    <div id="page4" class="container">
        <h1>Level 3: Why I Love You ❤️</h1>
        <div id="reasons-box"><div id="reasons-scroller"></div></div>
        <button id="reasons-nxt" class="btn" style="display:none" onclick="nextPage(5)">Next: Hamara Future ✨</button>
    </div>

    <div id="page5" class="container">
        <h1>Level 4: Future Timeline 🏠</h1>
        <div class="timeline">
            <div class="time-item"><b>Aaj:</b> Aapka ye smile karna aur mere saath hona.</div>
            <div class="time-item"><b>Aane Wala Saal:</b> Hamari dher saari dates aur shopping trips.</div>
            <div class="time-item"><b>2027:</b> Ek bahut lambi trip jahan sirf hum dono honge.</div>
            <div class="time-item"><b>Future:</b> Hamara apna pyaara sa ghar aur dher saari khushiyan.</div>
            <div class="time-item"><b>Forever:</b> Mera aapka haath hamesha ke liye thaame rakhna.</div>
        </div>
        <button class="btn" onclick="nextPage(6)">Hamari Yaadein Dekhiye 🎬</button>
    </div>

    <div id="page6" class="container">
        <h1>Level 5: Special Video 🎬</h1>
        <video id="mainVideo" onended="document.getElementById('finalNxt').style.display='block';">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
        </video>
        <button class="btn" id="finalNxt" style="display:none" onclick="nextPage(7)">Mera Khat Padhiye 💌</button>
    </div>

    <div id="page7" class="container">
        <h1>Aapke Liye Mera Khat ❤️</h1>
        <div class="letter-content" id="longLetter"></div>
        <button class="btn" onclick="location.reload()">Dobara Shuru Karein? ❤️</button>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let player;
        function onYouTubeIframeAPIReady() {
            player = new YT.Player('player', {
                height: '0', width: '0', videoId: 'l6E16JAk_Fs',
                playerVars: { 'autoplay': 1, 'loop': 1, 'playlist': 'l6E16JAk_Fs' }
            });
        }

        function startExperience() { if(player) player.unMute(); nextPage(2); }

        function nextPage(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
            const v = document.getElementById('mainVideo');
            if(n === 6) { if(player) player.pauseVideo(); v.play(); } 
            else { v.pause(); if(player) player.playVideo(); }
            if(n === 4) startReasonScroll();
            if(n === 7) injectLetter();
        }

        let foundCount = 0;
        function found(id, word) {
            document.getElementById('found-msg').innerText = "Found: " + word + " ✨";
            foundCount++;
            if(foundCount >= 4) document.getElementById('hunt-nxt').style.display = 'block';
        }

        function startReasonScroll() {
            const scroller = document.getElementById('reasons-scroller');
            const reasons = ["Aapki smile", "Aapka gussa", "Aapka care", "Humari baatein", "Aapka sath", "Aapka bharosa", "Aapki masoomiyat", "Aapki aankhein"];
            for(let i=1; i<=100; i++) {
                const div = document.createElement('div');
                div.className = 'reason-item';
                div.innerText = i + ". " + reasons[i % reasons.length];
                scroller.appendChild(div);
            }
            let top = 0;
            const timer = setInterval(() => {
                top -= 0.6;
                scroller.style.transform = `translateY(${top}px)`;
                if(top < -2200) { clearInterval(timer); document.getElementById('reasons-nxt').style.display='block'; }
            }, 40);
        }

        function injectLetter() {
            const text = "Meri Pyaari Jaan,\n\nAapne socha hoga ki ye journey itni lambi kyun hai? Kyunki meri poori zindagi aapki tareef karne ke liye kam hai. Aap meri wo sukoon ho jo mujhe kahin aur nahi milta...\n\n(Aapka real 1000+ words ka emotional message yahan expand hoga...)\n\nMain waada karta hoon ki hamesha aapka sath nibhaunga. I love you so much! ❤️";
            document.getElementById('longLetter').innerText = text.repeat(15);
        }
    </script>
</body>
</html>
