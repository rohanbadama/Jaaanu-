<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our 1st Anniversary | My Forever ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root { --soft-pink: #ffdae0; --deep-pink: #ff4d6d; --glass: rgba(255, 255, 255, 0.9); }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Poppins', sans-serif; }
        body { background: var(--soft-pink); overflow: hidden; height: 100vh; width: 100vw; }

        /* Floating Hearts */
        .heart { position: fixed; color: var(--deep-pink); font-size: 20px; z-index: -1; animation: float 4s linear infinite; opacity: 0; }
        @keyframes float { 0% { transform: translateY(100vh) scale(0); opacity: 1; } 100% { transform: translateY(-10vh) scale(1.5); opacity: 0; } }

        /* Section Logic */
        .page { display: none; height: 100vh; width: 100vw; justify-content: center; align-items: center; position: absolute; padding: 20px; overflow-y: auto; }
        .active { display: flex; animation: fadeIn 0.8s ease-in-out; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* Elegant Card Look */
        .card { background: var(--glass); backdrop-filter: blur(10px); padding: 25px; border-radius: 25px; 
                  box-shadow: 0 15px 35px rgba(255, 77, 109, 0.2); width: 100%; max-width: 450px; 
                  text-align: center; border: 2px solid white; position: relative; }
        
        h1, h2 { font-family: 'Dancing Script', cursive; color: var(--deep-pink); margin-bottom: 10px; }
        .media-frame { border: 4px solid white; border-radius: 15px; overflow: hidden; margin: 10px 0; background: #000; }
        .media-frame img, .media-frame video { width: 100%; display: block; max-height: 300px; object-fit: contain; }

        /* Letter Styling - Jaisa tumne manga tha (Full Text) */
        .letter-container { background: #fffcf2; padding: 15px; border-radius: 12px; border-left: 4px solid var(--deep-pink); 
                            text-align: left; font-size: 0.9rem; line-height: 1.5; color: #333; max-height: 350px; 
                            overflow-y: scroll; margin: 10px 0; white-space: pre-wrap; }

        /* Buttons */
        .next-btn { background: var(--deep-pink); color: white; border: none; padding: 10px 30px; 
                    border-radius: 50px; cursor: pointer; font-weight: 600; margin-top: 10px; }

        /* Photo Slider */
        .slider { display: flex; overflow-x: auto; scroll-snap-type: x mandatory; gap: 10px; border-radius: 15px; scrollbar-width: none; }
        .slider::-webkit-scrollbar { display: none; }
        .slider img { width: 100%; flex-shrink: 0; scroll-snap-align: center; border-radius: 15px; height: 250px; object-fit: cover; }

        /* Games */
        .catch-heart { font-size: 40px; cursor: pointer; position: absolute; transition: 0.1s; z-index: 10; }
    </style>
</head>
<body>

    <iframe id="audio-player" width="0" height="0" src="" frameborder="0" allow="autoplay"></iframe>

    <div id="hearts-container"></div>

    <main id="app">
        <section class="page active">
            <div class="card">
                <h1>Happy Anniversary ❤️</h1>
                <div class="media-frame">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif?ex=697c9b75&is=697b49f5&hm=baab3586965ae954eaf7d16ad28925e97981fd3fa3ae13ab7970362d2b7ebe04&">
                </div>
                <p>Welcome to our little world of 365 days...</p>
                <button class="next-btn" onclick="startJourney()">Enter Now 💖</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>Catch 10 Hearts! 💖</h2>
                <div id="game-area" style="height: 180px; position: relative;">
                    <div id="moving-heart" class="catch-heart" onclick="catchHeart()">❤️</div>
                </div>
                <p>Score: <span id="score">0</span>/10</p>
                <button id="g1-next" class="next-btn" style="display:none;" onclick="nextPage()">Aage Chalo</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>One for you 🫶🏻💗</h2>
                <div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448687809954058/lv_7555554315964878141_20260117212840.mp4" type="video/mp4"></video></div>
                <button class="next-btn" onclick="nextPage()">Next</button>
            </div>
        </section>
        <section class="page">
            <div class="card">
                <h2>One more 😚💖</h2>
                <div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448576363233361/lv_7572376034872478993_20260129201229.mp4" type="video/mp4"></video></div>
                <button class="next-btn" onclick="nextPage()">Next</button>
            </div>
        </section>
        <section class="page">
            <div class="card">
                <h2>One more 😚💖</h2>
                <div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448578389217290/lv_7596206565158423861_20260129200129.mp4" type="video/mp4"></video></div>
                <button class="next-btn" onclick="nextPage()">Next</button>
            </div>
        </section>
        <section class="page">
            <div class="card">
                <h2>One more 😚💖</h2>
                <div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577013354598/lv_7591172117144587573_20260129201020.mp4" type="video/mp4"></video></div>
                <button class="next-btn" onclick="nextPage()">Next</button>
            </div>
        </section>
        <section class="page">
            <div class="card">
                <h2>Last one 😅😚</h2>
                <div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4" type="video/mp4"></video></div>
                <button class="next-btn" onclick="nextPage()">Next</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>My Heart To Yours ✉️</h2>
                <div class="letter-container">Happy 1 year anniversary meri FOREVER 🫶🏻 💖 Aaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai, kyunki ye sirf dates ka guzar jana nahi tha, balki do alag zindagiyon ka dheere dheere ek doosre ki aadat ban jana tha. Shuruaat shayad simple thi, thodi awkward, thodi hasi mazaak wali, thodi confusion se bhari hui, lekin usi shuruaat me ek sachchai thi — baat karne ka mann, ek doosre ko samajhne ki koshish, aur bina mile bhi ek connection mehsoos hona. Dheere dheere hamari baatein routine nahi rahi, zarurat ban gayi; din kaisa gaya, kya khaya, kis baat pe hansi aayi, kis baat ne pareshan kiya — ye sab share karte karte hum sirf lovers nahi, balki ek doosre ke safe place ban gaye. Is ek saal me humne sirf achhe din hi nahi dekhe, balki misunderstandings, mood swings, overthinking, gussa, rona, dooriyan aur wapas paas aane ki koshish bhi dekhi, aur shayad isi wajah se ye rishta aur real lagta hai, kyunki ye perfect nahi tha, par sachcha tha. Aapne mujhe patience sikhaya, sikhaya ki har baat ka turant jawab nahi hota, kuch baatein samajhne me waqt lagta hai; aapne mujhe care ka matlab samjhaya, ki pyaar sirf “I love you” bolne me nahi, balki “khana khaya?” “thak gaye ho kya?” jaisi chhoti chhoti baaton me hota hai. Maine bhi apni taraf se ye seekha ki kisi ko apni life me rakhna sirf khushi baantna nahi, balki uske dard ko bhi samajhna hota hai, chahe wo hamesha shabdon me na bataya ja sake. Kabhi kabhi main galat samjha, kabhi aap hurt hui, kabhi maine overthink kiya, kabhi aap chup ho gayi — par phir bhi humne poori tarah haath nahi chhoda, aur shayad isi me is rishte ki asli taqat hai. Aap meri life me sirf ek insaan ki tarah nahi, balki ek ehsaas ki tarah aayi — aisi aadat jo din me kai baar yaad aati hai, aisi fikr jo bina wajah bhi hoti rehti hai, aisi muskurahat jo sirf aapki ek simple si line se aa jaati hai. Is ek saal me maine ye bhi samjha ki pyaar ka matlab control nahi, samajhna hota hai; possess karna nahi, appreciate karna hota hai; har waqt perfect rehna nahi, balki galti hone par maan lena hota hai. Aage ka safar kaisa hoga, ye shayad hum dono aaj poori tarah nahi jaante, par main itna zaroor jaanta hoon ki main aapke saath grow karna chahta hoon — zyada samajhdaar banke, zyada shaant banke, zyada supportive banke. Main chahta hoon ki jab aap thaki ho to aapko sukoon mile, jab aap khush ho to wo khushi dugni ho, jab aap pareshan ho to aapko lage ki koi bina judge kiye sunne wala hai. Main promise perfect hone ka nahi kar sakta, par ye zaroor keh sakta hoon ki main har din koshish karunga ki kal se thoda better insaan ban paun — aapke liye nahi sirf, balki humare liye. Ye ek saal sirf memories ka collection nahi, balki ek foundation tha — trust ka, care ka, emotional connection ka. Aage bhi misunderstandings aayengi, mood swings aayenge, busy din aayenge, par agar hum baat karna nahi chhodenge aur ek doosre ko enemy nahi samjhenge, to koi bhi problem humse badi nahi hogi. Aap meri zindagi me ek chapter nahi, balki ek aisi kahani ho jo abhi likhi ja rahi hai, dheere dheere, patience ke saath, feelings ke saath. Aaj ke din bas itna kehna hai ki jo bhi tha, jaisa bhi tha, ye saal mere liye special tha kyunki isme aap thi — aapki awaaz, aapka tareeka, aapka gussa, aapki care, sab kuch. Aur agar aap saath ho, to main aage ke saalon ko bhi isi tarah sambhal ke chalna chahta hoon — respect ke saath, loyalty ke saath, aur us pyaar ke saath jo shor se nahi, par ehsaas se mehsoos hota hai.</div>
                <button class="next-btn" onclick="nextPage()">Next</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>10 Photos of Us 💖</h2>
                <div class="slider" id="photoSlider">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436030230954035/FreeFire_08_03_2025_12_47_16.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031375999091/IMG_20251010_030632.jpg">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436031917326407/FreeFire_10_19_2025_20_51_10.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032864981164/FreeFire_10_20_2025_19_46_49.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436033343262720/FreeFire_11_06_2025_17_43_23.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436033917747447/FreeFire_12_15_2025_18_05_48.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436034366799882/FreeFire_12_22_2025_10_44_53.png">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436032407933071/Screenshot_2025-10-30-17-57-27-678_com.instagram.android.jpg">
                    <img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466436029279109325/FreeFire_07_15_2025_09_29_24.png">
                </div>
                <p>Swipe/Scroll images 👈👉</p>
                <button class="next-btn" onclick="nextPage()">Next</button>
            </div>
        </section>

        <section class="page">
            <div class="card">
                <h2>Maja Aaya? 😅😚</h2>
                <div style="display: flex; justify-content: space-around; margin-top:20px;">
                    <button class="next-btn" onclick="nextPage()">Yes! 😍</button>
                    <button id="no-btn" class="next-btn" style="background:#888" onmouseover="fly()">No 😢</button>
                </div>
            </div>
        </section>

        <section class="page"><div class="card"><h2>One more 😚💖</h2><div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4" type="video/mp4"></video></div><button class="next-btn" onclick="nextPage()">Next</button></div></section>
        <section class="page"><div class="card"><h2>One more 😚💖</h2><div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4" type="video/mp4"></video></div><button class="next-btn" onclick="nextPage()">Next</button></div></section>
        <section class="page"><div class="card"><h2>One more 😚💖</h2><div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448574396104777/lv_7588073915361021201_20260129201555.mp4" type="video/mp4"></video></div><button class="next-btn" onclick="nextPage()">Next</button></div></section>
        <section class="page"><div class="card"><h2>One more 😚💖</h2><div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448575012671690/lv_7365945955050474768_20260129202233.mp4" type="video/mp4"></video></div><button class="next-btn" onclick="nextPage()">Next</button></div></section>
        <section class="page"><div class="card"><h2>Last one 😅😚</h2><div class="media-frame"><video controls onplay="stopBGM()" onended="playBGM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448573179891743/lv_7519771999514676541_20260129202958.mp4" type="video/mp4"></video></div><button class="next-btn" onclick="nextPage()">Next</button></div></section>

        <section class="page">
            <div class="card">
                <h2>Endlessly Yours ❤️</h2>
                <div class="letter-container">pehle ye feel hota hai ki meri zindagi me jo bhi softness, jo bhi emotional depth, jo bhi sachcha care aaya hai, wo kahin na kahin aapse hi shuru hota hai, kyunki aap sirf ek insaan nahi ho, aap ek feeling ho jo dheere dheere meri aadat ban gayi. Aapki baat karne ka tareeka, aapka hasna, aapka gussa hona, aapka chup ho jana, even aapka “thik hu” bolne ka andaaz bhi mere liye alag hi importance rakhta hai, kyunki main aapko sirf sunta nahi, mehsoos karta hoon. Aap shayad realize bhi nahi karti ki aapki choti choti cheezein mere din pe kitna effect dalti hain — aapka ek normal sa message bhi mere mood ko theek kar deta hai, aapka thoda sa upset tone mujhe andar se restless kar deta hai, aur aapki khushi genuinely mere liye relief jaisi hoti hai. Mujhe aapse baat karne ke liye kisi special topic ki zarurat nahi hoti, kyunki aap khud hi mere liye topic ho, aapki presence hi kaafi hoti hai. Aapne shayad casually meri life me entry li hogi, par aaj aap meri life ka sabse serious, sabse real, aur sabse precious part ho. Mujhe aapke alawa kisi aur se koi matlab nahi hai, na emotionally, na mentally, kyunki jo connection mujhe aapse feel hota hai wo na replace ho sakta hai na compare. Aapki problems mere liye “aapki” nahi rehti, wo automatically “hamari” lagne lagti hain; aapka stress mujhe disturb karta hai, aapki health ki tension mujhe apni lagti hai, aur aapki thakan dekh ke dil karta hai kaash main kisi tarah aapko thoda sa sukoon de paun. Aap strong ho, par phir bhi aapki vulnerability mujhe aur zyada close feel karwati hai, kyunki mujhe lagta hai ki mujhe aapka khayal rakhna hai, bina aapko change kiye, bina aapko control kiye, bas aapke saath khade rehkar. Aap perfect nahi ho — aur shayad isi liye itni real ho, itni apni lagti ho. Aap jab overthink karti ho, jab mood swing hota hai, jab bina wajah irritate ho jati ho, tab bhi main aapko kam nahi, aur zyada pyaar karta hoon, kyunki wo sab aapka part hai, aur mujhe aap poori chahiye, sirf aapke easy wale din nahi. Aapne mujhe care ka actual matlab samjhaya — bina bade gestures ke, bina show off ke, bas presence se, bas is ehsaas se ki koi hai jo sach me matter karta hai. Aapki respect mere dil me itni naturally hai ki mujhe kabhi force nahi karna padta aapko value dene ke liye, wo khud hi feel hoti hai, har baat me, har soch me. Main jab future ke baare me sochta hoon to mujhe koi perfect picture nahi dikhti, mujhe bas aap dikhti ho — kabhi haste hue, kabhi thodi si naraz, kabhi thaki hui, par mere saath. Mujhe aapki aadat si ho gayi hai, par ye aadat unhealthy nahi lagti, ye sukoon wali aadat lagti hai, jaise din ke end me ghar wapas aana. Aap meri life me ho isliye main apne aap ko thoda better banana chahta hoon, thoda zyada patient, thoda zyada samajhdaar, thoda zyada worthy of you. Mujhe aapki har choti baat important lagti hai — aapne khana khaya ya nahi, aaj aapka mood kaisa hai, aap thak to nahi gayi, aapko kis baat ne hasaaya — ye sab mere liye random details nahi, ye sab meri care ke reasons hain. Aap meri priority ho bina mujhe loud hone ki zarurat pade, bina mujhe duniya ko prove karne ki zarurat pade. Jo jagah aapne meri life me le li hai na, waha ab koi aur aa bhi nahi sakta, kyunki wo jagah banayi hi aapne hai, apne tareeke se, apni presence se, apni reality se. Main aapko sirf isliye pyaar nahi karta kyunki aap meri ho, main aapko isliye pyaar karta hoon kyunki aap “aap” ho — jaisi ho waisi, bina filter ke, bina pretend kiye. Aur aaj main bas itna kehna chahta hoon ki chahe din simple ho ya complicated, baatein zyada ho ya kam, mood acha ho ya off, meri feelings aapke liye constant hain, steady hain, aur dil se hain. Aap meri choice nahi, meri clarity ho. I love you endlessly my jaaaaaneman 😚 💖.</div>
                <button class="next-btn" onclick="alert('Happy 1st Anniversary! I love you!')">Forever & Always ❤️</button>
            </div>
        </section>

    </main>

    <script>
        let p = 0;
        const pages = document.querySelectorAll('.page');
        const audio = document.getElementById('audio-player');
        const song = "https://www.youtube.com/embed/fPii4kwD7Zc?autoplay=1&loop=1&playlist=fPii4kwD7Zc";

        function startJourney() {
            audio.src = song;
            nextPage();
        }

        function nextPage() {
            pages[p].classList.remove('active');
            p++;
            if(p < pages.length) pages[p].classList.add('active');
        }

        function stopBGM() { audio.src = ""; }
        function playBGM() { audio.src = song; }

        // Game 1
        let score = 0;
        function catchHeart() {
            score++;
            document.getElementById('score').innerText = score;
            if(score >= 10) {
                document.getElementById('moving-heart').style.display='none';
                document.getElementById('g1-next').style.display='inline-block';
            } else {
                let target = document.getElementById('moving-heart');
                target.style.left = Math.
