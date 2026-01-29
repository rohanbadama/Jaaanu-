<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 1st Anniversary</title>
    <style>
        :root { --pink: #ffafcc; --dark-pink: #ff2a6d; --bg: #fff0f3; }
        body { margin: 0; font-family: 'Arial', sans-serif; background: var(--bg); display: flex; justify-content: center; align-items: center; height: 100vh; overflow: hidden; }
        
        /* Background Slideshow */
        #slideshow { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -1; display: none; }
        .slide { position: absolute; width: 100%; height: 100%; object-fit: cover; opacity: 0; transition: opacity 1.5s; }

        .card { background: white; padding: 30px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); width: 90%; max-width: 400px; text-align: center; border: 4px solid var(--pink); z-index: 10; }
        .hidden { display: none; }
        img { width: 100%; border-radius: 15px; margin-bottom: 15px; max-height: 250px; object-fit: contain; }
        video { width: 100%; border-radius: 15px; }
        button { background: var(--dark-pink); color: white; border: none; padding: 12px 25px; border-radius: 25px; cursor: pointer; font-size: 1rem; margin-top: 15px; }
        
        .rose-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; margin: 20px 0; }
        .rose { font-size: 30px; cursor: pointer; transition: 0.3s; }
        .rose:hover { transform: scale(1.2); }
        .typing { text-align: left; white-space: pre-wrap; height: 200px; overflow-y: auto; font-size: 0.9rem; line-height: 1.5; border: 1px dashed var(--pink); padding: 10px; }
        .glowing { font-size: 2.5rem; color: white; text-shadow: 0 0 10px var(--dark-pink), 0 0 20px var(--dark-pink); animation: pulse 1s infinite alternate; }
        @keyframes pulse { from { transform: scale(1); } to { transform: scale(1.1); } }
    </style>
</head>
<body>

    <div id="player" style="position:absolute; top:-9999px;"></div>

    <div id="page1" class="card">
        <h1>Welcome My Love ❤️</h1>
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNHJpdmVycXN6bjF3eXp6N3R3eXp6N3R3eXp6N3R3eXp6N3R3JnB0PWFwcF9pbnN0YWxs/MDJ9FqnEx7qxHRAAkO/giphy.gif" alt="Welcome GIF">
        <p>A small surprise for our 1st Anniversary...</p>
        <button onclick="startExperience()">Click to Start</button>
    </div>

    <div id="page2" class="card hidden">
        <h2>Sweet Loading...</h2>
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNXN6bzF3eXp6N3R3eXp6N3R3eXp6N3R3eXp6N3R3eXp6JnB0PWFwcF9pbnN0YWxs/l41lTfuxV5F6K+O1W/giphy.gif">
        <p>Game is loading! Please wait for <span id="timer">5</span>s</p>
    </div>

    <div id="videoPage" class="card hidden">
        <h3 id="vTitle">Memory 1</h3>
        <video id="vPlayer" controls onplay="toggleBGM(false)" onended="videoDone()">
            <source src="" type="video/mp4">
        </video>
        <button id="nextVBtn" class="hidden" onclick="loadNextVideo()">Next Memory</button>
    </div>

    <div id="msgPage" class="card hidden">
        <h2>Pick your Roses 🌹</h2>
        <div class="rose-grid">
            <span class="rose" onclick="showMsg(0, this)">🌹</span>
            <span class="rose" onclick="showMsg(1, this)">🌹</span>
            <span class="rose" onclick="showMsg(2, this)">🌹</span>
            <span class="rose" onclick="showMsg(3, this)">🌹</span>
            <span class="rose" onclick="showMsg(4, this)">🌹</span>
        </div>
        <p id="displayMsg">Tap each rose to see a message!</p>
        <button id="toLetter" class="hidden" onclick="showPage('letterPage')">Read My Letter</button>
    </div>

    <div id="letterPage" class="card hidden">
        <h2>My Heart for You</h2>
        <div id="typewriter" class="typing"></div>
        <button id="finalBtn" class="hidden" onclick="showFinal()">Love You</button>
    </div>

    <div id="finalPage" class="hidden">
        <div id="slideshow"></div>
        <h1 class="glowing">I LOVE YOU FOREVER ❤️</h1>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let ytPlayer;
        let vIndex = 0;
        let rosesFound = 0;
        const vLinks = [
            "https://www.w3schools.com/html/mov_bbb.mp4", // Test Link (Replace with your direct mp4 links)
            "your_discord_link_1", 
            "your_discord_link_2",
            "your_discord_link_3",
            "your_discord_link_4"
        ];
        
        const photoLinks = [
            "https://picsum.photos/800/1200?random=1", 
            "https://picsum.photos/800/1200?random=2"
        ];

        const msgs = ["You're my world!", "Best 1 year ever.", "You're so beautiful.", "Thanks for everything!", "I'm yours!"];

        function onYouTubeIframeAPIReady() {
            ytPlayer = new YT.Player('player', {
                height: '0', width: '0',
                videoId: 'fPii4kwD7Zc', // Your Background Music ID
                events: { 'onReady': (e) => e.target.setVolume(50) }
            });
        }

        function startExperience() {
            if(ytPlayer) ytPlayer.playVideo();
            showPage('page2');
            let sec = 5;
            let t = setInterval(() => {
                sec--;
                document.getElementById('timer').innerText = sec;
                if(sec <= 0) { clearInterval(t); showPage('videoPage'); loadNextVideo(); }
            }, 1000);
        }

        function showPage(id) {
            document.querySelectorAll('.card').forEach(c => c.classList.add('hidden'));
            document.getElementById(id).classList.remove('hidden');
        }

        function toggleBGM(play) {
            if(!ytPlayer) return;
            play ? ytPlayer.playVideo() : ytPlayer.pauseVideo();
        }

        function loadNextVideo() {
            const vp = document.getElementById('vPlayer');
            if(vIndex < vLinks.length) {
                vp.src = vLinks[vIndex];
                document.getElementById('vTitle').innerText = "Memory " + (vIndex + 1);
                document.getElementById('nextVBtn').classList.add('hidden');
                vIndex++;
                vp.load();
            } else {
                showPage('msgPage');
            }
        }

        function videoDone() {
            toggleBGM(true);
            document.getElementById('nextVBtn').classList.remove('hidden');
        }

        function showMsg(i, el) {
            document.getElementById('displayMsg').innerText = msgs[i];
            el.style.opacity = "0.3";
            rosesFound++;
            if(rosesFound >= 5) document.getElementById('toLetter').classList.remove('hidden');
        }

        function showFinal() {
            showPage('finalPage');
            const ss = document.getElementById('slideshow');
            ss.style.display = 'block';
            photoLinks.forEach((url, i) => {
                const img = document.createElement('img');
                img.src = url; img.className = 'slide';
                if(i===0) img.style.opacity = 1;
                ss.appendChild(img);
            });
            let current = 0;
            setInterval(() => {
                const s = document.querySelectorAll('.slide');
                s[current].style.opacity = 0;
                current = (current + 1) % s.length;
                s[current].style.opacity = 1;
            }, 3000);
        }
        
        // Typing animation code yaha aayega... (simliar to previous)
    </script>
</body>
</html>
