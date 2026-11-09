# -<!DOCTYPE html>
<html lang="fr" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bienvenue à South Park, Sarah ! ❤️</title>

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>

    <!-- Canvas Confetti -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <!-- Google Fonts (Luckiest Guy & Fredoka) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;600;700&family=Luckiest+Guy&family=Plus+Jakarta+Sans:wght@600;800&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'sp-blue': '#2b7fb9',
                        'sp-snow': '#f4f9fc',
                        'sp-red': '#e63946',
                        'sp-yellow': '#ffb703',
                        'sp-pink': '#ff70a6',
                        'sp-dark': '#1d3557',
                        'paper-border': '#152238'
                    },
                    fontFamily: {
                        cartoon: ['"Luckiest Guy"', 'cursive'],
                        bubble: ['"Fredoka"', 'sans-serif'],
                        sans: ['"Plus Jakarta Sans"', 'sans-serif']
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Fredoka', sans-serif;
            background: linear-gradient(180deg, #1e3a8a 0%, #3b82f6 40%, #93c5fd 75%, #e0f2fe 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Paper Cutout Effect */
        .paper-cutout {
            background-color: #ffffff;
            border: 4px solid #1e293b;
            box-shadow: 6px 6px 0px #1e293b;
            border-radius: 18px;
            position: relative;
        }

        .paper-cutout-pink {
            background-color: #fff0f3;
            border: 4px solid #1e293b;
            box-shadow: 6px 6px 0px #1e293b;
            border-radius: 18px;
        }

        .paper-cutout-yellow {
            background-color: #fef9c3;
            border: 4px solid #1e293b;
            box-shadow: 6px 6px 0px #1e293b;
            border-radius: 18px;
        }

        .paper-btn {
            border: 3px solid #1e293b;
            box-shadow: 4px 4px 0px #1e293b;
            transition: all 0.15s ease-in-out;
        }
        .paper-btn:hover {
            transform: translate(-2px, -2px);
            box-shadow: 6px 6px 0px #1e293b;
        }
        .paper-btn:active {
            transform: translate(2px, 2px);
            box-shadow: 2px 2px 0px #1e293b;
        }

        /* Snow & Heart Canvas background */
        #snow-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        /* Speech Bubble Arrow */
        .speech-bubble::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            border-width: 15px 15px 0;
            border-style: solid;
            border-color: #ffffff transparent;
            display: block;
            width: 0;
        }
    </style>
</head>
<body class="relative text-slate-900 pb-16 antialiased">

    <!-- Canvas Animation (Flocons de neige & Cœurs) -->
    <canvas id="snow-canvas"></canvas>

    <!-- Header & Banner Style South Park -->
    <header class="relative z-10 pt-10 pb-6 px-4 text-center">
        <div class="max-w-4xl mx-auto space-y-4">
            
            <!-- Mountain Peak Badge -->
            <div class="inline-block bg-sp-yellow text-slate-900 border-4 border-slate-900 font-cartoon tracking-wider px-6 py-2 text-sm sm:text-base rounded-full shadow-[4px_4px_0px_#1e293b] transform -rotate-1">
                🏔️ Colorado Springs • Le Coin le plus Romantique 🏔️
            </div>

            <!-- Title -->
            <h1 class="font-cartoon text-4xl sm:text-6xl md:text-7xl text-white tracking-wide drop-shadow-[5px_5px_0px_#1e293b] uppercase">
                Bienvenue à South Park, <span class="text-sp-yellow">Sarah !</span> ❤️
            </h1>

            <!-- Cute Speech Bubble Header -->
            <div class="max-w-xl mx-auto paper-cutout p-6 text-center mt-6">
                <p class="font-bubble text-lg sm:text-xl font-bold text-slate-800 leading-relaxed">
                    « Même dans toute la ville enneigée de South Park, t'es la seule personne qui me fait chaud au cœur. »
                </p>
                <div class="mt-3 flex justify-center gap-2 font-cartoon text-sp-red text-sm sm:text-base">
                    <span>✨ Hemleghkem ❤️ ✨</span>
                </div>
            </div>

            <!-- South Park Cutout Characters Representation -->
            <div class="flex justify-center items-end gap-4 pt-4">
                <!-- Character Boy Cutout -->
                <div class="w-20 h-24 sm:w-28 sm:h-32 bg-sky-500 border-4 border-slate-900 rounded-t-full relative flex flex-col items-center justify-end shadow-[4px_4px_0px_#1e293b]">
                    <div class="w-full h-8 bg-red-600 border-b-4 border-slate-900 absolute top-0 rounded-t-full"></div>
                    <div class="w-6 h-6 bg-yellow-400 rounded-full border-2 border-slate-900 absolute -top-3"></div>
                    <div class="bg-amber-200 w-16 h-10 rounded-full border-2 border-slate-900 mb-4 flex items-center justify-center gap-2">
                        <div class="w-3 h-4 bg-white rounded-full border border-black flex items-center justify-center"><div class="w-1.5 h-1.5 bg-black rounded-full"></div></div>
                        <div class="w-3 h-4 bg-white rounded-full border border-black flex items-center justify-center"><div class="w-1.5 h-1.5 bg-black rounded-full"></div></div>
                    </div>
                </div>

                <!-- Heart Icon Between -->
                <div class="text-4xl sm:text-5xl text-sp-red animate-bounce mb-6">❤️</div>

                <!-- Character Sarah Cutout -->
                <div class="w-20 h-24 sm:w-28 sm:h-32 bg-sp-pink border-4 border-slate-900 rounded-t-full relative flex flex-col items-center justify-end shadow-[4px_4px_0px_#1e293b]">
                    <div class="w-full h-8 bg-purple-600 border-b-4 border-slate-900 absolute top-0 rounded-t-full"></div>
                    <div class="w-7 h-7 bg-pink-300 rounded-full border-2 border-slate-900 absolute -top-3"></div>
                    <div class="bg-amber-200 w-16 h-10 rounded-full border-2 border-slate-900 mb-4 flex items-center justify-center gap-2">
                        <div class="w-3 h-4 bg-white rounded-full border border-black flex items-center justify-center"><div class="w-1.5 h-1.5 bg-black rounded-full"></div></div>
                        <div class="w-3 h-4 bg-white rounded-full border border-black flex items-center justify-center"><div class="w-1.5 h-1.5 bg-black rounded-full"></div></div>
                    </div>
                </div>
            </div>

        </div>
    </header>

    <!-- Main Content Container -->
    <main class="relative z-10 max-w-4xl mx-auto px-4 space-y-12">

        <!-- SECTION 1: LE GÉNÉRATEUR DE COMPLIMENTS SOUTH PARK -->
        <section class="paper-cutout p-6 sm:p-8 text-center space-y-6">
            <div class="inline-block bg-sp-red text-white px-4 py-1 border-2 border-slate-900 rounded-full font-cartoon text-xs uppercase tracking-wider">
                🍿 Machine à Douceurs 🍿
            </div>
            
            <h2 class="font-cartoon text-2xl sm:text-4xl text-slate-900">
                Le Distributeur de Compliments South Park 🧀
            </h2>

            <div id="compliment-box" class="paper-cutout-pink p-6 min-h-[120px] flex items-center justify-center">
                <p class="font-bubble text-lg sm:text-2xl text-slate-900 font-bold leading-relaxed" id="compliment-text">
                    « Clique ci-dessous pour recevoir ton compliment spécial South Park ! »
                </p>
            </div>

            <button onclick="newCompliment()" class="paper-btn px-8 py-4 bg-sp-yellow hover:bg-amber-400 font-cartoon text-slate-900 text-base sm:text-lg rounded-2xl flex items-center gap-3 mx-auto">
                <i class="fa-solid fa-cookie-bite text-xl"></i> Piocher un compliment pour Sarah
            </button>
        </section>

        <!-- SECTION 2: LE CHEESY POOFS TICKET À GRATTER -->
        <section class="paper-cutout-yellow p-6 sm:p-8 text-center space-y-6">
            <div>
                <span class="bg-sp-blue text-white px-4 py-1 border-2 border-slate-900 rounded-full font-cartoon text-xs uppercase tracking-wider">
                    🎟️ Surprise Grattage
                </span>
                <h2 class="font-cartoon text-2xl sm:text-4xl text-slate-900 mt-2">
                    Le Cheesy Poofs Love Ticket 🧀❤️
                </h2>
                <p class="text-slate-700 text-sm sm:text-base font-semibold mt-1">
                    Gratte le sachet de Cheesy Poofs avec ton doigt ou ta souris pour révéler ton bon privilège !
                </p>
            </div>

            <!-- Scratch Box -->
            <div class="max-w-md mx-auto relative w-full h-48 sm:h-56 paper-cutout overflow-hidden shadow-md">
                <!-- Secret Reward -->
                <div class="absolute inset-0 bg-rose-100 p-6 flex flex-col items-center justify-center text-center">
                    <span class="font-cartoon text-sp-red text-xl sm:text-2xl">🎉 GAGNÉ SARAH ! 🎉</span>
                    <p class="font-bubble text-base sm:text-xl font-bold text-slate-900 mt-2">
                        "Bon pour une soirée South Park sous le plaid avec livraison de tes plats préférés !" 🍕🎬
                    </p>
                    <span class="text-xs text-slate-600 font-bold mt-2">Valable sans limite de temps ❤️</span>
                </div>

                <!-- Canvas Layer to scratch -->
                <canvas id="scratch-canvas" class="absolute inset-0 w-full h-full cursor-pointer z-10"></canvas>
            </div>

            <div class="flex justify-between items-center max-w-md mx-auto text-xs font-bold text-slate-800">
                <span id="scratch-prog">Progression : 0%</span>
                <button onclick="resetScratch()" class="underline hover:text-sp-red">Re-gratter</button>
            </div>
        </section>

        <!-- SECTION 3: QUIZ PERSONNAGE SOUTH PARK -->
        <section class="paper-cutout p-6 sm:p-8 text-center space-y-6">
            <span class="bg-emerald-500 text-white px-4 py-1 border-2 border-slate-900 rounded-full font-cartoon text-xs uppercase tracking-wider">
                🧩 Quiz Amoureux
            </span>
            <h2 class="font-cartoon text-2xl sm:text-4xl text-slate-900">
                Quel personnage de South Park es-tu quand tu m'aimes ?
            </h2>

            <div id="quiz-container" class="space-y-4 max-w-xl mx-auto text-left">
                <p class="font-bubble text-base sm:text-lg font-bold text-slate-800 text-center" id="quiz-question">
                    Question : Quand je te prépare ton plat préféré, tu réagis comment ?
                </p>

                <div class="space-y-3" id="quiz-answers">
                    <button onclick="answerQuiz('stan')" class="paper-btn w-full p-4 bg-white text-left font-semibold text-slate-800 rounded-xl hover:bg-sky-50">
                        💙 Façon Stan : Je suis trop émue et toute timide.
                    </button>
                    <button onclick="answerQuiz('cartman')" class="paper-btn w-full p-4 bg-white text-left font-semibold text-slate-800 rounded-xl hover:bg-amber-50">
                        🧀 Façon Cartman : "C'est mon plat ! Et je mange TOUT !"
                    </button>
                    <button onclick="answerQuiz('butters')" class="paper-btn w-full p-4 bg-white text-left font-semibold text-slate-800 rounded-xl hover:bg-pink-50">
                        ✨ Façon Butters : Je saute partout avec un grand sourire innocent.
                    </button>
                </div>
            </div>

            <div id="quiz-result" class="hidden paper-cutout-pink p-6 text-center space-y-3 max-w-xl mx-auto">
                <h3 class="font-cartoon text-2xl text-sp-red" id="result-title">Résultat !</h3>
                <p class="font-bubble text-lg text-slate-800 font-bold" id="result-desc"></p>
                <button onclick="resetQuiz()" class="paper-btn px-6 py-2 bg-sp-blue text-white font-cartoon rounded-xl text-sm">
                    Recommencer le test
                </button>
            </div>
        </section>

        <!-- SECTION 4: LE BOUTON MAGIQUE ESQUIVEUR -->
        <section class="paper-cutout p-8 sm:p-12 text-center space-y-6 relative overflow-hidden">
            <h2 class="font-cartoon text-3xl sm:text-5xl text-slate-900">
                Question Capitale à South Park 💌
            </h2>
            <p class="font-bubble text-lg sm:text-xl font-bold text-slate-700">
                Est-ce que tu m'aimes plus que tout Sarah ?
            </p>

            <div class="relative min-h-[140px] flex items-center justify-center gap-6" id="dodge-area">
                <!-- YES BUTTON -->
                <button id="btn-yes" class="paper-btn px-10 py-4 bg-sp-red hover:bg-red-600 text-white font-cartoon text-xl rounded-2xl z-10">
                    OUI ! ❤️
                </button>

                <!-- NO BUTTON (DODGES) -->
                <button id="btn-no" class="paper-btn px-8 py-3.5 bg-slate-200 text-slate-700 font-cartoon text-lg rounded-2xl absolute sm:relative">
                    Non 😜
                </button>
            </div>

            <div id="love-success" class="hidden paper-cutout-pink p-6 max-w-md mx-auto text-center space-y-2">
                <h3 class="font-cartoon text-3xl text-sp-red">JE LE SAVAIS ! 🎉❤️</h3>
                <p class="font-bubble text-lg font-bold text-slate-800">
                    Tu es la meilleure chose qui me soit arrivée. Hemleghkem Sarah ! 🥰
                </p>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="text-center pt-12 text-white font-bubble text-sm">
        <p class="font-cartoon text-lg text-sp-yellow drop-shadow-[2px_2px_0px_#1e293b]">
            Créé spécialement pour Sarah ❤️
        </p>
        <p class="opacity-90 mt-1">Inspiré de South Park avec tout mon amour.</p>
    </footer>

    <!-- Logic Script -->
    <script>
        /* --- 1. Snow & Hearts Canvas Animation --- */
        const canvas = document.getElementById('snow-canvas');
        const ctx = canvas.getContext('2d');

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        resizeCanvas();
        window.addEventListener('resize', resizeCanvas);

        const items = [];
        for (let i = 0; i < 45; i++) {
            items.push({
                x: Math.random() * canvas.width,
                y: Math.random() * canvas.height,
                radius: Math.random() * 4 + 2,
                speedY: Math.random() * 1.2 + 0.5,
                speedX: Math.sin(Math.random() * Math.PI) * 0.5,
                isHeart: Math.random() > 0.6
            });
        }

        function draw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            items.forEach(item => {
                ctx.beginPath();
                if (item.isHeart) {
                    ctx.fillStyle = 'rgba(230, 57, 70, 0.6)';
                    ctx.font = `${item.radius * 3.5}px serif`;
                    ctx.fillText('❤️', item.x, item.y);
                } else {
                    ctx.fillStyle = 'rgba(255, 255, 255, 0.8)';
                    ctx.arc(item.x, item.y, item.radius, 0, Math.PI * 2);
                    ctx.fill();
                }

                item.y += item.speedY;
                item.x += Math.sin(item.y * 0.01) * 0.5;

                if (item.y > canvas.height) {
                    item.y = -10;
                    item.x = Math.random() * canvas.width;
                }
            });
            requestAnimationFrame(draw);
        }
        draw();

        /* --- 2. Compliments Generator --- */
        const compliments = [
            "T'es encore plus précieuse qu'un bon d'achat illimité au Park County Market. 🛒❤️",
            "Je t'aime plus que Cartman n'aime les Cheesy Poofs ! 🧀😍",
            "Si je devais choisir entre le meilleur plat de la Terre et toi... les pâtes aux Sarah gagnent à tous les coups 🍝❤️",
            "Même avec toutes les dingueries qui se passent à South Park, t'es la seule personne avec qui j'ai envie de rester posé. Hemleghkem ! ✨",
            "T'es la fille la plus stylée, drôle et mignonne de tout le Colorado (et de la planète entière). 🏆💕",
            "Un jour sans toi, c'est comme un épisode de South Park sans réplique culte : c'est impossible ! 🔥"
        ];

        function newCompliment() {
            const text = document.getElementById('compliment-text');
            const rand = compliments[Math.floor(Math.random() * compliments.length)];
            text.style.opacity = 0;
            setTimeout(() => {
                text.textContent = `« ${rand} »`;
                text.style.opacity = 1;
            }, 150);

            if (typeof confetti === 'function') {
                confetti({ particleCount: 25, spread: 50, origin: { y: 0.6 } });
            }
        }

        /* --- 3. Scratch Card Logic --- */
        const scratchCanvas = document.getElementById('scratch-canvas');
        const scratchCtx = scratchCanvas.getContext('2d');
        let isScratchedDone = false;

        function initScratch() {
            scratchCanvas.width = scratchCanvas.offsetWidth;
            scratchCanvas.height = scratchCanvas.offsetHeight;
            isScratchedDone = false;

            scratchCtx.fillStyle = '#ffb703';
            scratchCtx.fillRect(0, 0, scratchCanvas.width, scratchCanvas.height);

            scratchCtx.fillStyle = '#1e293b';
            scratchCtx.font = 'bold 18px "Luckiest Guy", cursive';
            scratchCtx.textAlign = 'center';
            scratchCtx.fillText('🧀 GRATTE LE CHEESY POOFS ! 🧀', scratchCanvas.width / 2, scratchCanvas.height / 2);
        }

        function scratch(e) {
            if (isScratchedDone) return;
            const rect = scratchCanvas.getBoundingClientRect();
            const clientX = e.touches ? e.touches[0].clientX : e.clientX;
            const clientY = e.touches ? e.touches[0].clientY : e.clientY;

            const x = clientX - rect.left;
            const y = clientY - rect.top;

            scratchCtx.globalCompositeOperation = 'destination-out';
            scratchCtx.beginPath();
            scratchCtx.arc(x, y, 22, 0, Math.PI * 2);
            scratchCtx.fill();

            checkScratch();
        }

        function checkScratch() {
            if (isScratchedDone) return;
            const data = scratchCtx.getImageData(0, 0, scratchCanvas.width, scratchCanvas.height).data;
            let clear = 0;
            for (let i = 3; i < data.length; i += 4) {
                if (data[i] === 0) clear++;
            }
            const percent = Math.round((clear / (data.length / 4)) * 100);
            document.getElementById('scratch-prog').textContent = `Progression : ${percent}%`;

            if (percent > 40 && !isScratchedDone) {
                isScratchedDone = true;
                confetti({ particleCount: 100, spread: 70, origin: { y: 0.6 } });
            }
        }

        let scratching = false;
        scratchCanvas.addEventListener('mousedown', (e) => { scratching = true; scratch(e); });
        scratchCanvas.addEventListener('mousemove', (e) => { if (scratching) scratch(e); });
        window.addEventListener('mouseup', () => scratching = false);

        scratchCanvas.addEventListener('touchstart', (e) => { scratching = true; scratch(e); });
        scratchCanvas.addEventListener('touchmove', (e) => { if (scratching) scratch(e); });
        window.addEventListener('touchend', () => scratching = false);

        function resetScratch() {
            document.getElementById('scratch-prog').textContent = 'Progression : 0%';
            initScratch();
        }

        window.addEventListener('load', initScratch);

        /* --- 4. Quiz Logic --- */
        function answerQuiz(type) {
            const container = document.getElementById('quiz-container');
            const result = document.getElementById('quiz-result');
            const title = document.getElementById('result-title');
            const desc = document.getElementById('result-desc');

            container.classList.add('hidden');
            result.classList.remove('hidden');

            if (type === 'stan') {
                title.textContent = "💙 Tu es Stan quand tu m'aimes !";
                desc.textContent = "Sensible, hyper touchante et profondément loyale. Quand tu m'aimes, c'est avec tout ton cœur !";
            } else if (type === 'cartman') {
                title.textContent = "🧀 Tu es Cartman (version passionnée) !";
                desc.textContent = "Déterminée et gourmande ! Quand tu veux tes câlins ou tes pâtes aux Sarah, personne n'a le droit de négocier !";
            } else {
                title.textContent = "✨ Tu es Butters la plus adorable !";
                desc.textContent = "Une boule de pure gentillesse, d'innocence et de mignonnerie absolue. Tu illumines ma vie !";
            }
            confetti({ particleCount: 50, spread: 60, origin: { y: 0.6 } });
        }

        function resetQuiz() {
            document.getElementById('quiz-container').classList.remove('hidden');
            document.getElementById('quiz-result').classList.add('hidden');
        }

        /* --- 5. Dodge Button Game --- */
        const btnNo = document.getElementById('btn-no');
        const btnYes = document.getElementById('btn-yes');
        const dodgeArea = document.getElementById('dodge-area');
        const success = document.getElementById('love-success');

        function moveNo() {
            const areaRect = dodgeArea.getBoundingClientRect();
            const btnRect = btnNo.getBoundingClientRect();

            const maxX = areaRect.width - btnRect.width - 20;
            const maxY = areaRect.height - btnRect.height - 20;

            const x = Math.max(10, Math.floor(Math.random() * maxX));
            const y = Math.max(10, Math.floor(Math.random() * maxY));

            btnNo.style.position = 'absolute';
            btnNo.style.left = `${x}px`;
            btnNo.style.top = `${y}px`;
        }

        btnNo.addEventListener('mouseover', moveNo);
        btnNo.addEventListener('touchstart', (e) => { e.preventDefault(); moveNo(); });

        btnYes.addEventListener('click', () => {
            btnNo.style.display = 'none';
            success.classList.remove('hidden');
            confetti({
                particleCount: 150,
                spread: 90,
                origin: { y: 0.6 },
                colors: ['#e63946', '#ffb703', '#ff70a6', '#ffffff']
            });
        });
    </script>
</body>
</html>
