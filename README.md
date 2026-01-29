<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mere Dil Ki Dhadkan ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&family=Great+Vibes&display=swap');

        :root { --primary: #ff4d6d; --secondary: #c9184a; --bg: #fff0f3; }
        body { margin: 0; background: var(--bg); font-family: 'Poppins', sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; overflow: hidden; }

        .container { background: #fff; width: 92%; max-width: 420px; padding: 25px 15px; border-radius: 30px; box-shadow: 0 15px 40px rgba(0,0,0,0.1); text-align: center; display: none; position: relative; max-height: 85vh; overflow-y: auto; border: 2px solid #ffccd5; }
        .active { display: block; animation: fadeIn 0.8s ease; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        h1 { font-family: 'Dancing Script', cursive; color: var(--primary); font-size: 1.8rem; margin: 10px 0; }
        .game-img { width: 180px; height: auto; margin: 10px auto; display: block; border-radius: 15px; }
        .btn { background: var(--primary); color: white; border: none; padding: 12px 25px; border-radius: 50px; cursor: pointer; margin-top: 15px; width: 85%; font-weight: 600; }

        /* Hidden Message Hunt */
        .hunt-area { position: relative; width: 280px; height: 280px; margin: 0 auto; background: url('https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif') center/cover; border-radius: 15px; border: 3px solid var(--primary); }
        .hotspot { position: absolute; width: 60px; height: 60px; background: transparent; cursor: pointer; }

        /* Manual Scrolling Reasons */
        #reasons-box { height: 350px; overflow-y: scroll; border: 2px solid #ffccd5; padding: 15px; background: #fffdf5; border-radius: 15px; margin: 15px 0; }
        .reason-item { padding: 12px 0; border-bottom: 1px solid #eee; font-size: 0.95rem; text-align: left; color: #444; line-height: 1.4; }

        /* Catch Game */
        #catch-game { height: 200px; position: relative; background: #fff0f3; border-radius: 15px; overflow: hidden; border: 1px dashed var(--primary); }
        #moving-heart { position: absolute; cursor: pointer; font-size: 2rem; transition: 0.2s; }

        video { width: 100%; border-radius: 20px; border: 3px solid var(--primary); }
        .letter-content { text-align: left; font-family: 'Great Vibes', cursive; font-size: 1.6rem; line-height: 1.8; background: #fffdf5; padding: 25px; border-radius: 15px; color: #333; }
    </style>
</head>
<body>

    <div style="display:none"><div id="player"></div></div>

    <div id="page1" class="container active">
        <h1>Suno, Meri Jaan... ❤️</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Aapke liye maine kuch bahut gehra aur pyaara banaya hai. Ise har ek step par mehsoos kijiye...</p>
        <button class="btn" onclick="startExperience()">Ji, Shuru Karein ✨</button>
    </div>

    <div id="page2" class="container">
        <h1>Level 1: Memory Test 🧩</h1>
        <img src="https://media.tenor.com/X9S79Uu3v7MAAAAi/mochi-mochi-peach-cat-cat.gif" class="game-img">
        <p>Aapko yaad hai hamari pehli call kitni der chali thi?</p>
        <button class="btn" style="background:white; color:#444; border:1px solid #ddd; margin:5px 0;" onclick="alert('Nahi ji, thoda aur yaad kijiye!')">08:45</button>
        <button class="btn" style="background:white; color:#444; border:1px solid #ddd; margin:5px 0;" onclick="nextPage(3)">10:53</button>
        <button class="btn" style="background:white; color:#444; border:1px solid #ddd; margin:5px 0;" onclick="alert('Itni lambi bhi nahi thi!')">12:10</button>
    </div>

    <div id="page3" class="container">
        <h1>Level 2: Chhupi Hui Khushiyan 🔍</h1>
        <p>Is photo mein 4 jagah tap karke secret words dhoondhiye!</p>
        <div class="hunt-area">
            <div class="hotspot" style="top: 5%; left: 5%;" onclick="found(1, 'Hamesha')"></div>
            <div class="hotspot" style="top: 75%; left: 75%;" onclick="found(2, 'Sath')"></div>
            <div class="hotspot" style="top: 15%; left: 70%;" onclick="found(3, 'Rehna')"></div>
            <div class="hotspot" style="top: 70%; left: 10%;" onclick="found(4, 'Mere')"></div>
        </div>
        <p id="found-msg" style="color:var(--secondary); font-weight:bold; height:20px;"></p>
        <button id="hunt-nxt" class="btn" style="display:none" onclick="nextPage(4)">Level 3 Par Chalein ➡️</button>
    </div>

    <div id="page4" class="container">
        <h1>Level 3: Kyun Itna Pyar Hai? ❤️</h1>
        <p>Ise poora niche tak scroll karke padhiye...</p>
        <div id="reasons-box">
            <div id="reasons-list"></div>
        </div>
        <button id="reasons-nxt" class="btn" style="display:none" onclick="nextPage(5)">Ek Chota Sa Game 🎮</button>
    </div>

    <div id="page5" class="container">
        <h1>Level 4: Catch My Heart 💖</h1>
        <p>Mera dil bahut tezz bhag raha hai, ise 5 baar pakdiye!</p>
        <div id="catch-game">
            <div id="moving-heart" onclick="catchHeart()">❤️</div>
        </div>
        <p id="catch-count">Pakda gaya: 0/5</p>
        <button id="catch-nxt" class="btn" style="display:none" onclick="nextPage(6)">Yaadein Dekhiye 🎬</button>
    </div>

    <div id="page6" class="container">
        <h1>Level 5: Fir you🫶🏻🎀</h1>
        <video id="mainVideo" controls onended="document.getElementById('finalNxt').style.display='block';">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
        </video>
        <button class="btn" id="finalNxt" style="display:none" onclick="nextPage(7)">Mera Khat Padhiye 💌</button>
    </div>

    <div id="page7" class="container">
        <h1>Mera Akhri Khat ❤️</h1>
        <div class="letter-content" id="finalLetter">
Meri Pyaari Jaan,

Aapne is safar mein jo waqt bitaya, wo dikhata hai ki aap mujhse kitna pyar karti hain. Maine ye sab isliye banaya taaki aapko bata sakun ki aap meri zindagi mein kya mayne rakhti hain. Har ek choti yaad, har ek call, aur har ek muskurahat mere liye ek khazane jaisi hai.

Jab hum pehli baar mile the, mujhe nahi pata tha ki aap meri poori duniya ban jayengi. Aapne mujhe sikhaya ki kisi ka sath hona kya hota hai. Main waada karta hoon ki main hamesha aapka haath thaame rakhunga, chahe rasta kitna bhi mushkil ho. Aap meri sabse badi taqat ho.

Mujhe aapki masoomiyat, aapka mujh par gussa karna, aur fir itne pyar se manana bahut pasand hai. Main hamesha koshish karunga ki aapki aankhon mein sirf khushi ke aansu hon. Hum milkar apne har sapne ko pura karenge. 

Aap sirf meri girlfriend nahi ho, aap mera sukoon ho. Thank you mere sath rehne ke liye aur mujhe itna pyar dene ke liye. Ye khat sirf shuruat hai humari us lambi kahani ki jo humein sath likhni hai.

Main hamesha aapka hi rahunga. I love you so much, forever and always! ❤️
        </div>
        <button class="btn" onclick="location.reload()">Dobara Dekhiye ❤️</button>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let player;
        function onYouTubeIframeAPIReady() {
            player = new YT.Player('player', {
                height: '0', width: '0', videoId: 'l6E16JAk_Fs',
                playerVars: { 'autoplay': 1, 'loop': 1, 'playlist': 'l6E16JAk_Fs', 'mute': 0 }
            });
        }

        function startExperience() { if(player) { player.playVideo(); player.unMute(); } nextPage(2); }

        function nextPage(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
            const v = document.getElementById('mainVideo');
            if(n === 6) { if(player) player.pauseVideo(); v.play(); } 
            else { v.pause(); if(player) player.playVideo(); }
            if(n === 4) loadReasons();
        }

        let foundCount = 0;
        function found(id, word) {
            document.getElementById('found-msg').innerText = "Dhoondh liya: " + word + " ✨";
            foundCount++;
            if(foundCount >= 4) document.getElementById('hunt-nxt').style.display = 'block';
        }

        let catched = 0;
        function catchHeart() {
            catched++;
            document.getElementById('catch-count').innerText = "Pakda gaya: " + catched + "/5";
            const h = document.getElementById('moving-heart');
            h.style.top = Math.random() * 150 + "px";
            h.style.left = Math.random() * 250 + "px";
            if(catched >= 5) document.getElementById('catch-nxt').style.display = 'block';
        }

        function loadReasons() {
            const list = document.getElementById('reasons-list');
            const arr = ["Aapki smile", "Aapka care", "Aapki awaaz", "Aapka gussa", "Humari call", "Aapka pyar"];
            for(let i=1; i<=100; i++) {
                const d = document.createElement('div');
                d.className = 'reason-item';
                d.innerText = i + ". " + arr[i % arr.length] + " (Special Reason #" + i + ")";
                list.appendChild(d);
            }
            const box = document.getElementById('reasons-box');
            box.onscroll = () => { if(box.scrollHeight - box.scrollTop <= box.clientHeight + 2) document.getElementById('reasons-nxt').style.display = 'block'; };
        }
    </script>
</body>
</html>
