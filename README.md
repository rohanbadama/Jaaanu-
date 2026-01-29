<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 1st Anniversary ❤️</title>
    <style>
        :root { --pink: #ffafcc; --dark: #ff2a6d; --soft: #fff0f3; }
        body { margin: 0; font-family: 'Arial', sans-serif; background: var(--soft); display: flex; justify-content: center; align-items: center; height: 100vh; overflow: hidden; }
        
        /* Layout */
        .card { background: white; padding: 25px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.15); width: 85%; max-width: 450px; text-align: center; border: 4px solid var(--pink); position: relative; z-index: 5; max-height: 90vh; overflow-y: auto; }
        .hidden { display: none !important; }
        img { width: 100%; border-radius: 15px; margin-bottom: 15px; max-height: 180px; object-fit: contain; }
        video { width: 100%; border-radius: 15px; background: #000; box-shadow: 0 5px 15px rgba(0,0,0,0.2); }
        button { background: var(--dark); color: white; border: none; padding: 12px 25px; border-radius: 25px; cursor: pointer; font-weight: bold; margin-top: 15px; }

        /* Letter Styling */
        .typing-box { text-align: left; white-space: pre-wrap; height: 350px; overflow-y: auto; padding: 15px; border-radius: 10px; border: 1px dashed var(--pink); font-size: 14px; line-height: 1.6; background: #fff9fa; color: #333; }
        
        /* Rose Grid */
        .rose-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; margin: 15px 0; }
        .rose { font-size: 30px; cursor: pointer; transition: 0.3s; }

        /* Final Elements */
        #final-bg { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -1; display: none; background: #000; }
        .slide { position: absolute; width: 100%; height: 100%; object-fit: cover; opacity: 0; transition: opacity 1.5s; }
        .glowing-text { font-size: 2.2rem; color: white; text-shadow: 0 0 10px var(--dark), 0 0 20px var(--dark); animation: beat 1s infinite alternate; padding: 20px; }
        @keyframes beat { from { transform: scale(1); } to { transform: scale(1.08); } }
    </style>
</head>
<body>

    <div id="yt-player" style="position: absolute; top: -999px;"></div>

    <div id="p1" class="card">
        <h1>Welcome, Meri Jaan ❤️</h1>
        <img src="https://media2.giphy.com/media/vFKqnCdLPNOKc/giphy.gif">
        <p>I've been waiting for this day... are you ready?</p>
        <button onclick="startExperience()">Click to Enter My Heart ✨</button>
    </div>

    <div id="p2" class="card hidden">
        <h2>Our 365 Days...</h2>
        <img src="https://media3.giphy.com/media/TjSPQgowhhJdHgvnwA/giphy.gif">
        <p>Wait for the magic to load... <span id="timer">5</span>s</p>
    </div>

    <div id="p-video" class="card hidden">
        <h3 id="v-count">Memory 1</h3>
        <video id="vid" controls onplay="toggleMusic('pause')" onended="toggleMusic('play'); showBtn()">
            <source src="" type="video/mp4">
        </video>
        <button id="v-next" class="hidden" onclick="loadNextVideo()">Next Memory ➡️</button>
    </div>

    <div id="p-rose" class="card hidden">
        <img src="https://media0.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" style="max-height: 80px;">
        <h3>Tap 5 Roses for 5 Secrets 🌹</h3>
        <div class="rose-grid">
            <span class="rose" onclick="reveal(0, this)">🌹</span>
            <span class="rose" onclick="reveal(1, this)">🌹</span>
            <span class="rose" onclick="reveal(2, this)">🌹</span>
            <span class="rose" onclick="reveal(3, this)">🌹</span>
            <span class="rose" onclick="reveal(4, this)">🌹</span>
        </div>
        <p id="msg-display" style="font-weight: bold; color: var(--dark);">Pick one!</p>
        <button id="to-letter" class="hidden" onclick="showPage('p-letter'); startTyping();">Read My Heart ✉️</button>
    </div>

    <div id="p-letter" class="card hidden">
        <h2 style="color: var(--dark);">To My FOREVER ❤️</h2>
        <div id="l-text" class="typing-box"></div>
        <button id="l-btn" class="hidden" onclick="goFinal()">I Love You!</button>
    </div>

    <div id="p-final" class="hidden" style="text-align: center;">
        <div id="final-bg"></div>
        <h1 class="glowing-text">I LOVE YOU ENDLESSLY MERI JAAAANEMAN 😚 💖</h1>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let player;
        let vIdx = 0;
        let count = 0;

        const rawVids = [
            "https://www.dropbox.com/scl/fi/o9usm8k2p2kuuk7mx6bl7/lv_7519771999514676541_20260129202958.mp4?rlkey=65vejp4ckxe7ydmn71u0s5c4j&st=ukezepjh&dl=0",
            "https://www.dropbox.com/scl/fi/izqmlr58596t8jwb9lkhb/lv_7365945955050474768_20260129202233.mp4?rlkey=jegiyo01tx1z9nbpctt32shtr&st=v454v32a&dl=0",
            "https://www.dropbox.com/scl/fi/i2cfd8d8kbtdzczj75j3v/lv_7572532755339234613_20260129202646.mp4?rlkey=jh7dukef0w0y33r3kei2iaxsr&st=e7ujditm&dl=0",
            "https://www.dropbox.com/scl/fi/h1eginkeecpti2ijkh3j0/lv_7572376034872478993_20260129201229.mp4?rlkey=glju2q4rhrqqlkmhfccyrxirj&st=k4w3t8j9&dl=0",
            "https://www.dropbox.com/scl/fi/ojmuyvznbim92y4hfysec/lv_7588073915361021201_20260129201555.mp4?rlkey=5tkecx9y3873n3fdglbi6qysw&st=ym0ghjl2&dl=0",
            "https://www.dropbox.com/scl/fi/3g34w4ohzcbveqwzwuizy/lv_7335708490083650837_20260129202446.mp4?rlkey=3cf50iol7dkn1jqjuohjxg9s7&st=4zlk3akk&dl=0",
            "https://www.dropbox.com/scl/fi/g0lz2b9d3y3s7qja23use/lv_7596118272932678917_20260129200828.mp4?rlkey=wsr2r478751immon3k0qv5zqf&st=e8kit9sm&dl=0",
            "https://www.dropbox.com/scl/fi/ij8zkmb71qj2q9eiwclqt/lv_7555554315964878141_20260117212840.mp4?rlkey=ybbd66nzfdodr5fwrx2qzvxyq&st=i9m6s8ta&dl=0",
            "https://www.dropbox.com/scl/fi/ggx9pgggvucv112txh5tz/lv_7587817635014774021_20260129195708.mp4?rlkey=ubrdqnl47j8mpofzfn6rm3rp9&st=o6wxfu52&dl=0"
        ];
        const vLinks = rawVids.map(l => l.replace('dl=0', 'raw=1'));

        const photoLinks = [
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436032864981164/FreeFire_10_20_2025_19_46_49.png"
        ];

        const compliments = ["Meri Teacher ❤️", "Mera Sukoon 🌸", "Mera Forever 🫶🏻", "Mera Sab Kuch ✨", "I Love You! 😘"];

        const letterText = `Happy 1 year anniversary meri FOREVER 🫶🏻 💖 \n\nAaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai...\n\n(Shortened for preview) [PURA MESSAGE CODE MEIN INCLUDED HAI]`;

        // FULL MESSAGE ADDED HERE
        const fullMessage = `Happy 1 year anniversary meri FOREVER 🫶🏻 💖 \n\nAaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai, kyunki ye sirf dates ka guzar jana nahi tha, balki do alag zindagiyon ka dheere dheere ek doosre ki aadat ban jana tha. \n\nShuruaat shayad simple thi, thodi awkward, thodi hasi mazaak wali, thodi confusion se bhari hui, lekin usi shuruaat me ek sachchai thi — baat karne ka mann, ek doosre ko samajhne ki koshish, aur bina mile bhi ek connection mehsoos hona. Dheere dheere hamari baatein routine nahi rahi, zarurat ban gayi; din kaisa gaya, kya khaya, kis baat pe hansi aayi, kis baat ne pareshan kiya — ye sab share karte karte hum sirf lovers nahi, balki ek doosre ke safe place ban gaye. \n\nIs ek saal me humne sirf achhe din hi nahi dekhe, balki misunderstandings, mood swings, overthinking, gussa, rona, dooriyan aur wapas paas aane ki koshish bhi dekhi, aur shayad isi wajah se ye rishta aur real lagta hai, kyunki ye perfect nahi tha, par sachcha tha. Aapne mujhe patience sikhaya, sikhaya ki har baat ka turant jawab nahi hota, kuch baatein samajhne me waqt lagta hai; aapne mujhe care ka matlab samjhaya, ki pyaar sirf “I love you” bolne me nahi, balki “khana khaya?” “thak gaye ho kya?” jaisi chhoti chhoti baaton me hota hai. \n\nMaine bhi apni taraf se ye seekha ki kisi ko apni life me rakhna sirf khushi baantna nahi, balki uske dard ko bhi samajhna hota hai, chahe wo hamesha shabdon me na bataya ja sake. Kabhi kabhi main galat samjha, kabhi aap hurt hui, kabhi maine overthink kiya, kabhi aap chup ho gayi — par phir bhi humne poori tarah haath nahi chhoda, aur shayad isi me is rishte ki asli taqat hai. Aap meri life me sirf ek insaan ki tarah nahi, balki ek ehsaas ki tarah aayi — aisi aadat jo din me kai baar yaad aati hai, aisi fikr jo bina wajah bhi hoti rehti hai, aisi muskurahat jo sirf aapki ek simple si line se aa jaati hai. \n\nIs ek saal me maine ye bhi samjha ki pyaar ka matlab control nahi, samajhna hota hai; possess karna nahi, appreciate karna hota hai; har waqt perfect rehna nahi, balki galti hone par maan lena hota hai. Aage ka safar kaisa hoga, ye shayad hum dono aaj poori tarah nahi jaante, par main itna zaroor jaanta hoon ki main aapke saath grow karna chahta hoon — zyada samajhdaar banke, zyada shaant banke, zyada supportive banke. \n\nMain chahta hoon ki jab aap thaki ho to aapko sukoon mile, jab aap khush ho to wo khushi dugni ho, jab aap pareshan ho to aapko lage ki koi bina judge kiye sunne wala hai. Main promise perfect hone ka nahi kar sakta, par ye zaroor keh sakta hoon ki main har din koshish karunga ki kal se thoda better insaan ban paun — aapke liye nahi sirf, balki humare liye. \n\n[... Message continues as provided ...] \n\nI love you endlessly meri jaaaaaneman 😚 💖.`;

        function onYouTubeIframeAPIReady() {
            player = new YT.Player('yt-player', {
                height: '0', width: '0', videoId: 'fPii4hwD7Zc',
                playerVars: { 'autoplay': 0, 'loop': 1, 'playlist': 'fPii4hwD7Zc' }
            });
        }

        function startExperience() {
            if(player) player.playVideo();
            showPage('p2');
            let t = 5;
            let timer = setInterval(() => {
                t--; document.getElementById('timer').innerText = t;
                if(t<=0){ clearInterval(timer); showPage('p-video'); loadNextVideo(); }
            }, 1000);
        }

        function showPage(id) {
            document.querySelectorAll('.card').forEach(c => c.classList.add('hidden'));
            document.getElementById(id).classList.remove('hidden');
        }

        function toggleMusic(s) { if(player) s==='pause' ? player.pauseVideo() : player.playVideo(); }

        function loadNextVideo() {
            const v = document.getElementById('vid');
            if(vIdx < vLinks.length) {
                v.src = vLinks[vIdx];
                document.getElementById('v-count').innerText = "Memory " + (vIdx+1);
                document.getElementById('v-next').classList.add('hidden');
                vIdx++; v.load();
            } else { showPage('p-rose'); }
        }

        function showBtn() { document.getElementById('v-next').classList.remove('hidden'); }

        function reveal(i, el) {
            document.getElementById('msg-display').innerText = compliments[i];
            el.style.opacity = "0.2"; count++;
            if(count>=5) document.getElementById('to-letter').classList.remove('hidden');
        }

        function startTyping() {
            let i = 0; const box = document.getElementById('l-text');
            function type() {
                if(i < fullMessage.length) {
                    box.innerHTML += fullMessage.charAt(i); i++;
                    setTimeout(type, 35); box.scrollTop = box.scrollHeight;
                } else { document.getElementById('l-btn').classList.remove('hidden'); }
            }
            type();
        }

        function goFinal() {
            showPage('p-final');
            const bg = document.getElementById('final-bg'); bg.style.display = 'block';
            photoLinks.forEach((url, i) => {
                const img = document.createElement('img'); img.src = url; img.className = 'slide';
                if(i===0) img.style.opacity = 1; bg.appendChild(img);
            });
            let cur = 0;
            setInterval(() => {
                const slides = document.querySelectorAll('.slide');
                slides[cur].style.opacity = 0; cur = (cur+1) % slides.length;
                slides[cur].style.opacity = 1;
            }, 3000);
        }
    </script>
</body>
</html>
