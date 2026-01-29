<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Forever Love ❤️</title>
    <style>
        :root {
            --pink-bg: #fff0f3;
            --dark-pink: #ff4d6d;
            --rose-red: #c9184a;
        }

        body {
            margin: 0; padding: 0;
            background-color: var(--pink-bg);
            font-family: 'Poppins', sans-serif;
            display: flex; justify-content: center; align-items: center;
            height: 100vh; overflow: hidden;
        }

        .container {
            background: white;
            padding: 25px;
            border-radius: 25px;
            box-shadow: 0 15px 40px rgba(255, 77, 109, 0.2);
            width: 90%; max-width: 420px;
            display: none; text-align: center;
            animation: fadeIn 0.8s ease;
            max-height: 90vh; overflow-y: auto;
        }

        .active { display: block; }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

        h1 { color: var(--dark-pink); font-family: 'Dancing Script', cursive; font-size: 1.8rem; margin-bottom: 10px; }
        
        .video-grid {
            display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin: 20px 0;
        }

        video {
            width: 100%; border-radius: 15px; border: 2px solid #ffccd5;
            object-fit: cover; height: 150px;
        }

        button {
            background: var(--dark-pink); color: white; border: none;
            padding: 12px 30px; border-radius: 50px; cursor: pointer;
            font-weight: bold; transition: 0.3s; margin-top: 15px;
            box-shadow: 0 4px 15px rgba(255, 77, 109, 0.3);
        }

        button:hover { background: var(--rose-red); transform: translateY(-3px); }

        .rose-box { display: flex; justify-content: center; gap: 20px; font-size: 50px; margin: 20px 0; }
        .rose { cursor: pointer; transition: 0.3s; }
        .rose:active { transform: scale(0.8); }

        .letter-content {
            text-align: left; background: #fffcf2; border: 1px dashed var(--dark-pink);
            padding: 25px; font-style: italic; color: #444; line-height: 1.8;
            font-size: 0.9rem; border-radius: 15px; margin-top: 15px;
        }

        .cat-img { width: 120px; }
        #msg-display { font-weight: 600; color: var(--rose-red); min-height: 40px; margin-top: 10px; font-size: 0.9rem; }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;600&display=swap" rel="stylesheet">
</head>
<body>

    <div id="page1" class="container active">
        <h1>Happy Rose Day, Baby 🌹</h1>
        <img src="https://media.tenor.com/26_G9X5K6v0AAAAi/peach-cat.gif" class="cat-img">
        <p>A rose for the person who makes my world more beautiful just by being in it. Ready for a little journey?</p>
        <button onclick="nextPage(2)">Open Our Memories ❤️</button>
    </div>

    <div id="page2" class="container">
        <h1>Our Love Moments ❤️</h1>
        <div class="video-grid">
            <video autoplay muted loop playsinline><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336738921152542/VID_20260120_100024_122.mp4?ex=697c6001&is=697b0e81&hm=71f7b5bb1d547aec732cf86c204c5bb204e722a3579d5b008cbcad5f353547d0&"></video>
            <video autoplay muted loop playsinline><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336737633501295/VID_20260120_100036_661.mp4?ex=697c6001&is=697b0e81&hm=846479f1120cb7e4ca96d277954dffd56355536acaff1f434164a6b98e576d52&"></video>
            <video autoplay muted loop playsinline><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336738317303903/VID_20260120_094507_902.mp4?ex=697c6001&is=697b0e81&hm=a94fb9f91f4bce24d40816d4ec879ca260db39334c60bed894b6af31fbe9e2a9&"></video>
            <video autoplay muted loop playsinline><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466336738627555439/VID_20260120_100019_245.mp4?ex=697c6001&is=697b0e81&hm=9a3fb6c2f85133bbda896d1e32690ad6d3f2cbee8a53bcaf213194d2cefbf171&"></video>
        </div>
        <p>Every second spent with you is like a beautiful dream I never want to wake up from.</p>
        <button onclick="nextPage(3)">Pick a Gift 🌹</button>
    </div>

    <div id="page3" class="container">
        <h1>Pick a Rose</h1>
        <p>One of these roses holds a secret message...</p>
        <div class="rose-box">
            <span class="rose" onclick="reveal('The first rose says: Your smile is my favorite thing in the whole world. Never let it fade! 😊')">🌹</span>
            <span class="rose" onclick="reveal('The second rose says: You are not just my partner, you are my peace and my home. Thank you. ❤️')">🌹</span>
            <span class="rose" onclick="reveal('The third rose says: I promise to stand by you through every storm and every sunshine. Forever. 💍')">🌹</span>
        </div>
        <div id="msg-display"></div>
        <button id="nxt-btn" style="display:none;" onclick="nextPage(4)">Read My Letter 💌</button>
    </div>

    <div id="page4" class="container">
        <h1>From My Heart...</h1>
        <div class="letter-content">
            My Dearest, <br><br>
            As I write this, my heart is overflowing with thoughts of you. I often wonder how my life was so empty before we met. You are the rose that stands out in the garden of my life—the most beautiful and the most fragrant. <br><br>
            Whenever I feel lost, your voice is the only thing that brings me back to peace. Every moment we share, from the long conversations to the comfortable silences, is etched into my soul forever. You've shown me that love isn't just about grand gestures, but about the little things that make life worth living. <br><br>
            I promise to cherish you more with every passing day. I promise to be the shoulder you lean on and the hand you hold through every season of life. You are my soulmate, my best friend, and my entire universe. I can't imagine a single day without your light. <br><br>
            Thank you for being mine and for making me the luckiest person alive. I promise to keep our love blooming, forever and always. <br><br>
            <b>Always Yours, ❤️</b>
        </div>
        <button onclick="nextPage(5)">One Final Note 🌸</button>
    </div>

    <div id="page5" class="container">
        <h1>I Love You!</h1>
        <img src="https://media.tenor.com/it76yY9_97wAAAAi/peach-and-goma-peach-goma.gif" class="cat-img">
        <p>Thank you for being my constant bloom. Wishing you a day as beautiful as your soul.</p>
        <p style="font-size: 1.2rem; font-weight: bold; color: var(--dark-pink);">Happy Rose Day Once Again! 🌹</p>
        <button onclick="location.reload()">Re-play Our Story ❤️</button>
    </div>

    <script>
        let count = 0;
        function nextPage(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('page'+n).classList.add('active');
        }
        function reveal(m) {
            document.getElementById('msg-display').innerText = m;
            count++;
            if(count >= 3) document.getElementById('nxt-btn').style.display = 'inline-block';
        }
    </script>
</body>
</html>
