<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Forever Love ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&family=Great+Vibes&display=swap');

        :root {
            --primary: #ff4d6d;
            --secondary: #c9184a;
            --bg: #fff0f3;
        }

        body {
            margin: 0; padding: 0; background: var(--bg);
            font-family: 'Poppins', sans-serif;
            display: flex; justify-content: center; align-items: center;
            height: 100vh; overflow: hidden;
        }

        .container {
            background: #fff; width: 90%; max-width: 420px;
            padding: 35px 20px; border-radius: 35px;
            box-shadow: 0 15px 50px rgba(255, 77, 109, 0.2);
            text-align: center; display: none;
            position: relative; z-index: 10;
            max-height: 88vh; overflow-y: auto;
            border: 2px solid #ffccd5;
        }

        .active { display: block; animation: slideIn 0.8s ease; }
        @keyframes slideIn { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }

        h1 { font-family: 'Dancing Script', cursive; color: var(--primary); font-size: 2.3rem; margin-bottom: 10px; }
        .game-img { width: 160px; margin: 20px auto; display: block; border-radius: 15px; }

        .btn {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white; border: none; padding: 15px 35px;
            border-radius: 50px; cursor: pointer; font-weight: 600;
            margin-top: 25px; transition: 0.3s; width: 90%; font-size: 1rem;
        }

        .choice-card { 
            background: #fffafa; border: 2px solid #ffccd5; 
            padding: 15px; margin: 12px 0; border-radius: 20px;
            cursor: pointer; transition: 0.3s; font-size: 0.95rem; color: #444;
        }
        .choice-card:hover { border-color: var(--primary); background: #fff0f3; transform: scale(1.02); }
        
        .letter-content {
            text-align: left; font-family: 'Great Vibes', cursive;
            font-size: 1.6rem; line-height: 1.8; color: #222;
            background: #fffdf5; padding: 30px; border-radius: 20px;
            max-height: 500px; overflow-y: auto; white-space: pre-wrap;
        }

        video { width: 100%; border-radius: 25px; border: 5px solid white; box-shadow: 0 8px 25px rgba(0,0,0,0.1); }
        
        /* Progress Bar */
        .progress-container { width: 80%; background: #eee; border-radius: 10px; margin: 10px auto; height: 8px; }
        .progress-bar { height: 100%; background: var(--primary); width: 0%; border-radius: 10px; transition: 0.5s; }
    </style>
</head>
<body>

    <div style="display:none"><div id="player"></div></div>

    <div id="page1" class="container active">
        <h1>Welcome, My Queen ❤️</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Aapne socha bhi nahi hoga ki aaj aapke liye kya taiyar kiya hai. Ye sirf ek website nahi, humare pyar ki journey hai. Kya aap 30 minute mere saath bitane ke liye taiyar hain?</p>
        <button class="btn" onclick="startExperience()">Ji, Shuru Karte Hain! 🫶🏻</button>
    </div>

    <div id="page2" class="container">
        <div class="progress-container"><div class="progress-bar" style="width: 15%"></div></div>
        <h1>Hamari Pehli Mulakat ☁️</h1>
        <img src="https://media.tenor.com/On7tBy_9mS0AAAAi/peach-goma-love.gif" class="game-img">
        <p>Aapko yaad hai hum pehli baar kahan aur kaise mile the? Zara aankhein band karke wo pal yaad kijiye...</p>
        <div class="choice-card" onclick="nextPage(3)">Haan, wo pal hamesha yaad rahega! ❤️</div>
        <div class="choice-card" onclick="alert('Thoda aur yaad kijiye, wo bahut haseen pal tha! ✨')">Mujhe thoda bhool gaya...</div>
    </div>

    <div id="page3" class="container">
        <div class="progress-container"><div class="progress-bar" style="width: 30%"></div></div>
        <h1>The Beauty Test ✨</h1>
        <img src="https://media.tenor.com/X9S79Uu3v7MAAAAi/mochi-mochi-peach-cat-cat.gif" class="game-img">
        <p>Mere hisab se aap is duniya ki sabse pyari ladki hain. Aapko kya lagta hai, mujhe aapki kaunsi cheez sabse zyada pasand hai?</p>
        <div class="choice-card" onclick="nextPage(4)">Meri Pyari Si Aankhein 👀</div>
        <div class="choice-card" onclick="nextPage(4)">Mera Masoom Sa Chehra 😊</div>
        <div class="choice-card" onclick="nextPage(4)">Mera Saaf Dil ❤️</div>
    </div>

    <div id="page4" class="container">
        <div class="progress-container"><div class="progress-bar" style="width: 45%"></div></div>
        <h1>Ek Paheli Aapke Liye 🧩</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Wo kya cheez hai jo sirf meri hai, par use dekh kar smile aapke chehre par aati hai?</p>
        <div class="choice-card" onclick="nextPage(5)">Aapka Pyar ❤️</div>
        <div class="choice-card" onclick="nextPage(5)">Aapki Pagalpan Wali Baatein 😂</div>
    </div>

    <div id="page5" class="container">
        <div class="progress-container"><div class="progress-bar" style="width: 60%"></div></div>
        <h1>Hamara Future 🏠</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Aapne kabhi socha hai hum 10 saal baad kahan honge? Main toh bas aapka haath pakde dekhna chahta hoon.</p>
        <div class="choice-card" onclick="nextPage(6)">Hamesha Saath, Ek Chota Sa Ghar 💍</div>
        <div class="choice-card" onclick="nextPage(6)">Duniya Bhar Ki Sair Karte Hue ✈️</div>
    </div>

    <div id="page6" class="container">
        <div class="progress-container"><div class="progress-bar" style="width: 75%"></div></div>
        <h1>Secret Connection ⚡</h1>
        <img src="https://media.tenor.com/On7tBy_9mS0AAAAi/peach-goma-love.gif" class="game-img">
        <p>Jab hum dur hote hain, tab aapko meri sabse zyada yaad kab aati hai?</p>
        <div class="choice-card" onclick="nextPage(7)">Raat ko sone se pehle 🌙</div>
        <div class="choice-card" onclick="nextPage(7)">Jab bhi koi romantic gana sunun 🎵</div>
    </div>

    <div id="page7" class="container">
        <div class="progress-container"><div class="progress-bar" style="width: 90%"></div></div>
        <h1>Relive For you 🫶🏻🎀</h1>
        <video id="mainVideo" onended="document.getElementById('letterBtn').style.display='block';">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
        </video>
        <p>Is video ko poora dekhiye, isme humari yaadein hain...</p>
        <button class="btn" id="letterBtn" style="display:none" onclick="nextPage(8)">Aage badhiye, ek surprise aur hai 💌</button>
    </div>

    <div id="page8" class="container">
        <h1>Mere Dil Ka Sabse Bada Khat ❤️</h1>
        <div class="letter-content" id="finalLetter">
Meri Pyaari Jaan,

Aaj jab main ye likh raha hoon, mere pass lafzon ki kami pad rahi hai. Aapne socha hoga ki ye journey itni lambi kyun hai? Kyunki 30 minute toh kya, meri poori zindagi bhi aapki tareef karne ke liye kam hai. Aap meri zindagi ka wo tohfa hain jise maine maanga nahi tha, par bhagwan ne mujhe de diya kyunki unhe pata tha ki mujhe aapki sabse zyada zaroorat hai.

Aapki har ek baat, aapka wo gussa hona, phir mera aapko manana, wo lambi baatein jo khatam hi nahi hoti... ye sab meri zindagi ka sabse khoobsurat hissa hain. Main jaanta hoon ki main hamesha perfect nahi hota, par aapne mujhe jaisa hoon waise hi accept kiya. Aapne mujhe ek behtar insaan banaya hai.

Aapko yaad hai humne kitne sapne dekhe hain? Wo ghar, wo raaste, wo sath mein khana banana... main har ek sapne ko haqeeqat mein badalna chahta hoon. Main chahta hoon ki jab hum 80 saal ke ho jayein, tab bhi main aapka haath pakad kar wahi kahu jo aaj keh raha hoon—ki aap hi meri pehli aur aakhri mohabbat ho.

Aapki smile meri duniya ki sabse badi power hai. Jab aap hasti hain, to lagta hai jaise sab kuch thik ho jayega. Main waada karta hoon ki main aapki is smile ko kabhi fika nahi padne dunga. Main hamesha aapke peeche ek chattar ki tarah khada rahunga, har mushkil se aapko bachaunga.

Aap mere liye sirf meri girlfriend nahi hain, aap meri soulmate hain. Log kehte hain soulmates wo hote hain jo bilkul ek jaise hote hain, par main kehta hoon soulmates wo hote hain jo ek doosre ko poora karte hain, jaise aap mujhe karti hain. Mere bina aap, aur aapke bina main, dono hi adhoore hain.

Aapki wo masoomiyat, wo choti choti baaton par khush ho jana, aur mujhse itna pyar karna... main kabhi nahi bhool sakta. Main khush-naseeb hoon ki is bheed bhari duniya mein mujhe aap mil gayi. Aap meri har dua ka asar hain, meri har khushi ka raaz hain.

Main chahta hoon ki aap is khat ko araam se padhein, har ek word ko mehsoos karein. Kyunki ye sirf words nahi hain, ye mere dil ki dhadkan hai jo aapke liye dhadakti hai. Main har pal aapke saath rehna chahta hoon, aapki baaton ko sunna chahta hoon, aur aapke saath budha hona chahta hoon.

Humara sath hamesha aise hi bana rahe, yahi meri sabse badi khwahish hai. I love you more than anyone can ever imagine. Aap meri jaan ho, meri shaan ho, aur mera poora jahan ho.

Hamesha aapka hi,
Aapka Deewana ❤️
        </div>
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
            if(n === 7) { if(player) player.pauseVideo(); v.play(); } 
            else { v.pause(); if(player) player.playVideo(); }
        }
    </script>
</body>
</html>
