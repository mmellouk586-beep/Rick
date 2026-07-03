<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RICK | Cyber Security Researcher</title>
    
    <!-- خطوط جوجل - خط Cairo الاحترافي -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;700&display=swap" rel="stylesheet">
    
    <!-- مكتبة Font Awesome للأيقونات - نسخة مستقرة ومحدثة -->
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
        }
    </style>
</head>
<body>

    <!-- الهيدر -->
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

    <!-- قسم المهارات والأدوات -->
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

    <!-- قسم الاتصال -->
    <section id="contact">
        <h2 class="section-title">تواصل معي</h2>
        <div class="contact-info">
            <p>هل تريد تأمين مشروعك أو لديك استفسار أمني؟ لا تتردد في مراسلتي مباشرة عبر المنصات التالية:</p>
            
            <div class="social-links">
                <!-- استبدل العلامة # بروابطك الحقيقية لاحقاً -->
                <a href="#" target="_blank" title="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="#" target="_blank" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>
                <a href="mailto:rick@example.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
            </div>
        </div>
    </section>

    <!-- الفوتر -->
    <footer>
        <p>&copy; 2026 RICK. جميع الحقوق محفوظة | مستضاف بأمان على GitHub Pages</p>
    </footer>

    <!-- كود جافا سكريبت لإصلاح وتفعيل قائمة الجوال التفاعلية -->
    <script>
        const mobileMenu = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');

        // فتح وإغلاق القائمة عند الضغط على الزر في الجوال
        mobileMenu.addEventListener('click', () => {
            navList.classList.toggle('active');
        });

        // إغلاق القائمة تلقائياً عند الضغط على أي رابط لتسهيل التنقل
        const navLinks = document.querySelectorAll('#nav-list a');
        navLinks.forEach(link => {
            link.addEventListener('click', () => {
                navList.classList.remove('active');
            });
        });
    </script>
</body>
</html>
