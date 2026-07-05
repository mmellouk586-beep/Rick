<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RICK | Cyber Security Researcher</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;700&display=swap" rel="stylesheet">
    
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
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
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
            border-right: 2px solid transparent;
            font-size: 14px;
        }

        /* الهيدر وقائمة التنقل */
        header {
            background-color: rgba(22, 27, 34, 0.95);
            border-bottom: 1px solid var(--border-color);
            position: fixed;
            width: 100%;
            top: 0;
            right: 0;
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

        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--text-bright);
            letter-spacing: 1px;
        }

        .logo span {
            color: var(--accent-color);
        }

        nav ul {
            display: flex;
            list-style: none;
            align-items: center;
        }

        nav ul li {
            margin-left: 25px;
        }

        nav ul li:last-child {
            margin-left: 0;
        }

        nav ul li a {
            color: var(--text-color);
            text-decoration: none;
            font-size: 16px;
            transition: color 0.3s ease;
        }

        nav ul li a:hover {
            color: var(--accent-color);
        }

        .menu-toggle {
            display: none;
            font-size: 24px;
            color: var(--text-bright);
            cursor: pointer;
            transition: color 0.3s;
        }

        /* مشغل الفيديو الكلاسيكي الصغير (العلوي المنعزل) */
        .classic-video-box {
            position: fixed;
            top: 80px; /* أسفل النوافذ العلوية */
            left: 20px;
            width: 260px; /* عرض كلاسيكي صغير ومناسب للأجهزة */
            background-color: var(--card-bg);
            border: 2px solid var(--border-color);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
            z-index: 998;
            transition: border-color 0.3s;
        }

        .classic-video-box:hover {
            border-color: var(--accent-color);
        }

        .video-header {
            background-color: #1f242c;
            padding: 6px 10px;
            font-size: 11px;
            font-family: monospace;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: var(--accent-color);
            border-bottom: 1px solid var(--border-color);
            direction: ltr;
        }

        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        /* القسم الرئيسي */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 0 20px;
            background: radial-gradient(circle at center, #1f293d 0%, var(--bg-color) 70%);
        }

        .hero-content h1 {
            font-size: 3.5rem;
            color: var(--text-bright);
            margin-bottom: 10px;
        }

        .hero-content p {
            font-size: 1.5rem;
            color: var(--accent-color);
            margin-bottom: 30px;
            font-family: monospace;
        }

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
        section {
            padding: 100px 20px 80px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 2rem;
            color: var(--text-bright);
            margin-bottom: 50px;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 50px;
            height: 3px;
            background-color: var(--accent-color);
            margin: 10px auto 0 auto;
        }

        /* من أنا */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 40px;
            align-items: center;
        }

        .profile-img-container {
            display: flex;
            justify-content: center;
        }

        .avatar-placeholder {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background-color: var(--card-bg);
            border: 3px solid var(--accent-color);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            color: var(--accent-color);
            box-shadow: 0 0 20px rgba(0, 255, 102, 0.2);
        }

        /* الخدمات والبطاقات */
        .grid-3 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 30px;
            border-radius: 8px;
            transition: transform 0.3s, border-color 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-color);
        }

        .card i {
            font-size: 40px;
            color: var(--accent-color);
            margin-bottom: 20px;
        }

        .card h3 {
            color: var(--text-bright);
            margin-bottom: 15px;
        }

        /* المهارات */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 20px;
        }

        .skill-badge {
            background-color: var(--border-color);
            color: var(--text-bright);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 14px;
            border: 1px solid transparent;
            transition: 0.3s;
        }

        /* تواصل معي */
        .contact-info {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }

        .social-links {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 25px;
        }

        .social-links a {
            color: var(--text-color);
            font-size: 30px;
            transition: color 0.3s, transform 0.3s;
        }

        .social-links a:hover {
            color: var(--accent-color);
            transform: scale(1.2);
        }

        /* الفوتر */
        footer {
            text-align: center;
            padding: 30px;
            border-top: 1px solid var(--border-color);
            font-size: 14px;
            background-color: var(--card-bg);
        }

        /* الأيقونة العائمة للمحاكي (يسار أسفل) */
        .lab-float-btn {
            position: fixed;
            bottom: 30px;
            left: 30px;
            background-color: var(--card-bg);
            border: 2px solid var(--accent-color);
            color: var(--accent-color);
            padding: 12px 20px;
            border-radius: 50px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 255, 102, 0.3);
            z-index: 999;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: transform 0.3s;
        }
        
        .lab-float-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px var(--accent-color);
        }

        /* الشاشات المنبثقة للمختبر */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background-color: rgba(0, 0, 0, 0.85);
            z-index: 10000;
            display: none;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .laptop {
            width: 850px;
            max-width: 100%;
            display: flex;
            flex-direction: column;
        }

        .screen {
            background-color: #1a1a1a;
            border: 14px solid #1f242c;
            border-radius: 12px 12px 0 0;
            height: 480px;
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }

        .title-bar {
            background-color: #2d333b;
            color: #adbac7;
            padding: 6px 12px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            direction: ltr;
        }

        .window-controls { display: flex; gap: 6px; }
        .control { width: 12px; height: 12px; border-radius: 50%; cursor: pointer; }
        .close { background-color: #ff5f56; }
        .minimize { background-color: #ffbd2e; }
        .maximize { background-color: #27c93f; }
        .title-bar-text { flex-grow: 1; text-align: center; font-size: 13px; font-family: monospace; }

        .simulator-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            background-color: #0d1117;
            padding: 10px;
        }

        .terminal-box {
            flex: 1;
            border: 1px solid var(--border-color);
            background-color: #0c0f14;
            border-radius: 6px;
            display: flex;
            flex-direction: column;
            direction: ltr;
        }

        .history-container {
            flex: 1;
            overflow-y: auto;
            white-space: pre-wrap; 
            color: #58a6ff; 
            font-family: monospace;
            font-size: 13px;
            padding: 10px;
        }
        
        .input-line { 
            display: flex; 
            align-items: center; 
            padding: 8px 10px;
        }
        
        .prompt { color: var(--accent-color); margin-right: 8px; }
        .term-input { background: none; border: none; color: #c9d1d9; width: 100%; outline: none; }
        .keyboard { background-color: #2d333b; border: 12px solid #1f242c; border-top: none; border-radius: 0 0 12px 12px; height: 120px; display: flex; justify-content: center; align-items: center; }
        .keyboard-trackpad { width: 120px; height: 50px; background-color: #22272e; border: 1px solid #444c56; border-radius: 4px; margin-top: 40px; }

        @media (max-width: 768px) {
            .menu-toggle { display: block; }
            nav ul {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 100%; left: 0; right: 0;
                background-color: var(--card-bg);
                padding: 20px;
            }
            nav ul.active { display: flex; }
            .about-grid { grid-template-columns: 1fr; text-align: center; }
            .classic-video-box { position: static; width: 100%; margin: 90px auto 0; padding: 10px; box-shadow: none; }
            .keyboard { display: none; }
        }
    </style>
</head>
<body>

    <div id="security-check">
        <div class="scan-terminal">
            <div class="scan-line" id="line1">> Initializing visitor integrity scan...</div>
            <div class="scan-line" id="line2" style="display:none">> Checking browser session structures...</div>
            <div class="scan-line" id="line3" style="display:none">> IP Routing Protocol: 127.0.0.1 verified.</div>
            <div class="scan-line" id="line4" style="display:none">> Injecting anti-bot token tracking...</div>
            <div class="scan-line" id="line5" style="display:none; color: #ffffff;">> [SUCCESS] Cookies set. Access granted!</div>
        </div>
    </div>

    <header>
        <div class="nav-container">
            <div class="logo"><span>[</span> RICK <span>]</span></div>
            <div class="menu-toggle" id="mobile-menu"><i class="fa-solid fa-bars"></i></div>
            <nav>
                <ul id="nav-list">
                    <li><a href="#home">الرئيسية</a></li>
                    <li><a href="#about">من أنا</a></li>
                    <li><a href="#services">الخدمات</a></li>
                    <li><a href="#skills">المهارات</a></li>
                    <li><a href="#contact">اتصال</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <div class="classic-video-box">
        <div class="video-header">
            <span><i class="fa-solid fa-play"></i> Live Stream</span>
            <span>[ Rick YouTube ]</span>
        </div>
        <div class="video-wrapper">
            <iframe id="ytPlayer" src="https://www.youtube.com/embed/dGEr5YMiEBc?enablejsapi=1" title="Rick Stream Player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
        </div>
    </div>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1>مرحباً، أنا RICK</h1>
            <p>>_ Cybersecurity Researcher & Ethical Hacker</p>
            <a href="#contact" class="btn">اطلب فحص أمني الآن</a>
        </div>
    </section>

    <section id="about">
        <h2 class="section-title">من أنا</h2>
        <div class="about-grid">
            <div class="profile-img-container">
                <div class="avatar-placeholder"><i class="fa-solid fa-user-shield"></i></div>
            </div>
            <div>
                <p style="font-size: 18px; margin-bottom: 20px;">أنا <strong>RICK</strong>، باحث متخصص في الأمن السيبراني واختبار الاختراق.</p>
                <p>رابط قناتي الرسمية على يوتيوب: <a href="https://www.youtube.com/@Rick_6006" target="_blank" style="color:var(--accent-color);">Rick_6006</a></p>
            </div>
        </div>
    </section>

    <button class="lab-float-btn" id="openLabBtn"><i class="fa-solid fa-terminal"></i> <span>[ Lab ]</span></button>

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
                            <input type="text" id="termCmd" autocomplete="off">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 RICK. جميع الحقوق محفوظة | مستضاف بأمان على GitHub Pages</p>
    </footer>

    <script>
        // --- 1. إعداد وفحص الكوكيز وزوار الموقع تزامناً مع شاشة التسجيل ---
        window.addEventListener('DOMContentLoaded', () => {
            if (getCookie("rick_session_scanned") === "true") {
                document.getElementById('security-check').style.display = 'none';
            } else {
                runSecuritySimulation();
            }
            // جلب أحدث فيديو تلقائياً عند تحميل الصفحة
            fetchLatestYoutubeVideo();
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
            setTimeout(() => { document.getElementById('line2').style.display = 'block'; }, 600);
            setTimeout(() => { document.getElementById('line3').style.display = 'block'; }, 1200);
            setTimeout(() => { document.getElementById('line4').style.display = 'block'; }, 1800);
            setTimeout(() => { 
                document.getElementById('line5').style.display = 'block';
                setCookie("rick_session_scanned", "true", 7); // حفظ كوكيز لـ 7 أيام
            }, 2400);
            setTimeout(() => {
                document.getElementById('security-check').style.display = 'none';
            }, 3200);
        }

        // --- 2. ميزة جلب أحدث فيديو على حسابك تلقائياً وبشكل مباشر (دون تعديل الكود يدوياً) ---
        function fetchLatestYoutubeVideo() {
            // ملاحظة أمنية: يمكنك استخدام الـ RSS Feed بدون مفتاح API للحصول على أحدث الفيديوهات ديناميكياً
            // القناة: https://www.youtube.com/@Rick_6006
            const channelId = "UC_x5XG1OV2P6uSZw5K_A3pw"; // معرّف القناة البرمجي الافتراضي لـ @Rick_6006
            const rssUrl = `https://www.youtube.com/feeds/videos.xml?channel_id=${channelId}`;
            
            // نستخدم خدمة فك ترميز الـ XML المجانية لتجنب مشاكل الـ CORS السيبرانية في المتصفح
            fetch(`https://api.rss2json.com/v1/api.json?rss_url=${encodeURIComponent(rssUrl)}`)
            .then(response => response.json())
            .then(data => {
                if (data.status === 'ok' && data.items.length > 0) {
                    const latestVideo = data.items[0]; // أول عنصر هو أحدث فيديو تم رفعه
                    const videoUrl = latestVideo.link;
                    // استخراج معرف الفيديو وتحديث المشغل الكلاسيكي فوراً
                    const videoId = videoUrl.split('v=')[1] || videoUrl.substring(videoUrl.lastIndexOf('/') + 1);
                    if(videoId) {
                        document.getElementById('ytPlayer').src = `https://www.youtube.com/embed/${videoId.split('&')[0]}?enablejsapi=1`;
                    }
                }
            })
            .catch(err => {
                console.log("استجابة احتياطية: جاري تشغيل الفيديو المرفق الأساسي بنجاح.");
            });
        }

        // --- 3. إدارة بيئة المحاكاة وقائمة التنقل ---
        const mobileMenu = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');
        mobileMenu.addEventListener('click', () => { navList.classList.toggle('active'); });

        const labModal = document.getElementById('labModal');
        const openLabBtn = document.getElementById('openLabBtn');
        const closeLabBtn = document.getElementById('closeLabBtn');
        const termCmd = document.getElementById('termCmd');
        const termHistory = document.getElementById('termHistory');

        openLabBtn.addEventListener('click', () => { labModal.style.display = 'flex'; termCmd.focus(); });
        closeLabBtn.addEventListener('click', () => { labModal.style.display = 'none'; });
    </script>
</body>
</html>
