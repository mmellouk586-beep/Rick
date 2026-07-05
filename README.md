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

        nav ul { display: flex; list-style: none; align-items: center; }
        nav ul li { margin-right: 25px; }
        nav ul li a { color: var(--text-color); text-decoration: none; font-size: 16px; transition: color 0.3s ease; }
        nav ul li a:hover { color: var(--accent-color); }
        .menu-toggle { display: none; font-size: 24px; color: var(--text-bright); cursor: pointer; }

        /* قسم المقاطع اليوتيوب الديناميكية */
        #video-section {
            display: none;
            padding: 120px 20px 80px 20px;
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }

        .videos-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 25px;
            margin-top: 30px;
        }

        .video-wrapper {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 10px;
            width: 320px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            transition: border-color 0.3s;
        }
        .video-wrapper:hover {
            border-color: var(--accent-color);
        }

        .video-container {
            width: 100%;
            height: 500px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            overflow: hidden;
            background: #000;
        }

        .video-container iframe { width: 100%; height: 100%; border: none; }
        .video-title { font-size: 14px; color: var(--text-bright); margin-top: 10px; text-align: right; overflow: hidden; text-overflow: ellipsis; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; }

        /* الأقسام العامة */
        .hero { height: 100vh; display: flex; align-items: center; justify-content: center; text-align: center; padding: 0 20px; background: radial-gradient(circle at center, #1f293d 0%, var(--bg-color) 70%); }
        .hero-content h1 { font-size: 3.5rem; color: var(--text-bright); margin-bottom: 10px; }
        .hero-content p { font-size: 1.5rem; color: var(--accent-color); margin-bottom: 30px; font-family: monospace; }
        .btn { display: inline-block; padding: 12px 30px; background-color: transparent; color: var(--accent-color); border: 2px solid var(--accent-color); border-radius: 5px; text-decoration: none; font-weight: bold; transition: all 0.3s ease; cursor: pointer; }
        .btn:hover { background-color: var(--accent-color); color: var(--bg-color); box-shadow: 0 0 15px var(--accent-color); }

        section { padding: 100px 20px 80px 20px; max-width: 1200px; margin: 0 auto; }
        .section-title { text-align: center; font-size: 2rem; color: var(--text-bright); margin-bottom: 50px; position: relative; }
        .section-title::after { content: ''; display: block; width: 50px; height: 3px; background-color: var(--accent-color); margin: 10px auto 0 auto; }

        .about-grid { display: grid; grid-template-columns: 1fr 2fr; gap: 40px; align-items: center; }
        .profile-img-container { display: flex; justify-content: center; }
        .avatar-placeholder { width: 180px; height: 180px; border-radius: 50%; background-color: var(--card-bg); border: 3px solid var(--accent-color); display: flex; align-items: center; justify-content: center; font-size: 65px; color: var(--accent-color); box-shadow: 0 0 20px rgba(0, 255, 102, 0.2); }

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

        /* نافذة بيئة الاختبار (Lab) */
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
                    <p style="font-size: 18px; margin-bottom: 20px;">أنا <strong>RICK</strong>، باحث متخصص في الأمن السيبراني.</p>
                    <p>مرحباً بك في بوابتي الشخصية لتتبع وتحليل البيانات وفحص الأنظمة المتقدمة.</p>
                </div>
            </div>
        </section>

        <section id="services">
            <h2 class="section-title">الخدمات الأمنية</h2>
            <div class="grid-3">
                <div class="card"><i class="fa-solid fa-network-wired"></i><h3>اختبار اختراق الشبكات</h3><p>فحص شامل للشبكات الداخلية والخارجية للمؤسسات.</p></div>
                <div class="card"><i class="fa-solid fa-code-bug"></i><h3>فحص تطبيقات الويب</h3><p>تحليل أمني دقيق للتطبيقات ومواقع الويب.</p></div>
                <div class="card"><i class="fa-solid fa-shield-halved"></i><h3>الاستجابة للحوادث</h3><p>تقديم الدعم السريع وتأمين النظام مجدداً.</p></div>
            </div>
        </section>

        <section id="skills">
            <h2 class="section-title">المهارات والأدوات</h2>
            <div class="grid-3">
                <div class="card"><h3>أنظمة التشغيل</h3><div class="skills-container"><span class="skill-badge">Linux (Kali / Parrot)</span></div></div>
                <div class="card"><h3>أدوات الفحص</h3><div class="skills-container"><span class="skill-badge">Nmap / Burp Suite</span></div></div>
                <div class="card"><h3>الشبكات</h3><div class="skills-container"><span class="skill-badge">TCP/IP / Canarytokens</span></div></div>
            </div>
        </section>

        <section id="contact">
            <h2 class="section-title">تواصل معي</h2>
            <div class="contact-info">
                <div class="social-links">
                    <a href="#" title="GitHub"><i class="fa-brands fa-github"></i></a>
                    <a href="mailto:rick@example.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
                </div>
            </div>
        </section>
    </div>

    <section id="video-section">
        <h2 class="section-title">المقاطع المنشورة</h2>
        <div class="videos-grid" id="youtubeVideosGrid"></div>
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
                    <div class="terminal-box" id="terminalBoxContainer">
                        <div id="termHistory" class="history-container"><span class="system-msg">Welcome to Termux-SecLab. Type 'help' to see available commands.</span></div>
                        <div class="input-line">
                            <span class="prompt">rick@seclab:~$</span>
                            <input type="text" id="textCmd" class="term-input" autocomplete="off" autofocus>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 RICK. جميع الحقوق محفوظة</p>
        <a href="#privacy" class="privacy-link" onclick="alert('سياسة الخصوصية:\nنحن نحترم خصوصيتك بالكامل. جميع عمليات المحاكاة والفحص الأمني داخل هذا الموقع تجري محلياً في بيئة اختبار آمنة تماماً، ولا نقوم بجمع أو مشاركة أي بيانات حساسة تخص الزوار.')">سياسة الخصوصية</a>
    </footer>

    <script>
        const YOUTUBE_API_KEY = "ضغ_مفتاح_الـ_API_الخاص_بجل_هنا"; 
        const YOUTUBE_CHANNEL_ID = "UCwFk399Vw8Xq3K_R-3-zOtw";

        const MY_PRESET_VIDEOS = [
            { id: "dGEr5YMiEBc", title: "مقطع تتبع وتحليل البيانات - الجزء الأول" },
            { id: "jTgCFVL2HVs", title: "مقطع تتبع وتحليل البيانات - الجزء الثاني" }
        ];

        function speakVideoTitle(text) {
            if ('speechSynthesis' in window) {
                window.speechSynthesis.cancel(); 
                const utterance = new SpeechSynthesisUtterance(text);
                utterance.lang = 'ar-SA';       
                utterance.rate = 0.95;          
                utterance.pitch = 1.0;          
                window.speechSynthesis.speak(utterance);
            }
        }

        document.addEventListener('DOMContentLoaded', () => {
            if (getCookie("rick_session_scanned") === "true") {
                document.getElementById('security-check').style.display = 'none';
            } else {
                runSecuritySimulation();
            }

            const labModal = document.getElementById('labModal');
            const openLabBtn = document.getElementById('openLabBtn');
            const closeLabBtn = document.getElementById('closeLabBtn');
            const textCmd = document.getElementById('textCmd');
            const termHistory = document.getElementById('termHistory');
            const terminalBoxContainer = document.getElementById('terminalBoxContainer');

            if (openLabBtn) {
                openLabBtn.onclick = function(e) {
                    e.preventDefault();
                    labModal.style.display = 'flex';
                    if(textCmd) textCmd.focus();
                };
            }

            if (closeLabBtn) {
                closeLabBtn.onclick = function() {
                    labModal.style.display = 'none';
                };
            }

            if (terminalBoxContainer && textCmd) {
                terminalBoxContainer.onclick = function() {
                    textCmd.focus();
                };
            }

            if (textCmd) {
                textCmd.addEventListener('keydown', function(e) {
                    if (e.key === 'Enter') {
                        const command = textCmd.value.trim();
                        if (command.length > 0) {
                            executeCommand(command);
                        }
                        textCmd.value = '';
                    }
                });
            }

            function executeCommand(cmd) {
                termHistory.innerHTML += `<div><span class="prompt">rick@seclab:~$</span> <span style="color: #fff">${cmd}</span></div>`;
                let output = '';
                const lowerCmd = cmd.toLowerCase();

                if (lowerCmd === 'help') {
                    output = `<span class="cmd-output">Available Commands:<br>
                    - <b>tools</b> : List cybersecurity research tools deployed.<br>
                    - <b>scan</b>  : Run a demo network integrity check.<br>
                    - <b>clear</b> : Clear the terminal interface.<br>
                    - <b>about</b> : Show researcher credential file.</span>`;
                } else if (lowerCmd === 'tools') {
                    output = `<span class="cmd-output">[+] Deployed Tools Inside Termux:<br>
                    - nmap v7.92 (Network Mapper)<br>
                    - hping3 (Packet Generator)<br>
                    - sqlmap v1.6 (Automation Exploit)</span>`;
                } else if (lowerCmd === 'scan') {
                    output = `<span class="cmd-output success-msg">[*] Scanning target loopback...<br>
                    [+] Host 127.0.0.1 is UP.<br>
                    [+] Port 80/tcp OPEN (http)<br>
                    [+] Port 443/tcp OPEN (https)<br>
                    [+] Scan finished. No vulnerability found on current interface.</span>`;
                } else if (lowerCmd === 'about') {
                    output = `<span class="cmd-output">File: rick_credentials.txt<br>
                    Role: Cyber Security Researcher / Bug Bounty Hunter.<br>
                    Specialty: Web Apps Security & Network Auditing.</span>`;
                } else if (lowerCmd === 'clear') {
                    termHistory.innerHTML = '';
                    return;
                } else {
                    output = `<span class="cmd-output" style="color: #ff5f56">Command '${cmd}' not found. Type 'help' for options.</span>`;
                }

                termHistory.innerHTML += output;
                termHistory.scrollTop = termHistory.scrollHeight;
            }

            fetchLatestYouTubeVideos();
        });

        function fetchLatestYouTubeVideos() {
            const grid = document.getElementById('youtubeVideosGrid');
            if (!grid) return;

            if (!YOUTUBE_API_KEY || YOUTUBE_API_KEY.includes("ضغ_")) {
                loadPresetVideos(grid);
                return;
            }

            const url = `https://www.googleapis.com/youtube/v3/search?key=${YOUTUBE_API_KEY}&channelId=${YOUTUBE_CHANNEL_ID}&part=snippet,id&order=date&maxResults=5`;
            fetch(url)
                .then(response => response.json())
                .then(data => {
                    if (data.items && data.items.length > 0) {
                        grid.innerHTML = '';
                        let latestVideoId = '';
                        data.items.forEach((item, index) => {
                            let videoId = item.id.videoId;
                            if(videoId) {
                                if(index === 0) latestVideoId = videoId;
                                grid.innerHTML += createVideoCard(videoId, item.snippet.title);
                            }
                        });
                        
                        if (latestVideoId) {
                            const lastSeenVideo = localStorage.getItem('last_seen_video_id');
                            const isSubscribed = localStorage.getItem('notifications_enabled') === 'true';
                            if (lastSeenVideo && lastSeenVideo !== latestVideoId && isSubscribed) {
                                sendSystemNotification("فيديو جديد متاح!", "قام RICK بنشر مقطع جديد على يوتيوب.");
                            }
                            localStorage.setItem('last_seen_video_id', latestVideoId);
                        }
                    } else {
                        loadPresetVideos(grid);
                    }
                })
                .catch(() => {
                    loadPresetVideos(grid);
                });
        }

        function loadPresetVideos(gridElement) {
            gridElement.innerHTML = '';
            MY_PRESET_VIDEOS.forEach(video => {
                gridElement.innerHTML += createVideoCard(video.id, video.title);
            });
        }

        // تم تفعيل تدوير وتشغيل الفيديو تلقائياً وبكامل طاقة الصوت بالاعتماد على ميزات الأوتوبلاي غير المكتومة
        function createVideoCard(id, title) {
            const cleanTitle = title.replace(/['"\\]/g, "");
            return `
                <div class="video-wrapper" onmouseenter="speakVideoTitle('${cleanTitle}')">
                    <div class="video-container">
                        <iframe src="https://www.youtube.com/embed/${id}?autoplay=1&mute=0&rel=0&modestbranding=1" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                    </div>
                    <div class="video-title">${title}</div>
                </div>
            `;
        }

        function sendSystemNotification(title, body) {
            if ("Notification" in window && Notification.permission === "granted") {
                new Notification(title, { body: body, icon: "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/svgs/solid/user-shield.svg" });
            }
        }

        function activateFollow() {
            if (!("Notification" in window)) { alert("متصفحك لا يدعم الإشعارات."); return; }
            Notification.requestPermission().then(permission => {
                if (permission === "granted") {
                    localStorage.setItem('notifications_enabled', 'true');
                    sendSystemNotification("RICK System Control", "تم تفعيل نظام المتابعة الذكي وقناتك متصلة حالياً!");
                }
            });
        }

        function toggleView() {
            const mainWrapper = document.getElementById('main-content-wrapper');
            const videoSection = document.getElementById('video-section');
            if (videoSection.style.display === 'block') {
                videoSection.style.display = 'none';
                mainWrapper.style.display = 'block';
                if ('speechSynthesis' in window) window.speechSynthesis.cancel();
            } else {
                mainWrapper.style.display = 'none';
                videoSection.style.display = 'block';
                speakVideoTitle("مرحباً بك في مركز العمليات، جاري عرض أحدث المقاطع الأمنية وتشغيلها تلقائياً بالصوت.");
            }
        }

        function resetToHome() {
            document.getElementById('video-section').style.display = 'none';
            document.getElementById('main-content-wrapper').style.display = 'block';
            if ('speechSynthesis' in window) window.speechSynthesis.cancel();
        }

        function setCookie(name, value, days) { let expires = ""; if (days) { let date = new Date(); date.setTime(date.getTime() + (days * 24 * 60 * 60 * 1000)); expires = "; expires=" + date.toUTCString(); } document.cookie = name + "=" + (value || "")  + expires + "; path=/"; }
        function getCookie(name) { let nameEQ = name + "="; let ca = document.cookie.split(';'); for(let i=0;i < ca.length;i++) { let c = ca[i]; while (c.charAt(0)==' ') c = c.substring(1,c.length); if (c.indexOf(nameEQ) == 0) return c.substring(nameEQ.length,c.length); } return null; }
        function runSecuritySimulation() { setTimeout(() => { document.getElementById('line2').style.display = 'block'; }, 400); setTimeout(() => { document.getElementById('line3').style.display = 'block'; }, 800); setTimeout(() => { document.getElementById('line4').style.display = 'block'; }, 1200); setTimeout(() => { document.getElementById('line5').style.display = 'block'; setCookie("rick_session_scanned", "true", 7); document.getElementById('liveCookieBox').style.display = 'block'; document.getElementById('cookieValueSpan').innerText = `rick_session_scanned=true`; }, 1600); setTimeout(() => { document.getElementById('security-check').style.display = 'none'; }, 3200); }

        const mobileMenu = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');
        if (mobileMenu) {
            mobileMenu.addEventListener('click', () => { navList.classList.toggle('active'); });
        }
    </script>
</body>
</html>
