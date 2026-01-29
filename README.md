<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anniversary Surprise ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap');

        * { box-sizing: border-box; }
        body, html { 
            margin: 0; padding: 0; width: 100%; height: 100%; 
            overflow: hidden; font-family: 'Poppins', sans-serif;
            background: #fff5f7;
        }

        /* Har Page ki Setting */
        .page {
            display: none; /* Default hidden */
            width: 100%; height: 100vh;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            text-align: center;
            position: relative;
        }

        .active { display: flex !important; }

        h1 { font-family: 'Dancing Script', cursive; color: #ff4d6d; font-size: 2.5rem; margin-bottom: 20px; }

        /* Symmetry GIFs Grid */
        .gif-grid {
            display: grid; grid-template-columns: 1fr 1fr;
            gap: 10px; max-width: 320px; margin-bottom: 20px;
        }
        .gif-grid img { width: 100%; border-radius: 12px; border: 3px solid white; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }

        /* Video Styling */
        .video-container { width: 100%; max-width: 300px; border-radius: 20px; overflow: hidden; border: 6px solid white; box-shadow: 0 10px 30px rgba(0,0,0,0.2); }
        video { width: 100%; display: block; }

        /* Letter Styling (Manual Scroll) */
        .letter-container {
            background: white; padding: 25px; border-radius: 15px;
            width: 90%; max-width: 350px; height: 350px;
            overflow-y: auto; text-align: left; line-height: 1.7;
            border: 1px solid #ffccd5; box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        /* Photo Slider (6th Card) */
        .slider { width: 280px; height: 380px; position: relative; border-radius: 15px; overflow: hidden; border: 5px solid white; }
        .slider img { width: 100%; height: 100%; object-fit: cover; position: absolute; top: 0; left: 0; opacity: 0; transition: 0.5s; }
        .slider img.show { opacity: 1; }

        /* Buttons */
        .btn {
            background: #ff4d6d; color: white; border: none;
            padding: 12px 30px; border-radius: 25px; font-size: 1rem;
            font-weight: 600; margin-top: 25px; cursor: pointer;
            box-shadow: 0 4px 10px rgba(255, 77, 109, 0.3);
        }

        /* Floating Hearts */
        .heart { position: fixed; color: #ff4d6d; pointer-events: none; z-index: 999; animation: moveUp 4s linear forwards; }
        @keyframes moveUp { to { transform: translateY(-100vh) rotate(360deg); opacity: 0; } }
    </style>
</head>
<body>

<audio id="bgMusic" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<div class="page active" id="p1">
    <h1>Our Journey Begins... ❤️</h1>
    <div class="gif-grid">
        <img src="https://media.tenor.com/7S8YgN_Gv98AAAAi/cute-cat.gif">
        <img src="https://media.tenor.com/gYf_65_AclAAAAAi/milk-and-mocha.gif">
        <img src="https://media.tenor.com/X-1M5qC6v3QAAAAi/hug.gif">
        <img src="https://media.tenor.com/vH95e5vW6EIAAAAi/mocha.gif">
    </div>
    <button class="btn" onclick="nextPage(1)">Start Surprise ✨</button>
</div>

<div class="page" id="p2">
    <h1>For You... 🎁</h1>
    <div class="video-container">
        <video id="v1" controls onplay="music(false)" onpause="music(true)">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4" type="video/mp4">
        </video>
    </div>
    <button class="btn" onclick="nextPage(2)">Next Surprise ➡</button>
</div>

<div class="page" id="p3">
    <h1>My Heart to Yours 💌</h1>
    <div class="letter-container">
        <p><b>Jaaneman,</b></p>
        <p>Happy Anniversary! Is poore saal mein tumne mujhe jitni khushiyan di hain, main unhe lafzon mein bayaan nahi kar sakta. Tum mere liye sirf meri partner nahi, meri duniya ho.</p>
        <p>Mujhe yaad hai hamari wo chhoti baatein, wo ladaiyan, aur wo pyaara sa waqt jo humne saath bitaya. Main hamesha tumhare saath rehna chahta hoon. (Scroll karo...)</p>
        <p>I love you more than everything! ❤️</p>
    </div>
    <button class="btn" onclick="nextPage(3)">See More ✨</button>
</div>

<div class="page" id="p4">
    <h1>Our Memories 📸</h1>
    <div class="slider" onclick="slide()">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png" class="show">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466437297821192326/Screenshot_2025-07-21-03-45-44-645_com.instagram.android.jpg">
        <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png">
    </div>
    <p style="margin-top:10px; font-size:0.8rem;">Tap photo to swipe</p>
    <button class="btn" onclick="nextPage(4)">Final Surprise 🌹</button>
</div>

<div class="page" id="p5">
    <h1>The Last One... ❤️</h1>
    <div class="video-container">
        <video id="v2" controls onplay="music(false)" onpause="music(true)">
            <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448575633555579/lv_7335708490083650837_202446.mp4" type="video/mp4">
        </video>
    </div>
    <p>I Love You Forever!</p>
</div>

<script>
    const audio = document.getElementById('bgMusic');
    
    function music(play) {
        if(play) audio.play();
        else audio.pause();
    }

    function nextPage(current) {
        // Music start on first click
        if(current === 1) music(true);
        
        // Hide current, show next
        document.getElementById('p' + current).classList.remove('active');
        document.getElementById('p' + (current + 1)).classList.add('active');
        
        // Stop any playing video
        const vids = document.querySelectorAll('video');
        vids.forEach(v => { v.pause(); v.currentTime = 0; });
        music(true);
    }

    let slideIndex = 0;
    function slide() {
        const imgs = document.querySelectorAll('.slider img');
        imgs[slideIndex].classList.remove('show');
        slideIndex = (slideIndex + 1) % imgs.length;
        imgs[slideIndex].classList.add('show');
    }

    // Floating Hearts
    setInterval(() => {
        const h = document.createElement('div');
        h.innerHTML = '❤️';
        h.className = 'heart';
        h.style.left = Math.random() * 100 + 'vw';
        h.style.top = '100vh';
        document.body.appendChild(h);
        setTimeout(() => h.remove(), 4000);
    }, 400);
</script>

</body>
</html>
