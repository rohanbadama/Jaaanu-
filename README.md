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
        .btn { background: var(--primary); color: white; border: none; padding: 12px 25px; border-radius: 50px; cursor: pointer; margin-top: 15px; width: 85%; font-weight: 600; transition: 0.3s; }
        .btn:active { transform: scale(0.95); }

        /* Hidden Message Hunt */
        .hunt-area { position: relative; width: 280px; height: 280px; margin: 0 auto; background: url('https://media.tenor.com/On7tBy_9mS0AAAAi/peach-goma-love.gif') center/cover; border-radius: 15px; border: 3px solid var(--primary); }
        .hotspot { position: absolute; width: 60px; height: 60px; background: rgba(255, 255, 255, 0.01); border-radius: 50%; cursor: pointer; }

        /* Manual Scrolling Reasons */
        #reasons-box { height: 350px; overflow-y: scroll; border: 2px solid #ffccd5; padding: 15px; background: #fffdf5; border-radius: 15px; margin: 15px 0; }
        .reason-item { padding: 12px 0; border-bottom: 1px solid #eee; font-size: 0.95rem; text-align: left; color: #444; line-height: 1.4; }

        .timeline { text-align: left; padding: 15px; border-left: 2px solid var(--primary); margin-left: 20px; }
        .time-item { margin-bottom: 25px; position: relative; padding-left: 20px; font-size: 0.9rem; }
        .time-item::before { content: '🌸'; position: absolute; left: -32px; background: white; }

        video { width: 100%; border-radius: 20px; border: 3px solid var(--primary); }
        .letter-content { text-align: left; font-family: 'Great Vibes', cursive; font-size: 1.6rem; line-height: 1.8; background: #fffdf5; padding: 25px; border-radius: 15px; white-space: pre-wrap; color: #333; }
    </style>
</head>
<body>

    <div style="display:none"><div id="player"></div></div>

    <div id="page1" class="container active">
        <h1>Suno, Meri Jaan... ❤️</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Aapke liye maine kuch bahut gehra aur pyaara banaya hai. Ise araam se har ek step par mehsoos kijiye...</p>
        <button class="btn" onclick="startExperience()">Ji, Bilkul ✨</button>
    </div>

    <div id="page2" class="container">
        <h1>Level 1: Hamari Yaadein 🧩</h1>
        <img src="https://media.tenor.com/X9S79Uu3v7MAAAAi/mochi-mochi-peach-cat-cat.gif" class="game-img">
        <p>Aapko yaad hai hamari pehli call kitni der chali thi?</p>
        <button class="btn" style="background:white; color:#444; border:1px solid #ddd; margin:5px 0;" onclick="alert('Nahi ji, thoda aur yaad kijiye!')">08:45</button>
        <button class="btn" style="background:white; color:#444; border:1px solid #ddd; margin:5px 0;" onclick="nextPage(3)">10:53</button>
        <button class="btn" style="background:white; color:#444; border:1px solid #ddd; margin:5px 0;" onclick="alert('Itni lambi bhi nahi thi!')">12:10</button>
    </div>

    <div id="page3" class="container">
        <h1>Level 2: Chhupi Hui Khushiyan 🔍</h1>
        <p>Is photo mein 4 jagah "Secret Words" hain. Unhe dhoondh kar tap kijiye!</p>
        <div class="hunt-area">
            <div class="hotspot" style="top: 10%; left: 10%;" onclick="found(1, 'Hamesha')"></div>
            <div class="hotspot" style="top: 75%; left: 70%;" onclick="found(2, 'Sath')"></div>
            <div class="hotspot" style="top: 15%; left: 65%;" onclick="found(3, 'Rehna')"></div>
            <div class="hotspot" style="top: 70%; left: 15%;" onclick="found(4, 'Mere')"></div>
        </div>
        <p id="found-msg" style="color:var(--secondary); font-weight:bold; height:20px;"></p>
        <button id="hunt-nxt" class="btn" style="display:none" onclick="nextPage(4)">Agla Level ➡️</button>
    </div>

    <div id="page4" class="container">
        <h1>Level 3: Kyun Itna Pyar Hai? ❤️</h1>
        <p>Aapko chune ke 100 kaaran. Ise araam se scroll karke padhiye...</p>
        <div id="reasons-box">
            <div id="reasons-list"></div>
        </div>
        <button id="reasons-nxt" class="btn" style="display:none" onclick="nextPage(5)">Hamara Future 🏠</button>
    </div>

    <div id="page5" class="container">
        <h1>Level 4: Hamara Safar 🏠</h1>
        <div class="timeline">
            <div class="time-item"><b>Abhi:</b> Aapki ye pyari si muskurahat jo mere liye sabkuch hai.</div>
            <div class="time-item"><b>Agla Saal:</b> Humari wo pehli trip jiska humein besabri se intezar hai.</div>
            <div class="time-item"><b>2027:</b> Humara apna chota sa aashiyana jahan sirf sukoon hoga.</div>
            <div class="time-item"><b>Hamesha:</b> Aapka haath mere haath mein, har mushkil ke waqt.</div>
        </div>
        <button class="btn" onclick="nextPage(6)">Special Video Dekhiye 🎬</button>
    </div>

    <div id="page6" class="container">
        <h1>Level 5: For you 🫶🏻🎀</h1>
        <video id="mainVideo" controls onended="document.getElementById('finalNxt').style.display='block';">
            <source src="https://raw.githubusercontent.com/Anshul-code-hub/cdn/main/your_video.mp4" type="video/mp4">
            </video>
        <button class="btn" id="finalNxt" style="display:none" onclick="nextPage(7)">Mera Khat Padhiye 💌</button>
    </div>

    <div id="page7" class="container">
        <h1>Mera Akhri Khat ❤️</h1>
        <div class="letter-content">
Meri Pyaari Jaan,

Main aaj jo bhi likh raha hoon, wo mere dil ki gehraiyon se nikal raha hai. Aapne aaj is safar mein jo waqt bitaya, wo sirf ek website nahi thi, wo meri koshish thi aapko ye batane ki ki aap mere liye kitni khaas hain. 

Aapki wo pehli call se lekar aaj tak, har ek lamha mere liye kisi sapne se kam nahi hai. Main aksar baithkar sochta hoon ki aapne mujh mein aisa kya dekha jo itna pyar kiya, par sach toh ye hai ki aapne mujhe mujhse behtar banaya hai. Jab aap smile karti hain, toh lagta hai jaise duniya ki saari pareshaaniyan khatam ho gayi hon. 

Main jaanta hoon main kabhi kabhi bahut ziddi ho jata hoon, ya aapko pareshan kar deta hoon, par yakeen maniye, mera har ek ehsaas sirf aapke liye hai. Main chahta hoon ki humara sath hamesha aise hi bana rahe. Hum milkar wo har sapna pura karein jo humne dekha hai—wo lambi trips, wo dher saari shopping, aur wo shaamein jahan sirf hum dono hon.

Aap meri soulmate hain, meri sabse acchi dost hain aur meri poori duniya hain. Aapke bina meri zindagi ek khali kitab ki tarah hai. Main waada karta hoon ki main hamesha aapka sath dunga, chahe halaat kaise bhi hon. Main hamesha aapko wo respect aur wo pyar dunga jiske aap haqdaar hain. 

Aapne mujhe sikhaya ki mohabbat sirf kehne ki cheez nahi, nibhane ki cheez hai. Main hamesha aapka hi rahunga. Thank you meri zindagi mein aane ke liye aur use itna haseen banane ke liye. Aapki masoomiyat aur aapka ye bholapan hamesha aise hi rakhna. 

I love you more than words can ever describe. Forever and always! ❤️
        </div>
        <button class="btn" onclick="location.reload()">Dobara Dekhiye ❤️</button>
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
            if(n === 4) loadReasons();
        }

        let foundCount = 0;
        function found(id, word) {
            document.getElementById('found-msg').innerText = "Found: " + word + " ✨";
            foundCount++;
            if(foundCount >= 4) document.getElementById('hunt-nxt').style.display = 'block';
        }

        function loadReasons() {
            const list = document.getElementById('reasons-list');
            const data = [
                "Aapki smile jo sab kuch bhula deti hai.", "Aapki masoomiyat.", "Aapka mera itna khayal rakhna.", "Aapka mujhse ladna aur fir manana.", "Humari lambi baatein.", "Aapka mujh par bharosa karna.", "Aapka mere bure jokes par hasna.", "Aapka mujhe samjhana.", "Aapka mere nakhre uthana.", "Aapka meri har baat sunna.", "Aapka mera support banna.", "Aapki aankhein.", "Aapka mere liye special feel karwana.", "Aapka mere sath budha hone ka sapna.", "Aapki sadgi.", "Aapka mujhe hamesha 'Aap' kehna.", "Aapka mere liye rona.", "Aapka mere liye itna wait karna.", "Aapki awaaz.", "Aapka meri fikr karna."
            ];
            for(let i=0; i<100; i++) {
                const div = document.createElement('div');
                div.className = 'reason-item';
                div.innerText = (i+1) + ". " + (data[i % data.length] || "Aapka mere sath hamesha rehna.");
                list.appendChild(div);
            }
            const box = document.getElementById('reasons-box');
            box.onscroll = function() {
                if (box.scrollHeight - box.scrollTop <= box.clientHeight + 2) {
                    document.getElementById('reasons-nxt').style.display = 'block';
                }
            };
        }
    </script>
</body>
</html>
