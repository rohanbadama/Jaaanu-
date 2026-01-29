<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 1st Anniversary My Love</title>
    <style>
        :root {
            --pink: #ffafcc;
            --dark-pink: #ff2a6d;
            --bg-color: #fff0f3;
        }

        body {
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            text-align: center;
        }

        /* Background Slideshow */
        #slideshow {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: -1;
            display: none;
        }
        .slide {
            position: absolute;
            width: 100%; height: 100%;
            object-fit: cover;
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }

        .card {
            background: white;
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            width: 90%;
            max-width: 400px;
            position: relative;
            border: 5px solid var(--pink);
        }

        .hidden { display: none; }

        img, video {
            width: 100%;
            border-radius: 15px;
            margin-bottom: 15px;
        }

        button {
            background: var(--dark-pink);
            color: white;
            border: none;
            padding: 10px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.1rem;
            transition: transform 0.2s;
        }

        button:hover { transform: scale(1.1); }

        .typing {
            font-size: 1.2rem;
            text-align: left;
            white-space: pre-wrap;
            max-height: 300px;
            overflow-y: auto;
            padding: 10px;
        }

        .glowing-text {
            font-size: 2rem;
            color: #fff;
            text-shadow: 0 0 10px var(--dark-pink), 0 0 20px var(--dark-pink), 0 0 40px var(--dark-pink);
            animation: glow 1.5s infinite alternate;
        }

        @keyframes glow {
            from { opacity: 0.7; }
            to { opacity: 1; text-shadow: 0 0 20px var(--dark-pink), 0 0 30px var(--dark-pink); }
        }

        .gift-box {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
        }
        .rose { cursor: pointer; font-size: 2rem; }
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="https://www.youtube.com/watch?v=fPii4kwD7Zc" type="audio/mpeg">
        </audio>

    <div id="slideshow"></div>

    <div id="page1" class="card">
        <h1>Welcome, My Love ❤️</h1>
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif" alt="Welcome">
        <p>I have a special surprise for you...</p>
        <button onclick="nextPage(2); playMusic()">Start Surprise</button>
    </div>

    <div id="page2" class="card hidden">
        <h2>Mini Game 🎮</h2>
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466399975205376052/From_KlickPin_CF_Resultado_de_imagen_para_Milk__Mocha_STICKERS___Hug_gif_Cute_gif_Cute_love_gif.gif">
        <p>Wait for 5 seconds to unlock next stage...</p>
        <div id="timer">5</div>
    </div>

    <div id="videoPages" class="card hidden">
        <h2 id="videoTitle">Our Memories</h2>
        <video id="mainVideo" controls onplay="pauseMusic()" onended="videoEnded()">
            <source src="" type="video/mp4">
        </video>
        <p id="videoStatus">Watch till the end!</p>
        <button id="nextVideoBtn" class="hidden" onclick="loadNextVideo()">Next Video</button>
    </div>

    <div id="page8" class="card hidden">
        <h2>Pick a Rose 🌹</h2>
        <div class="gift-box" id="roseBox">
            <div class="rose" onclick="revealMessage(0)">🌹</div>
            <div class="rose" onclick="revealMessage(1)">🌹</div>
            <div class="rose" onclick="revealMessage(2)">🌹</div>
            <div class="rose" onclick="revealMessage(3)">🌹</div>
            <div class="rose" onclick="revealMessage(4)">🌹</div>
        </div>
        <p id="roseMessage"></p>
        <button id="letterBtn" class="hidden" onclick="nextPage(9)">Open Letter</button>
    </div>

    <div id="page9" class="card hidden">
        <h2>My Letter to You ✉️</h2>
        <div id="letterArea" class="typing"></div>
        <button id="finalBtn" class="hidden" onclick="startEnd()">Love You!</button>
    </div>

    <div id="page10" class="hidden">
        <h1 class="glowing-text">I LOVE YOU FOREVER ❤️</h1>
        <p style="color: white;">Happy 1st Anniversary!</p>
    </div>

    <script>
        let music = document.getElementById('bgMusic');
        let currentVideoIndex = 0;
        const videoLinks = [
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448687809954058/lv_7555554315964878141_20260117212840.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448576363233361/lv_7572376034872478993_20260129201229.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448578389217290/lv_7596206565158423861_20260129200129.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448577013354598/lv_7591172117144587573_20260129201020.mp4",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4"
        ];

        const photos = [
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg"
            // Baki photos yaha add karein...
        ];

        const compliments = [
            "You are the most beautiful person I know!",
            "Thank you for being my rock.",
            "I learn something new from you every day.",
            "Your smile makes everything better.",
            "I'm so lucky to have you in my life!"
        ];

        function playMusic() { music.play(); }
        function pauseMusic() { music.pause(); }

        function nextPage(num) {
            document.querySelectorAll('.card').forEach(c => c.classList.add('hidden'));
            if(num === 2) {
                document.getElementById('page2').classList.remove('hidden');
                let count = 5;
                let itv = setInterval(() => {
                    count--;
                    document.getElementById('timer').innerText = count;
                    if(count === 0) {
                        clearInterval(itv);
                        nextPage('video');
                    }
                }, 1000);
            } else if(num === 'video') {
                document.getElementById('videoPages').classList.remove('hidden');
                loadNextVideo();
            } else {
                document.getElementById('page' + num).classList.remove('hidden');
                if(num === 9) startTyping();
            }
        }

        function loadNextVideo() {
            if(currentVideoIndex < videoLinks.length) {
                const v = document.getElementById('mainVideo');
                v.src = videoLinks[currentVideoIndex];
                v.load();
                document.getElementById('nextVideoBtn').classList.add('hidden');
                document.getElementById('videoTitle').innerText = "Video " + (currentVideoIndex + 1);
                currentVideoIndex++;
            } else {
                nextPage(8);
            }
        }

        function videoEnded() {
            playMusic();
            document.getElementById('nextVideoBtn').classList.remove('hidden');
        }

        let revealedCount = 0;
        function revealMessage(idx) {
            document.getElementById('roseMessage').innerText = compliments[idx];
            revealedCount++;
            if(revealedCount >= 5) document.getElementById('letterBtn').classList.remove('hidden');
        }

        function startTyping() {
            const text = "Happy 1st Anniversary My Love!\n\nThank you for coming into my life and teaching me so much. This past year has been the best journey of my life. I promise to be by your side forever. You are my world, my everything.\n\nLove you to the moon and back!";
            let i = 0;
            const area = document.getElementById('letterArea');
            function type() {
                if (i < text.length) {
                    area.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, 50);
                } else {
                    document.getElementById('finalBtn').classList.remove('hidden');
                }
            }
            type();
        }

        function startEnd() {
            document.getElementById('page9').classList.add('hidden');
            document.getElementById('page10').classList.remove('hidden');
            document.getElementById('slideshow').style.display = 'block';
            
            // Start Slideshow
            const show = document.getElementById('slideshow');
            photos.forEach(url => {
                let img = document.createElement('img');
                img.src = url;
                img.className = 'slide';
                show.appendChild(img);
            });

            let currentSlide = 0;
            const slides = document.querySelectorAll('.slide');
            slides[0].style.opacity = 1;
            setInterval(() => {
                slides[currentSlide].style.opacity = 0;
                currentSlide = (currentSlide + 1) % slides.length;
                slides[currentSlide].style.opacity = 1;
            }, 3000);
        }
    </script>
</body>
</html>
