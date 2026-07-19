<!DOCTYPE html>
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
            --accent-hover: rgba(0, 255, 102, 0.15);
            --text-color: #c9d1d9;
            --text-bright: #ffffff;
            --border-color: #30363d;
            --overlay-bg: rgba(22, 27, 34, 0.85);
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

        .nav-video-toggle, .nav-users-btn {
            background: none; border: 1px solid var(--border-color); color: var(--accent-color);
            padding: 5px 12px; border-radius: 4px; cursor: pointer; font-size: 13px; display: flex; align-items: center; gap: 6px; transition: all 0.3s;
            margin-left: 10px;
        }
        .nav-video-toggle:hover, .nav-users-btn:hover { border-color: var(--accent-color); box-shadow: 0 0 10px rgba(0, 255, 102, 0.2); }

        nav ul { display: flex; list-style: none; align-items: center; }
        nav ul li { margin-right: 25px; }
        nav ul li a { color: var(--text-color); text-decoration: none; font-size: 16px; transition: color 0.3s ease; }
        nav ul li a:hover { color: var(--accent-color); }
        .menu-toggle { display: none; font-size: 24px; color: var(--text-bright); cursor: pointer; }

        /* قسم المقاطع الجديد المدمج كلياً */
        #video-section {
            display: none;
            padding: 120px 20px 80px 20px;
            max-width: 800px;
            margin: 0 auto;
        }

        .videos-grid {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 35px;
            margin-top: 30px;
        }

        /* حاوية الفيديو الشاملة بنظام المنصات الحديثة */
        .modern-video-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            width: 100%;
            max-width: 650px;
            overflow: hidden;
            box-shadow: 0 8px 24px rgba(0,0,0,0.4);
            position: relative;
            transition: border-color 0.3s, transform 0.3s;
        }
        .modern-video-card:hover { border-color: var(--accent-color); transform: translateY(-2px); }

        /* منطقة تشغيل الفيديو المدمجة مع أدوات التفاعل */
        .video-player-frame {
            position: relative;
            width: 100%;
            height: 420px;
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .video-player-frame video {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }

        /* الأزرار العائمة الجانبية (مثل تيك توك و ريلز) */
        .video-floating-actions {
            position: absolute;
            left: 15px;
            bottom: 80px;
            display: flex;
            flex-direction: column;
            gap: 15px;
            z-index: 10;
        }

        .action-circle-btn {
            width: 45px;
            height: 45px;
            background: rgba(0, 0, 0, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: #fff;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.2s ease;
            backdrop-filter: blur(5px);
        }
        .action-circle-btn:hover {
            transform: scale(1.1);
            border-color: var(--accent-color);
            color: var(--accent-color);
        }
        .action-circle-btn i { font-size: 18px; }
        .action-circle-btn span { font-size: 10px; margin-top: 2px; font-weight: bold; }
        .action-circle-btn.active i { color: #ff3366; animation: heartBeat 0.3s ease-in-out; }

        @keyframes heartBeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.3); }
            100% { transform: scale(1); }
        }

        /* شريط البيانات السفلي المدمج فوق الفيديو */
        .video-bottom-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0,0,0,0.95));
            padding: 20px 15px 15px 15px;
            color: #fff;
            text-align: right;
            pointer-events: none;
        }
        .video-bottom-overlay * { pointer-events: auto; }
        .video-overlay-title { font-size: 15px; font-weight: 700; color: var(--text-bright); margin-bottom: 5px; }
        .video-overlay-desc { font-size: 12px; color: #b3b3b3; max-height: 50px; overflow-y: auto; }

        /* نافذة/درج الردود والتعليقات المدمج التفاعلي */
        .video-comments-tray {
            background: #11161d;
            border-top: 1px solid var(--border-color);
            padding: 15px;
            text-align: right;
        }

        .tray-interactive-form {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .tray-input-wrapper {
            position: relative;
            display: flex;
            align-items: center;
        }
        .tray-input-wrapper i {
            position: absolute;
            right: 15px;
            color: var(--accent-color);
        }
        .tray-input {
            width: 100%;
            padding: 10px 40px 10px 80px;
            background: #0d1117;
            border: 1px solid var(--border-color);
            border-radius: 20px;
            color: var(--text-bright);
            font-size: 13px;
            outline: none;
            transition: border-color 0.3s;
        }
        .tray-input:focus { border-color: var(--accent-color); }

        .tray-submit-btn {
            position: absolute;
            left: 5px;
            background: var(--accent-color);
            color: #000;
            border: none;
            padding: 6px 14px;
            border-radius: 15px;
            font-size: 12px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.2s;
        }
        .tray-submit-btn:hover { background: #00cc52; }

        /* خيارات التفاعل السريع بنمط الكبسولات */
        .quick-interaction-capsules {
            display: flex;
            gap: 8px;
            overflow-x: auto;
            padding-bottom: 5px;
        }
        .capsule-option { cursor: pointer; }
        .capsule-option input { display: none; }
        .capsule-option span {
            display: inline-block;
            padding: 4px 12px;
            background: #1f242c;
            border: 1px solid var(--border-color);
            border-radius: 15px;
            font-size: 12px;
            color: var(--text-color);
            white-space: nowrap;
            transition: all 0.2s;
        }
        .capsule-option input:checked + span {
            border-color: var(--accent-color);
            color: var(--accent-color);
            background: var(--accent-hover);
        }

        /* الأقسام العامة المستقرة */
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
        
        .status-dot {
            width: 10px; height: 10px; background-color: var(--accent-color);
            border-radius: 50%; display: inline-block; margin-right: 8px;
            box-shadow: 0 0 8px var(--accent-color);
        }
        .status-dot.pulsing { animation: pulse-animation 1.5s infinite; }

        .profile-view { display: none; text-align: center; padding: 10px 0; }
        .profile-avatar-large { width: 85px; height: 85px; border-radius: 50%; background: #21262d; display: flex; align-items: center; justify-content: center; color: var(--accent-color); border: 2px solid var(--accent-color); margin: 0 auto 15px auto; font-size: 30px; }
        .back-to-users-btn { background: none; border: 1px solid var(--border-color); color: var(--text-color); padding: 4px 12px; border-radius: 4px; cursor: pointer; font-size: 12px; float: right; }

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
            .video-player-frame { height: 280px; }
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
                </ul>
            </nav>
        </div>
    </header>

    <!-- واجهة عرض الصفحة الرئيسية التقليدية -->
    <div id="main-content-view">
        <section class="hero" id="home">
            <div class="avatar-placeholder hero-avatar"><i class="fa-solid fa-user-shield"></i></div>
            <div class="hero-content">
                <h1>RICK</h1>
                <p>Cyber Security Researcher & Ethical Hacker</p>
                <a href="#about" class="btn">اكتشف المزيد</a>
            </div>
        </section>

        <section id="about">
            <h2 class="section-title">من أنا</h2>
            <div class="about-grid">
                <div class="profile-img-container">
                    <div class="avatar-placeholder"><i class="fa-solid fa-terminal"></i></div>
                </div>
                <div>
                    <h3>مرحباً بك في عالم الحماية واختبار الاختراق</h3>
                    <p style="margin-top:15px;">متخصص في تقييم الثغرات الأمنية البرمجية وحماية الشبكات الافتراضية.</p>
                    <div class="skills-container">
                        <span class="skill-badge">Nmap Expert</span>
                        <span class="skill-badge">Penetration Testing</span>
                        <span class="skill-badge">Python Scripting</span>
                        <span class="skill-badge">Web Application Security</span>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- قسم المقاطع بالتصميم المدمج الجديد تماماً -->
    <main id="video-section">
        <h2 class="section-title">المقاطع الأمنية والتعليمية</h2>
        <div class="videos-grid">
            
            <!-- كرت فيديو متكامل مدمج الأدوات -->
            <article class="modern-video-card" id="video-card-1">
                <div class="video-player-frame">
                    <video id="main-video-element" controls preload="metadata">
                        <source src="your-video-file.mp4" type="video/mp4">
                        متصفحك لا يدعم تشغيل الفيديو.
                    </video>

                    <!-- الأزرار العائمة الجانبية (مثل تطبيقات الفيديو الحديثة) -->
                    <div class="video-floating-actions">
                        <button class="action-circle-btn" onclick="handleLike(this)" title="إعجاب">
                            <i class="fa-solid fa-heart"></i>
                            <span class="count">0</span>
                        </button>
                        <button class="action-circle-btn" onclick="focusCommentInput('comment-text-1')" title="تعليق">
                            <i class="fa-solid fa-comment"></i>
                            <span>رد</span>
                        </button>
                        <button class="action-circle-btn" onclick="shareVideo()" title="مشاركة">
                            <i class="fa-solid fa-share"></i>
                        </button>
                    </div>

                    <!-- شريط البيانات الشفاف السفلي للمقطع -->
                    <div class="video-bottom-overlay">
                        <h3 class="video-overlay-title">شرح تقنيات هندسة فحص الجلسات والملفات</h3>
                        <div class="video-overlay-desc">
                            استعراض حي لآليات قراءة وحقن قيم تتبع المتصفح ومحاكاة الثغرات المتقدمة.
                        </div>
                    </div>
                </div>

                <!-- درج التعليقات السريع المدمج أسفل المقطع مباشرة -->
                <div class="video-comments-tray">
                    <form class="tray-interactive-form" onsubmit="submitCommentForm(event, 'comment-text-1', 'capsule-group-1')">
                        
                        <!-- خيارات كبسولات الرد السريع للتفاعل بنقرة واحدة -->
                        <div class="quick-interaction-capsules" id="capsule-group-1">
                            <label class="capsule-option">
                                <input type="radio" name="reaction_type_1" value="🔥 مذهل">
                                <span>🔥 مذهل</span>
                            </label>
                            <label class="capsule-option">
                                <input type="radio" name="reaction_type_1" value="💡 استفسار تقني">
                                <span>💡 استفسار تقني</span>
                            </label>
                            <label class="capsule-option">
                                <input type="radio" name="reaction_type_1" value="🛡️ شكراً جزيلاً">
                                <span>🛡️ شكراً جزيلاً</span>
                            </label>
                        </div>

                        <!-- حقل النص الإدخالي الذكي مع زر الإرسال المدمج في نفس السطر -->
                        <div class="tray-input-wrapper">
                            <i class="fa-solid fa-user-astronaut"></i>
                            <input type="text" id="comment-text-1" class="tray-input" placeholder="اكتب تعليقك أو استفسارك هنا..." required>
                            <button type="submit" class="tray-submit-btn">إرسال الرد</button>
                        </div>
                    </form>
                </div>
            </article>

        </div>
    </main>

    <!-- الأيقونة العائمة للمحاكي -->
    <button class="lab-float-btn" onclick="openSimulator()"><i class="fa-solid fa-flask"></i> [ Security Lab ]</button>

    <!-- نافذة المحاكي الأمنية -->
    <div class="modal-overlay" id="simulator-modal">
        <div class="laptop">
            <div class="screen">
                <div class="title-bar">
                    <div class="window-controls"><div class="control close" onclick="closeSimulator()"></div></div>
                    <div class="title-bar-text">Terminal Shell - Sandbox Environment</div>
                </div>
                <div class="simulator-content">
                    <div class="terminal-box">
                        <div class="history-container" id="term-history">Welcome to Security Sandbox Terminal... Type 'help' for available commands.</div>
                        <div class="input-line">
                            <span class="prompt">rick@security-lab:~$</span>
                            <input type="text" class="term-input" id="terminal-input-field" autofocus>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- نافذة قائمة المستخدمين -->
    <div class="modal-overlay" id="users-modal">
        <div class="users-modal-content">
            <div class="modal-header">
                <h3><i class="fa-solid fa-users-gear" style="color:var(--accent-color);"></i> قائمة الباحثين المتصلين</h3>
                <button class="modal-close-btn" onclick="closeUsersModal()">&times;</button>
            </div>
            <div id="users-main-list-view">
                <div class="users-list">
                    <div class="user-item" onclick="viewUserProfile('Rick Master', 'نشط الآن في بيئة فحص الثغرات المحمية', 'Senior Pentester')">
                        <div class="user-info-brief">
                            <div class="user-avatar-small"><i class="fa-solid fa-user-secret"></i></div>
                            <div>
                                <strong style="color:var(--text-bright);">Rick Master</strong>
                                <p style="font-size:11px; color:#8b949e;">Senior Pentester</p>
                            </div>
                        </div>
                        <span class="status-dot pulsing"></span>
                    </div>
                </div>
            </div>
            <div id="user-profile-detail-view" class="profile-view">
                <button class="back-to-users-btn" onclick="backToUsersList()"><i class="fa-solid fa-arrow-left"></i> عودة</button>
                <div style="clear:both;"></div>
                <div class="profile-avatar-large"><i class="fa-solid fa-user-shield"></i></div>
                <h4 id="prof-name" style="color:var(--text-bright); margin-bottom:5px;">-</h4>
                <p id="prof-title" style="color:var(--accent-color); font-size:12px; margin-bottom:15px;">-</p>
                <p id="prof-desc" style="color:var(--text-color); font-size:13px; padding:0 20px;">-</p>
                <button class="open-msg-btn" onclick="triggerDirectMessage()"><i class="fa-solid fa-paper-plane"></i> إرسال رسالة مشفرة</button>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 RICK Security Researcher. All Rights Reserved.</p>
        <a href="#" class="privacy-link">سياسة الخصوصية وأمان البيانات</a>
    </footer>

    <script>
        // إعدادات الشاشة التحضيرية والتحقق من ملفات الارتباط (Cookies)
        document.addEventListener("DOMContentLoaded", () => {
            setTimeout(() => { document.getElementById('line2').style.display = 'block'; }, 400);
            setTimeout(() => { document.getElementById('line3').style.display = 'block'; }, 900);
            setTimeout(() => { document.getElementById('line4').style.display = 'block'; }, 1400);
            setTimeout(() => { 
                document.getElementById('line5').style.display = 'block';
                document.getElementById('liveCookieBox').style.display = 'block';
                document.getElementById('cookieValueSpan').innerText = "sec_session_token_xyz123";
            }, 1900);
            setTimeout(() => {
                const overlay = document.getElementById('security-check');
                overlay.style.transition = "opacity 0.4s";
                overlay.style.opacity = 0;
                setTimeout(() => overlay.remove(), 400);
            }, 3000);
        });

        // التبديل السلس بين الواجهة الرئيسية وقسم المقاطع
        function toggleView() {
            const mainView = document.getElementById('main-content-view');
            const videoSection = document.getElementById('video-section');
            if(videoSection.style.display === 'block') {
                resetToHome();
            } else {
                mainView.style.display = 'none';
                videoSection.style.display = 'block';
                window.scrollTo(0, 0);
            }
        }

        function resetToHome() {
            document.getElementById('main-content-view').style.display = 'block';
            document.getElementById('video-section').style.display = 'none';
        }

        // أداء زر الإعجاب العائم
        function handleLike(btn) {
            btn.classList.toggle('active');
            let countSpan = btn.querySelector('.count');
            let currentCount = parseInt(countSpan.innerText);
            if(btn.classList.contains('active')) {
                countSpan.innerText = currentCount + 1;
            } else {
                countSpan.innerText = currentCount - 1;
            }
        }

        // التركيز على حقل النص تلقائياً عند الضغط على أيقونة التعليق الجانبية
        function focusCommentInput(inputId) {
            const input = document.getElementById(inputId);
            input.focus();
            input.scrollIntoView({ behavior: 'smooth', block: 'center' });
        }

        // إرسال التعليق والمشاركة عبر البريد المدمج الخلفي ديناميكياً
        function submitCommentForm(event, textInputId, capsuleGroupId) {
            event.preventDefault();
            const textValue = document.getElementById(textInputId).value;
            const capsuleGroup = document.getElementById(capsuleGroupId);
            const checkedRadio = capsuleGroup.querySelector('input[type="radio"]:checked');
            const reactionValue = checkedRadio ? checkedRadio.value : 'لا يوجد تفاعل سريع';

            // تكوين نص الرسالة الموحد لإرساله
            const finalBody = `نوع التفاعل السريع: ${reactionValue}\nنص التعليق المكتوب: ${textValue}`;
            
            // فتح نافذة البريد لإرسال البيانات للخادم أو للمسؤول مباشرة
            window.location.href = `mailto:support@yourdomain.com?subject=تفاعل جديد على مقطع الفيديو&body=${encodeURIComponent(finalBody)}`;
            
            // إعادة ضبط الحقول بعد الإرسال الناجح
            document.getElementById(textInputId).value = '';
            if(checkedRadio) checkedRadio.checked = false;
            alert('تم تجهيز تفاعلك وإرساله بنجاح!');
        }

        function shareVideo() {
            if (navigator.share) {
                navigator.share({ title: 'مقاطع RICK الأمنية', url: window.location.href });
            } else {
                alert('تم نسخ رابط المقطع إلى الحافظة بمحاكاة آمنة!');
            }
        }

        // معالجة القوائم المنبثقة والمحاكي
        function openSimulator() { document.getElementById('simulator-modal').style.display = 'flex'; }
        function closeSimulator() { document.getElementById('simulator-modal').style.display = 'none'; }
        function openUsersModal() { document.getElementById('users-modal').style.display = 'flex'; }
        function closeUsersModal() { document.getElementById('users-modal').style.display = 'none'; backToUsersList(); }
        
        function viewUserProfile(name, desc, title) {
            document.getElementById('users-main-list-view').style.display = 'none';
            const profileView = document.getElementById('user-profile-detail-view');
            profileView.style.display = 'block';
            document.getElementById('prof-name').innerText = name;
            document.getElementById('prof-title').innerText = title;
            document.getElementById('prof-desc').innerText = desc;
        }

        function backToUsersList() {
            document.getElementById('user-profile-detail-view').style.display = 'none';
            document.getElementById('users-main-list-view').style.display = 'block';
        }

        function triggerDirectMessage() { alert('جاري إنشاء اتصال آمن ومسار مشفر للدردشة النفقية الـ P2P...'); }
        function activateFollow() { alert('تم تسجيل المتابعة لملف الباحث باكتشاف ناجح لبيئة العرض.'); }

        // معالجة أوامر المحاكي الطرفي
        document.getElementById('terminal-input-field').addEventListener('keydown', function(e) {
            if (e.key === 'Enter') {
                const input = this.value.trim();
                const history = document.getElementById('term-history');
                if(!input) return;

                let output = `\nrick@security-lab:~$ ${input}\n`;
                if(input.toLowerCase() === 'help') {
                    output += "Commands available: help, clear, scan, status";
                } else if(input.toLowerCase() === 'clear') {
                    history.innerHTML = '';
                    this.value = '';
                    return;
                } else if(input.toLowerCase() === 'scan') {
                    output += "[+] Accessing automated asset mapping suite...\n[!] Vulnerability scanning initialized on localhost target.\n[+] Results recorded cleanly inside environment memory buffer.";
                } else if(input.toLowerCase() === 'status') {
                    output += "System Integrity: 100%\nActive Session Tokens: 1\nDatabase Target Status: CONNECTED";
                } else {
                    output += `bash: command not found: ${input}`;
                }

                history.innerHTML += output;
                this.value = '';
                history.scrollTop = history.scrollHeight;
            }
        });

        // القائمة المتجاوبة للهواتف الذكية
        document.getElementById('mobile-menu').addEventListener('click', () => {
            document.getElementById('nav-list').classList.toggle('active');
        });
    </script>
</body>
</html>
