<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Forever Journey ❤️</title>
    <style>
        :root {
            --primary-color: #ff4d6d;
            --bg-color: #fff0f3;
            --text-color: #590d22;
        }

        body, html {
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* Floating Hearts Animation */
        .heart {
            position: fixed;
            color: var(--primary-color);
            font-size: 20px;
            z-index: -1;
            user-select: none;
            animation: float 5s linear infinite;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        /* Container & Sections */
        .section {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            text-align: center;
        }

        /* Grid Cards */
        .card-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            max-width: 500px;
            margin-top: 20px;
        }

        .card {
            background: white;
            border-radius: 15px;
            padding: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .card:hover { transform: scale(1.05); }

        .card img {
            width: 100%;
            border-radius: 10px;
            aspect-ratio: 1/1;
            object-fit: cover;
        }

        /* Video Container */
        .video-box {
            width: 90%;
            max-width: 350px;
            border: 5px solid white;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        /* Buttons */
        .btn {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            font-size: 1.1rem;
            cursor: pointer;
            margin-top: 20px;
            box-shadow: 0 4px 10px rgba(255, 77, 109, 0.4);
        }

        /* Letter Box (Manual Scroll) */
        .letter-box {
            background: #fff;
            padding: 30px;
            border-radius: 5px;
            max-width: 400px;
            height: 300px;
            overflow-y: auto;
            border-left: 5px solid var(--primary-color);
            line-height: 1.6;
            text-align: left;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.05);
        }

        /* Photo Slider (6th Card) */
        .slider {
            position: relative;
            width: 100%;
            height: 150px;
            overflow: hidden;
            border-radius: 10px;
        }

        .slider img {
            position: absolute;
            width: 100%;
            height: 100%;
            display: none;
        }

        .slider img.active { display: block; }

        .vibrate { animation: shake 0.2s infinite; }
        @keyframes shake {
            0% { transform: translate(1px, 1px) rotate(0deg); }
            20% { transform: translate(-3px, 0px) rotate(1deg); }
            100% { transform: translate(1px, -1px) rotate(-1deg); }
        }

        #phase2 { display: none; }
    </style>
</head>
<body>

<audio id="bgMusic" loop>
    <source src="https://www.mediafire.com/file/qp25u85zldwh5mu/Darkhaast+(From+Shivaay).mp3/file" type="audio/mpeg">
</audio>

<div id="phase1">
    <div class="section">
        <h2>Happy Anniversary, My Jaan! ❤️</h2>
        <div class="card-grid" id="intro-grid">
            <div class="card"><img src="https://media.tenor.com/7S8YgN_Gv98AAAAi/cute-cat.gif"></div>
            <div class="card"><img src="https://media.tenor.com/gYf_65_AclAAAAAi/milk-and-mocha.gif"></div>
        </div>
        <button class="btn" onclick="startApp()">Tap to Start Our Magic ✨</button>
    </div>

    <div class="section">
        <h3 id="vid-title">For You... 🎁</h3>
        <video id="videoPlayer" class="video-box" controls onplay="pauseMusic()" onpause="playMusic()" onended="nextVideo()">
            <source id="videoSource" src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4" type="video/mp4">
        </video>
        <p id="vid-count">1 / 5</p>
    </div>

    <div class="section">
        <div class="letter-box">
            <h3>My Dearest...</h3>
            <p>Happy Anniversary! This year has been the most beautiful journey of my life because you were in it. Every moment spent with you feels like a blessing. I promise to hold your hand through every high and low...</p>
            <p>(Scroll down to read more...)</p>
            <p>You are my best friend, my soulmate, and my everything. I love you more than words can express. Thank you for being mine! ❤️</p>
        </div>
    </div>

    <div class="section">
        <h3>Little Moments, Big Love ✨</h3>
        <div class="card-grid">
            <div class="card"><img src="https://media.tenor.com/v8tT9oV7jPAAAAAi/cute.gif"><p>You're Mine</p></div>
            <div class="card"><img src="https://media.tenor.com/264PjO7v6m0AAAAi/love.gif"><p>Always & Forever</p></div>
            <div class="card"><img src="https://media.tenor.com/vH95e5vW6EIAAAAi/mocha.gif"><p>My World</p></div>
            <div class="card"><img src="https://media.tenor.com/9-C-S-kKzG8AAAAi/cute.gif"><p>Sweetest Soul</p></div>
            <div class="card"><img src="https://media.tenor.com/X-1M5qC6v3QAAAAi/hug.gif"><p>Warm Hugs</p></div>
            <div class="card" id="slider-card">
                <div class="slider" id="photoSlider" onclick="nextSlide()">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png" class="active">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466437297821192326/Screenshot_2025-07-21-03-45-44-645_com.instagram.android.jpg">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032407933071/Screenshot_2025-10-30-17-57-27-678_com.instagram.android.jpg">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032864981164/FreeFire_10_20_2025_19_46_49.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436033343262720/FreeFire_11_06_2025_17_43_23.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436033917747447/FreeFire_12_15_2025_18_05_48.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436034366799882/FreeFire_12_22_2025_10_44_53.png">
                </div>
                <p>Tap to Swipe 📸</p>
            </div>
        </div>
    </div>

    <div class="section" id="trigger-sec">
        <h3>Maja Aaya? 😍</h3>
        <div>
            <button class="btn" onclick="goToPhase2()">Haa! ❤️</button>
            <button class="btn" style="background:#888;" onmouseover="vibrateScreen()" onclick="alert('Nahi ka option nahi hai! 😜')">Naa 😤</button>
        </div>
    </div>
</div>

<div id="phase2">
    <div class="section">
        <h3>Wait, There's More! 🌹</h3>
        <p>Round 2 starts now...</p>
        </div>
</div>

<script>
    // Music Controls
    const music = document.getElementById('bgMusic');
    function playMusic() { music.play(); }
    function pauseMusic() { music.pause(); }
    function startApp() { 
        playMusic();
        window.scrollBy(0, window.innerHeight);
    }

    // Video Logic
    const videos1 = [
        "https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4",
        "https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4",
        "https://cdn.discordapp.com/attachments/1421877888877203559/1466448574396104777/lv_7588073915361021201_20260129201555.mp4",
        "https://cdn.discordapp.com/attachments/1421877888877203559/1466448575012671690/lv_7365945955050474768_20260129202233.mp4",
        "https://cdn.discordapp.com/attachments/1421877888877203559/1466448573179891743/lv_7519771999514676541_20260129202958.mp4"
    ];
    let currentVid = 0;
    const titles = ["For You...", "Because You're Special", "Our Memories", "Just Love", "Last One..."];

    function nextVideo() {
        currentVid++;
        if(currentVid < videos1.length) {
            document.getElementById('videoSource').src = videos1[currentVid];
            document.getElementById('videoPlayer').load();
            document.getElementById('vid-title').innerText = titles[currentVid];
            document.getElementById('vid-count').innerText = (currentVid + 1) + " / 5";
        }
    }

    // Photo Slider Logic
    let currentSlide = 0;
    function nextSlide() {
        const slides = document.querySelectorAll('#photoSlider img');
        slides[currentSlide].classList.remove('active');
        currentSlide = (currentSlide + 1) % slides.length;
        slides[currentSlide].classList.add('active');
    }

    // Floating Hearts
    setInterval(() => {
        const heart = document.createElement('div');
        heart.classList.add('heart');
        heart.innerHTML = '❤️';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = (Math.random() * 3 + 2) + 's';
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 5000);
    }, 500);

    function vibrateScreen() {
        document.body.classList.add('vibrate');
        setTimeout(() => document.body.classList.remove('vibrate'), 500);
    }

    function goToPhase2() {
        document.getElementById('phase1').style.display = 'none';
        document.getElementById('phase2').style.display = 'block';
        window.scrollTo(0,0);
    }
</script>

</body>
</html>
