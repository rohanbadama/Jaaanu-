<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our 1st Anniversary ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap');
        
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { background: #fff0f3; font-family: 'Poppins', sans-serif; overflow: hidden; color: #590d22; }

        /* Pages System */
        .page { 
            display: none; width: 100%; height: 100vh; 
            flex-direction: column; align-items: center; justify-content: center;
            padding: 20px; text-align: center; position: absolute;
        }
        .active { display: flex !important; animation: fadeIn 0.8s ease; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

        /* Titles */
        h1 { font-family: 'Dancing Script', cursive; font-size: 2.8rem; color: #ff4d6d; margin-bottom: 15px; }
        h2 { font-size: 1.2rem; margin-bottom: 20px; color: #c9184a; }

        /* Symmetry Grid (Entrance) */
        .symmetry-grid {
            display: grid; grid-template-columns: 1fr 1fr; gap: 15px;
            max-width: 350px; margin-bottom: 30px;
        }
        .symmetry-grid img { width: 100%; border-radius: 15px; border: 4px solid white; box-shadow: 0 8px 20px rgba(0,0,0,0.1); }

        /* Video Box */
        .video-wrapper {
            width: 100%; max-width: 320px; border-radius: 25px; 
            overflow: hidden; border: 8px solid white; box-shadow: 0 15px 35px rgba(0,0,0,0.2);
        }
        video { width: 100%; display: block; }

        /* Letter Box (Manual Scroll) */
        .letter-container {
            background: white; width: 90%; max-width: 380px; height: 400px;
            overflow-y: auto; padding: 30px; border-radius: 20px;
            text-align: left; line-height: 1.8; border: 2px solid #ffccd5;
            box-shadow: inset 0 0 15px rgba(0,0,0,0.05);
        }

        /* 6-Card Grid Layout */
        .grid-6 {
            display: grid; grid-template-columns: 1fr 1fr; gap: 12px;
            max-width: 360px; width: 100%;
        }
        .card {
            background: white; border-radius: 15px; padding: 8px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08); position: relative;
        }
        .card img { width: 100%; border-radius: 10px; aspect-ratio: 1/1; object-fit: cover; }
        .card p { font-size: 11px; margin-top: 5px; font-weight: 600; color: #ff4d6d; }

        /* Manual Photo Slider (Card 6) */
        .slider { width: 100%; height: 100%; position: relative; overflow: hidden; border-radius: 10px; }
        .slider img { position: absolute; top:0; left:0; width:100%; height:100%; opacity:0; transition: 0.4s; }
        .slider img.active { opacity: 1; }

        /* Buttons */
        .btn {
            background: #ff4d6d; color: white; border: none; padding: 14px 35px;
            border-radius: 50px; font-weight: 600; cursor: pointer; margin-top: 25px;
            box-shadow: 0 5px 15px rgba(255, 77, 109, 0.4); transition: 0.3s;
        }
        .btn:active { transform: scale(0.95); }

        /* Hearts Background */
        .heart { position: fixed; color: #ff4d6d; pointer-events: none; z-index: -1; animation: float 4s linear infinite; }
        @keyframes float { from { transform: translateY(100vh); opacity: 1; } to { transform: translateY(-10vh); opacity: 0; } }
    </style>
</head>
<body>

<audio id="mainMusic" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<div class="page active" id="p1">
    <h1>Our Special Day ❤️</h1>
    <div class="symmetry-grid">
        <img src="https://media.tenor.com/7S8YgN_Gv98AAAAi/cute-cat.gif">
        <img src="https://media.tenor.com/gYf_65_AclAAAAAi/milk-and-mocha.gif">
    </div>
    <button class="btn" onclick="startExperience()">Open Your Gift 🎁</button>
</div>

<div class="page" id="p2">
    <h2>For You...</h2>
    <div class="video-wrapper">
        <video controls onplay="toggleMusic(false)" onpause="toggleMusic(true)">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4" type="video/mp4">
        </video>
    </div>
    <button class="btn" onclick="go(3)">Next Video ➡</button>
</div>

<div class="page" id="p3">
    <h2>Because You're Special</h2>
    <div class="video-wrapper">
        <video controls onplay="toggleMusic(false)" onpause="toggleMusic(true)">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4" type="video/mp4">
        </video>
    </div>
    <button class="btn" onclick="go(4)">Next Video ➡</button>
</div>

<div class="page" id="p7">
    <h1>My Letter to You 💌</h1>
    <div class="letter-container">
        <p><b>Meri Jaan,</b></p>
        <p>Happy 1st Anniversary! Ye ek saal mere liye kisi sapne se kam nahi tha. Maine har din tumse kuch naya seekha aur har pal tumse aur bhi zyada pyar kiya.</p>
        <p>Tumhara mere saath hona hi meri sabse badi taqat hai. Wo hamari baatein, wo lambi raatein, aur wo choti-choti khushiyan—main sab kuch hamesha ke liye sambhal kar rakhna chahta hoon.</p>
        <p>(Please scroll down...)</p>
        <p>I promise to be with you in every situation. You are my world, my soulmate, and my forever. Love you infinitely! ❤️</p>
    </div>
    <button class="btn" onclick="go(8)">Next: A Small Surprise ➡</button>
</div>

<div class="page" id="p8">
    <h1>Little Moments ✨</h1>
    <div class="grid-6">
        <div class="card"><img src="https://media.tenor.com/v8tT9oV7jPAAAAAi/cute.gif"><p>You're Cute</p></div>
        <div class="card"><img src="https://media.tenor.com/264PjO7v6m0AAAAi/love.gif"><p>I Love You</p></div>
        <div class="card"><img src="https://media.tenor.com/vH95e5vW6EIAAAAi/mocha.gif"><p>My World</p></div>
        <div class="card"><img src="https://media.tenor.com/9-C-S-kKzG8AAAAi/cute.gif"><p>Together</p></div>
        <div class="card"><img src="https://media.tenor.com/X-1M5qC6v3QAAAAi/hug.gif"><p>Warm Hugs</p></div>
        <div class="card" onclick="nextSlide()">
            <div class="slider" id="photoSlider">
                <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png" class="active">
                <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png">
                <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466437297821192326/Screenshot_2025-07-21-03-45-44-645_com.instagram.android.jpg">
                <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png">
            </div>
            <p>Tap to swipe photos 📸</p>
        </div>
    </div>
    <button class="btn" onclick="go(9)">Next ➡</button>
</div>

<div class="page" id="p9">
    <h1>Maja Aaya? 😍</h1>
    <div style="display:flex; gap:20px;">
        <button class="btn" onclick="go(10)">Haa! ❤️</button>
        <button class="btn" style="background:#888;" id="noBtn" onmouseover="moveNo()">Naa 😤</button>
    </div>
</div>

<div class="page" id="p10">
    <h1>Phase 2 Begins... 🌹</h1>
    <p>Abhi toh bahut kuch baaki hai mere dost!</p>
    <button class="btn" onclick="go(1)">Back to Start</button>
</div>

<script>
    let music = document.getElementById('mainMusic');

    function startExperience() {
        music.play();
        go(2);
    }

    function go(pageNumber) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        document.getElementById('p' + pageNumber).classList.add('active');
        
        // Stop any playing video when moving pages
        document.querySelectorAll('video').forEach(v => { v.pause(); v.currentTime = 0; });
        toggleMusic(true);
    }

    function toggleMusic(play) {
        if(play) music.play();
        else music.pause();
    }

    // Photo Slider logic
    let slideIdx = 0;
    function nextSlide() {
        const slides = document.querySelectorAll('#photoSlider img');
        slides[slideIdx].classList.remove('active');
        slideIdx = (slideIdx + 1) % slides.length;
        slides[slideIdx].classList.add('active');
    }

    // No Button Escape logic
    function moveNo() {
        const btn = document.getElementById('noBtn');
        btn.style.position = 'absolute';
        btn.style.left = Math.random() * 80 + '%';
        btn.style.top = Math.random() * 80 + '%';
    }

    // Background Hearts
    setInterval(() => {
        const heart = document.createElement('div');
        heart.innerHTML = '❤️';
        heart.className = 'heart';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 4000);
    }, 400);
</script>

</body>
</html>
