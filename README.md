<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RICK | Cyber Security Researcher</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght=300;400;700&display=swap" rel="stylesheet">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    
    <style>
        :root {
            --bg-color: #0d1117;
            --card-bg: #161b22;
            --accent-color: #00ff66;
            --text-color: #c9d1d9;
            --text-bright: #ffffff;
            --border-color: #30363d;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cairo', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* شاشة الفحص الأمني عند الدخول */
        #security-check {
            position: fixed;
            top: 0; left: 0; width: 100vw; height: 100vh;
            background-color: #05070a;
            z-index: 99999;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: var(--accent-color);
            font-family: monospace;
            padding: 20px;
            direction: ltr;
        }

        .scan-terminal {
            width: 100%;
            max-width: 500px;
            background: #090d13;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            padding: 20px;
            box-shadow: 0 0 20px rgba(0, 255, 102, 0.1);
        }

        .scan-line { margin-bottom: 8px; white-space: nowrap; overflow: hidden; font-size: 14px; }
        .cookie-display-panel { margin-top: 15px; background: #161b22; border: 1px dashed var(--accent-color); padding: 10px; border-radius: 4px; width: 100%; font-size: 12px; color: #ffcc00; }

        /* الهيدر وقائمة التنقل */
        header {
            background-color: rgba(22, 27, 34, 0.95);
            border-bottom: 1px solid var(--border-color);
            position: fixed;
            width: 100%; top: 0; right: 0; z-index: 1000;
            backdrop-filter: blur(10px);
        }

        .nav-container {
            max-width: 1200px; margin: 0 auto;
            display: flex; justify-content: space-between; align-items: center; padding: 15px 20px;
        }

        .logo-area { display: flex; align-items: center; gap: 10px; }
        .logo { font-size: 24px; font-weight: 700; color: var(--text-bright); letter-spacing: 1px; }
        .logo span { color: var(--accent-color); }

        .header-follow-btn {
            background: #21262d; border: 1px solid var(--accent-color); color: var(--accent-color);
            padding: 3px 10px; border-radius: 4px; font-size: 12px; cursor: pointer; font-weight: bold; transition: all 0.2s; margin-left: 10px;
        }
        .header-follow-btn:hover { background: var(--accent-color); color: #000; box-shadow: 0 0 10px var(--accent-color); }

        .nav-video-toggle {
            background: none; border: 1px solid var(--border-color); color: var(--accent-color);
            padding: 5px 12px; border-radius: 4px; cursor: pointer; font-size: 13px; display: flex; align-items: center; gap: 6px; transition: all 0.3s;
        }
        .nav-video-toggle:hover { border-color: var(--accent-color); box-shadow: 0 0 10px rgba(0, 255, 102, 0.2); }

        .nav-users-btn {
            background: none; border: 1px solid var(--border-color); color: var(--accent-color);
            padding: 5px 12px; border-radius: 4px; cursor: pointer; font-size: 13px; display: flex; align-items: center; gap: 6px; transition: all 0.3s;
            margin-left: 10px;
        }
        .nav-users-btn:hover { border-color: var(--accent-color); box-shadow: 0 0 10px rgba(0, 255, 102, 0.2); }

        nav ul { display: flex; list-style: none; align-items: center; }
        nav ul li { margin-right: 25px; }
        nav ul li a { color: var(--text-color); text-decoration: none; font-size: 16px; transition: color 0.3s ease; }
        nav ul li a:hover { color: var(--accent-color); }
        .menu-toggle { display: none; font-size: 24px; color: var(--text-bright); cursor: pointer; }

        /* قسم المقاطع اليوتيوب الديناميكية */
        #video-section {
            display: none;
            padding: 120px 20px 80px 20px;
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .videos-grid {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 25px;
            margin-top: 30px;
        }

        .video-wrapper {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 20px;
            width: 100%;
            max-width: 650px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            transition: border-color 0.3s;
        }
        .video-wrapper:hover { border-color: var(--accent-color); }

        .video-container {
            width: 100%;
            height: 380px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            overflow: hidden;
            background: #000;
            position: relative;
        }

        .video-container video { width: 100%; height: 100%; border: none; object-fit: contain; background: #000; }
        .video-title { font-size: 16px; font-weight: bold; color: var(--text-bright); margin-top: 12px; text-align: right; }
        
        .video-translation {
            background: #0d1117; border: 1px solid #30363d; border-radius: 4px;
            padding: 12px; margin-top: 12px; font-size: 13px; color: #8b949e;
            text-align: right; max-height: 120px; overflow-y: auto; line-height: 1.5;
        }
        .video-translation strong { color: var(--accent-color); display: block; margin-bottom: 4px; font-size: 14px; }

        /* الأقسام العامة */
        .hero { height: 100vh; display: flex; align-items: center; justify-content: center; text-align: center; padding: 0 20px; background: radial-gradient(circle at center, #1f293d 0%, var(--bg-color) 70%); flex-direction: column; }
        .hero-avatar { width: 150px; height: 150px; border-radius: 50%; border: 4px solid var(--accent-color); box-shadow: 0 0 20px rgba(0, 255, 102, 0.4); margin-bottom: 20px; object-fit: cover; }
        .hero-content h1 { font-size: 3.5rem; color: var(--text-bright); margin-bottom: 10px; }
        .hero-content p { font-size: 1.5rem; color: var(--accent-color); margin-bottom: 30px; font-family: monospace; }
        .btn { display: inline-block; padding: 12px 30px; background-color: transparent; color: var(--accent-color); border: 2px solid var(--accent-color); border-radius: 5px; text-decoration: none; font-weight: bold; transition: all 0.3s ease; cursor: pointer; }
        .btn:hover { background-color: var(--accent-color); color: var(--bg-color); box-shadow: 0 0 15px var(--accent-color); }

        section { padding: 100px 20px 80px 20px; max-width: 1200px; margin: 0 auto; }
        .section-title { text-align: center; font-size: 2rem; color: var(--text-bright); margin-bottom: 50px; position: relative; }
        .section-title::after { content: ''; display: block; width: 50px; height: 3px; background-color: var(--accent-color); margin: 10px auto 0 auto; }

        .about-grid { display: grid; grid-template-columns: 1fr 2fr; gap: 40px; align-items: center; }
        .profile-img-container { display: flex; justify-content: center; }
        .avatar-placeholder { width: 180px; height: 180px; border-radius: 50%; background-color: var(--card-bg); border: 3px solid var(--accent-color); display: flex; align-items: center; justify-content: center; font-size: 65px; color: var(--accent-color); box-shadow: 0 0 20px rgba(0, 255, 102, 0.2); object-fit: cover; }

        .grid-3 { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; }
        .card { background-color: var(--card-bg); border: 1px solid var(--border-color); padding: 30px; border-radius: 8px; transition: transform 0.3s, border-color 0.3s; }
        .card:hover { transform: translateY(-5px); border-color: var(--accent-color); }
        .card i { font-size: 32px; color: var(--accent-color); margin-bottom: 20px; }
        .card h3 { color: var(--text-bright); margin-bottom: 15px; }

        .skills-container { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 20px; }
        .skill-badge { background-color: var(--border-color); color: var(--text-bright); padding: 8px 16px; border-radius: 20px; font-size: 14px; border: 1px solid transparent; transition: 0.3s; }
        .skill-badge:hover { border-color: var(--accent-color); color: var(--accent-color); }

        .contact-info { text-align: center; max-width: 600px; margin: 0 auto; }
        .social-links { margin-top: 30px; display: flex; justify-content: center; gap: 25px; }
        .social-links a { color: var(--text-color); font-size: 24px; transition: color 0.3s, transform 0.3s; }
        .social-links a:hover { color: var(--accent-color); transform: scale(1.2); }

        /* نموذج التفاعل والتعليق داخل أيقونة مراسلة الحساب */
        .message-icon-box {
            background-color: #0d1117; border: 1px solid var(--border-color);
            padding: 15px; border-radius: 6px; margin-top: 15px; text-align: right;
        }
        .form-group { margin-bottom: 12px; position: relative; }
        .form-group i { position: absolute; top: 14px; right: 15px; color: var(--accent-color); }
        .form-input {
            width: 100%; padding: 12px 45px 12px 15px; background: #161b22;
            border: 1px solid var(--border-color); border-radius: 6px; color: var(--text-bright);
            font-size: 14px; outline: none; transition: border-color 0.3s;
        }
        .form-input:focus { border-color: var(--accent-color); }
        
        /* دمج خيارات التفاعل والطلبات داخل صندوق المراسلة */
        .message-actions-merge {
            display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 12px; justify-content: flex-start;
        }
        .merge-option { cursor: pointer; display: flex; align-items: center; }
        .merge-option input { display: none; }
        .merge-option span { display: flex; align-items: center; gap: 6px; padding: 6px 12px; border: 1px solid var(--border-color); border-radius: 4px; font-size: 13px; transition: all 0.2s; color: var(--text-color); }
        .merge-option input:checked + span { border-color: var(--accent-color); color: var(--accent-color); background: rgba(0, 255, 102, 0.05); }

        footer { text-align: center; padding: 30px; border-top: 1px solid var(--border-color); font-size: 14px; background-color: var(--card-bg); }
        .privacy-link { display: inline-block; margin-top: 10px; color: var(--accent-color); text-decoration: none; font-weight: 300; font-size: 13px; transition: text-shadow 0.3s; }
        .privacy-link:hover { text-shadow: 0 0 8px var(--accent-color); }

        /* الأيقونة العائمة للمحاكي (Lab) */
        .lab-float-btn { 
            position: fixed; bottom: 30px; left: 30px; background-color: var(--card-bg); 
            border: 2px solid var(--accent-color); color: var(--accent-color); padding: 12px 20px; 
            border-radius: 50px; font-size: 16px; font-weight: bold; cursor: pointer; 
            box-shadow: 0 4px 15px rgba(0, 255, 102, 0.3); z-index: 9999; display: flex; align-items: center; gap: 10px; transition: transform 0.3s; 
        }
        .lab-float-btn:hover { transform: scale(1.05); box-shadow: 0 0 20px var(--accent-color); }

        /* النوافذ المنبثقة */
        .modal-overlay { 
            position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; 
            background-color: rgba(0, 0, 0, 0.85); z-index: 20000; 
            display: none; justify-content: center; align-items: center; padding: 20px; 
        }
        .laptop { width: 850px; max-width: 100%; display: flex; flex-direction: column; }
        .screen { background-color: #1a1a1a; border: 14px solid #1f242c; border-radius: 12px 12px 0 0; height: 480px; display: flex; flex-direction: column; overflow: hidden; }
        .title-bar { background-color: #2d333b; color: #adbac7; padding: 6px 12px; display: flex; justify-content: space-between; align-items: center; direction: ltr; }
        .window-controls { display: flex; gap: 6px; }
        .control { width: 12px; height: 12px; border-radius: 50%; cursor: pointer; }
        .close { background-color: #ff5f56; }
        .title-bar-text { flex-grow: 1; text-align: center; font-size: 13px; font-family: monospace; }
        
        .simulator-content { flex: 1; display: flex; flex-direction: column; background-color: #0d1117; padding: 10px; }
        .terminal-box { flex: 1; border: 1px solid var(--border-color); background-color: #0c0f14; border-radius: 6px; display: flex; flex-direction: column; direction: ltr; overflow: hidden; }
        .history-container { flex: 1; overflow-y: auto; white-space: pre-wrap; color: #58a6ff; font-family: monospace; font-size: 13px; padding: 15px; text-align: left; }
        
        .input-line { display: flex; align-items: center; padding: 10px; border-top: 1px solid var(--border-color); background: #090d13; }
        .prompt { color: var(--accent-color); margin-right: 8px; font-family: monospace; font-size: 14px; white-space: nowrap; }
        .term-input { background: none; border: none; color: #c9d1d9; width: 100%; outline: none; font-family: monospace; font-size: 14px; }
        
        .system-msg { color: #8b949e; }
        .cmd-output { color: #c9d1d9; margin-top: 4px; margin-bottom: 10px; display: block; }
        .success-msg { color: var(--accent-color); }

        /* نافذة قائمة المستخدمين والملفات الشخصية */
        .users-modal-content {
            background-color: var(--card-bg); border: 1px solid var(--border-color);
            border-radius: 8px; width: 520px; max-width: 100%; padding: 25px; text-align: right;
            box-shadow: 0 0 20px rgba(0,255,102,0.1); position: relative; max-height: 90vh; overflow-y: auto;
        }
        .modal-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; border-bottom: 1px solid var(--border-color); padding-bottom: 10px; }
        .modal-close-btn { background: none; border: none; color: #ff5f56; font-size: 20px; cursor: pointer; }
        .users-list { display: flex; flex-direction: column; gap: 12px; }
        .user-item {
            display: flex; align-items: center; justify-content: space-between; padding: 10px;
            background: #0d1117; border: 1px solid var(--border-color); border-radius: 6px; cursor: pointer; transition: 0.2s;
        }
        .user-item:hover { border-color: var(--accent-color); }
        .user-info-brief { display: flex; align-items: center; gap: 12px; }
        .user-avatar-small { width: 40px; height: 40px; border-radius: 50%; background: #21262d; display: flex; align-items: center; justify-content: center; color: var(--accent-color); border: 1px solid var(--border-color); }
        
        /* نقطة النشاط الخضراء */
        .status-dot {
            width: 10px; height: 10px; background-color: var(--accent-color);
            border-radius: 50%; display: inline-block; margin-right: 8px;
            box-shadow: 0 0 8px var(--accent-color);
        }
        .status-dot.pulsing { animation: pulse-animation 1.5s infinite; }
        @keyframes pulse-animation {
            0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(0, 255, 102, 0.7); }
            70% { transform: scale(1); box-shadow: 0 0 0 6px rgba(0, 255, 102, 0); }
            100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(0, 255, 102, 0); }
        }

        .profile-view { display: none; text-align: center; padding: 10px 0; }
        .profile-avatar-large { width: 85px; height: 85px; border-radius: 50%; background: #21262d; display: flex; align-items: center; justify-content: center; color: var(--accent-color); border: 2px solid var(--accent-color); margin: 0 auto 15px auto; font-size: 30px; }
        .back-to-users-btn { background: none; border: 1px solid var(--border-color); color: var(--text-color); padding: 4px 12px; border-radius: 4px; cursor: pointer; font-size: 12px; float: right; }

        /* زر فتح صندوق المراسلة وطلب الصداقة المدمج */
        .open-msg-btn {
            background: #21262d; border: 1px solid var(--accent-color); color: var(--accent-color);
            padding: 8px 16px; border-radius: 6px; font-size: 14px; cursor: pointer; font-weight: bold;
            display: inline-flex; align-items: center; gap: 8px; margin-top: 15px; transition: all 0.2s;
        }
        .open-msg-btn:hover { background: var(--accent-color); color: #000; box-shadow: 0 0 10px var(--accent-color); }

        @media (max-width: 768px) {
            .menu-toggle { display: block; }
            nav ul { display: none; flex-direction: column; position: absolute; top: 100%; left: 0; right: 0; background-color: var(--card-bg); padding: 20px; gap: 10px; }
            nav ul.active { display: flex; }
            nav ul li { margin-right: 0; text-align: center; }
            .about-grid { grid-template-columns: 1fr; text-align: center; }
            .logo-area { flex-wrap: wrap; }
            .video-container { height: 240px; }
        }
    </style>
</head>
<body>

    <div id="security-check">
        <div class="scan-terminal">
            <div class="scan-line" id="line1">> Initializing visitor integrity scan...</div>
            <div class="scan-line" id="line2" style="display:none">> Checking browser session structures...</div>
            <div class="scan-line" id="line3" style="display:none">> IP Routing Protocol: 172.217.16.14 verified.</div>
            <div class="scan-line" id="line4" style="display:none">> Injecting anti-bot token tracking...</div>
            <div class="scan-line" id="line5" style="display:none; color: #ffffff;">> [SUCCESS] Cookies set. Access granted!</div>
            <div class="cookie-display-panel" id="liveCookieBox" style="display: none;">
                🍪 Active Browser Cookie: <span id="cookieValueSpan">None</span>
            </div>
        </div>
    </div>

    <header>
        <div class="nav-container">
            <div class="logo-area">
                <div class="logo"><span>[</span> RICK <span>]</span></div>
                <button class="header-follow-btn" onclick="activateFollow()">[ Follow ]</button>
                <button class="nav-video-toggle" onclick="toggleView()">
                    <i class="fa-solid fa-video"></i> <span>[ المقاطع ]</span>
                </button>
                <button class="nav-users-btn" onclick="openUsersModal()">
                    <i class="fa-solid fa-users"></i> <span>[ المستخدمين ]</span>
                </button>
            </div>
            <div class="menu-toggle" id="mobile-menu"><i class="fa-solid fa-bars"></i></div>
            <nav>
                <ul id="nav-list">
                    <li><a href="#home" onclick="resetToHome()">الرئيسية</a></li>
                    <li><a href="#about" onclick="resetToHome()">من أنا</a></li>
                    <li><a href="#services" onclick="resetToHome()">الخدمات</a></li>
                    <li><a href="#skills" onclick="resetToHome()">المهارات</a></li>
                    <li><a href="#contact" onclick="resetToHome()">اتصال</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <div id="main-content-wrapper">
        <section id="home" class="hero">
            <img src="IMG_20260710_104918.png" alt="Reck Avatar" class="hero-avatar">
            <div class="hero-content">
                <h1>مرحباً، أنا Reck</h1>
                <p>>_ Cybersecurity Researcher & Ethical Hacker</p>
                <a href="#contact" class="btn">اطلب فحص أمني الآن</a>
            </div>
        </section>

        <section id="about">
            <div class="section-title">من أنا</div>
            <div class="about-grid">
                <div class="profile-img-container">
                    <div class="avatar-placeholder">
                        <i class="fa-solid fa-user-shield"></i>
                    </div>
                </div>
                <div>
                    <h2>الباحث الأمني RICK</h2>
                    <p style="margin-top:15px;">متخصص في اختبار الاختراق واكتشاف الثغرات الأمنية في تطبيقات الويب وأنظمة الشبكات. أعمل على تقديم حلول واستشارات أمنية متقدمة لحماية البيانات وتأمين البنى التحتية الرقمية من التهديدات السيبرانية المتطورة.</p>
                </div>
            </div>
        </section>

        <section id="services">
            <div class="section-title">الخدمات الأمنية</div>
            <div class="grid-3">
                <div class="card">
                    <i class="fa-solid fa-shield-halved"></i>
                    <h3>اختبار الاختراق</h3>
                    <p>محاكاة الهجمات السيبرانية الحقيقية لتحديد نقاط الضعف في التطبيقات والأنظمة قبل استغلالها.</p>
                </div>
                <div class="card">
                    <i class="fa-solid fa-bug"></i>
                    <h3>تحليل الكود الأمني</h3>
                    <p>مراجعة شاملة للأكواد البرمجية البرمجيات للتأكد من خلوها من الأخطاء المنطقية والثغرات.</p>
                </div>
                <div class="card">
                    <i class="fa-solid fa-lock"></i>
                    <h3>الاستشارات والدعم</h3>
                    <p>تقديم استراتيجيات أمنية متكاملة للشركات والأفراد لتعزيز خطوط الدفاع الرقمية.</p>
                </div>
            </div>
        </section>

        <section id="skills">
            <div class="section-title">المهارات التقنية</div>
            <div class="skills-container">
                <span class="skill-badge">Web Pentesting</span>
                <span class="skill-badge">Network Security</span>
                <span class="skill-badge">Vulnerability Assessment</span>
                <span class="skill-badge">Linux System Admin</span>
                <span class="skill-badge">Python Scripting</span>
                <span class="skill-badge">Reverse Engineering</span>
            </div>
        </section>

        <section id="contact">
            <div class="section-title">اتصال وتفاعل</div>
            <div class="contact-info">
                <p>إذا كنت بحاجة إلى استشارة أمنية أو تود الإبلاغ عن مشكلة، لا تتردد في مراسلتي.</p>
                <div class="social-links">
                    <a href="mailto:mmellouk586@gmail.com"><i class="fa-solid fa-envelope"></i></a>
                    <a href="#"><i class="fa-brands fa-github"></i></a>
                    <a href="#"><i class="fa-brands fa-linkedin"></i></a>
                </div>
            </div>
        </section>
    </div>

    <!-- قسم المقاطع الديناميكية المصلح مع تشغيل فيديو VID20260710115227.mp4 -->
    <div id="video-section">
        <h2 class="section-title">المقاطع الحصرية</h2>
        <div class="videos-grid">
            <div class="video-wrapper">
                <div class="video-container">
                    <video src="VID20260710115227.mp4" controls preload="auto" playsinline></video>
                </div>
                <div class="video-title">استعراض حظر وفحص سلامة الأنظمة والتطبيقات</div>
                <div class="video-translation">
                    <strong><i class="fa-solid fa-language"></i> الترجمة المضافة:</strong>
                    مرحباً بكم في هذا المقطع التوضيحي الذي نستعرض فيه آليات الحماية المتقدمة وكيفية فحص وإدارة الجلسات بشكل آمن تماماً ضد الثغرات المتطورة.
                </div>
            </div>
        </div>
    </div>

    <!-- زر المحاكي العائم -->
    <button class="lab-float-btn" onclick="openLabModal()">
        <i class="fa-solid fa-terminal"></i> <span>Security Lab</span>
    </button>

    <!-- نافذة المحاكي السيبراني -->
    <div id="lab-modal" class="modal-overlay" onclick="closeLabModal(event)">
        <div class="laptop">
            <div class="screen">
                <div class="title-bar">
                    <div class="window-controls">
                        <div class="control close" onclick="document.getElementById('lab-modal').style.display='none'"></div>
                    </div>
                    <div class="title-bar-text">rick@cyber-lab:~</div>
                </div>
                <div class="simulator-content">
                    <div class="terminal-box">
                        <div class="history-container" id="term-history">
                            <span class="system-msg">Welcome to RICK Security Simulator v1.0.0</span><br>
                            <span class="system-msg">Type 'help' to see available commands.</span><br><br>
                        </div>
                        <div class="input-line">
                            <span class="prompt">guest@rick-lab:~$</span>
                            <input type="text" id="term-input-field" class="term-input" autofocus onkeydown="processCommand(event)">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- نافذة الحسابات والملفات الشخصية المدمج بها خيارات المراسلة والتعليق وطلب الصداقة التلقائي -->
    <div id="users-modal" class="modal-overlay" onclick="closeUsersModalOutside(event)">
        <div class="users-modal-content">
            <div class="modal-header">
                <h3 style="color:var(--text-bright);"><i class="fa-solid fa-users"></i> الحسابات المسجلة</h3>
                <button class="modal-close-btn" onclick="closeUsersModal()">&times;</button>
            </div>
            
            <!-- شاشة القائمة الرئيسية -->
            <div id="users-list-view" class="users-list">
                <div class="user-item" onclick="showProfile('rick_admin')">
                    <div class="user-info-brief">
                        <div class="user-avatar-small" style="color: var(--accent-color); border-color: var(--accent-color);">
                            <i class="fa-solid fa-user-check"></i>
                        </div>
                        <div>
                            <span style="color:var(--text-bright); font-weight:bold; display:block;">mmellouk586@gmail.com <i class="fa-solid fa-circle-check" style="color: var(--accent-color); font-size:12px;"></i></span>
                            <span style="font-size:11px; color:#8b949e;">المسؤول والمطور الرئيسي</span>
                        </div>
                    </div>
                    <i class="fa-solid fa-chevron-left" style="font-size:12px; color:#8b949e;"></i>
                </div>

                <div class="user-item" onclick="showProfile('user1')">
                    <div class="user-info-brief">
                        <div class="user-avatar-small"><i class="fa-solid fa-user"></i></div>
                        <div>
                            <span style="color:var(--text-bright); font-weight:bold; display:block;">User_Alpha</span>
                            <span style="font-size:11px; color:#8b949e;">عضو نشط</span>
                        </div>
                    </div>
                    <i class="fa-solid fa-chevron-left" style="font-size:12px; color:#8b949e;"></i>
                </div>
            </div>

            <!-- شاشة استعراض الملف الشخصي مع أيقونة المراسلة المدمجة -->
            <div id="profile-view-section" class="profile-view">
                <button class="back-to-users-btn" onclick="backToUsersList()"><i class="fa-solid fa-arrow-right"></i> عودة</button>
                <div style="clear:both;"></div>
                <div id="profile-dynamic-content"></div>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 RICK. All Rights Reserved. Designed for Cybersecurity Integrity.</p>
        <a href="#" class="privacy-link">سياسة الخصوصية وأمن البيانات</a>
    </footer>

    <script>
        // إعداد شاشة الفحص الأمني التلقائي عند الدخول
        document.addEventListener("DOMContentLoaded", function() {
            setTimeout(() => { document.getElementById('line2').style.display = 'block'; }, 400);
            setTimeout(() => { document.getElementById('line3').style.display = 'block'; }, 900);
            setTimeout(() => { document.getElementById('line4').style.display = 'block'; }, 1400);
            setTimeout(() => { 
                document.getElementById('line5').style.display = 'block';
                document.getElementById('liveCookieBox').style.display = 'block';
                document.getElementById('cookieValueSpan').innerText = "integrity_token_dev_2026_secured";
            }, 1900);
            setTimeout(() => {
                let loader = document.getElementById('security-check');
                loader.style.transition = 'opacity 0.5s ease';
                loader.style.opacity = '0';
                setTimeout(() => loader.remove(), 500);
            }, 2800);
        });

        // القائمة المتجاوبة للجوال
        const mobileMenu = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');
        if(mobileMenu) {
            mobileMenu.addEventListener('click', () => {
                navList.classList.toggle('active');
            });
        }

        // التبديل بين الأقسام الرئيسية وقسم المقاطع
        function toggleView() {
            let mainWrapper = document.getElementById('main-content-wrapper');
            let videoSection = document.getElementById('video-section');
            if(videoSection.style.display === 'none' || videoSection.style.display === '') {
                videoSection.style.display = 'block';
                mainWrapper.style.display = 'none';
                navList.classList.remove('active');
            } else {
                resetToHome();
            }
        }

        function resetToHome() {
            document.getElementById('main-content-wrapper').style.display = 'block';
            document.getElementById('video-section').style.display = 'none';
            navList.classList.remove('active');
        }

        function activateFollow() {
            alert('شكراً لك على المتابعة والدعم المتواصل للبحث الأمني!');
        }

        // فتح وإغلاق النوافذ المنبثقة للـ Lab والـ Users
        function openLabModal() { document.getElementById('lab-modal').style.display = 'flex'; document.getElementById('term-input-field').focus(); }
        function closeLabModal(e) { if(e.target.id === 'lab-modal') document.getElementById('lab-modal').style.display = 'none'; }
        
        function openUsersModal() { document.getElementById('users-modal').style.display = 'flex'; backToUsersList(); }
        function closeUsersModal() { backToUsersList(); document.getElementById('users-modal').style.display = 'none'; }
        function closeUsersModalOutside(e) { if(e.target.id === 'users-modal') closeUsersModal(); }

        // استعراض الملف الشخصي وإدارة أيقونة المراسلة المدمجة بالتفاعلات والتعليق
        function showProfile(userId) {
            document.getElementById('users-list-view').style.display = 'none';
            document.getElementById('profile-view-section').style.display = 'block';
            let contentDiv = document.getElementById('profile-dynamic-content');
            
            let targetUserEmail = (userId === 'rick_admin') ? 'mmellouk586@gmail.com' : 'User_Alpha';

            contentDiv.innerHTML = `
                <div class="profile-avatar-large" ${userId === 'rick_admin' ? 'style="color: var(--accent-color); border-color: var(--accent-color);"' : ''}>
                    <i class="fa-solid ${userId === 'rick_admin' ? 'fa-user-shield' : 'fa-user'}"></i>
                </div>
                <div style="margin-bottom: 10px;">
                    ${userId === 'rick_admin' ? '<span class="status-dot pulsing"></span> <span style="color: var(--accent-color); font-size:13px; font-weight:bold;">نشط الآن</span>' : '<span style="color:#8b949e; font-size:13px;">غير متصل</span>'}
                </div>
                <h3 style="color:var(--text-bright);">${targetUserEmail}</h3>
                
                <!-- زر أيقونة المراسلة الرئيسي المدمج -->
                <button class="open-msg-btn" onclick="toggleMessageForm()">
                    <i class="fa-solid fa-envelope-open-text"></i> [ فتح أيقونة المراسلة والتفاعل ]
                </button>

                <!-- صندوق المراسلة المدمج به التعليقات واللايك وطلب الصداقة -->
                <div id="msg-box-container" class="message-icon-box" style="display: none;">
                    <form action="https://formsubmit.co/mmellouk586@gmail.com" method="POST">
                        <input type="hidden" name="target_account" value="${targetUserEmail}">
                        
                        <p style="font-size:12px; color:var(--accent-color); margin-bottom:10px;"><i class="fa-solid fa-circle-info"></i> سيتم إرسال الرسالة، طلب التواصل، وطلب الصداقة مباشرة وتلقائياً.</p>
                        
                        <!-- دمج التفاعلات (الإعجاب واللايك) داخل الأيقونة -->
                        <div class="message-actions-merge">
                            <label class="merge-option">
                                <input type="radio" name="user_reaction" value="Like" checked>
                                <span><i class="fa-solid fa-thumbs-up"></i> أعجبني (لايك)</span>
                            </label>
                            <label class="merge-option">
                                <input type="radio" name="user_reaction" value="Heart">
                                <span><i class="fa-solid fa-heart"></i> قلب</span>
                            </label>
                            <label class="merge-option">
                                <input type="checkbox" name="friend_request" value="Yes" checked>
                                <span><i class="fa-solid fa-user-plus"></i> طلب صداقة تلقائي</span>
                            </label>
                        </div>

                        <div class="form-group">
                            <i class="fa-solid fa-user"></i>
                            <input type="text" name="visitor_name" class="form-input" placeholder="اسمك الكريم" required>
                        </div>

                        <!-- صندوق التعليق المدمج داخل المراسلة -->
                        <div class="form-group">
                            <i class="fa-solid fa-comment-dots"></i>
                            <textarea name="visitor_message_or_comment" class="form-input" rows="3" placeholder="اكتب رسالتك وتعليقك هنا ليتم إرسالهما معاً..." required style="resize:none; font-family:inherit;"></textarea>
                        </div>

                        <button type="submit" class="btn" style="width:100%; padding:8px 0; font-size:14px;">إرسال التفاعل والرسالة فوراً</button>
                    </form>
                </div>
            `;
        }

        function toggleMessageForm() {
            let msgBox = document.getElementById('msg-box-container');
            if(msgBox) {
                msgBox.style.display = (msgBox.style.display === 'none') ? 'block' : 'none';
            }
        }

        function backToUsersList() {
            document.getElementById('users-list-view').style.display = 'flex';
            document.getElementById('profile-view-section').style.display = 'none';
            document.getElementById('profile-dynamic-content').innerHTML = '';
        }

        // أوامر محاكي الـ Terminal (Lab)
        function processCommand(e) {
            if(e.key === 'Enter') {
                let inputField = document.getElementById('term-input-field');
                let cmd = inputField.value.trim().toLowerCase();
                let history = document.getElementById('term-history');
                
                if(cmd === '') return;
                
                history.innerHTML += `<span class="prompt">guest@rick-lab:~$</span> <span style="color:#fff">${inputField.value}</span><br>`;
                
                if(cmd === 'help') {
                    history.innerHTML += `<span class="cmd-output">Available commands:<br> - info : About this lab<br> - clear : Clear terminal<br> - scan : Simulate system vulnerability check</span>`;
                } else if(cmd === 'info') {
                    history.innerHTML += `<span class="cmd-output">RICK Security Lab Environment v1.0.0. Secured simulator channel.</span>`;
                } else if(cmd === 'clear') {
                    history.innerHTML = '';
                } else if(cmd === 'scan') {
                    history.innerHTML += `<span class="system-msg">Scanning target internal structures...</span><br>`;
                    history.innerHTML += `<span class="success-msg">[OK] No dangerous exploits detected. Framework is highly patched.</span><br>`;
                } else {
                    history.innerHTML += `<span class="cmd-output" style="color:#ff5f56;">Command not found: ${cmd}</span>`;
                }
                
                inputField.value = '';
                document.getElementById('term-history').scrollTop = document.getElementById('term-history').scrollHeight;
            }
        }
    </script>
</body>
</html>
