<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>1 Year of Us ❤️</title>
    <style>
        :root { --p: #ff4d6d; --s: #ff85a1; --bg: #0a0a0a; }
        body { margin: 0; background: var(--bg); font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; color: white; overflow-x: hidden; }
        .screen { min-height: 100vh; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 20px; box-sizing: border-box; text-align: center; display: none; }
        .active { display: flex; }
        
        /* Glass UI */
        .glass { background: rgba(255, 255, 255, 0.1); backdrop-filter: blur(10px); border: 1px solid rgba(255,255,255,0.2); border-radius: 20px; padding: 25px; width: 90%; max-width: 500px; box-shadow: 0 10px 30px rgba(0,0,0,0.5); }
        
        button { background: var(--p); color: white; border: none; padding: 12px 25px; border-radius: 30px; font-weight: bold; cursor: pointer; margin-top: 15px; box-shadow: 0 4px 15px var(--p); }
        
        /* Letter Box */
        .letter-scroll { text-align: left; height: 350px; overflow-y: auto; background: rgba(0,0,0,0.3); padding: 15px; border-radius: 10px; font-size: 15px; line-height: 1.7; white-space: pre-wrap; border-left: 4px solid var(--p); }

        /* Video Styling */
        video { width: 100%; border-radius: 15px; margin-top: 10px; border: 2px solid var(--s); }

        /* Slideshow */
        .full-img { position: fixed; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: -1; opacity: 0; transition: opacity 1.5s; }
        .overlay { position: absolute; z-index: 10; text-align: center; width: 100%; }
    </style>
</head>
<body>

    <div id="player" style="position: absolute; top: -999px;"></div>

    <div id="scr-1" class="screen active">
        <div class="glass">
            <h1>Happy 1st Anniversary! ❤️</h1>
            <img src="https://media2.giphy.com/media/vFKqnCdLPNOKc/giphy.gif" width="150">
            <p>Ready to relive our beautiful journey?</p>
            <button onclick="startApp()">Yes, Take Me In! ✨</button>
        </div>
    </div>

    <div id="scr-game" class="screen">
        <div class="glass">
            <h2>Game: Catch the Love! ❤️</h2>
            <p>Quick! Tap 10 floating hearts to unlock the videos!</p>
            <div id="game-area" style="height: 200px; position: relative; overflow: hidden; background: rgba(0,0,0,0.2); border-radius: 15px;"></div>
            <h3 id="score">Score: 0</h3>
        </div>
    </div>

    <div id="scr-vid" class="screen">
        <div class="glass">
            <h2 id="v-title">Memory #1</h2>
            <video id="v-player" controls>
                <source src="" type="video/mp4">
            </video>
            <div style="display:flex; gap:10px; justify-content:center;">
                <button onclick="nextVideo()">Skip/Next Memory ➡️</button>
            </div>
        </div>
    </div>

    <div id="scr-letter" class="screen">
        <div class="glass" style="max-width: 600px;">
            <h2>From My Heart 🫶🏻</h2>
            <div class="letter-scroll" id="letter-content"></div>
            <button id="final-btn" class="hidden" onclick="goFinal()" style="display:none;">See Final Surprise ✨</button>
        </div>
    </div>

    <div id="scr-final" class="screen">
        <div id="slides-container"></div>
        <div class="overlay">
            <h1 style="font-size: 3rem; text-shadow: 0 0 20px red;">I LOVE YOU FOREVER ❤️</h1>
            <p style="font-size: 1.5rem;">Happy 1st Anniversary, Meri Jaan!</p>
        </div>
    </div>

    <script src="https://www.youtube.com/iframe_api"></script>
    <script>
        let yt, vIdx = 0, score = 0;
        
        // 5 BIGGEST VIDEOS
        const vLinks = [
            "https://www.dropbox.com/scl/fi/o9usm8k2p2kuuk7mx6bl7/lv_7519771999514676541_20260129202958.mp4?rlkey=65vejp4ckxe7ydmn71u0s5c4j&st=ukezepjh&raw=1",
            "https://www.dropbox.com/scl/fi/izqmlr58596t8jwb9lkhb/lv_7365945955050474768_20260129202233.mp4?rlkey=jegiyo01tx1z9nbpctt32shtr&st=v454v32a&raw=1",
            "https://www.dropbox.com/scl/fi/i2cfd8d8kbtdzczj75j3v/lv_7572532755339234613_20260129202646.mp4?rlkey=jh7dukef0w0y33r3kei2iaxsr&st=e7ujditm&raw=1",
            "https://www.dropbox.com/scl/fi/h1eginkeecpti2ijkh3j0/lv_7572376034872478993_20260129201229.mp4?rlkey=glju2q4rhrqqlkmhfccyrxirj&st=k4w3t8j9&raw=1",
            "https://www.dropbox.com/scl/fi/ojmuyvznbim92y4hfysec/lv_7588073915361021201_20260129201555.mp4?rlkey=5tkecx9y3873n3fdglbi6qysw&st=ym0ghjl2&raw=1"
        ];

        const photos = [
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png",
            "https://cdn.discordapp.com/attachments/1421877888877203559/1466436032864981164/FreeFire_10_20_2025_19_46_49.png"
        ];

        const fullLetter = `Happy 1 year anniversary meri FOREVER 🫶🏻 💖 \nAaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai, kyunki ye sirf dates ka guzar jana nahi tha, balki do alag zindagiyon ka dheere dheere ek doosre ki aadat ban jana tha. Shuruaat shayad simple thi, thodi awkward, thodi hasi mazaak wali, thodi confusion se bhari hui, lekin usi shuruaat me ek sachchai thi — baat karne ka mann, ek doosre ko samajhne ki koshish, aur bina mile bhi ek connection mehsoos hona. Dheere dheere hamari baatein routine nahi rahi, zarurat ban gayi; din kaisa gaya, kya khaya, kis baat pe hansi aayi, kis baat ne pareshan kiya — ye sab share karte karte hum sirf lovers nahi, balki ek doosre ke safe place ban gaye. Is ek saal me humne sirf achhe din hi nahi dekhe, balki misunderstandings, mood swings, overthinking, gussa, rona, dooriyan aur wapas paas aane ki koshish bhi dekhi, aur shayad isi wajah se ye rishta aur real lagta hai, kyunki ye perfect nahi tha, par sachcha tha. Aapne mujhe patience sikhaya, sikhaya ki har baat ka turant jawab nahi hota, kuch baatein samajhne me waqt lagta hai; aapne mujhe care ka matlab samjhaya, ki pyaar sirf “I love you” bolne me nahi, balki “khana khaya?” “thak gaye ho kya?” jaisi chhoti chhoti baaton me hota hai. Maine bhi apni taraf se ye seekha ki kisi ko apni life me rakhna sirf khushi baantna nahi, balki uske dard ko bhi samajhna hota hai, chahe wo hamesha shabdon me na bataya ja sake. Kabhi kabhi main galat samjha, kabhi aap hurt hui, kabhi maine overthink kiya, kabhi aap chup ho gayi — par phir bhi humne poori tarah haath nahi chhoda, aur shayad isi me is rishte ki asli taqat hai. Aap meri life me sirf ek insaan ki tarah nahi, balki ek ehsaas ki tarah aayi — aisi aadat jo din me kai baar yaad aati hai, aisi fikr jo bina wajah bhi hoti rehti hai, aisi muskurahat jo sirf aapki ek simple si line se aa jaati hai. Is ek saal me maine ye bhi samjha ki pyaar ka matlab control nahi, samajhna hota hai; possess karna nahi, appreciate karna hota hai; har waqt perfect rehna nahi, balki galti hone par maan lena hota hai. Aage ka safar kaisa hoga, ye shayad hum dono aaj poori tarah nahi jaante, par main itna zaroor jaanta hoon ki main aapke saath grow karna chahta hoon — zyada samajhdaar banke, zyada shaant banke, zyada supportive banke. Main chahta hoon ki jab aap thaki ho to aapko sukoon mile, jab aap khush ho to wo khushi dugni ho, jab aap pareshan ho to aapko lage ki koi bina judge kiye sunne wala hai. Main promise perfect hone ka nahi kar sakta, par ye zaroor keh sakta hoon ki main har din koshish karunga ki kal se thoda better insaan ban paun — aapke liye nahi sirf, balki humare liye. Ye ek saal sirf memories ka collection nahi, balki ek foundation tha — trust ka, care ka, emotional connection ka. Aage bhi misunderstandings aayengi, mood swings aayenge, busy din aayenge, par agar hum baat karna nahi chhodenge aur ek doosre ko enemy nahi samjhenge, to koi bhi problem humse badi nahi hogi. Aap meri zindagi me ek chapter nahi, balki ek aisi kahani ho jo abhi likhi ja rahi hai, dheere dheere, patience ke saath, feelings ke saath. Aaj ke din bas itna kehna hai ki jo bhi tha, jaisa bhi tha, ye saal mere liye special tha kyunki isme aap thi — aapki awaaz, aapka tareeka, aapka gussa, aapka care, sab kuch. Aur agar aap saath ho, to main aage ke saalon ko bhi isi tarah sambhal ke chalna chahta hoon — respect ke saath, loyalty ke saath, aur us pyaar ke saath jo shor se nahi, par ehsaas se mehsoos hota hai.\n\nJab main aapke baare me sochta hoon na, to mujhe sabse pehle ye feel hota hai ki meri zindagi me jo bhi softness, jo bhi emotional depth, jo bhi sachcha care aaya hai, wo kahin na kahin aapse hi shuru hota hai, kyunki aap sirf ek insaan nahi ho, aap ek feeling ho jo dheere dheere meri aadat ban gayi. Aapki baat karne ka tareeka, aapka hasna, aapka gussa hona, aapka chup ho jana, even aapka “thik hu” bolne ka andaaz bhi mere liye alag hi importance rakhta hai, kyunki main aapko sirf sunta nahi, mehsoos karta hoon. Aap shayad realize bhi nahi karti ki aapki choti choti cheezein mere din pe kitna effect dalti hain — aapka ek normal sa message bhi mere mood ko theek kar deta hai, aapka thoda sa upset tone mujhe andar se restless kar deta hai, aur aapki khushi genuinely mere liye relief jaisi hoti hai. Mujhe aapse baat karne ke liye kisi special topic ki zarurat nahi hoti, kyunki aap khud hi mere liye topic ho, aapki presence hi kaafi hoti hai. Aapne shayad casually meri life me entry li hogi, par aaj aap meri life ka sabse serious, sabse real, aur sabse precious part ho. Mujhe aapke alawa kisi aur se koi matlab nahi hai, na emotionally, na mentally, kyunki jo connection mujhe aapse feel hota hai wo na replace ho sakta hai na compare. Aapki problems mere liye “aapki” nahi rehti, wo automatically “hamari” lagne lagti hain; aapka stress mujhe disturb karta hai, aapki health ki tension mujhe apni lagti hai, aur aapki thakan dekh ke dil karta hai kaash main kisi tarah aapko thoda sa sukoon de paun. Aap strong ho, par phir bhi aapki vulnerability mujhe aur zyada close feel karwati hai, kyunki mujhe lagta hai ki mujhe aapka khayal rakhna hai, bina aapko change kiye, bina aapko control kiye, bas aapke saath khade rehkar. Aap perfect nahi ho — aur shayad isi liye itni real ho, itni apni lagti ho. Aap jab overthink karti ho, jab mood swing hota hai, jab bina wajah irritate ho jati ho, tab bhi main aapko kam nahi, aur zyada pyaar karta hoon, kyunki wo sab aapka part hai, aur mujhe aap poori chahiye, sirf aapke easy wale din nahi. Aapne mujhe care ka actual matlab samjhaya — bina bade gestures ke, bina show off ke, bas presence se, bas is ehsaas se ki koi hai jo sach me matter karta hai. Aapki respect mere dil me itni naturally hai ki mujhe kabhi force nahi karna padta aapko value dene ke liye, wo khud hi feel hoti hai, har baat me, har soch me. Main jab future ke baare me sochta hoon to mujhe koi perfect picture nahi dikhti, mujhe bas aap dikhti ho — kabhi haste hue, kabhi thodi si naraz, kabhi thaki hui, par mere saath. Mujhe aapki aadat si ho gayi hai, par ye aadat unhealthy nahi lagti, ye sukoon wali aadat lagti hai, jaise din ke end me ghar wapas aana. Aap meri life me ho isliye main apne aap ko thoda better banana chahta hoon, thoda zyada patient, thoda zyada samajhdaar, thoda zyada worthy of you. Mujhe aapki har choti baat important lagti hai — aapne khana khaya ya nahi, aaj aapka mood kaisa hai, aap thak to nahi gayi, aapko kis baat ne hasaaya — ye sab mere liye random details nahi, ye sab meri care ke reasons hain. Aap meri priority ho bina mujhe loud hone ki zarurat pade, bina mujhe duniya ko prove karne ki zarurat pade. Jo jagah aapne meri life me le li hai na, waha ab koi aur aa bhi nahi sakta, kyunki wo jagah banayi hi aapne hai, apne tareeke se, apni presence se, apni reality se. Main aapko sirf isliye pyaar nahi karta kyunki aap meri ho, main aapko isliye pyaar karta hoon kyunki aap “aap” ho — jaisi ho waisi, bina filter ke, bina pretend kiye. Aur aaj main bas itna kehna chahta hoon ki chahe din simple ho ya complicated, baatein zyada ho ya kam, mood acha ho ya off, meri feelings aapke liye constant hain, steady hain, aur dil se hain. Aap meri choice nahi, meri clarity ho. I love you endlessly meri jaaaaaneman 😚 💖 .`;

        function onYouTubeIframeAPIReady() {
            yt = new YT.Player('player', { height: '0', width: '0', videoId: 'fPii4hwD7Zc', playerVars: { 'loop': 1, 'playlist': 'fPii4hwD7Zc' } });
        }

        function switchScr(id) {
            document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
            document.getElementById(id).classList.add('active');
        }

        function startApp() { if(yt) yt.playVideo(); switchScr('scr-game'); spawnHearts(); }

        // Game Logic
        function spawnHearts() {
            const area = document.getElementById('game-area');
            const interval = setInterval(() => {
                const h = document.createElement('div');
                h.innerHTML = "❤️";
                h.style.position = "absolute";
                h.style.left = Math.random() * 90 + "%";
                h.style.top = "100%";
                h.style.fontSize = "25px";
                h.style.cursor = "pointer";
                h.style.transition = "top 3s linear";
                area.appendChild(h);
                setTimeout(() => h.style.top = "-20%", 100);
                h.onclick = () => {
                    score++;
                    document.getElementById('score').innerText = "Score: " + score;
                    h.remove();
                    if(score >= 10) { clearInterval(interval); switchScr('scr-vid'); nextVideo(); }
                };
            }, 800);
        }

        // Video Logic
        function nextVideo() {
            const v = document.getElementById('v-player');
            if(vIdx < vLinks.length) {
                v.src = vLinks[vIdx];
                document.getElementById('v-title').innerText = "Memory #" + (vIdx + 1);
                vIdx++;
                v.load();
            } else {
                switchScr('scr-letter');
                startTyping();
            }
        }

        // Letter Logic
        function startTyping() {
            let i = 0;
            const target = document.getElementById('letter-content');
            function type() {
                if(i < fullLetter.length) {
                    target.innerHTML += fullLetter.charAt(i);
                    i++;
                    setTimeout(type, 30);
                    target.scrollTop = target.scrollHeight;
                } else {
                    document.getElementById('final-btn').style.display = "block";
                }
            }
            type();
        }

        // Final Logic (No Black Screen)
        function goFinal() {
            switchScr('scr-final');
            const container = document.getElementById('slides-container');
            photos.forEach((url, index) => {
                const img = document.createElement('img');
                img.src = url;
                img.className = 'full-img';
                if(index === 0) img.style.opacity = 1;
                container.appendChild(img);
            });
            let cur = 0;
            setInterval(() => {
                const imgs = document.querySelectorAll('.full-img');
                if(imgs.length > 0) {
                    imgs[cur].style.opacity = 0;
                    cur = (cur + 1) % imgs.length;
                    imgs[cur].style.opacity = 1;
                }
            }, 3500);
        }
    </script>
</body>
</html>
