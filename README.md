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
            margin-left: 25px; /* مسافة متناسقة للغة العربية */
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

        /* زر القائمة للموبايل */
        .menu-toggle {
            display: none;
            font-size: 24px;
            color: var(--text-bright);
            cursor: pointer;
            transition: color 0.3s;
        }

        .menu-toggle:hover {
            color: var(--accent-color);
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

        .skill-badge:hover {
            border-color: var(--accent-color);
            color: var(--accent-color);
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

        /* ==========================================
           أنماط الأيقونة العائمة والنافذة المنبثقة للمحاكي
           ========================================== */
        
        /* زر التشغيل العائم المخصص للمحاكي */
        .lab-float-btn {
            position: fixed;
            bottom: 30px;
            left: 30px; /* في جهة اليسار لعدم حجب عناصر تصفح أخرى */
            background-color: var(--card-bg);
            border: 2px solid var(--accent-color);
            color: var(--accent-color);
            padding: 12px 20px;
            border-radius: 50px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 255, 102, 0.3);
            z-index: 9999;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .lab-float-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px var(--accent-color);
        }

        .lab-float-btn i {
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0% { opacity: 0.5; }
            50% { opacity: 1; }
            100% { opacity: 0.5; }
        }

        /* الخلفية المظلمة عند فتح المحاكي */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background-color: rgba(0, 0, 0, 0.85);
            z-index: 10000;
            display: none; /* مخفي افتراضياً */
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        /* هيكل اللابتوب داخل المودال */
        .laptop {
            width: 850px;
            max-width: 100%;
            display: flex;
            flex-direction: column;
            animation: zoomIn 0.3s ease-out;
        }

        @keyframes zoomIn {
            from { transform: scale(0.8); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        /* شاشة اللابتوب */
        .screen {
            background-color: #1a1a1a;
            border: 14px solid #1f242c;
            border-radius: 12px 12px 0 0;
            height: 480px;
            display: flex;
            flex-direction: column;
            overflow: hidden;
            position: relative;
        }

        /* شريط التحكم بالنافذة العلوي */
        .title-bar {
            background-color: #2d333b;
            color: #adbac7;
            padding: 6px 12px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            direction: ltr;
        }

        .window-controls {
            display: flex;
            gap: 6px;
        }

        .control {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            cursor: pointer;
        }

        .close { background-color: #ff5f56; }
        .minimize { background-color: #ffbd2e; }
        .maximize { background-color: #27c93f; }

        .title-bar-text {
            flex-grow: 1;
            text-align: center;
            font-size: 13px;
            font-family: monospace;
        }

        /* واجهة وتصميم التيرمينال الداخلي */
        .simulator-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            background-color: #0d1117;
            padding: 10px;
        }

        .lab-header {
            text-align: center;
            color: #c9d1d9;
            margin: 5px 0 10px;
            direction: rtl;
        }
        .lab-header h3 { font-size: 18px; margin-bottom: 4px; color: var(--text-bright); }
        .lab-header p { font-size: 13px; color: #8b949e; }

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
            font-family: 'Courier New', Courier, monospace;
            font-size: 13px;
            line-height: 1.5;
            padding: 10px;
        }
        
        .input-line { 
            display: flex; 
            align-items: center; 
            border-top: 1px solid #21262d;
            padding: 8px 10px;
        }
        
        .prompt { 
            color: var(--accent-color);
            font-weight: bold;
            margin-right: 8px; 
            white-space: nowrap;
        }
        
        .term-input { 
            background: none; 
            border: none; 
            color: #c9d1d9; 
            font-family: inherit; 
            font-size: 15px; 
            width: 100%; 
            outline: none; 
        }

        .system-msg { color: #8b949e; font-style: italic; }
        .success-msg { color: #7ee787; font-weight: bold; }
        .error-msg { color: #ff7b72; }

        .hint-btn {
            display: block;
            margin: 0 auto 8px;
            background: #21262d;
            border: 1px solid #30363d;
            color: #c9d1d9;
            padding: 4px 12px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 12px;
            direction: rtl;
        }

        /* قاعدة لوحة المفاتيح أسفل اللابتوب */
        .keyboard {
            background-color: #2d333b;
            border: 12px solid #1f242c;
            border-top: none;
            border-radius: 0 0 12px 12px;
            height: 120px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .keyboard-trackpad {
            width: 120px;
            height: 50px;
            background-color: #22272e;
            border: 1px solid #444c56;
            border-radius: 4px;
            margin-top: 40px;
        }

        /* التجاوب مع الهواتف والشاشات الصغيرة */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block; /* إظهار زر القائمة في الجوال */
            }

            nav ul {
                display: none; /* إخفاء القائمة الافتراضية */
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background-color: var(--card-bg);
                border-bottom: 1px solid var(--border-color);
                padding: 20px;
                gap: 15px;
            }

            nav ul.active {
                display: flex; /* إظهارها عند الضغط على الزر */
            }

            nav ul li {
                margin-left: 0;
                text-align: center;
                width: 100%;
            }

            .about-grid {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-content h1 {
                font-size: 2.3rem;
            }

            .hero-content p {
                font-size: 1.1rem;
            }

            /* في الجوال: يتم إلغاء جسم اللابتوب وتحويل الشاشة لعرض كامل لراحة المستخدم */
            .modal-overlay { padding: 5px; }
            .keyboard { display: none; }
            .screen { height: 90vh; border: 4px solid #1f242c; border-radius: 8px; }
            .lab-float-btn { bottom: 20px; left: 20px; padding: 10px 15px; font-size: 14px; }
        }
    </style>
</head>
<body>

    <header>
        <div class="nav-container">
            <div class="logo"><span>[</span> RICK <span>]</span></div>
            <div class="menu-toggle" id="mobile-menu">
                <i class="fa-solid fa-bars"></i>
            </div>
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
                <div class="avatar-placeholder">
                    <i class="fa-solid fa-user-shield"></i>
                </div>
            </div>
            <div>
                <p style="font-size: 18px; margin-bottom: 20px;">
                    أنا <strong>RICK</strong>، باحث متخصص في الأمن السيبراني واختبار الاختراق. أعمل على مساعدة الشركات والمطورين في تأمين بنيتهم التحتية الرقمية، وتطبيقاتهم، وحمايتها من التهديدات السيبرانية المتقدمة.
                </p>
                <p>
                    شغفي يكمن في تحليل البروتوكولات الشبكية، ومراجعة الأكواد البرمجية، واكتشاف الثغرات الأمنية الحرجة. أهدافي دائماً تتمحور حول خلق بيئة رقمية أكثر أماناً ومقاومة للهجمات.
                </p>
            </div>
        </div>
    </section>

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

    <section id="skills">
        <h2 class="section-title">المهارات والأدوات التقنية</h2>
        <div class="grid-3">
            <div class="card">
                <h3><i class="fa-solid fa-terminal" style="font-size: 20px; color: var(--accent-color);"></i> أنظمة التشغيل</h3>
                <div class="skills-container">
                    <span class="skill-badge">Linux (Kali / Parrot)</span>
                    <span class="skill-badge">Termux Environment</span>
                    <span class="skill-badge">Android Security</span>
                </div>
            </div>
            <div class="card">
                <h3><i class="fa-solid fa-screwdriver-wrench" style="font-size: 20px; color: var(--accent-color);"></i> أدوات الفحص</h3>
                <div class="skills-container">
                    <span class="skill-badge">Nmap / Masscan</span>
                    <span class="skill-badge">Burp Suite</span>
                    <span class="skill-badge">Wireshark</span>
                    <span class="skill-badge">Nikto</span>
                </div>
            </div>
            <div class="card">
                <h3><i class="fa-solid fa-gears" style="font-size: 20px; color: var(--accent-color);"></i> الشبكات والمراقبة</h3>
                <div class="skills-container">
                    <span class="skill-badge">TCP/IP Architecture</span>
                    <span class="skill-badge">DNS & HTTP Security</span>
                    <span class="skill-badge">Canarytokens Monitoring</span>
                </div>
            </div>
        </div>
    </section>

    <section id="contact">
        <h2 class="section-title">تواصل معي</h2>
        <div class="contact-info">
            <p>هل تريد تأمين مشروعك أو لديك استفسار أمني؟ لا تتردد في مراسلتي مباشرة عبر المنصات التالية:</p>
            
            <div class="social-links">
                <a href="#" target="_blank" title="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="#" target="_blank" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>
                <a href="mailto:rick@example.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
            </div>
        </div>
    </section>

    <button class="lab-float-btn" id="openLabBtn">
        <i class="fa-solid fa-terminal"></i> <span>[ Lab ]</span>
    </button>

    <div class="modal-overlay" id="labModal">
        <div class="laptop">
            <div class="screen">
                <div class="title-bar">
                    <div class="window-controls">
                        <div class="control close" id="closeLabBtn" title="إغلاق المختبر"></div>
                        <div class="control minimize"></div>
                        <div class="control maximize"></div>
                    </div>
                    <div class="title-bar-text">Termux-SecLab v3.1 [Laptop Mode]</div>
                </div>

                <div class="simulator-content">
                    <div class="lab-header">
                        <h3>🤖 بيئة محاكاة التيرمينال</h3>
                        <p>المهمة: افحص الهدف <span style="color: #ff7b72;">vulnerable-target.local</span> واكتشف الثغرة!</p>
                    </div>

                    <button class="hint-btn" onclick="showLabHint()">💡 تلميحة للمهمة</button>

                    <div class="terminal-box" onclick="document.getElementById('termCmd').focus()">
                        <div id="termHistory" class="history-container"><span class="system-msg">Welcome to Termux-SecLab Environment v3.1
Type 'help' to see available commands.
------------------------------------------------------------</span></div>
                        <div class="input-line">
                            <span class="prompt">rick@seclab:~$</span>
                            <input type="text" id="termCmd" autocomplete="off" autocapitalize="none" spellcheck="false">
                        </div>
                    </div>
                </div>
            </div>

            <div class="keyboard">
                <div class="keyboard-trackpad"></div>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 RICK. جميع الحقوق محفوظة | مستضاف بأمان على GitHub Pages</p>
    </footer>

    <script>
        // --- أولاً: أكواد تحكم القائمة الأصلية للموقع ---
        const mobileMenu = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');

        mobileMenu.addEventListener('click', () => {
            navList.classList.toggle('active');
        });

        const navLinks = document.querySelectorAll('#nav-list a');
        navLinks.forEach(link => {
            link.addEventListener('click', () => {
                navList.remove();
            });
        });

        // --- ثانياً: أكواد التحكم بالنافذة المنبثقة للمحاكي ---
        const labModal = document.getElementById('labModal');
        const openLabBtn = document.getElementById('openLabBtn');
        const closeLabBtn = document.getElementById('closeLabBtn');
        const termCmd = document.getElementById('termCmd');
        const termHistory = document.getElementById('termHistory');

        // فتح نافذة اللابتوب والتركيز على حقل الكتابة تلقائياً
        openLabBtn.addEventListener('click', () => {
            labModal.style.display = 'flex';
            termCmd.focus();
        });

        // إغلاق النافذة
        closeLabBtn.addEventListener('click', () => {
            labModal.style.display = 'none';
        });

        // إغلاق عند الضغط خارج جسم اللابتوب
        labModal.addEventListener('click', (e) => {
            if (e.target === labModal) {
                labModal.style.display = 'none';
            }
        });

        // --- ثالثاً: منطق عمل أوامر التيرمينال التفاعلية ---
        let labState = {
            scanned: false,
            vulnerabilityFound: false
        };

        termCmd.addEventListener('keydown', function(e) {
            if (e.key === 'Enter') {
                const command = termCmd.value.trim();
                if (command) {
                    executeLabCommand(command);
                }
                termCmd.value = '';
            }
        });

        function showLabHint() {
            alert("تلميحة: ابدأ الفحص بكتابة أمر nmap للمستهدف كالتالي:\nnmap vulnerable-target.local");
        }

        function executeLabCommand(cmd) {
            let output = `\n<span class="prompt">rick@seclab:~$</span> ${cmd}\n`;
            const tokens = cmd.split(' ');
            const baseCmd = tokens[0].toLowerCase();
            const arg = tokens[1];

            switch(baseCmd) {
                case 'help':
                    output += `Available Commands:
- <span class="success-msg">help</span>       : Show this menu
- <span class="success-msg">clear</span>      : Clear terminal screen
- <span class="success-msg">nmap</span>       : Network mapper tool
- <span class="success-msg">curl</span>       : Data transfer utility
- <span class="success-msg">whois</span>      : Domain registration intelligence`;
                    break;

                case 'clear':
                    termHistory.innerHTML = '';
                    return;

                case 'whois':
                    if (arg === 'vulnerable-target.local') {
                        output += `Domain: vulnerable-target.local
Registrar: SecLabs Registry Internal
Status: Active
Admin IP: 10.0.2.15`;
                    } else {
                        output += `<span class="error-msg">Usage: whois vulnerable-target.local</span>`;
                    }
                    break;

                case 'nmap':
                    if (arg === 'vulnerable-target.local') {
                        labState.scanned = true;
                        output += `Starting Nmap 7.92...
Scanning vulnerable-target.local (10.0.2.15)
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 8.2p1
80/tcp   open  http    Apache httpd 2.4.41
<span class="error-msg">8080/tcp open  http    Apache Struts v2.3 (VULNERABLE)</span>

Nmap done: 1 IP address scanned.`;
                    } else {
                        output += `<span class="error-msg">Usage: nmap vulnerable-target.local</span>`;
                    }
                    break;

                case 'curl':
                    if (!labState.scanned) {
                        output += `<span class="error-msg">Error: Host unreachable. Try scanning the network first!</span>`;
                    } else if (arg === 'http://vulnerable-target.local:8080') {
                        output += `<span class="success-msg">[+] Connected to Apache Struts Portal!</span>
[!] Alert: Remote Code Execution (RCE) vulnerability detected.
[💡] Try to exploit it by appending parameters: <span class="success-msg">?cmd=id</span>`;
                        labState.vulnerabilityFound = true;
                    } else if (arg === 'http://vulnerable-target.local:8080?cmd=id' && labState.vulnerabilityFound) {
                        output += `<span class="success-msg">HTTP/1.1 200 OK</span>
Response Payload:
--------------------------------------
<span class="success-msg">uid=0(root) gid=0(root) groups=0(root)
[🏆] CONGRATULATIONS Rick! You successfully got Root access!</span>`;
                    } else {
                        output += `<span class="error-msg">Usage: curl http://vulnerable-target.local:8080</span>`;
                    }
                    break;

                default:
                    output += `<span class="error-msg">bash: ${baseCmd}: command not found</span>`;
            }

            termHistory.innerHTML += output;
            termHistory.scrollTop = termHistory.scrollHeight;
        }
    </script>
</body>
</html>
