<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Queen ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&family=Great+Vibes&display=swap');

        :root {
            --primary: #ff4d6d;
            --secondary: #c9184a;
            --bg: #fff0f3;
            --card-white: #ffffff;
        }

        body {
            margin: 0; padding: 0; background: var(--bg);
            font-family: 'Poppins', sans-serif;
            display: flex; justify-content: center; align-items: center;
            height: 100vh; overflow: hidden;
        }

        .container {
            background: var(--card-white);
            width: 90%; max-width: 400px;
            padding: 30px 20px; border-radius: 30px;
            box-shadow: 0 15px 40px rgba(255, 77, 109, 0.2);
            text-align: center; display: none;
            position: relative; z-index: 10;
            max-height: 85vh; overflow-y: auto;
            border: 1px solid #ffccd5;
        }

        .active { display: block; animation: fadeIn 0.8s ease; }
        @keyframes fadeIn { from { opacity: 0; transform: scale(0.9); } to { opacity: 1; transform: scale(1); } }

        h1 { font-family: 'Dancing Script', cursive; color: var(--primary); font-size: 2.2rem; margin-bottom: 10px; }
        p { color: #555; line-height: 1.6; font-size: 0.9rem; }

        .btn {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white; border: none; padding: 12px 30px;
            border-radius: 50px; cursor: pointer; font-weight: 600;
            margin-top: 20px; transition: 0.3s; width: 80%;
        }

        .game-img { width: 140px; margin: 15px auto; display: block; border-radius: 20px; }

        /* Game Styles */
        .game-option { 
            background: #fff; border: 2px solid #ffccd5; 
            padding: 10px; margin: 10px 0; border-radius: 15px;
            cursor: pointer; transition: 0.3s; font-size: 0.85rem;
        }
        .game-option:hover { border-color: var(--primary); background: #fff0f3; }
        
        .letter-content {
            text-align: left; font-family: 'Great Vibes', cursive;
            font-size: 1.4rem; line-height: 1.6; color: #333;
            background: #fffdf5; padding: 25px; border-radius: 15px;
            max-height: 450px; overflow-y: auto; white-space: pre-wrap;
            border: 1px solid #eee;
        }

        video { width: 100%; border-radius: 20px; border: 4px solid white; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
    </style>
</head>
<body>

    <div style="display:none"><div id="player"></div></div>

    <div id="page1" class="container active">
        <h1>Hello, My Life ❤️</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Aapke liye maine kuch bahut khaas banaya hai. Kya aap mere saath is chote se safar par chalengi?</p>
        <button class="btn" onclick="startExperience()">Ji Bilkul! ✨</button>
    </div>

    <div id="page2" class="container">
        <h1>Level 1: Truth Test 🧩</h1>
        <img src="https://media.tenor.com/On7tBy_9mS0AAAAi/peach-goma-love.gif" class="game-img">
        <p>Aapke liye sabse sahi baat kya hai?</p>
        <div class="game-option" onclick="alert('Galat! Aap toh pari hain ❤️');">Sirf ek ladki</div>
        <div class="game-option" onclick="nextPage(3)">Duniya ki sabse khoobsurat pari 👼</div>
        <div class="game-option" onclick="alert('Ye toh jhoot hai! 😊');">Normal si ladki</div>
    </div>

    <div id="page3" class="container">
        <h1>Level 2: Catch The Love 💖</h1>
        <img src="https://media.tenor.com/X9S79Uu3v7MAAAAi/mochi-mochi-peach-cat-cat.gif" class="game-img">
        <p>Kya aapko pata hai ki meri khushi kahan hai?</p>
        <div class="game-option" onclick="alert('Nahi, ye nahi hai.');">Sone mein</div>
        <div class="game-option" onclick="nextPage(4)">Aapki pyari si smile mein 😊</div>
        <div class="game-option" onclick="alert('Khana toh pasand hai par aap pehle!');">Khane mein</div>
    </div>

    <div id="page4" class="container">
        <h1>Level 3: Who is Cuter? 🧸</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Is duniya mein sabse cute kaun hai?</p>
        <div class="game-option" onclick="nextPage(5)">Obviously AAP! (Meri Jaan) ❤️</div>
        <div class="game-option" onclick="alert('Nahi, aap zyada cute ho!');">Teddy Bear</div>
    </div>

    <div id="page5" class="container">
        <h1>Level 4: Connection Check ⚡</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Mera favourite kaam kya hai?</p>
        <div class="game-option" onclick="nextPage(6)">Aapko pareshan karna aur pyar karna 🥰</div>
        <div class="game-option" onclick="alert('Nahi, ye boring hai.');">Mobile chalana</div>
    </div>

    <div id="page6" class="container">
        <h1>Level 5: Magic Promise 💍</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Kya aap mera haath hamesha pakde rahengi?</p>
        <div class="game-option" onclick="nextPage(7)">Hamesha, har mod par ❤️</div>
    </div>

    <div id="page7" class="container">
        <h1>Level 6: My World 👑</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="game-img">
        <p>Mera poora sansar kaun hai?</p>
        <div class="game-option" onclick="nextPage(8)">Aap aur sirf Aap ❤️</div>
    </div>

    <div id="page8" class="container">
        <h1>For you 🫶🏻🎀</h1>
        <video id="mainVideo" onended="document.getElementById('finalNxt').style.display='block';">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336739311489057/lv_7555554315964878141_20260117212840.mp4?ex=697c6001&is=697b0e81&hm=ce5b8a803dcfde1f356dd870d25e6f42b03c64a79f69e3b99b21fe03c5d93424&" type="video/mp4">
        </video>
        <button class="btn" id="finalNxt" style="display:none" onclick="nextPage(9)">Ab Mera Khat Padhiye 💌</button>
    </div>

    <div id="page9" class="container">
        <h1>Mere Dil Ki Baat ❤️</h1>
        <div class="letter-content">
Meri Pyaari Jaan,

Aapko pata hai, jab maine pehli baar aapko dekha tha, tab mujhe nahi pata tha ki aap meri poori duniya ban jayengi. Main aksar baith kar ye sochta hoon ki meri zindagi aapke bina kaisi hoti? Shayad wahi purani, boring aur bina kisi maqsad ki. Par aapne aakar meri har ek cheez badal di. Aapne mujhe sikhaya ki kisi se be-intehaan mohabbat kaise ki jati hai.

Aapki wo muskurahat, jise dekh kar main apni saari thakan bhool jata hoon, wo meri sabse badi taqat hai. Jab aap mujhse baat karti hain, to lagta hai jaise waqt ruk gaya ho. Main chahta hoon ki humari har subah aur har shaam bas ek doosre ke saath beete. Main jaanta hoon ki main kabhi kabhi aapko pareshan karta hoon, gussa dila deta hoon, par yakeen maniye, us gusse ke peeche bhi sirf aur sirf aapke liye dher saara pyar hota hai.

Main aapke liye duniya ki har khushi lana chahta hoon. Aap wo sukoon hain jo mujhe kahin aur nahi mil sakta. Humne jo waqt saath bitaya hai, jo videos humne banaye hain, wo sirf clips nahi hain, wo meri zindagi ke sabse haseen hisse hain. Main har din bhagwan se yahi dua karta hoon ki humara sath hamesha aise hi bana rahe. 

Aap mere liye sirf meri girlfriend nahi hain, aap meri sabse acchi dost hain, meri guide hain, aur mera ghar hain. Jab hum saath hote hain, to mujhe kisi aur cheez ki zaroorat nahi lagti. Aapki har choti choti khushi ka dhyan rakhna mera sabse bada kaam hai. Main aapke saath har wo sapna pura karna chahta hoon jo humne dekha hai.

Main waada karta hoon ki main har mod par aapka haath thaame rakhunga. Chahe rasta kitna bhi mushkil ho, aap mujhe apne bagal mein hamesha payengi. Meri zindagi ka har ek lamha ab aapke naam hai. Aapki aankhon mein kabhi aansu nahi aane dunga, aur agar kabhi aaye bhi, to wo sirf khushi ke honge. 

Aapko dekh kar lagta hai ki kudrat ne aapko fursat mein banaya hai. Itni saadgi aur itni masoomiyat shayad hi kisi aur mein ho. Main khush-naseeb hoon ki aap meri hain. Aap meri har dua ka asar hain. 

Aapke saath har din ek naya adventure hai. Main chahta hoon ki hum budhe ho jayein par humara pyar hamesha aise hi naya bana rahe. Main aapke saath dher saari baatein karna chahta hoon, wo bhi tab jab hum dono ke paas kehne ko kuch na ho, bas khamoshi ho aur humara sath. 

Main hamesha aapki izzat karunga aur aapko wo sab dunga jiski aap haqdaar hain. Aap meri queen hain aur main hamesha aapka khayal rakhunga. Thank you meri zindagi mein aane ke liye aur mujhe itna pyar dene ke liye. Aapke bina main adhoora hoon.

Hamesha aapka hi rahunga. I love you to the moon and back, infinity times! ❤️
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
            if(n === 8) { if(player) player.pauseVideo(); v.play(); } 
            else { v.pause(); if(player) player.playVideo(); }
        }
    </script>
</body>
</html>
