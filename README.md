<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Anniversary Journey ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root { --p: #fff0f3; --s: #ff4d6d; --text: #444; }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Poppins', sans-serif; }
        body { background: var(--p); height: 100vh; overflow: hidden; }
        
        /* Persistent Background Music Container */
        #music-container { position: fixed; top: -100px; left: -100px; width: 1px; height: 1px; overflow: hidden; }

        .page { display: none; height: 100vh; width: 100vw; justify-content: center; align-items: center; position: absolute; padding: 20px; text-align: center; }
        .active { display: flex; animation: fadeIn 0.5s ease forwards; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        .card { background: white; padding: 25px; border-radius: 20px; box-shadow: 0 10px 30px rgba(255, 77, 109, 0.2); 
                  width: 100%; max-width: 400px; border: 2px solid #ffb3c1; position: relative; max-height: 90vh; overflow-y: auto; }
        
        h1, h2 { font-family: 'Dancing Script', cursive; color: var(--s); margin-bottom: 15px; }
        .media-frame { border-radius: 15px; overflow: hidden; margin: 15px 0; background: #000; min-height: 100px; border: 3px solid #ffe5ec; }
        .media-frame img, .media-frame video { width: 100%; display: block; max-height: 350px; }

        .letter-box { background: #fffcf2; padding: 20px; border-radius: 10px; text-align: left; font-size: 0.9rem; 
                      line-height: 1.6; color: #333; max-height: 300px; overflow-y: scroll; border-left: 5px solid var(--s); white-space: pre-wrap; }

        .next-btn { background: var(--s); color: white; border: none; padding: 12px 30px; border-radius: 25px; cursor: pointer; font-weight: 600; margin-top: 15px; width: 80%; }
        
        .game-btn { background: white; border: 2px solid var(--s); color: var(--s); padding: 10px; margin: 5px; border-radius: 12px; cursor: pointer; display: inline-block; transition: 0.2s; }
        .game-btn:hover { background: var(--s); color: white; }

        .heart-float { position: fixed; color: var(--s); font-size: 20px; z-index: -1; animation: up 4s linear infinite; }
        @keyframes up { 0% { transform: translateY(110vh) scale(0); opacity: 1; } 100% { transform: translateY(-10vh) scale(1.5); opacity: 0; } }
    </style>
</head>
<body>

<div id="music-container">
    <div id="player"></div>
</div>

<main id="app">
    <section class="page active">
        <div class="card">
            <h1>Happy 1 Year! ❤️</h1>
            <div class="media-frame"><img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif"></div>
            <p>I have a surprise for you. Ready?</p>
            <button class="next-btn" onclick="startApp()">Start Experience 💖</button>
        </div>
    </section>

    <section class="page"><div class="card"><h2>Game 1: Catch the Heart</h2><div id="g1" style="height:150px; position:relative;"><div id="t1" onclick="score(1)" style="position:absolute; cursor:pointer; font-size:40px;">❤️</div></div><p>Score: <span id="s1">0</span>/10</p></div></section>
    <section class="page"><div class="card"><h2>Game 2: Memory Test</h2><p>Click the hearts in order: 1, 2, 3</p><button class="game-btn" onclick="check(1)">1</button><button class="game-btn" onclick="check(2)">2</button><button class="game-btn" onclick="check(3)">3</button></div></section>
    <section class="page"><div class="card"><h2>Game 3: Find Me</h2><p>Which one is our anniversary month?</p><button class="game-btn" onclick="alert('Try again!')">Dec</button><button class="game-btn" onclick="nextPage()">Jan</button><button class="game-btn" onclick="alert('Try again!')">Feb</button></div></section>
    <section class="page"><div class="card"><h2>Game 4: Quick Math</h2><p>You + Me = ?</p><button class="game-btn" onclick="nextPage()">Everything ❤️</button></div></section>

    <script>
        const vLinks = [
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448687809954058/lv_7555554315964878141_20260117212840.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448576363233361/lv_7572376034872478993_20260129201229.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448578389217290/lv_7596206565158423861_20260129200129.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448577013354598/lv_7591172117144587573_20260129201020.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4"
        ];
        vLinks.forEach((l, i) => {
            document.write(`<section class="page"><div class="card"><h2>Memory #${i+1} 🫶🏻</h2><div class="media-frame"><video controls onplay="toggleMusic(false)" onended="toggleMusic(true)"><source src="${l}" type="video/mp4"></video></div><button class="next-btn" onclick="nextPage()">Next</button></div></section>`);
        });
    </script>

    <section class="page">
        <div class="card">
            <h2>Part 1: My Forever ✉️</h2>
            <div class="letter-box">Happy 1 year anniversary meri FOREVER 🫶🏻 💖 Aaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai... [FULL TEXT FROM YOUR MESSAGE] ...Aap meri zindagi me ek chapter nahi, balki ek aisi kahani ho jo abhi likhi ja rahi hai. I love you!</div>
            <button class="next-btn" onclick="nextPage()">Continue Journey...</button>
        </div>
    </section>

    <section class="page"><div class="card"><h2>Game 5: Catch Again!</h2><div id="g5" style="height:150px; position:relative;"><div id="t5" onclick="score(5)" style="position:absolute; cursor:pointer; font-size:40px;">🌸</div></div><p>Score: <span id="s5">0</span>/5</p></div></section>
    <section class="page"><div class="card"><h2>Game 6: Do you love me?</h2><div style="display:flex; justify-content:center; gap:10px;"><button class="next-btn" onclick="nextPage()">YES! 😍</button><button class="next-btn" id="no-btn" onmouseover="moveNo()" style="background:#888">No 😢</button></div></div></section>
    <section class="page"><div class="card"><h2>Game 7: Secret Box</h2><div id="boxes"></div></div></section>
    <section class="page"><div class="card"><h2>Game 8: The Final Quiz</h2><p>Who is the luckiest person? (It's me!)</p><button class="next-btn" onclick="nextPage()">Me because of YOU ❤️</button></div></section>

    <script>
        const vLinks2 = [
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448574396104777/lv_7588073915361021201_20260129201555.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448575012671690/lv_7365945955050474768_20260129202233.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448573179891743/lv_7519771999514676541_20260129202958.mp4"
        ];
        vLinks2.forEach((l, i) => {
            document.write(`<section class="page"><div class="card"><h2>Memory #${i+6} 💖</h2><div class="media-frame"><video controls onplay="toggleMusic(false)" onended="toggleMusic(true)"><source src="${l}" type="video/mp4"></video></div><button class="next-btn" onclick="nextPage()">Next</button></div></section>`);
        });
    </script>

    <section class="page">
        <div class="card">
            <h2>Endlessly Yours ❤️</h2>
            <div class="letter-box">pehle ye feel hota hai ki meri zindagi me jo bhi softness, jo bhi emotional depth, jo bhi sachcha care aaya hai... [FULL TEXT OF MESSAGE 2] ...Aap meri choice nahi, meri clarity ho. I love you endlessly my jaaaaaneman 😚 💖.</div>
            <button class="next-btn" onclick="alert('Happy Anniversary!')">I Love You Forever ❤️</button>
        </div>
    </section>
</main>

<script src="https://www.youtube.com/iframe_api"></script>
<script>
    let player;
    let currentStep = 0;
    const pages = document.querySelectorAll('.page');

    function onYouTubeIframeAPIReady() {
        player = new YT.Player('player', {
            height: '0', width: '0',
            videoId: 'fPii4kwD7Zc',
            playerVars: { 'autoplay': 0, 'loop': 1, 'playlist': 'fPii4kwD7Zc' }
        });
    }

    function startApp() {
        player.playVideo();
        nextPage();
    }

    function nextPage() {
        pages[currentStep].classList.remove('active');
        currentStep++;
        if(currentStep < pages.length) {
            pages[currentStep].classList.add('active');
            toggleMusic(true); // Resume music on new page unless video starts
        }
    }

    function toggleMusic(play) {
        if(play) player.playVideo();
        else player.pauseVideo();
    }

    // Games Logic
    let s1 = 0, s5 = 0;
    function score(n) {
        if(n==1) { s1++; document.getElementById('s1').innerText=s1; move('t1'); if(s1>=10) nextPage(); }
        if(n==5) { s5++; document.getElementById('s5').innerText=s5; move('t5'); if(s5>=5) nextPage(); }
    }
    function move(id) { let t=document.getElementById(id); t.style.left=Math.random()*80+'%'; t.style.top=Math.random()*80+'%'; }

    let mCheck = 1;
    function check(n) { if(n==mCheck) { mCheck++; if(mCheck>3) nextPage(); } else { mCheck=1; alert('Wrong order! Try again.'); }}

    function moveNo() { let b=document.getElementById('no-btn'); b.style.position='fixed'; b.style.left=Math.random()*80+'vw'; b.style.top=Math.random()*80+'vh'; }

    // Init Box Game
    const bDiv = document.getElementById('boxes');
    for(let i=0; i<3; i++) {
        let b = document.createElement('button'); b.className='game-btn'; b.innerText='???';
        b.onclick = () => { if(i==1) nextPage(); else alert('Empty! Try another.'); };
        bDiv.appendChild(b);
    }

    // Hearts background
    setInterval(() => {
        const h = document.createElement('div'); h.innerHTML = '❤️'; h.className = 'heart-float';
        h.style.left = Math.random()*100+'vw'; h.style.animationDuration = (Math.random()*2+2)+'s';
        document.body.appendChild(h); setTimeout(()=>h.remove(), 4000);
    }, 500);
</script>
</body>
</html>
