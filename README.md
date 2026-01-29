<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 1st Anniversary ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root { --soft-pink: #ffdae0; --deep-pink: #ff4d6d; --glass: rgba(255, 255, 255, 0.85); }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Poppins', sans-serif; }
        body { background: var(--soft-pink); overflow: hidden; height: 100vh; width: 100vw; }

        /* Floating Hearts Animation */
        .heart { position: fixed; color: var(--deep-pink); font-size: 20px; z-index: -1; animation: float 4s linear infinite; opacity: 0; }
        @keyframes float { 0% { transform: translateY(100vh) scale(0); opacity: 1; } 100% { transform: translateY(-10vh) scale(1.5); opacity: 0; } }

        /* Page System */
        .page { display: none; height: 100vh; width: 100vw; justify-content: center; align-items: center; position: absolute; padding: 20px; }
        .active { display: flex; animation: fadeIn 1s ease-in-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

        /* Card Aesthetic */
        .card { background: var(--glass); backdrop-filter: blur(10px); padding: 30px; border-radius: 30px; 
                  box-shadow: 0 15px 35px rgba(255, 77, 109, 0.2); width: 100%; max-width: 450px; 
                  text-align: center; border: 2px solid white; position: relative; max-height: 90vh; overflow-y: auto; }
        
        h1, h2 { font-family: 'Dancing Script', cursive; color: var(--deep-pink); margin-bottom: 15px; font-size: 2rem; }
        .media-frame { border: 6px solid white; border-radius: 20px; overflow: hidden; margin: 15px 0; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        .media-frame img, .media-frame video { width: 100%; display: block; }

        /* Letter Styling (The Scrollable Message) */
        .letter-container { background: #fffcf2; padding: 20px; border-radius: 15px; border-left: 5px solid var(--deep-pink); 
                            text-align: left; font-size: 0.95rem; line-height: 1.6; color: #444; max-height: 400px; 
                            overflow-y: scroll; margin: 15px 0; scrollbar-width: thin; }
        .letter-container::-webkit-scrollbar { width: 5px; }
        .letter-container::-webkit-scrollbar-thumb { background: var(--deep-pink); border-radius: 10px; }

        /* Buttons */
        .btn-group { display: flex; justify-content: center; gap: 15px; margin-top: 15px; }
        .next-btn { background: var(--deep-pink); color: white; border: none; padding: 12px 35px; 
                    border-radius: 50px; cursor: pointer; font-weight: 600; transition: 0.3s; }
        .next-btn:hover { transform: scale(1.05); box-shadow: 0 5px 15px rgba(255, 77, 109, 0.4); }

        /* Game Elements */
        .catch-heart { font-size: 45px; cursor: pointer; position: absolute; transition: 0.2s; z-index: 10; }
        #no-btn { position: relative; }

        /* Photo Slider */
        .slider { display: flex; overflow-x: auto; scroll-snap-type: x mandatory; gap: 10px; border-radius: 15px; }
        .slider img { width: 100%; flex-shrink: 0; scroll-snap-align: center; border-radius: 15px; }
    </style>
</head>
<body>

    <iframe id="audio-player" width="0" height="0" src="" frameborder="0" allow="autoplay"></iframe>

    <div id="hearts-container"></div>

    <main id="app">
        <section class="page active">
            <div class="card">
                <h1>Welcome, My Love ❤️</h1>
                <div class="media-frame">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif?ex=697c9b75&is=697b49f5&hm=baab3586965ae954eaf7d16ad28925e97981fd3fa3ae13ab7970362d2b7ebe04&">
                </div>
                <p>Ek khubsurat safar ki shuruaat...</p>
                <button class="next-btn" onclick="initExperience()">Start Journey</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>Catch My Love! 💖</h2>
                <div id="game-zone" style="height: 200px; position: relative; background: rgba(255,255,255,0.3); border-radius: 15px;">
                    <div id="target" class="catch-heart" onclick="scorePoint()">❤️</div>
                </div>
                <p style="margin-top:10px;">Score: <span id="score">0</span>/10</p>
                <button id="game-next" class="next-btn" style="display:none;" onclick="nextPage()">Aage Badho</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>One for you 🫶🏻💗</h2>
                <div class="media-frame">
                    <video id="v1" controls onplay="pauseMusic()" onended="resumeMusic()">
                        <source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448687809954058/lv_7555554315964878141_20260117212840.mp4?ex=697cc844&is=697b76c4&hm=942bdabac104d84b472af89469de8d1080cd3cfae11d6ab2a68fe158cdb1c83f&" type="video/mp4">
                    </video>
                </div>
                <button class="next-btn" onclick="nextPage()">Next</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>A Letter to My Forever ✉️</h2>
                <div class="letter-container">
                    Happy 1 year anniversary meri FOREVER 🫶🏻 💖 Aaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai, kyunki ye sirf dates ka guzar jana nahi tha, balki do alag zindagiyon ka dheere dheere ek doosre ki aadat ban jana tha. Shuruaat shayad simple thi, thodi awkward, thodi hasi mazaak wali, thodi confusion se bhari hui, lekin usi shuruaat me ek sachchai thi — baat karne ka mann, ek doosre ko samajhne ki koshish, aur bina mile bhi ek connection mehsoos hona. Dheere dheere hamari baatein routine nahi rahi, zarurat ban gayi; din kaisa gaya, kya khaya, kis baat pe hansi aayi, kis baat ne pareshan kiya — ye sab share karte karte hum sirf lovers nahi, balki ek doosre ke safe place ban gaye. Is ek saal me humne sirf achhe din hi nahi dekhe, balki misunderstandings, mood swings, overthinking, gussa, rona, dooriyan aur wapas paas aane ki koshish bhi dekhi, aur shayad isi wajah se ye rishta aur real lagta hai, kyunki ye perfect nahi tha, par sachcha tha. Aapne mujhe patience sikhaya, sikhaya ki har baat ka turant jawab nahi hota, kuch baatein samajhne me waqt lagta hai; aapne mujhe care ka matlab samjhaya, ki pyaar sirf “I love you” bolne me nahi, balki “khana khaya?” “thak gaye ho kya?” jaisi chhoti chhoti baaton me hota hai. Maine bhi apni taraf se ye seekha ki kisi ko apni life me rakhna sirf khushi baantna nahi, balki uske dard ko bhi samajhna hota hai, chahe wo hamesha shabdon me na bataya ja sake. Kabhi kabhi main galat samjha, kabhi aap hurt hui, kabhi maine overthink kiya, kabhi aap chup ho gayi — par phir bhi humne poori tarah haath nahi chhoda, aur shayad isi me is rishte ki asli taqat hai. Aap meri life me sirf ek insaan ki tarah nahi, balki ek ehsaas ki tarah aayi — aisi aadat jo din me kai baar yaad aati hai, aisi fikr jo bina wajah bhi hoti rehti hai, aisi muskurahat jo sirf aapki ek simple si line se aa jaati hai. Is ek saal me maine ye bhi samjha ki pyaar ka matlab control nahi, samajhna hota hai; possess karna nahi, appreciate karna hota hai; har waqt perfect rehna nahi, balki galti hone par maan lena hota hai. Aage ka safar kaisa hoga, ye shayad hum dono aaj poori tarah nahi jaante, par main itna zaroor jaanta hoon ki main aapke saath grow karna chahta hoon — zyada samajhdaar banke, zyada shaant banke, zyada supportive banke. Main chahta hoon ki jab aap thaki ho to aapko sukoon mile, jab aap khush ho to wo khushi dugni ho, jab aap pareshan ho to aapko lage ki koi bina judge kiye sunne wala hai. Main promise perfect hone ka nahi kar sakta, par ye zaroor keh sakta hoon ki main har din koshish karunga ki kal se thoda better insaan ban paun — aapke liye nahi sirf, balki humare liye. Ye ek saal sirf memories ka collection nahi, balki ek foundation tha — trust ka, care ka, emotional connection ka. Aage bhi misunderstandings aayengi, mood swings aayenge, busy din aayenge, par agar hum baat karna nahi chhodenge aur ek doosre ko enemy nahi samjhenge, to koi bhi problem humse badi nahi hogi. Aap meri zindagi me ek chapter nahi, balki ek aisi kahani ho jo abhi likhi ja rahi hai, dheere dheere, patience ke saath, feelings ke saath. Aaj ke din bas itna kehna hai ki jo bhi tha, jaisa bhi tha, ye saal mere liye special tha kyunki isme aap thi — aapki awaaz, aapka tareeka, aapka gussa, aapki care, sab kuch. Aur agar aap saath ho, to main aage ke saalon ko bhi isi tarah sambhal ke chalna chahta hoon — respect ke saath, loyalty ke saath, aur us pyaar ke saath jo shor se nahi, par ehsaas se mehsoos hota hai.
                </div>
                <p style="font-size:0.8rem; color:var(--deep-pink);">[Scroll down to read all]</p>
                <button class="next-btn" onclick="nextPage()">Next Page</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>Our Precious Moments 📸</h2>
                <div class="slider" id="main-slider">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032864981164/FreeFire_10_20_2025_19_46_49.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436033343262720/FreeFire_11_06_2025_17_43_23.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436033917747447/FreeFire_12_15_2025_18_05_48.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436034366799882/FreeFire_12_22_2025_10_44_53.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032407933071/Screenshot_2025-10-30-17-57-27-678_com.instagram.android.jpg?ex=697cbc7b&is=697b6afb&hm=dd2876199b5c244959fd4df9f1745d64d98f13409d606d2bcc5380087eb69080&">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png">
                </div>
                <p style="margin-top:10px;">Swipe to see our memories 👈👉</p>
                <button class="next-btn" onclick="nextPage()">Next</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>Maja Aaya? 😅😚</h2>
                <div class="btn-group">
                    <button class="next-btn" onclick="nextPage()">Yes! 😍</button>
                    <button id="no-btn" class="next-btn" style="background:#888" onmouseover="runAway()">No 😢</button>
                </div>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>Final One 😅😚</h2>
                <div class="media-frame">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466430191994798120/From_KlickPin_CF_Bunny_Sticker_-_Bunny_-_Discover__Share_GIFs___Cute_love_gif_Cute_gif_Love_you_gif.gif">
                </div>
                <div class="letter-container">
                    pehle ye feel hota hai ki meri zindagi me jo bhi softness, jo bhi emotional depth, jo bhi sachcha care aaya hai, wo kahin na kahin aapse hi shuru hota hai, kyunki aap sirf ek insaan nahi ho, aap ek feeling ho jo dheere dheere meri aadat ban gayi. Aapki baat karne ka tareeka, aapka hasna, aapka gussa hona, aapka chup ho jana, even aapka “thik hu” bolne ka andaaz bhi mere liye alag hi importance rakhta hai, kyunki main aapko sirf sunta nahi, mehsoos karta hoon. Aap shayad realize bhi nahi karti ki aapki choti choti cheezein mere din pe kitna effect dalti hain — aapka ek normal sa message bhi mere mood ko theek kar deta hai, aapka thoda sa upset tone mujhe andar se restless kar deta hai, aur aapki khushi genuinely mere liye relief jaisi hoti hai. Mujhe aapse baat karne ke liye kisi special topic ki zarurat nahi hoti, kyunki aap khud hi mere liye topic ho, aapki presence hi kaafi hoti hai. Aapne shayad casually meri life me entry li hogi, par aaj aap meri life ka sabse serious, sabse real, aur sabse precious part ho. Mujhe aapke alawa kisi aur se koi matlab nahi hai, na emotionally, na mentally, kyunki jo connection mujhe aapse feel hota hai wo na replace ho sakta hai na compare. Aapki problems mere liye “aapki” nahi rehti, wo automatically “hamari” lagne lagti hain; aapka stress mujhe disturb karta hai, aapki health ki tension mujhe apni lagti hai, aur aapki thakan dekh ke dil karta hai kaash main kisi tarah aapko thoda sa sukoon de paun. Aap strong ho, par phir bhi aapki vulnerability mujhe aur zyada close feel karwati hai, kyunki mujhe lagta hai ki mujhe aapka khayal rakhna hai, bina aapko change kiye, bina aapko control kiye, bas aapke saath khade rehkar. Aap perfect nahi ho — aur shayad isi liye itni real ho, itni apni lagti ho. Aap jab overthink karti ho, jab mood swing hota hai, jab bina wajah irritate ho jati ho, tab bhi main aapko kam nahi, aur zyada pyaar karta hoon, kyunki wo sab aapka part hai, aur mujhe aap poori chahiye, sirf aapke easy wale din nahi. Aapne mujhe care ka actual matlab samjhaya — bina bade gestures ke, bina show off ke, bas presence se, bas is ehsaas se ki koi hai jo sach me matter karta hai. Aapki respect mere dil me itni naturally hai ki mujhe kabhi force nahi karna padta aapko value dene ke liye, wo khud hi feel hoti hai, har baat me, har soch me. Main jab future ke baare me sochta hoon to mujhe koi perfect picture nahi dikhti, mujhe bas aap dikhti ho — kabhi haste hue, kabhi thodi si naraz, kabhi thaki hui, par mere saath. Mujhe aapke aadat si ho gayi hai, par ye aadat unhealthy nahi lagti, ye sukoon wali aadat lagti hai, jaise din ke end me ghar wapas aana. Aap meri life me ho isliye main apne aap ko thoda better banana chahta hoon, thoda zyada patient, thoda zyada samajhdaar, thoda zyada worthy of you. Mujhe aapki har choti baat important lagti hai — aapne khana khaya ya nahi, aaj aapka mood kaisa hai, aap thak to nahi gayi, aapko kis baat ne hasaaya — ye sab mere liye random details nahi, ye sab meri care ke reasons hain. Aap meri priority ho bina mujhe loud hone ki zarurat pade, bina mujhe duniya ko prove karne ki zarurat pade. Jo jagah aapne meri life me le li hai na, waha ab koi aur aa bhi nahi sakta, kyunki wo jagah banayi hi aapne hai, apne tareeke se, apni presence se, apni reality se. Main aapko sirf isliye pyaar nahi karta kyunki aap meri ho, main aapko isliye pyaar karta hoon kyunki aap “aap” ho — jaisi ho waisi, bina filter ke, bina pretend kiye. Aur aaj main bas itna kehna chahta hoon ki chahe din simple ho ya complicated, baatein zyada ho ya kam, mood acha ho ya off, meri feelings aapke liye constant hain, steady hain, aur dil se hain. Aap meri choice nahi, meri clarity ho. I love you endlessly my jaaaaaneman 😚 💖.
                </div>
                <button class="next-btn" onclick="alert('Happy Anniversary once again, Jaane-man! ❤️')">I Love You ❤️</button>
            </div>
        </section>
    </main>

    <script>
        let pIdx = 0;
        const pages = document.querySelectorAll('.page');
        const audio = document.getElementById('audio-player');
        const songUrl = "https://www.youtube.com/embed/fPii4kwD7Zc?autoplay=1&loop=1&playlist=fPii4kwD7Zc";

        function initExperience() {
            audio.src = songUrl;
            nextPage();
        }

        function nextPage() {
            pages[pIdx].classList.remove('active');
            pIdx++;
            if(pIdx < pages.length) {
                pages[pIdx].classList.add('active');
                handleAudioControl();
            }
        }

        // Catch Heart Game
        let count = 0;
        function scorePoint() {
            count++;
            document.getElementById('score').innerText = count;
            if(count >= 10) {
                document.getElementById('target').style.display = 'none';
                document.getElementById('game-next').style.display = 'inline-block';
            } else {
                let x = Math.random() * 80;
                let y = Math.random() * 80;
                document.getElementById('target').style.left = x + '%';
                document.getElementById('target').style.top = y + '%';
            }
        }

        // Runaway Button
        function runAway() {
            const btn = document.getElementById('no-btn');
            btn.style.position = 'fixed';
            btn.style.left = Math.random() * 80 + 'vw';
            btn.style.top = Math.random() * 80 + 'vh';
        }

        // Audio Logic
        function pauseMusic() { audio.src = ""; }
        function resumeMusic() { audio.src = songUrl; }

        function handleAudioControl() {
            const hasVideo = pages[pIdx].querySelector('video');
            if(hasVideo) { pauseMusic(); } 
            else if(audio.src === "") { resumeMusic(); }
        }

        // Hearts Animation
        setInterval(() => {
            const h = document.createElement('div');
            h.innerHTML = '❤️'; h.className = 'heart';
            h.style.left = Math.random() * 100 + 'vw';
            h.style.animationDuration = (Math.random() * 2 + 3) + 's';
            document.getElementById('hearts-container').appendChild(h);
            setTimeout(() => h.remove(), 5000);
        }, 400);
    </script>
</body>
</html>
