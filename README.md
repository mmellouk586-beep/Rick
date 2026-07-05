<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RICK | Cyber Security Researcher</title>
    
    <!-- خطوط جوجل - خط Cairo الاحترافي -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;700&display=swap" rel="stylesheet">
    
    <!-- مكتبة Font Awesome للأيقونات -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    
    <style>
        :root {
            --bg-color: #0d1117;
            --card-bg: #161b22;
            --accent-color: #00ff66; /* أخضر الهكرز والأمن السيبراني */
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

        /* شاشة فحص تسجيل الزائر وإعداد الكوكيز */
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

        .scan-line {
            margin-bottom: 8px;
            white-space: nowrap;
            overflow: hidden;
            font-size: 14px;
        }

        /* لوحة عرض الكوكيز المحقونة على الشاشة */
        .cookie-display-panel {
            margin-top: 15px;
            background: #161b22;
            border: 1px dashed var(--accent-color);
            padding: 10px;
            border-radius: 4px;
            width: 100%;
            font-size: 12px;
            color: #ffcc00;
        }

        /* الهيدر وقائمة التنقل */
        header {
            background-color: rgba(22, 27, 34, 0.95);
            border-bottom: 1px solid var(--border-color);
            position: fixed;
            width: 100%;
            top: 0; right: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
        }

        .logo-area {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--text-bright);
            letter-spacing: 1px;
        }

        .logo span { color: var(--accent-color); }

        /* زر المتابعة الجديد بجانب الاسم مباشرة */
        .header-follow-btn {
            background: #21262d;
            border: 1px solid var(--accent-color);
            color: var(--accent-color);
            padding: 3px 10px;
            border-radius: 4px;
            font-size: 12px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.2s;
            margin-left: 10px;
        }
        .header-follow-btn:hover { background: var(--accent-color); color: #000; box-shadow: 0 0 10px var(--accent-color); }

        /* زر أيقونة الفيديو المدمج بالشريط العلوي للتبديل */
        .nav-video-toggle {
            background: none;
            border: 1px solid var(--border-color);
            color: var(--accent-color);
            padding: 5px 12px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 13px;
            display: flex;
            align-items: center;
            gap: 6px;
            transition: all 0.3s;
        }

        .nav-video-toggle:hover {
            border-color: var(--accent-color);
            box-shadow: 0 0 10px rgba(0, 255, 102, 0.2);
        }

        nav ul {
            display: flex;
            list-style: none;
            align-items: center;
        }

        nav ul li { margin-right: 25px; }
        nav ul li a { color: var(--text-color); text-decoration: none; font-size: 16px; transition: color 0.3s ease; }
        nav ul li a:hover { color: var(--accent-color); }
        .menu-toggle { display: none; font-size: 24px; color: var(--text-bright); cursor: pointer; }

        /* قسم المقاطع الجديد والمستقل */
        #video-section {
            display: none;
            padding: 120px 20px 80px 20px;
            max-width: 1000px;
            margin: 0 auto;
            text-align: center;
        }

        .video-container {
            max-width: 800px;
            margin: 30px auto;
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            border: 2px solid var(--accent-color);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 0 25px rgba(0, 255, 102, 0.15);
        }

        .video-container iframe {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
        }

        /* القسم الرئيسي والمحتويات */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 0 20px;
            background: radial-gradient(circle at center, #1f293d 0%, var(--bg-color) 70%);
        }

        .hero-content h1 { font-size: 3.5rem; color: var(--text-bright); margin-bottom: 10px; }
        .hero-content p { font-size: 1.5rem; color: var(--accent-color); margin-bottom: 30px; font-family: monospace; }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: transparent;
            color: var(--accent-color);
            border: 2px solid var(--accent-color);
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .btn:hover {
            background-color: var(--accent-color);
            color: var(--bg-color);
            box-shadow: 0 0 15px var(--accent-color);
        }

        /* الأقسام العامة */
        section { padding: 100px 20px 80px 20px; max-width: 1200px; margin: 0 auto; }
        .section-title { text-align: center; font-size: 2rem; color: var(--text-bright); margin-bottom: 50px; position: relative; }
        .section-title::after { content: ''; display: block; width: 50px; height: 3px; background-color: var(--accent-color); margin: 10px auto 0 auto; }

        /* من أنا */
        .about-grid { display: grid; grid-template-columns: 1fr 2fr; gap: 40px; align-items: center; }
        .profile-img-container { display: flex; justify-content: center; }
        .avatar-placeholder {
            width: 200px; height: 200px; border-radius: 50%;
            background-color: var(--card-bg); border: 3px solid var(--accent-color);
            display: flex; align-items: center; justify-content: center;
            font-size: 80px; color: var(--accent-color); box-shadow: 0 0 20px rgba(0, 255, 102, 0.2);
        }

        /* الخدمات والبطاقات */
        .grid-3 { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; }
        .card { background-color: var(--card-bg); border: 1px solid var(--border-color); padding: 30px; border-radius: 8px; transition: transform 0.3s, border-color 0.3s; }
        .card:hover { transform: translateY(-5px); border-color: var(--accent-color); }
        .card i { font-size: 40px; color: var(--accent-color); margin-bottom: 20px; }
        .card h3 { color: var(--text-bright); margin-bottom: 15px; }

        /* المهارات */
        .skills-container { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 20px; }
        .skill-badge { background-color: var(--border-color); color: var(--text-bright); padding: 8px 16px; border-radius: 20px; font-size: 14px; border: 1px solid transparent; transition: 0.3s; }
        .skill-badge:hover { border-color: var(--accent-color); color: var(--accent-color); }

        /* تواصل معي */
        .contact-info { text-align: center; max-width: 600px; margin: 0 auto; }
        .social-links { margin-top: 30px; display: flex; justify-content: center; gap: 25px; }
        .social-links a { color: var(--text-color); font-size: 30px; transition: color 0.3s, transform 0.3s; }
        .social-links a:hover { color: var(--accent-color); transform: scale(1.2); }

        /* الفوتر */
        footer { text-align: center; padding: 30px; border-top: 1px solid var(--border-color); font-size: 14px; background-color: var(--card-bg); }

        /* الأيقونة العائمة للمحاكي (يسار أسفل) */
        .lab-float-btn {
            position: fixed; bottom: 30px; left: 30px; background-color: var(--card-bg);
            border: 2px solid var(--accent-color); color: var(--accent-color); padding: 12px 20px;
            border-radius: 50px; font-size: 16px; font-weight: bold; cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 255, 102, 0.3); z-index: 999; display: flex; align-items: center; gap: 10px; transition: transform 0.3s;
        }
        .lab-float-btn:hover { transform: scale(1.05); box-shadow: 0 0 20px var(--accent-color); }

        /* شاشات اللابتوب والمحاكي */
        .modal-overlay { position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; background-color: rgba(0, 0, 0, 0.85); z-index: 10000; display: none; justify-content: center; align-items: center; padding: 20px; }
        .laptop { width: 850px; max-width: 100%; display: flex; flex-direction: column; }
        .screen { background-color: #1a1a1a; border: 14px solid #1f242c; border-radius: 12px 12px 0 0; height: 480px; display: flex; flex-direction: column; overflow: hidden; }
        .title-bar { background-color: #2d333b; color: #adbac7; padding: 6px 12px; display: flex; justify-content: space-between; align-items: center; direction: ltr; }
        .window-controls { display: flex; gap: 6px; }
        .control { width: 12px; height: 12px; border-radius: 50%; cursor: pointer; }
        .close { background-color: #ff5f56; }
        .title-bar-text { flex-grow: 1; text-align: center; font-size: 13px; font-family: monospace; }
        .simulator-content { flex: 1; display: flex; flex-direction: column; background-color: #0d1117; padding: 10px; }
        .terminal-box { flex: 1; border: 1px solid var(--border-color); background-color: #0c0f14; border-radius: 6px; display: flex; flex-direction: column; direction: ltr; }
        .history-container { flex: 1; overflow-y: auto; white-space: pre-wrap; color: #58a6ff; font-family: monospace; font-size: 13px; padding: 10px; }
        .input-line { display: flex; align-items: center; padding: 8px 10px; }
        .prompt { color: var(--accent-color); margin-right: 8px; }
        .term-input { background: none; border: none; color: #c9d1d9; width: 100%; outline: none; }

        @media (max-width: 768px) {
            .menu-toggle { display: block; }
            nav ul { display: none; flex-direction: column; position: absolute; top: 100%; left: 0; right: 0; background-color: var(--card-bg); padding: 20px; gap: 10px; }
            nav ul.active { display: flex; }
            nav ul li { margin-right: 0; text-align: center; }
            .about-grid { grid-template-columns: 1fr; text-align: center; }
        }
    </style>
</head>
<body>

    <!-- شاشة فحص تسجيل الزائر وإعداد الكوكيز -->
    <div id="security-check">
        <div class="scan-terminal">
            <div class="scan-line" id="line1">> Initializing visitor integrity scan...</div>
            <div class="scan-line" id="line2" style="display:none">> Checking browser session structures...</div>
            <div class="scan-line" id="line3" style="display:none">> IP Routing Protocol: 172.217.16.14 verified.</div>
            <div class="scan-line" id="line4" style="display:none">> Injecting anti-bot token tracking...</div>
            <div class="scan-line" id="line5" style="display:none; color: #ffffff;">> [SUCCESS] Cookies set. Access granted!</div>
            
            <!-- لوحة الكوكيز المرئية على الشاشة 🍪 -->
            <div class="cookie-display-panel" id="liveCookieBox" style="display: none;">
                🍪 Active Browser Cookie: <span id="cookieValueSpan">None</span>
            </div>
        </div>
    </div>

    <!-- الهيدر شريط التنقل العلوي -->
    <header>
        <div class="nav-container">
            <div class="logo-area">
                <div class="logo"><span>[</span> RICK <span>]</span></div>
                <!-- زر المتابعة الذكي بجانب الاسم مباشرة -->
                <button class="header-follow-btn" onclick="activateFollow()">[ Follow ]</button>
                
                <!-- زر التبديل لقسم المقاطع -->
                <button class="nav-video-toggle" onclick="toggleView()">
                    <i class="fa-solid fa-video"></i> <span>[ المقاطع ]</span>
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

    <!-- المحتويات الرئيسية للموقع (مجموعة في حاوية واحدة لتسهيل الإخفاء والإظهار) -->
    <div id="main-content-wrapper">
        <!-- القسم الرئيسي -->
        <section id="home" class="hero">
            <div class="hero-content">
                <h1>مرحباً، أنا RICK</h1>
                <p>>_ Cybersecurity Researcher & Ethical Hacker</p>
                <a href="#contact" class="btn">اطلب فحص أمني الآن</a>
            </div>
        </section>

        <!-- قسم من أنا -->
        <section id="about">
            <h2 class="section-title">من أنا</h2>
            <div class="about-grid">
                <div class="profile-img-container">
                    <div class="avatar-placeholder"><i class="fa-solid fa-user-shield"></i></div>
                </div>
                <div>
                    <p style="font-size: 18px; margin-bottom: 20px;">أنا <strong>RICK</strong>، باحث متخصص في الأمن السيبراني واختبار الاختراق العالي الكفاءة.</p>
                    <p>مرحباً بك في بوابتي الشخصية لتتبع وتحليل البيانات وفحص الأجهزة والأنظمة المتقدمة.</p>
                </div>
            </div>
        </section>

        <!-- قسم الخدمات -->
        <section id="services">
            <h2 class="section-title">الخدمات الأمنية</h2>
            <div class="grid-3">
                <div class="card">
                    <i class="fa-solid fa-network-wired"></i>
                    <h3>اختبار اختراق الشبكات</h3>
                    <p>فحص شامل للشبكات الداخلية والخارجية للمؤسسات، واكتشاف منافذ الضعف والقصور في إعدادات السيرفرات والأجهزة.</p>
                </div>
                <div class="card">
                    <i class="fa-solid fa-code-bug"></i>
                    <h3>فحص تطبيقات الويب</h3>
                    <p>تحليل أمني دقيق للتطبيقات ومواقع الويب للتأكد من خلوها من ثغرات حقن البيانات (SQLi)، وثغرات المواقع (XSS).</p>
                </div>
                <div class="card">
                    <i class="fa-solid fa-shield-halved"></i>
                    <h3>الاستجابة للحوادث</h3>
                    <p>تقديم الدعم السريع في حال التعرض لاختراق، تتبع مصدر الهجوم، وتأمين النظام مجدداً لحمايته مستقبلاً.</p>
                </div>
            </div>
        </section>

        <!-- قسم المهارات التقنية -->
        <section id="skills">
            <h2 class="section-title">المهارات والأدوات التقنية</h2>
            <div class="grid-3">
                <div class="card">
                    <h3><i class="fa-solid fa-terminal" style="font-size: 20px; color: var(--accent-color); margin-bottom:0;"></i> أنظمة التشغيل</h3>
                    <div class="skills-container">
                        <span class="skill-badge">Linux (Kali / Parrot)</span>
                        <span class="skill-badge">Termux Environment</span>
                        <span class="skill-badge">Android Security</span>
                    </div>
                </div>
                <div class="card">
                    <h3><i class="fa-solid fa-screwdriver-wrench" style="font-size: 20px; color: var(--accent-color); margin-bottom:0;"></i> أدوات الفحص</h3>
                    <div class="skills-container">
                        <span class="skill-badge">Nmap / Masscan</span>
                        <span class="skill-badge">Burp Suite</span>
                        <span class="skill-badge">Wireshark</span>
                        <span class="skill-badge">Nikto</span>
                    </div>
                </div>
                <div class="card">
                    <h3><i class="fa-solid fa-gears" style="font-size: 20px; color: var(--accent-color); margin-bottom:0;"></i> الشبكات والمراقبة</h3>
                    <div class="skills-container">
                        <span class="skill-badge">TCP/IP Architecture</span>
                        <span class="skill-badge">DNS & HTTP Security</span>
                        <span class="skill-badge">Canarytokens Monitoring</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- قسم الاتصال -->
        <section id="contact">
            <h2 class="section-title">تواصل معي</h2>
            <div class="contact-info">
                <p>هل تريد تأمين مشروعك أو لديك استفسار أمني؟ لا تتردد في مراسلتي مباشرة عبر المنصات التالية:</p>
                <div class="social-links">
                    <a href="#" title="GitHub"><i class="fa-brands fa-github"></i></a>
                    <a href="mailto:rick@example.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
                </div>
            </div>
        </section>
    </div>

    <!-- قسم المقاطع الجديد والمخفي افتراضياً -->
    <section id="video-section">
        <h2 class="section-title">أحدث إصدارات القناة</h2>
        <div class="video-container">
            <!-- تم تهيئة المشغل بالصوت الكامل وتشغيل تلقائي متخفّي -->
            <iframe id="yt-player" src="" allow="autoplay; encrypted-media" allowfullscreen></iframe>
        </div>
    </section>

    <!-- الأيقونة العائمة لفتح بيئة المحاكاة التيرمينال -->
    <button class="lab-float-btn" id="openLabBtn"><i class="fa-solid fa-terminal"></i> <span>[ Lab ]</span></button>

    <!-- نافذة لابتوب المحاكي المنبثقة -->
    <div class="modal-overlay" id="labModal">
        <div class="laptop">
            <div class="screen">
                <div class="title-bar">
                    <div class="window-controls"><div class="control close" id="closeLabBtn"></div></div>
                    <div class="title-bar-text">Termux-SecLab v3.1</div>
                </div>
                <div class="simulator-content">
                    <div class="terminal-box" onclick="document.getElementById('termCmd').focus()">
                        <div id="termHistory" class="history-container"><span class="system-msg">Welcome to Termux-SecLab. Type 'help' to see available commands.</span></div>
                        <div class="input-line">
                            <span class="prompt">rick@seclab:~$</span>
                            <input type="text" id="textCmd" autocomplete="off">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- الفوتر -->
    <footer>
        <p>&copy; 2026 RICK. جميع الحقوق محفوظة | مستضاف بأمان على GitHub Pages</p>
    </footer>

    <script>
        // --- 1. إدارة كوكيز الحماية وعرضها علناً على شاشة الفحص السوداء 🍪 ---
        window.addEventListener('DOMContentLoaded', () => {
            if (getCookie("rick_session_scanned") === "true") {
                document.getElementById('security-check').style.display = 'none';
            } else {
                runSecuritySimulation();
            }
        });

        function setCookie(name, value, days) {
            let expires = "";
            if (days) {
                let date = new Date();
                date.setTime(date.getTime() + (days * 24 * 60 * 60 * 1000));
                expires = "; expires=" + date.toUTCString();
            }
            document.cookie = name + "=" + (value || "")  + expires + "; path=/";
        }

        function getCookie(name) {
            let nameEQ = name + "=";
            let ca = document.cookie.split(';');
            for(let i=0;i < ca.length;i++) {
                let c = ca[i];
                while (c.charAt(0)==' ') c = c.substring(1,c.length);
                if (c.indexOf(nameEQ) == 0) return c.substring(nameEQ.length,c.length);
            }
            return null;
        }

        function runSecuritySimulation() {
            setTimeout(() => { document.getElementById('line2').style.display = 'block'; }, 400);
            setTimeout(() => { document.getElementById('line3').style.display = 'block'; }, 800);
            setTimeout(() => { document.getElementById('line4').style.display = 'block'; }, 1200);
            setTimeout(() => { 
                document.getElementById('line5').style.display = 'block';
                setCookie("rick_session_scanned", "true", 7);
                
                // عرض الكوكيز على الشاشة علناً 🍪
                document.getElementById('liveCookieBox').style.display = 'block';
                document.getElementById('cookieValueSpan').innerText = `rick_session_scanned=true (Expires in 7 Days)`;
            }, 1600);
            setTimeout(() => {
                document.getElementById('security-check').style.display = 'none';
            }, 3200);
        }

        // --- 2. نظام التبديل الكامل والذكي بين المحتويات وقسم المقاطع المحمي ---
        function toggleView() {
            const mainWrapper = document.getElementById('main-content-wrapper');
            const videoSection = document.getElementById('video-section');
            
            if (videoSection.style.display === 'block') {
                videoSection.style.display = 'none';
                mainWrapper.style.display = 'block';
            } else {
                mainWrapper.style.display = 'none';
                videoSection.style.display = 'block';
                loadChannelVideos(); // استدعاء الاتصال الخفي تلقائياً
            }
        }

        function resetToHome() {
            document.getElementById('video-section').style.display = 'none';
            document.getElementById('main-content-wrapper').style.display = 'block';
        }

        // --- 3. الاتصال البرمجي الخفي والمشفر بقناتك وسحب آخر المقاطع المرفوعة تلقائياً بالصوت ---
        function loadChannelVideos() {
            const channelId = "UCn_v2h6K44Yy913WfWp9rYg"; // المعرف البرمجي الفريد لقناتك Rick_6006
            const secureGateway = `https://api.rss2json.com/v1/api.json?rss_url=${encodeURIComponent('https://www.youtube.com/feeds/videos.xml?channel_id=' + channelId)}`;
            
            fetch(secureGateway)
            .then(res => res.json())
            .then(feedData => {
                if (feedData.status === 'ok' && feedData.items.length > 0) {
                    const latestRef = feedData.items[0].link;
                    const cleanId = latestRef.split('v=')[1] || latestRef.substring(latestRef.lastIndexOf('/') + 1);
                    if(cleanId) {
                        // تشغيل بالصوت الكامل مع إخفاء الواجهة الخارجية لليوتيوب
                        document.getElementById('yt-player').src = `https://www.youtube.com/embed/${cleanId.split('&')[0]}?autoplay=1&rel=0&modestbranding=1`;
                    }
                }
            })
            .catch(e => console.log("Hidden Tunnel Proxy Active."));
        }

        // --- 4. نظام المتابعة الداخلي والآمن (إشعارات الموقع المتصفح فقط) ---
        function activateFollow() {
            if (!("Notification" in window)) {
                alert("[System Alert]: تم تفعيل نظام الإشعارات الداخلي والربط الافتراضي بنجاح!");
            } else {
                Notification.requestPermission().then(permission => {
                    if (permission === "granted") {
                        new Notification("RICK System Control", {
                            body: "تم تفعيل التنبيهات بنجاح. ستتلقى تحديثات الإصدارات والفحوصات مباشرة هنا.",
                            icon: "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/svgs/solid/user-shield.svg"
                        });
                    } else {
                        alert("[System Alert]: تم تفعيل المتابعة بنجاح داخل النظام الافتراضي للموقع!");
                    }
                });
            }
        }

        // التحكم في قائمة الجوال (Mobile Menu)
        const mobileMenu = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');
        mobileMenu.addEventListener('click', () => { navList.classList.toggle('active'); });
        document.querySelectorAll('#nav-list a').forEach(link => {
            link.addEventListener('click', () => { navList.classList.remove('active'); });
        });

        // تشغيل وإغلاق بيئة محاكاة اللابتوب العائم
        const labModal = document.getElementById('labModal');
        const openLabBtn = document.getElementById('openLabBtn');
        const closeLabBtn = document.getElementById('closeLabBtn');
        openLabBtn.addEventListener('click', () => { labModal.style.display = 'flex'; });
        closeLabBtn.addEventListener('click', () => { labModal.style.display = 'none'; });
    </script>
</body>
</html>
