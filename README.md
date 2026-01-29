<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our 1st Anniversary ❤️</title>
    <style>
        :root { --pink: #ffafcc; --dark: #ff2a6d; --soft: #fff0f3; }
        body { margin: 0; font-family: 'Arial', sans-serif; background: var(--soft); display: flex; justify-content: center; align-items: center; height: 100vh; overflow: hidden; }
        
        .card { background: white; padding: 25px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.15); width: 85%; max-width: 400px; text-align: center; border: 4px solid var(--pink); position: relative; z-index: 5; }
        .hidden { display: none !important; }
        img { width: 100%; border-radius: 15px; margin-bottom: 15px; max-height: 200px; object-fit: contain; }
        video { width: 100%; border-radius: 15px; background: #000; box-shadow: 0 5px 15px rgba(0,0,0,0.2); }
        button { background: var(--dark); color: white; border: none; padding: 12px 25px; border-radius: 25px; cursor: pointer; font-weight: bold; margin-top: 15px; transition: 0.3s; }
        
        .rose-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; margin: 20px 0; }
        .rose { font-size: 35px; cursor: pointer; transition: 0.3s; }
        
        .typing-box { text-align: left; white-space: pre-wrap; height: 220px; overflow-y: auto; padding: 15px; border-radius: 10px; border: 1px dashed var(--pink); font-size: 14px; line-height: 1.6; background: #fff9fa; }
        
        #final-bg { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -1; display: none; }
        .slide { position: absolute; width: 100%; height: 100%; object-fit: cover; opacity: 0; transition: opacity 1.5s; }
        .glowing-text { font-size: 2.5rem; color: white; text-shadow: 0 0 10px var(--dark), 0 0 20px var(--dark); animation: beat 1s infinite alternate; }
        @keyframes beat { from { transform: scale(1); } to { transform: scale(1.05); } }
    </style>
</head>
<body>

    <div id="yt-player" style="position: absolute; top: -999px;"></div>

    <div id="p1" class="card">
        <h1>Hello, My Love ❤️</h1>
        <img src="https://media2.giphy.com/media/vFKqnCdLPNOKc/giphy.gif">
        <p>A special journey just for you...</p>
        <button onclick="startApp()">Enter Our World ✨</button>
    </div>

    <div id="p2" class="card hidden">
        <h2>Loading Memories...</h2>
        <img src="https://media3.giphy.com/media/TjSPQgowhhJdHgvnwA/giphy.gif">
        <p>Please wait <span id="timer">5</span>s</p>
    </div>

    <div id="p-video" class="card hidden">
        <h3 id="v-count">Memory 1</h3>
        <video id="vid" controls onplay="controlMusic('pause')" onended="controlMusic('play'); showNextBtn()">
            <source src="" type="video/mp4">
        </video>
        <button id="v-next" class="hidden" onclick="loadVideo()">Next Memory ➡️</button>
    </div>

    <div id="p-rose" class="card hidden">
        <img src="https://media0.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" style="max-height: 100px;">
        <h3>Pick 5 Roses for 5 Secrets 🌹</h3>
        <div class="rose-grid">
            <span class="rose" onclick="revealMsg(0, this)">🌹</span>
            <span class="rose" onclick="revealMsg(1, this)">🌹</span>
            <span class="rose" onclick="revealMsg(2, this)">🌹</span>
            <span class="rose" onclick="revealMsg(3, this)">🌹</span>
            <span class="rose" onclick="revealMsg(4, this)">🌹</span>
        </div>
        <p id="msg-display" style="font-weight: bold; color: var(--dark);">Tap a rose!</p>
        <button id="to-letter" class="hidden" onclick="showPage('p-letter'); startTyping();">Open My Letter ✉️</button>
    </div>

    <div id="p-letter" class="card">
        <img src="https://media1.giphy.com/media/LTNTIw21Qy0ko8SS4Y/giphy.gif" style="max-height: 80px;">
        <div id="l-text" class="typing-box"></div>
        <button id="l-btn" class="hidden" onclick="startFinal()">Final Surprise 🎁</button>
    </div>

    <div id="p-final" class="hidden">
        <div id="final-bg"></div>
        <h1 class="glowing-text">I LOVE YOU FOREVER ❤️</h1>
        <img src="https://media0.giphy.com/media/qiMbLh4WHEZyw/giphy.gif" style="width: 150px; margin-top: 20px;">
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let player;
        let vIdx = 0;
        let found = 0;

        // Aapki Dropbox Videos (Link updated with raw=1)
        const vLinks = [
            "https://www.dropbox.com/scl/fi/o9usm8k2p2kuuk7mx6bl7/lv_7519771999514676541_20260129202958.mp4?rlkey=65vejp4ckxe7ydmn71u0s5c4j&st=ukezepjh&raw=1",
            "https://www.dropbox.com/scl/fi/izqmlr58596t8jwb9lkhb/lv_7365945955050474768_20260129202233.mp4?rlkey=jegiyo01tx1z9nbpctt32shtr&st=v454v32a&raw=1",
            "https://www.dropbox.com/scl/fi/i2cfd8d8kbtdzczj75j3v/lv_7572532755339234613_20260129202646.mp4?rlkey=jh7dukef0w0y33r3kei2iaxsr&st=e7ujditm&raw=1",
            "https://www.dropbox.com/scl/fi/h1eginkeecpti2ijkh3j0/lv_7572376034872478993_20260129201229.mp4?rlkey=glju2q4rhrqqlkmhfccyrxirj&st=k4w3t8j9&raw=1",
            "https://www.dropbox.com/scl/fi/ojmuyvznbim92y4hfysec/lv_7588073915361021201_20260129201555.mp4?rlkey=5tkecx9y3873n3fdglbi6qysw&st=ym0ghjl2&raw=1"
        ];

        // Aapke Photo Links (Yaha apne images ke link dalein)
        const photos = [
            "https://picsum.photos/800/1200?random=1",
            "https://picsum.photos/800/1200?random=2",
            "https://picsum.photos/800/1200?random=3"
        ];

        const compliments = [
            "You are the best teacher of my life! 🎓",
            "Thank you for coming into my world. ❤️",
            "Every day with you is a gift. 🎁",
            "I'm so proud of us. 🥂",
            "I love you more than anything! 💖"
        ];

        function onYouTubeIframeAPIReady() {
            player = new YT.Player('yt-player', {
                height: '0', width: '0',
                videoId: 'fPii4hwD7Zc', 
                events: { 'onReady': (e) => e.target.setVolume(50) }
            });
        }

        function startApp() {
            if(player) player.playVideo();
            showPage('p2');
            let t = 5;
            let timer = setInterval(() => {
                t--;
                document.getElementById('timer').innerText = t;
                if(t <= 0) { clearInterval(timer); showPage('p-video'); loadVideo(); }
            }, 1000);
        }

        function showPage(id) {
            document.querySelectorAll('.card, #p-final').forEach(c => c.classList.add('hidden'));
            document.getElementById(id).classList.remove('hidden');
        }

        function controlMusic(s) {
            if(!player) return;
            s === 'play' ? player.playVideo() : player.pauseVideo();
        }

        function loadVideo() {
            const v = document.getElementById('vid');
            if(vIdx < vLinks.length) {
                v.src = vLinks[vIdx];
                document.getElementById('v-count').innerText = "Memory " + (vIdx + 1);
                document.getElementById('v-next').classList.add('hidden');
                vIdx++;
                v.load();
            } else {
                showPage('p-rose');
            }
        }

        function showNextBtn() { document.getElementById('v-next').classList.remove('hidden'); }

        function revealMsg(i, el) {
            document.getElementById('msg-display').innerText = compliments[i];
            el.style.opacity = "0.2";
            el.style.pointerEvents = "none";
            found++;
            if(found >= 5) document.getElementById('to-letter').classList.remove('hidden');
        }

        function startTyping() {
            const txt = "Happy 1 Year Anniversary My Love!\n\nThank you for coming into my life and teaching me so much. You've taught me patience, kindness, and what it truly means to be loved. \n\nI am so lucky to have you as my partner and my teacher. Thank you for making every day special. I promise to be yours forever.\n\nLove you always and forever ❤️";
            let i = 0;
            const target = document.getElementById('l-text');
            target.innerHTML = "";
            function type() {
                if(i < txt.length) {
                    target.innerHTML += txt.charAt(i);
                    i++;
                    setTimeout(type, 50);
                    target.scrollTop = target.scrollHeight;
                } else {
                    document.getElementById('l-btn').classList.remove('hidden');
                }
            }
            type();
        }

        function startFinal() {
            showPage('p-final');
            const bg = document.getElementById('final-bg');
            bg.style.display = 'block';
            photos.forEach((url, i) => {
                const img = document.createElement('img');
                img.src = url; img.className = 'slide';
                if(i === 0) img.style.opacity = 1;
                bg.appendChild(img);
            });
            let cur = 0;
            setInterval(() => {
                const slides = document.querySelectorAll('.slide');
                if(slides.length > 0) {
                    slides[cur].style.opacity = 0;
                    cur = (cur + 1) % slides.length;
                    slides[cur].style.opacity = 1;
                }
            }, 3000);
        }

        // Initialize first page
        window.onload = () => showPage('p1');
    </script>
</body>
</html>
