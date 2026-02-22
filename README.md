<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mayuri Tapkire · code & create</title>
    <!-- Fonts & Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Skill icons via cdn.jsdelivr.net (simple-icons) -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/devicon.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #0a0f1e 0%, #141b33 100%);
            font-family: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;
            display: flex;
            justify-content: center;
            padding: 2rem 1rem;
            color: #e2e8ff;
            line-height: 1.5;
        }

        .readme-card {
            max-width: 1100px;
            width: 100%;
            background: rgba(18, 25, 45, 0.75);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(108, 99, 255, 0.25);
            border-radius: 3rem;
            padding: 2.5rem 2.2rem;
            box-shadow: 0 30px 50px -15px rgba(0, 0, 0, 0.8), 0 0 0 1px rgba(108, 99, 255, 0.2) inset;
            transition: all 0.3s;
        }

        /* glow / animation */
        .glow-text {
            text-shadow: 0 0 8px #6c63ff, 0 0 20px #3b34b0;
        }

        .animated-bg {
            position: relative;
            overflow: hidden;
        }

        .animated-bg::before {
            content: '';
            position: absolute;
            top: -20%;
            left: -10%;
            width: 140%;
            height: 140%;
            background: radial-gradient(circle at 30% 40%, rgba(108, 99, 255, 0.15), transparent 60%);
            animation: rotateSlow 24s infinite linear;
            z-index: -1;
            pointer-events: none;
        }

        @keyframes rotateSlow {
            0% { transform: rotate(0deg) scale(1); }
            50% { transform: rotate(3deg) scale(1.02); }
            100% { transform: rotate(0deg) scale(1); }
        }

        /* typing gradient */
        .typing-demo {
            font-size: 1.6rem;
            font-weight: 600;
            background: linear-gradient(90deg, #a99eff, #8f87ff, #6c63ff, #8f87ff);
            background-size: 300% auto;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: gradientShift 6s ease infinite;
            display: inline-block;
        }

        @keyframes gradientShift {
            0% { background-position: 0% center; }
            50% { background-position: 100% center; }
            100% { background-position: 0% center; }
        }

        /* avatar style */
        .avatar-icon {
            display: flex;
            align-items: center;
            gap: 15px;
            flex-wrap: wrap;
        }

        .pulse-ring {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: linear-gradient(135deg, #6c63ff, #3a33aa);
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 30px #6c63ff;
            animation: pulseGlow 2.2s infinite;
        }

        .pulse-ring i {
            font-size: 3rem;
            color: white;
            filter: drop-shadow(0 0 8px #b0a8ff);
        }

        @keyframes pulseGlow {
            0% { box-shadow: 0 0 20px #6c63ff; }
            50% { box-shadow: 0 0 45px #b3aaff; }
            100% { box-shadow: 0 0 20px #6c63ff; }
        }

        /* section titles */
        .section-title {
            font-size: 1.9rem;
            font-weight: 700;
            margin-bottom: 1.3rem;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 2px solid rgba(108, 99, 255, 0.4);
            padding-bottom: 0.5rem;
        }

        .section-title i {
            color: #6c63ff;
            font-size: 2rem;
            filter: drop-shadow(0 0 5px #a38dff);
        }

        .chip-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 14px 18px;
            margin: 1.5rem 0 1.2rem;
        }

        .chip {
            background: rgba(30, 40, 70, 0.7);
            backdrop-filter: blur(4px);
            border: 1px solid rgba(108, 99, 255, 0.5);
            padding: 0.6rem 1.3rem;
            border-radius: 40px;
            font-weight: 500;
            color: #f0eeff;
            letter-spacing: 0.3px;
            box-shadow: 0 5px 10px -5px #00000055;
            transition: 0.2s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 1.05rem;
        }

        .chip i, .chip .devicon {
            font-size: 1.4rem;
            color: #b3a9ff;
        }

        .chip:hover {
            border-color: #9d93ff;
            background: rgba(58, 70, 115, 0.9);
            transform: translateY(-3px);
            box-shadow: 0 10px 18px -6px #6c63ff;
        }

        .project-card {
            background: rgba(13, 20, 40, 0.6);
            border-radius: 2rem;
            padding: 1.5rem 1.8rem;
            border: 1px solid #2c2f5a;
            box-shadow: 0 15px 25px -10px #00000080;
            transition: 0.25s;
            backdrop-filter: blur(5px);
            margin-bottom: 1.6rem;
        }

        .project-card:hover {
            border-color: #6c63ff;
            box-shadow: 0 20px 30px -12px #887eff;
        }

        .project-title {
            font-size: 1.7rem;
            font-weight: 600;
            background: linear-gradient(135deg, #c6bfff, #ffffff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 8px;
        }

        .tech-tag {
            background: #202844;
            border-radius: 30px;
            padding: 0.3rem 1rem;
            font-size: 0.9rem;
            color: #b1c3ff;
            display: inline-block;
            margin: 5px 8px 0 0;
            border: 1px solid #3b405f;
        }

        .stats-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
        }

        .stat-item {
            background: #111b33;
            border-radius: 30px;
            padding: 1rem 2rem;
            border: 1px solid #373d6d;
            box-shadow: 0 10px 15px -8px black;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .stat-item i {
            color: #ffd966;
        }

        .connect-link {
            background: rgba(30, 35, 60, 0.8);
            border-radius: 60px;
            padding: 0.8rem 1.8rem;
            font-size: 1.2rem;
            transition: all 0.2s;
            border: 1px solid #565a9e;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            margin: 0.5rem 1rem 0.5rem 0;
            color: white;
            text-decoration: none;
            backdrop-filter: blur(4px);
        }

        .connect-link:hover {
            background: #353f77;
            border-color: #b1aaff;
            transform: scale(1.02);
            box-shadow: 0 0 20px #6c63ff;
        }

        .footer-quote {
            font-size: 1.3rem;
            text-align: center;
            margin-top: 3rem;
            padding: 1.2rem;
            border-top: 1px dashed #4e54a3;
            font-style: italic;
            background: radial-gradient(ellipse at center, rgba(108, 99, 255, 0.15), transparent 80%);
        }

        hr {
            border: 0.5px solid #2d3460;
            margin: 2rem 0;
        }

        .badge-icon {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        /* animated sparkle */
        .sparkle {
            position: relative;
        }
        .sparkle::after {
            content: '✨';
            position: absolute;
            top: -15px;
            right: -15px;
            font-size: 1.3rem;
            opacity: 0.5;
            animation: twinkle 3s infinite;
        }
        @keyframes twinkle {
            0% { opacity: 0.2; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
            100% { opacity: 0.2; transform: scale(1); }
        }
    </style>
</head>
<body>
    <div class="readme-card animated-bg">
        <!-- header with avatar + typing effect -->
        <div class="avatar-icon" style="margin-bottom: 20px;">
            <div class="pulse-ring">
                <i class="fas fa-code"></i>
            </div>
            <div style="flex:1">
                <h1 style="font-size: 2.8rem; font-weight: 800; letter-spacing: -0.5px; background: linear-gradient(145deg, #ffffff, #c9c2ff); -webkit-background-clip: text; background-clip: text; color: transparent;">Mayuri Tapkire</h1>
                <div class="typing-demo" style="font-size: 1.5rem;">
                    <i class="fas fa-robot" style="color: #b1a6ff; margin-right: 5px;"></i> 
                    <span>CS (Data Science) · Full Stack · AI/ML</span>
                </div>
            </div>
        </div>

        <!-- about me / core concepts combined -->
        <div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
            <div style="flex: 2; min-width: 250px;">
                <div class="section-title"><i class="fas fa-user-astronaut"></i> about me</div>
                <div style="background: #0b1126; border-radius: 2rem; padding: 1.4rem; border: 1px solid #334075;">
                    <p style="font-size: 1.2rem; margin-bottom: 15px;">🎓 <strong>Computer Science (Data Science)</strong></p>
                    <p style="display: flex; gap: 12px; flex-wrap: wrap;">
                        <span class="chip"><i class="fas fa-mobile-alt"></i> Android</span>
                        <span class="chip"><i class="fas fa-brain"></i> ML/DL</span>
                        <span class="chip"><i class="fas fa-cloud"></i> LLMs</span>
                        <span class="chip"><i class="fas fa-cubes"></i> scalable apps</span>
                    </p>
                    <p style="margin-top: 18px; font-size: 1.1rem;"><i class="fas fa-seedling" style="color: #7ef0ba;"></i> learning from mistakes, growing consistently</p>
                    <p style="margin-top: 12px;"><i class="fas fa-bullseye" style="color: #ffa87e;"></i> aspiring software engineer</p>
                </div>
            </div>
            <div style="flex: 1.5; min-width: 200px;">
                <div class="section-title"><i class="fas fa-cogs"></i> core concepts</div>
                <div class="chip-grid" style="margin-top: 5px;">
                    <span class="chip">OOP</span>
                    <span class="chip">DSA</span>
                    <span class="chip">DBMS</span>
                    <span class="chip">Multithreading</span>
                    <span class="chip">Exception Handling</span>
                    <span class="chip">SDLC</span>
                </div>
            </div>
        </div>

        <!-- programming languages + web & app dev merged with icons -->
        <div class="section-title"><i class="fas fa-laptop-code"></i> languages & frameworks</div>
        <div class="chip-grid" style="margin-top: 0;">
            <!-- programming lang chips -->
            <span class="chip"><i class="devicon-java-plain-wordmark colored"></i> Java</span>
            <span class="chip"><i class="devicon-python-plain-wordmark colored"></i> Python</span>
            <span class="chip"><i class="devicon-php-plain colored"></i> PHP</span>
            <span class="chip"><i class="devicon-cplusplus-plain colored"></i> C++</span>
            <!-- web & db icons -->
            <span class="chip"><i class="devicon-django-plain-wordmark colored"></i> Django</span>
            <span class="chip"><i class="devicon-mysql-plain-wordmark colored"></i> MySQL</span>
            <span class="chip"><i class="devicon-html5-plain-wordmark colored"></i> HTML5</span>
            <span class="chip"><i class="devicon-css3-plain-wordmark colored"></i> CSS3</span>
            <span class="chip"><i class="devicon-javascript-plain colored"></i> JS</span>
            <span class="chip"><i class="devicon-android-plain-wordmark colored"></i> Android</span>
            <span class="chip"><i class="devicon-firebase-plain-wordmark colored"></i> Firebase</span>
            <span class="chip"><i class="devicon-react-original-wordmark colored"></i> React Native</span>
            <span class="chip"><i class="devicon-sqlite-plain-wordmark colored"></i> SQLite</span>
        </div>

        <!-- ML & data science row -->
        <div class="section-title"><i class="fas fa-chart-line"></i> data science & AI</div>
        <div class="chip-grid">
            <span class="chip">Data Cleaning</span>
            <span class="chip">EDA</span>
            <span class="chip">Feature Engineering</span>
            <span class="chip">Model Building</span>
            <span class="chip">LLM Integration</span>
            <span class="chip"><i class="fas fa-vector-square"></i> ChromaDB/FAISS</span>
        </div>

        <!-- featured projects (beautiful cards) -->
        <div class="section-title" style="margin-top: 2rem;"><i class="fas fa-rocket"></i> featured projects</div>

        <div class="project-card">
            <div class="project-title">🏥 Full Stack Hospital Management System</div>
            <p>Digitize hospital operations: patient management, appointments, billing.</p>
            <div style="margin-top: 10px;">
                <span class="tech-tag">Django</span>
                <span class="tech-tag">MySQL</span>
                <span class="tech-tag">HTML/CSS</span>
            </div>
        </div>

        <div class="project-card">
            <div class="project-title">🏢 HostelConnect – Android App</div>
            <p>Streamline hostel communication & complaint management.</p>
            <div style="margin-top: 10px;">
                <span class="tech-tag">Java</span>
                <span class="tech-tag">XML</span>
                <span class="tech-tag">Firebase</span>
            </div>
        </div>

        <div class="project-card">
            <div class="project-title">🤖 AI Document Intelligence Platform</div>
            <p>Semantic document search with vector embeddings + AI integration.</p>
            <div style="margin-top: 10px;">
                <span class="tech-tag">Django REST</span>
                <span class="tech-tag">MySQL</span>
                <span class="tech-tag">ChromaDB / FAISS</span>
            </div>
        </div>

        <div class="project-card">
            <div class="project-title">🧾 Smart Receipt Scanner & Expense Categorizer</div>
            <p>OCR receipt scanner with automatic expense categories.</p>
            <div style="margin-top: 10px;">
                <span class="tech-tag">Java</span>
                <span class="tech-tag">ML Kit</span>
                <span class="tech-tag">SQLite</span>
            </div>
        </div>

        <!-- github stats with style & animation -->
        <div class="section-title"><i class="fab fa-github"></i> github analytics</div>
        <div class="stats-grid">
            <div class="stat-item sparkle"><i class="fas fa-star"></i> 8 repositories</div>
            <div class="stat-item"><i class="fas fa-code-branch"></i> active commits</div>
            <div class="stat-item"><i class="fas fa-fire"></i> #streak</div>
        </div>

        <!-- placeholder for actual stats: images from github readme stats (using profile MMTapkire31) but we'll style like they're embedded -->
        <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; margin: 30px 0;">
            <img src="https://github-readme-stats.vercel.app/api?username=MMTapkire31&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d122b&icon_color=6c63ff&text_color=d0d4ff" alt="stats" style="border-radius: 20px; border: 2px solid #40477b; max-width: 100%;">
            <img src="https://github-readme-streak-stats.herokuapp.com/?user=MMTapkire31&theme=tokyonight&hide_border=true&background=0d122b&stroke=6c63ff&ring=a28cff&fire=ffb974" alt="streak" style="border-radius: 20px; border: 2px solid #40477b; max-width: 100%;">
        </div>

        <!-- connect with me -->
        <div class="section-title"><i class="fas fa-paper-plane"></i> connect with me</div>
        <div style="display: flex; flex-wrap: wrap; gap: 10px;">
            <a href="https://www.linkedin.com/in/mayuri-tapkire-667182326" class="connect-link"><i class="fab fa-linkedin"></i> LinkedIn</a>
            <a href="mailto:mayurit3105@gmail.com" class="connect-link"><i class="fas fa-envelope"></i> mayurit3105</a>
            <a href="mailto:tapkiremayuri31@gmail.com" class="connect-link"><i class="fas fa-envelope-open"></i> tapkiremayuri31</a>
        </div>
        <div style="margin-top: 15px;">
            <span class="chip" style="font-size: 1.2rem;"><i class="fab fa-github"></i> MMTapkire31</span>
        </div>

        <!-- footer quote / motto -->
        <div class="footer-quote">
            <i class="fas fa-crown" style="color: #f7d44b;"></i> Building with consistency. Growing with every challenge. 
            <span style="display: inline-block; animation: pulseGlow 2s infinite; margin-left: 8px;">✨</span>
        </div>

        <!-- tiny note (invisible marker) -->
        <p style="text-align: center; color: #5b6190; margin-top: 1rem;">
            <i class="fas fa-heart" style="color: #ff6a9c;"></i> full stack · android · ai/ml
        </p>
    </div>
</body>
</html>
