<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Forever Love ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root { --p: #ffdae0; --s: #ff4d6d; --glass: rgba(255, 255, 255, 0.9); }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Poppins', sans-serif; }
        body { background: var(--p); overflow: hidden; height: 100vh; }
        .heart-bg { position: fixed; color: var(--s); font-size: 20px; z-index: -1; animation: float 4s linear infinite; }
        @keyframes float { 0% { transform: translateY(110vh); opacity: 1; } 100% { transform: translateY(-10vh); opacity: 0; } }
        
        .page { display: none; height: 100vh; width: 100vw; justify-content: center; align-items: center; position: absolute; padding: 20px; }
        .active { display: flex; animation: fadeIn 0.5s ease; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        .card { background: var(--glass); padding: 25px; border-radius: 25px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); 
                  width: 100%; max-width: 420px; text-align: center; border: 2px solid white; max-height: 90vh; overflow-y: auto; }
        h1, h2 { font-family: 'Dancing Script', cursive; color: var(--s); margin-bottom: 10px; }
        
        .media-box { border: 4px solid white; border-radius: 15px; overflow: hidden; margin: 10px 0; background: #000; min-height: 150px; }
        .media-box img, .media-box video { width: 100%; display: block; }
        
        .letter-text { background: #fffcf2; padding: 15px; border-radius: 12px; text-align: left; font-size: 0.9rem; 
                       line-height: 1.5; color: #333; max-height: 300px; overflow-y: scroll; white-space: pre-wrap; border-left: 4px solid var(--s); }
        
        .next-btn { background: var(--s); color: white; border: none; padding: 12px 25px; border-radius: 50px; cursor: pointer; font-weight: 600; margin-top: 15px; }
        .game-btn { background: white; border: 2px solid var(--s); color: var(--s); padding: 8px; margin: 5px; border-radius: 10px; cursor: pointer; }
    </style>
</head>
<body>

<div id="h-cont"></div>
<iframe id="bg-music" width="0" height="0" src="" frameborder="0" allow="autoplay"></iframe>

<main id="main">
    <section class="page active">
        <div class="card">
            <h1>Happy Anniversary! ❤️</h1>
            <div class="media-box"><img src="https://cdn.discordapp.com/attachments/1421877888877203559/1466400575427051602/From_KlickPin_CF_Hello_Hi_Duck_GIF.gif"></div>
            <p>Taiyar ho? Ek lambi journey tumhara wait kar rahi hai...</p>
            <button class="next-btn" onclick="start()">Chalo Shuru Karein 💖</button>
        </div>
    </section>

    <section class="page"><div class="card"><h2>Game 1: Catch Heart</h2><div style="height:150px; position:relative;" id="g1-z"><div id="t1" onclick="hit(1)" style="position:absolute; cursor:pointer; font-size:30px;">❤️</div></div><p>Score: <span id="s1">0</span>/5</p><button class="next-btn" id="nb1" style="display:none" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Game 2: Click the Pink!</h2><div id="g2-z"></div><p id="s2">Find the pink button!</p><button class="next-btn" id="nb2" style="display:none" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Game 3: Mystery Box</h2><p>Click the right box to continue!</p><div id="g3-z"></div><button class="next-btn" id="nb3" style="display:none" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Game 4: Love Quiz</h2><p>Do you love me?</p><button class="next-btn" onclick="go()">YES! ❤️</button></div></section>

    <section class="page"><div class="card"><h2>Video 1 🫶🏻</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448687809954058/lv_7555554315964878141_20260117212840.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Video 2 💖</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448576363233361/lv_7572376034872478993_20260129201229.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Video 3 ✨</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448578389217290/lv_7596206565158423861_20260129200129.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Video 4 🫶🏻</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577013354598/lv_7591172117144587573_20260129201020.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Video 5 💖</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>

    <section class="page">
        <div class="card">
            <h2>Letter For You ✉️</h2>
            <div class="letter-text">Happy 1 year anniversary meri FOREVER 🫶🏻 💖 Aaj jab hamari saath ki is ek saal ki journey ko yaad karta hoon, to dil me ek ajeeb si shanti aur gehra sa ehsaas bhar jaata hai, kyunki ye sirf dates ka guzar jana nahi tha, balki do alag zindagiyon ka dheere dheere ek doosre ki aadat ban jana tha. Shuruaat shayad simple thi, thodi awkward, thodi hasi mazaak wali, thodi confusion se bhari hui, lekin usi shuruaat me ek sachchai thi — baat karne ka mann, ek doosre ko samajhne ki koshish, aur bina mile bhi ek connection mehsoos hona. Dheere dheere hamari baatein routine nahi rahi, zarurat ban gayi; din kaisa gaya, kya khaya, kis baat pe hansi aayi, kis baat ne pareshan kiya — ye sab share karte karte hum sirf lovers nahi, balki ek doosre ke safe place ban gaye. Is ek saal me humne sirf achhe din hi nahi dekhe, balki misunderstandings, mood swings, overthinking, gussa, rona, dooriyan aur wapas paas aane ki koshish bhi dekhi, aur shayad isi wajah se ye rishta aur real lagta hai, kyunki ye perfect nahi tha, par sachcha tha. Aapne mujhe patience sikhaya, sikhaya ki har baat ka turant jawab nahi hota, kuch baatein samajhne me waqt lagta hai; aapne mujhe care ka matlab samjhaya, ki pyaar sirf “I love you” bolne me nahi, balki “khana khaya?” “thak gaye ho kya?” jaisi chhoti chhoti baaton me hota hai. Maine bhi apni taraf se ye seekha ki kisi ko apni life me rakhna sirf khushi baantna nahi, balki uske dard ko bhi samajhna hota hai, chahe wo hamesha shabdon me na bataya ja sake. Kabhi kabhi main galat samjha, kabhi aap hurt hui, kabhi maine overthink kiya, kabhi aap chup ho gayi — par phir bhi humne poori tarah haath nahi chhoda, aur shayad isi me is rishte ki asli taqat hai. Aap meri life me sirf ek insaan ki tarah nahi, balki ek ehsaas ki tarah aayi — aisi aadat jo din me kai baar yaad aati hai, aisi fikr jo bina wajah bhi hoti rehti hai, aisi muskurahat jo sirf aapki ek simple si line se aa jaati hai. Is ek saal me maine ye bhi samjha ki pyaar ka matlab control nahi, samajhna hota hai; possess karna nahi, appreciate karna hota hai; har waqt perfect rehna nahi, balki galti hone par maan lena hota hai. Aage ka safar kaisa hoga, ye shayad hum dono aaj poori tarah nahi jaante, par main itna zaroor jaanta hoon ki main aapke saath grow karna chahta hoon — zyada samajhdaar banke, zyada shaant banke, zyada supportive banke. Main chahta hoon ki jab aap thaki ho to aapko sukoon mile, jab aap khush ho to wo khushi dugni ho, jab aap pareshan ho to aapko lage ki koi bina judge kiye sunne wala hai. Main promise perfect hone ka nahi kar sakta, par ye zaroor keh sakta hoon ki main har din koshish karunga ki kal se thoda better insaan ban paun — aapke liye nahi sirf, balki humare liye. Ye ek saal sirf memories ka collection nahi, balki ek foundation tha — trust ka, care ka, emotional connection ka. Aage bhi misunderstandings aayengi, mood swings aayenge, busy din aayenge, par agar hum baat karna nahi chhodenge aur ek doosre ko enemy nahi samjhenge, to koi bhi problem humse badi nahi hogi. Aap meri zindagi me ek chapter nahi, balki ek aisi kahani ho jo abhi likhi ja rahi hai, dheere dheere, patience ke saath, feelings ke saath. Aaj ke din bas itna kehna hai ki jo bhi tha, jaisa bhi tha, ye saal mere liye special tha kyunki isme aap thi — aapki awaaz, aapka tareeka, aapka gussa, aapki care, sab kuch. Aur agar aap saath ho, to main aage ke saalon ko bhi isi tarah sambhal ke chalna chahta hoon — respect ke saath, loyalty ke saath, aur us pyaar ke saath jo shor se nahi, par ehsaas se mehsoos hota hai.</div>
            <button class="next-btn" onclick="go()">Next</button>
        </div>
    </section>

    <section class="page"><div class="card"><h2>Phase 2 Game: Catch!</h2><div style="height:150px; position:relative;" id="g5-z"><div id="t5" onclick="hit(5)" style="position:absolute; cursor:pointer; font-size:30px;">🌸</div></div><p>Score: <span id="s5">0</span>/5</p><button class="next-btn" id="nb5" style="display:none" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Maja Aaya? 😚</h2><div style="display:flex; justify-content:space-around"><button class="next-btn" onclick="go()">YES!</button><button class="next-btn" id="no-btn" onmouseover="run()">No</button></div></div></section>
    
    <section class="page"><div class="card"><h2>Video 6 🫶🏻</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448577575260437/lv_7596118272932678917_20260129200828.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Video 7 💖</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448579022553170/lv_7587817635014774021_20260129195708.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Video 8 ✨</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448574396104777/lv_7588073915361021201_20260129201555.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Video 9 🫶🏻</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448575012671690/lv_7365945955050474768_20260129202233.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>
    <section class="page"><div class="card"><h2>Video 10 💖</h2><div class="media-box"><video controls onplay="pM()" onended="rM()"><source src="https://cdn.discordapp.com/attachments/1421877888877203559/1466448573179891743/lv_7519771999514676541_20260129202958.mp4"></video></div><button class="next-btn" onclick="go()">Next</button></div></section>

    <section class="page">
        <div class="card">
            <h2>Endlessly Yours ❤️</h2>
            <div class="letter-text">pehle ye feel hota hai ki meri zindagi me jo bhi softness, jo bhi emotional depth, jo bhi sachcha care aaya hai, wo kahin na kahin aapse hi shuru hota hai, kyunki aap sirf ek insaan nahi ho, aap ek feeling ho jo dheere dheere meri aadat ban gayi... [Pura Message Yahan Hai] ... Aap meri priority ho bina mujhe loud hone ki zarurat pade. I love you endlessly my jaaaaaneman 😚 💖.</div>
            <button class="next-btn" onclick="alert('Happy Anniversary My Love!')">The End ❤️</button>
        </div>
    </section>
</main>

<script>
    let cur = 0;
    const pgs = document.querySelectorAll('.page');
    const aud = document.getElementById('bg-music');
    const src = "https://www.youtube.com/embed/fPii4kwD7Zc?autoplay=1&loop=1&playlist=fPii4kwD7Zc";

    function start() { aud.src = src; go(); }
    function go() { pgs[cur].classList.remove('active'); cur++; if(cur < pgs.length) pgs[cur].classList.add('active'); rM(); }
    function pM() { aud.src = ""; }
    function rM() { if(!pgs[cur].querySelector('video')) aud.src = src; }

    // Games Logic
    let sc1 = 0, sc5 = 0;
    function hit(n) {
        if(n==1) { sc1++; document.getElementById('s1').innerText=sc1; if(sc1>=5) document.getElementById('nb1').style.display='block'; move('t1'); }
        if(n==5) { sc5++; document.getElementById('s5').innerText=sc5; if(sc5>=5) document.getElementById('nb5').style.display='block'; move('t5'); }
    }
    function move(id) { let t=document.getElementById(id); t.style.left=Math.random()*80+'%'; t.style.top=Math.random()*80+'%'; }

    // Init Game 2 & 3
    const g2 = document.getElementById('g2-z');
    for(let i=0; i<8; i++) {
        let b = document.createElement('button'); b.className='game-btn'; b.innerText='Click';
        b.onclick = () => { if(i==4) { b.style.bg='pink'; document.getElementById('nb2').style.display='block'; } };
        g2.appendChild(b);
    }
    const g3 = document.getElementById('g3-z');
    for(let i=0; i<3; i++) {
        let b = document.createElement('button'); b.className='game-btn'; b.innerText='Box '+(i+1);
        b.onclick = () => { if(i==1) document.getElementById('nb3').style.display='block'; };
        g3.appendChild(b);
    }

    function run() { let b=document.getElementById('no-btn'); b.style.position='fixed'; b.style.left=Math.random()*80+'vw'; b.style.top=Math.random()*80+'vh'; }

    setInterval(() => {
        const h = document.createElement('div'); h.innerHTML='❤️'; h.className='heart-bg';
        h.style.left = Math.random()*100+'vw'; h.style.animationDuration = (Math.random()*2+2)+'s';
        document.getElementById('h-cont').appendChild(h);
        setTimeout(() => h.remove(), 4000);
    }, 400);
</script>
</body>
</html>
