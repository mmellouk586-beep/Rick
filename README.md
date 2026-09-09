<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>RICK | Cyber Security Researcher</title>

    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;700&display=swap" rel="stylesheet" />

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" />

    <style>
        /* ===== VARIABLES ===== */
        :root {
            --bg-glass: rgba(255, 255, 255, 0.3);
            --glass-border: rgba(255, 255, 255, 0.5);
            --glass-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.1);
            --text-dark: #1e1e2f;
            --text-muted: #4a4a5a;
            --accent: #007bff;
            --accent-purple: #8b5cf6;
            --accent-soft: #66b0ff;
            --card-bg: rgba(255, 255, 255, 0.5);
            --chat-bg: rgba(255, 255, 255, 0.6);
            --online-color: #00b894;
            --offline-color: #ff6b6b;
            --recording-color: #ff6b6b;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cairo', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background: linear-gradient(145deg, #f5f7fa 0%, #e9edf5 100%);
            color: var(--text-dark);
            line-height: 1.6;
            min-height: 100vh;
            backdrop-filter: blur(2px);
            padding-top: 70px;
            /* مساحة للهيدر الثابت */
        }

        /* ===== GLASS BASE ===== */
        .glass {
            background: var(--bg-glass);
            backdrop-filter: blur(12px) saturate(180%);
            -webkit-backdrop-filter: blur(12px) saturate(180%);
            border: 1px solid var(--glass-border);
            box-shadow: var(--glass-shadow);
            border-radius: 16px;
        }

        /* ===== SECURITY SCREEN ===== */
        #security-check {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(20px);
            z-index: 99999;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: var(--text-dark);
            font-family: monospace;
            padding: 20px;
            direction: ltr;
        }
        .scan-terminal {
            width: 100%;
            max-width: 500px;
            background: rgba(255, 255, 255, 0.5);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.7);
            border-radius: 16px;
            padding: 20px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
        }
        .scan-line {
            margin-bottom: 8px;
            white-space: nowrap;
            overflow: hidden;
            font-size: 14px;
            color: var(--text-dark);
        }
        .cookie-display-panel {
            margin-top: 15px;
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(8px);
            border: 1px dashed var(--accent);
            padding: 10px;
            border-radius: 12px;
            width: 100%;
            font-size: 12px;
            color: var(--accent);
        }

        /* ===== HEADER (FIXED - NEVER HIDES) ===== */
        header {
            position: fixed;
            top: 0;
            right: 0;
            width: 100%;
            z-index: 1000;
            background: var(--bg-glass);
            backdrop-filter: blur(16px) saturate(180%);
            -webkit-backdrop-filter: blur(16px) saturate(180%);
            border-bottom: 1px solid var(--glass-border);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.04);
            /* إزالة أي transition أو transform متعلق بالإخفاء */
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 20px;
        }
        .logo-area {
            display: flex;
            align-items: center;
            gap: 8px;
            flex-wrap: wrap;
        }
        .logo {
            font-size: 24px;
            font-weight: 700;
            letter-spacing: 1px;
            /* تدرج أزرق - بنفسجي */
            background: linear-gradient(135deg, #007bff, #8b5cf6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .network-speed {
            display: flex;
            align-items: center;
            gap: 4px;
            background: rgba(255, 255, 255, 0.4);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            border-radius: 30px;
            padding: 2px 10px;
            font-size: 9px;
            color: var(--text-muted);
            font-family: monospace;
            direction: ltr;
        }
        .network-speed i {
            font-size: 9px;
            color: var(--accent);
        }
        .network-speed .speed-value {
            color: var(--accent);
            font-weight: bold;
            min-width: 30px;
            text-align: center;
        }
        .network-speed .speed-unit {
            color: var(--text-muted);
        }

        .header-follow-btn,
        .header-users-btn,
        .header-chat-btn,
        .nav-video-toggle {
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(8px);
            border: 1px solid var(--glass-border);
            color: var(--text-dark);
            padding: 3px 12px;
            border-radius: 30px;
            font-size: 11px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.25s ease;
            display: flex;
            align-items: center;
            gap: 4px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.02);
        }
        .header-follow-btn:hover,
        .header-users-btn:hover,
        .header-chat-btn:hover,
        .nav-video-toggle:hover {
            background: rgba(0, 123, 255, 0.15);
            border-color: var(--accent);
            box-shadow: 0 4px 12px rgba(0, 123, 255, 0.15);
            transform: translateY(-1px);
        }
        .header-chat-btn .chat-notification {
            background: var(--accent);
            color: #fff;
            border-radius: 50%;
            padding: 0 5px;
            font-size: 8px;
            font-weight: bold;
            min-width: 16px;
            text-align: center;
        }

        nav ul {
            display: flex;
            list-style: none;
            align-items: center;
            gap: 6px;
        }
        nav ul li a {
            color: var(--text-dark);
            text-decoration: none;
            font-size: 14px;
            font-weight: 500;
            padding: 4px 10px;
            border-radius: 30px;
            transition: 0.2s;
        }
        nav ul li a:hover {
            background: rgba(0, 123, 255, 0.1);
            color: var(--accent);
        }
        .menu-toggle {
            display: none;
            font-size: 22px;
            color: var(--text-dark);
            cursor: pointer;
        }

        /* ===== CHAT MODAL ===== */
        .chat-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(6px);
            z-index: 40000;
            display: none;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        .chat-box {
            background: var(--chat-bg);
            backdrop-filter: blur(20px) saturate(200%);
            -webkit-backdrop-filter: blur(20px) saturate(200%);
            border: 1px solid var(--glass-border);
            border-radius: 24px;
            width: 100%;
            max-width: 500px;
            height: 80vh;
            max-height: 600px;
            display: flex;
            flex-direction: column;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.08);
        }
        .chat-header {
            padding: 16px 20px;
            border-bottom: 1px solid var(--glass-border);
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(8px);
            border-radius: 24px 24px 0 0;
        }
        .chat-header h3 {
            color: var(--text-dark);
            font-size: 18px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .chat-header h3 i {
            color: var(--accent);
        }
        .chat-header .chat-status {
            font-size: 11px;
            color: var(--online-color);
            display: flex;
            align-items: center;
            gap: 4px;
        }
        .chat-header .chat-status .dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: var(--online-color);
            display: inline-block;
            animation: pulse 1.5s infinite;
        }
        @keyframes pulse {
            0%,
            100% {
                opacity: 1;
            }
            50% {
                opacity: 0.3;
            }
        }
        .chat-close-btn {
            background: none;
            border: none;
            color: var(--text-muted);
            font-size: 20px;
            cursor: pointer;
            transition: 0.3s;
        }
        .chat-close-btn:hover {
            color: var(--accent);
            transform: rotate(90deg);
        }

        .chat-messages {
            flex: 1;
            overflow-y: auto;
            padding: 16px 20px;
            display: flex;
            flex-direction: column;
            gap: 8px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(4px);
        }
        .chat-messages::-webkit-scrollbar {
            width: 4px;
        }
        .chat-messages::-webkit-scrollbar-thumb {
            background: var(--accent-soft);
            border-radius: 4px;
        }

        .chat-msg {
            max-width: 85%;
            padding: 8px 16px;
            border-radius: 18px;
            font-size: 13px;
            word-wrap: break-word;
            animation: msgAppear 0.3s ease;
            backdrop-filter: blur(4px);
        }
        .chat-msg.sent {
            background: var(--accent);
            color: #fff;
            align-self: flex-end;
            border-bottom-right-radius: 4px;
        }
        .chat-msg.received {
            background: rgba(255, 255, 255, 0.6);
            backdrop-filter: blur(8px);
            border: 1px solid var(--glass-border);
            color: var(--text-dark);
            align-self: flex-start;
            border-bottom-left-radius: 4px;
        }
        .chat-msg .msg-time {
            font-size: 9px;
            opacity: 0.6;
            display: block;
            margin-top: 4px;
        }
        .chat-msg .msg-sender {
            font-size: 10px;
            color: var(--accent);
            display: block;
            margin-bottom: 2px;
            font-weight: bold;
        }
        .chat-msg .msg-source {
            font-size: 9px;
            color: var(--text-muted);
            display: block;
            margin-top: 2px;
        }

        .chat-input-area {
            padding: 12px 20px;
            border-top: 1px solid var(--glass-border);
            display: flex;
            gap: 8px;
            align-items: center;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(8px);
            border-radius: 0 0 24px 24px;
            flex-wrap: wrap;
        }
        .chat-input-area input {
            flex: 1;
            background: rgba(255, 255, 255, 0.5);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            border-radius: 30px;
            padding: 8px 18px;
            color: var(--text-dark);
            outline: none;
            font-size: 13px;
            min-width: 100px;
        }
        .chat-input-area input:focus {
            border-color: var(--accent);
            box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.1);
        }

        .chat-input-area .voice-btn {
            background: rgba(255, 255, 255, 0.4);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            border-radius: 50%;
            width: 36px;
            height: 36px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            color: var(--text-dark);
            transition: all 0.3s;
            flex-shrink: 0;
        }
        .chat-input-area .voice-btn:hover {
            background: var(--accent);
            color: #fff;
            border-color: var(--accent);
        }
        .chat-input-area .voice-btn.recording {
            background: var(--recording-color);
            border-color: var(--recording-color);
            color: #fff;
            animation: pulse-rec 1s infinite;
        }
        @keyframes pulse-rec {
            0%,
            100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.1);
            }
        }

        .chat-input-area .chat-send-btn {
            background: var(--accent);
            border: none;
            color: #fff;
            padding: 8px 20px;
            border-radius: 30px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
            font-size: 13px;
            flex-shrink: 0;
        }
        .chat-input-area .chat-send-btn:hover {
            opacity: 0.85;
            transform: scale(0.97);
        }

        .typing-indicator {
            display: none;
            align-self: flex-start;
            padding: 6px 16px;
            background: rgba(255, 255, 255, 0.5);
            backdrop-filter: blur(8px);
            border: 1px solid var(--glass-border);
            border-radius: 18px;
            border-bottom-left-radius: 4px;
            font-size: 13px;
            color: var(--text-muted);
            animation: msgAppear 0.3s ease;
        }

        /* ===== USERS MODAL ===== */
        .users-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0, 0, 0, 0.15);
            backdrop-filter: blur(6px);
            z-index: 30000;
            display: none;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        .users-modal-box {
            background: var(--card-bg);
            backdrop-filter: blur(20px) saturate(200%);
            border: 1px solid var(--glass-border);
            border-radius: 24px;
            padding: 30px;
            max-width: 480px;
            width: 100%;
            text-align: center;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.06);
        }
        .users-modal-box h2 {
            color: var(--text-dark);
            margin-bottom: 20px;
            font-size: 22px;
        }

        .profile-card {
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(8px);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 25px 20px;
            margin-bottom: 20px;
        }
        .profile-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent-soft), var(--accent-purple));
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 12px;
            font-size: 36px;
            color: #fff;
            border: 3px solid rgba(255, 255, 255, 0.6);
            box-shadow: 0 8px 24px rgba(0, 123, 255, 0.2);
        }
        .status-dot {
            display: inline-block;
            width: 14px;
            height: 14px;
            border-radius: 50%;
            border: 2px solid #fff;
            transition: background-color 0.3s;
            background-color: var(--online-color);
            box-shadow: 0 0 0 2px rgba(0, 184, 148, 0.3);
        }
        .status-dot.offline {
            background-color: var(--offline-color);
        }
        .status-dot.idle {
            background-color: #fdcb6e;
        }

        .profile-name {
            color: var(--text-dark);
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 4px;
        }
        .profile-email {
            color: var(--accent);
            font-size: 14px;
            cursor: pointer;
            transition: 0.3s;
        }
        .profile-email:hover {
            text-shadow: 0 0 8px rgba(0, 123, 255, 0.2);
        }
        .profile-bio {
            color: var(--text-muted);
            font-size: 13px;
            margin-top: 8px;
            padding-top: 8px;
            border-top: 1px solid var(--glass-border);
        }

        .profile-actions {
            display: flex;
            gap: 8px;
            justify-content: center;
            margin-top: 12px;
            flex-wrap: wrap;
        }
        .profile-action-btn {
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            color: var(--text-dark);
            padding: 6px 14px;
            border-radius: 30px;
            font-size: 12px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 6px;
        }
        .profile-action-btn:hover {
            background: var(--accent);
            color: #fff;
            border-color: var(--accent);
            transform: translateY(-2px);
        }
        .profile-action-btn.friend-btn:hover {
            background: #00b894;
            border-color: #00b894;
        }
        .profile-action-btn.message-btn:hover {
            background: #fdcb6e;
            border-color: #fdcb6e;
            color: #1e1e2f;
        }

        .message-popup {
            display: none;
            margin-top: 12px;
            padding: 16px;
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(8px);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
        }
        .message-popup textarea {
            width: 100%;
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            border-radius: 12px;
            padding: 10px;
            color: var(--text-dark);
            font-family: 'Cairo', sans-serif;
            resize: vertical;
            min-height: 60px;
            outline: none;
            font-size: 13px;
        }
        .message-popup textarea:focus {
            border-color: var(--accent);
        }
        .message-popup .send-msg-btn {
            margin-top: 8px;
            background: var(--accent);
            border: none;
            color: #fff;
            padding: 8px;
            border-radius: 30px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
            width: 100%;
            font-size: 13px;
        }
        .message-popup .send-msg-btn:hover {
            opacity: 0.85;
        }

        .users-modal-close {
            margin-top: 12px;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            color: var(--text-dark);
            padding: 6px 20px;
            border-radius: 30px;
            cursor: pointer;
            transition: 0.3s;
            font-size: 13px;
        }
        .users-modal-close:hover {
            background: var(--accent);
            color: #fff;
            border-color: var(--accent);
        }

        /* ===== HERO ===== */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 120px 20px 60px;
            background: radial-gradient(circle at 30% 40%, rgba(0, 123, 255, 0.05) 0%, rgba(255, 255, 255, 0) 70%);
            flex-direction: column;
        }
        .hero-avatar {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            border: 4px solid rgba(255, 255, 255, 0.6);
            box-shadow: 0 8px 32px rgba(0, 123, 255, 0.15);
            margin-bottom: 20px;
            object-fit: cover;
            backdrop-filter: blur(4px);
        }
        .hero-content h1 {
            font-size: 3rem;
            color: var(--text-dark);
            margin-bottom: 10px;
        }
        .hero-content p {
            font-size: 1.2rem;
            color: var(--accent);
            margin-bottom: 30px;
            font-family: monospace;
        }
        .btn {
            display: inline-block;
            padding: 12px 32px;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(8px);
            border: 1px solid var(--glass-border);
            color: var(--text-dark);
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.02);
        }
        .btn:hover {
            background: var(--accent);
            color: #fff;
            border-color: var(--accent);
            box-shadow: 0 8px 24px rgba(0, 123, 255, 0.25);
            transform: translateY(-2px);
        }

        /* ===== SECTIONS ===== */
        section {
            padding: 60px 20px 40px;
            max-width: 1200px;
            margin: 0 auto;
        }
        .section-title {
            text-align: center;
            font-size: 2rem;
            color: var(--text-dark);
            margin-bottom: 40px;
            position: relative;
        }
        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 3px;
            background: var(--accent);
            margin: 10px auto 0;
            border-radius: 6px;
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 40px;
            align-items: center;
        }
        .avatar-placeholder {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(8px);
            border: 3px solid var(--glass-border);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 65px;
            color: var(--accent);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.04);
            object-fit: cover;
        }

        .grid-3 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            justify-items: center;
        }
        .card {
            background: var(--card-bg);
            backdrop-filter: blur(12px) saturate(180%);
            border: 1px solid var(--glass-border);
            padding: 30px;
            border-radius: 20px;
            transition: all 0.3s ease;
            box-shadow: var(--glass-shadow);
            width: 100%;
            max-width: 360px;
            text-align: center;
        }
        .card:hover {
            transform: translateY(-6px);
            border-color: var(--accent-soft);
            box-shadow: 0 12px 40px rgba(0, 123, 255, 0.08);
        }
        .card i {
            font-size: 32px;
            color: var(--accent);
            margin-bottom: 20px;
        }
        .card h3 {
            color: var(--text-dark);
            margin-bottom: 15px;
        }

        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 16px;
            justify-content: center;
        }
        .skill-badge {
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            color: var(--text-dark);
            padding: 6px 18px;
            border-radius: 30px;
            font-size: 14px;
            transition: 0.3s;
        }
        .skill-badge:hover {
            background: var(--accent);
            color: #fff;
            border-color: var(--accent);
        }

        .contact-info {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }
        .social-links {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 30px;
        }
        .social-links a {
            color: var(--text-muted);
            font-size: 28px;
            transition: all 0.3s;
        }
        .social-links a:hover {
            color: var(--accent);
            transform: scale(1.2);
        }

        footer {
            text-align: center;
            padding: 30px;
            border-top: 1px solid var(--glass-border);
            font-size: 14px;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(8px);
            color: var(--text-muted);
        }
        .privacy-link {
            display: inline-block;
            margin-top: 10px;
            color: var(--accent);
            text-decoration: none;
            font-weight: 300;
            font-size: 13px;
            transition: 0.3s;
        }
        .privacy-link:hover {
            text-shadow: 0 0 8px rgba(0, 123, 255, 0.2);
        }

        /* ===== VIDEO SECTION ===== */
        #video-section {
            display: none;
            padding: 120px 20px 80px;
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
            backdrop-filter: blur(12px) saturate(180%);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 15px;
            width: 340px;
            box-shadow: var(--glass-shadow);
            transition: all 0.3s;
        }
        .video-wrapper:hover {
            border-color: var(--accent-soft);
            transform: translateY(-4px);
        }
        .video-container {
            width: 100%;
            height: 450px;
            border-radius: 12px;
            overflow: hidden;
            background: #000;
            border: 1px solid var(--glass-border);
        }
        .video-container iframe,
        .video-container video {
            width: 100%;
            height: 100%;
            border: none;
            object-fit: cover;
        }
        .video-title {
            font-size: 15px;
            font-weight: bold;
            color: var(--text-dark);
            margin-top: 10px;
            text-align: right;
        }
        .video-translation {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            border-radius: 12px;
            padding: 10px;
            margin-top: 10px;
            font-size: 12px;
            color: var(--text-muted);
            text-align: right;
            max-height: 120px;
            overflow-y: auto;
            line-height: 1.5;
        }
        .video-translation strong {
            color: var(--accent);
            display: block;
            margin-bottom: 4px;
            font-size: 13px;
        }

        .interaction-buttons {
            display: flex;
            gap: 12px;
            margin-top: 12px;
            justify-content: center;
        }
        .interaction-btn {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            color: var(--text-dark);
            padding: 4px 16px;
            border-radius: 30px;
            font-size: 13px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 6px;
        }
        .interaction-btn:hover {
            border-color: var(--accent);
            color: var(--accent);
        }
        .interaction-btn.liked {
            border-color: #ff6b6b;
            color: #ff6b6b;
        }
        .interaction-btn i {
            font-size: 14px;
        }

        .comment-area {
            margin-top: 10px;
            display: flex;
            gap: 8px;
            align-items: center;
        }
        .comment-area input {
            flex: 1;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            border-radius: 30px;
            padding: 6px 16px;
            color: var(--text-dark);
            font-size: 12px;
            outline: none;
        }
        .comment-area input:focus {
            border-color: var(--accent);
        }
        .comment-area button {
            background: var(--accent);
            border: none;
            color: #fff;
            padding: 6px 14px;
            border-radius: 30px;
            font-weight: bold;
            cursor: pointer;
            font-size: 12px;
        }
        .comment-area button:hover {
            opacity: 0.85;
        }

        /* ===== LAB BUTTON (SMALLER) ===== */
        .lab-float-btn {
            position: fixed;
            bottom: 30px;
            left: 30px;
            background: var(--card-bg);
            backdrop-filter: blur(12px);
            border: 1px solid var(--glass-border);
            color: var(--text-dark);
            padding: 10px 18px;
            border-radius: 50px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            box-shadow: var(--glass-shadow);
            z-index: 9999;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s;
        }
        .lab-float-btn:hover {
            transform: scale(1.04);
            border-color: var(--accent);
            box-shadow: 0 8px 32px rgba(0, 123, 255, 0.15);
        }
        .lab-float-btn i {
            font-size: 18px;
        }

        /* ===== LAB MODAL ===== */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0, 0, 0, 0.15);
            backdrop-filter: blur(8px);
            z-index: 20000;
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
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(20px);
            border: 14px solid rgba(255, 255, 255, 0.3);
            border-radius: 20px 20px 0 0;
            height: 480px;
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }
        .title-bar {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(4px);
            color: var(--text-dark);
            padding: 6px 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            direction: ltr;
            border-bottom: 1px solid var(--glass-border);
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
        .close {
            background: #ff5f56;
        }
        .title-bar-text {
            flex-grow: 1;
            text-align: center;
            font-size: 13px;
            font-family: monospace;
        }

        .simulator-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            background: rgba(255, 255, 255, 0.1);
            padding: 10px;
        }
        .terminal-box {
            flex: 1;
            border: 1px solid var(--glass-border);
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(4px);
            border-radius: 12px;
            display: flex;
            flex-direction: column;
            direction: ltr;
            overflow: hidden;
        }
        .history-container {
            flex: 1;
            overflow-y: auto;
            white-space: pre-wrap;
            color: var(--text-dark);
            font-family: monospace;
            font-size: 13px;
            padding: 15px;
            text-align: left;
        }
        .input-line {
            display: flex;
            align-items: center;
            padding: 8px 12px;
            border-top: 1px solid var(--glass-border);
            background: rgba(255, 255, 255, 0.1);
        }
        .prompt {
            color: var(--accent);
            margin-right: 8px;
            font-family: monospace;
            font-size: 14px;
            white-space: nowrap;
        }
        .term-input {
            background: none;
            border: none;
            color: var(--text-dark);
            width: 100%;
            outline: none;
            font-family: monospace;
            font-size: 14px;
        }
        .system-msg {
            color: var(--text-muted);
        }
        .cmd-output {
            color: var(--text-dark);
            margin-top: 4px;
            margin-bottom: 10px;
            display: block;
        }
        .success-msg {
            color: var(--accent);
        }

        /* ===== AI CHATBOT (SMALLER) ===== */
        .ai-chatbot-toggle {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: var(--accent);
            color: #fff;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 22px;
            cursor: pointer;
            box-shadow: 0 8px 32px rgba(0, 123, 255, 0.35);
            z-index: 15000;
            border: none;
            transition: all 0.3s ease;
            backdrop-filter: blur(4px);
        }
        .ai-chatbot-toggle:hover {
            transform: scale(1.08);
            box-shadow: 0 12px 40px rgba(0, 123, 255, 0.45);
        }

        .ai-chatbot-window {
            position: fixed;
            bottom: 90px;
            right: 30px;
            width: 360px;
            max-width: 90vw;
            height: 420px;
            background: var(--chat-bg);
            backdrop-filter: blur(24px) saturate(200%);
            border: 1px solid var(--glass-border);
            border-radius: 24px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.08);
            z-index: 15001;
            display: none;
            flex-direction: column;
            overflow: hidden;
            transition: all 0.3s ease;
        }
        .ai-chatbot-window.open {
            display: flex;
        }

        .ai-chat-header {
            padding: 12px 18px;
            border-bottom: 1px solid var(--glass-border);
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(8px);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .ai-chat-header h4 {
            color: var(--text-dark);
            font-size: 15px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .ai-chat-header h4 i {
            color: var(--accent);
        }
        .ai-chat-close {
            background: none;
            border: none;
            color: var(--text-muted);
            font-size: 20px;
            cursor: pointer;
            transition: 0.3s;
        }
        .ai-chat-close:hover {
            color: var(--accent);
            transform: rotate(90deg);
        }

        .ai-chat-messages {
            flex: 1;
            overflow-y: auto;
            padding: 16px;
            display: flex;
            flex-direction: column;
            gap: 8px;
            background: rgba(255, 255, 255, 0.05);
        }
        .ai-msg {
            max-width: 85%;
            padding: 8px 16px;
            border-radius: 18px;
            font-size: 13px;
            word-wrap: break-word;
            animation: msgAppear 0.3s ease;
        }
        .ai-msg.bot {
            background: rgba(255, 255, 255, 0.4);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            color: var(--text-dark);
            align-self: flex-start;
            border-bottom-left-radius: 4px;
        }
        .ai-msg.user {
            background: var(--accent);
            color: #fff;
            align-self: flex-end;
            border-bottom-right-radius: 4px;
        }
        .ai-msg .msg-time {
            font-size: 9px;
            opacity: 0.6;
            display: block;
            margin-top: 4px;
        }

        .ai-chat-input-area {
            padding: 12px 16px;
            border-top: 1px solid var(--glass-border);
            display: flex;
            gap: 8px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(8px);
        }
        .ai-chat-input-area input {
            flex: 1;
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(4px);
            border: 1px solid var(--glass-border);
            border-radius: 30px;
            padding: 8px 16px;
            color: var(--text-dark);
            outline: none;
            font-size: 13px;
        }
        .ai-chat-input-area input:focus {
            border-color: var(--accent);
        }
        .ai-chat-input-area button {
            background: var(--accent);
            border: none;
            color: #fff;
            padding: 8px 16px;
            border-radius: 30px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
            font-size: 13px;
        }
        .ai-chat-input-area button:hover {
            opacity: 0.85;
        }

        @keyframes msgAppear {
            from {
                opacity: 0;
                transform: translateY(6px) scale(0.96);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }
            nav ul {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: rgba(255, 255, 255, 0.7);
                backdrop-filter: blur(20px);
                padding: 20px;
                gap: 10px;
                border-radius: 0 0 20px 20px;
                border: 1px solid var(--glass-border);
                border-top: none;
            }
            nav ul.active {
                display: flex;
            }
            nav ul li {
                margin-right: 0;
                text-align: center;
            }
            .about-grid {
                grid-template-columns: 1fr;
                text-align: center;
            }
            .profile-actions {
                flex-wrap: wrap;
                justify-content: center;
            }
            .network-speed {
                font-size: 8px;
                padding: 1px 8px;
            }
            .network-speed .speed-value {
                min-width: 30px;
            }
            .chat-box {
                max-height: 90vh;
                height: 90vh;
            }
            .chat-input-area input {
                min-width: 60px;
            }
            .ai-chatbot-window {
                width: 90vw;
                right: 5vw;
                bottom: 90px;
            }
            .hero-content h1 {
                font-size: 2.4rem;
            }

            .grid-3 {
                grid-template-columns: 1fr;
                justify-items: center;
            }
            .card {
                max-width: 100%;
                width: 100%;
            }
            .header-follow-btn,
            .header-users-btn,
            .header-chat-btn,
            .nav-video-toggle {
                font-size: 10px;
                padding: 2px 10px;
            }
            .logo {
                font-size: 18px;
            }
            .lab-float-btn {
                padding: 8px 14px;
                font-size: 12px;
                bottom: 20px;
                left: 20px;
            }
            .lab-float-btn i {
                font-size: 16px;
            }
            .ai-chatbot-toggle {
                width: 44px;
                height: 44px;
                font-size: 18px;
                bottom: 20px;
                right: 20px;
            }
            .video-wrapper {
                width: 100%;
            }
        }
    </style>
</head>
<body>

    <!-- ===== SECURITY CHECK ===== -->
    <div id="security-check">
        <div class="scan-terminal">
            <div class="scan-line" id="line1">> Initializing visitor integrity scan...</div>
            <div class="scan-line" id="line2" style="display:none">> Checking browser session structures...</div>
            <div class="scan-line" id="line3" style="display:none">> IP Routing Protocol: 172.217.16.14 verified.</div>
            <div class="scan-line" id="line4" style="display:none">> Injecting anti-bot token tracking...</div>
            <div class="scan-line" id="line5" style="display:none; color: var(--accent);">> [SUCCESS] Cookies set. Access granted!</div>
            <div class="cookie-display-panel" id="liveCookieBox" style="display: none;">
                🍪 Active Browser Cookie: <span id="cookieValueSpan">None</span>
            </div>
        </div>
    </div>

    <!-- ===== HEADER (FIXED - NEVER HIDES) ===== -->
    <header id="mainHeader">
        <div class="nav-container">
            <div class="logo-area">
                <div class="logo">RICK</div>
                <div class="network-speed" id="networkSpeed">
                    <i class="fa-solid fa-wifi"></i>
                    <span class="speed-value" id="speedValue">0</span>
                    <span class="speed-unit">Kbps</span>
                </div>
                <button class="header-follow-btn" onclick="activateFollow()">[ Follow ]</button>
                <button class="header-users-btn" onclick="openUsersModal()"><i class="fa-solid fa-users"></i> [ المستخدمين ]</button>
                <button class="header-chat-btn" onclick="openChat()">
                    <i class="fa-solid fa-comment-dots"></i>
                    <span>[ شات ]</span>
                    <span class="chat-notification" id="chatNotif" style="display:none;">0</span>
                </button>
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

    <!-- ===== MAIN CONTENT (ORIGINAL) ===== -->
    <div id="main-content-wrapper">
        <section id="home" class="hero">
            <img src="IMG_20260710_104918.png" alt="Rick Avatar" class="hero-avatar" />
            <div class="hero-content">
                <h1>مرحباً، أنا Rick</h1>
                <p>>_ Cybersecurity Researcher & Ethical Hacker</p>
                <a href="#contact" class="btn">اطلب فحص أمني الآن</a>
            </div>
        </section>

        <section id="about">
            <h2 class="section-title">من أنا</h2>
            <div class="about-grid">
                <div class="profile-img-container">
                    <img src="IMG_20260710_104918.png" alt="Rick Profile" class="avatar-placeholder" />
                </div>
                <div>
                    <p style="font-size: 18px; margin-bottom: 20px;">أنا <strong>Rick</strong>، باحث متخصص في الأمن السيبراني.</p>
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
                    <a href="https://www.tiktok.com/@rick_6000?_r=1&_t=ZS-97ujNamvHms" title="TikTok" target="_blank"><i class="fa-brands fa-tiktok"></i></a>
                    <a href="mailto:mmellouk586@gmail.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
                </div>
            </div>
        </section>
    </div>

    <!-- ===== VIDEO SECTION ===== -->
    <section id="video-section">
        <h2 class="section-title">المقاطع المنشورة</h2>
        <div class="videos-grid" id="youtubeVideosGrid"></div>
    </section>

    <!-- ===== CHAT MODAL ===== -->
    <div class="chat-modal" id="chatModal">
        <div class="chat-box">
            <div class="chat-header">
                <h3><i class="fa-solid fa-comment-dots"></i> غرفة الشات</h3>
                <div class="chat-status">
                    <span class="dot"></span> <span id="chatStatusText">متصل</span>
                </div>
                <button class="chat-close-btn" onclick="closeChat()"><i class="fa-solid fa-xmark"></i></button>
            </div>
            <div class="chat-messages" id="chatMessages">
                <div class="chat-empty">
                    <i class="fa-regular fa-comment"></i>
                    <p>لا توجد رسائل بعد<br>ابدأ المحادثة الآن!</p>
                </div>
            </div>
            <div class="typing-indicator" id="typingIndicator">
                <span>الطرف الآخر يكتب</span>
                <span class="dots">...</span>
            </div>
            <div class="chat-input-area">
                <div style="display:flex; flex:1; gap:5px; align-items:center; flex-wrap:wrap;">
                    <input type="text" id="chatInput" placeholder="اكتب رسالتك..." onkeypress="if(event.key==='Enter') sendChatMessage()" />
                    <button class="preview-btn" onclick="previewTextMessage()" title="استماع للرسالة قبل الإرسال" style="background:rgba(255,255,255,0.2); backdrop-filter:blur(4px); border:1px solid var(--glass-border); border-radius:30px; padding:4px 12px; font-size:11px; cursor:pointer; color:var(--text-dark);">
                        <i class="fa-solid fa-ear-listen"></i> استماع
                    </button>
                </div>
                <button class="voice-btn" id="voiceBtn" onclick="toggleRecording()" title="تسجيل رسالة صوتية">
                    <i class="fa-solid fa-microphone"></i>
                    <span class="recording-dot"></span>
                </button>
                <button class="chat-send-btn" onclick="sendChatMessage()"><i class="fa-regular fa-paper-plane"></i> إرسال</button>
            </div>
        </div>
    </div>

    <!-- ===== USERS MODAL ===== -->
    <div class="users-modal" id="usersModal">
        <div class="users-modal-box">
            <h2><i class="fa-solid fa-user"></i> الملف الشخصي</h2>
            <div class="profile-card">
                <div class="profile-avatar">
                    <i class="fa-solid fa-user-secret"></i>
                </div>
                <div class="profile-name">Rick</div>
                <div class="profile-email" onclick="copyEmail()">
                    <i class="fa-regular fa-envelope"></i> mmellouk586@gmail.com
                </div>
                <div class="profile-bio">
                    <i class="fa-solid fa-shield-halved" style="color: var(--accent);"></i>
                    باحث في الأمن السيبراني | متخصص في اختبار الاختراق
                </div>
            </div>
            <div class="profile-actions">
                <button class="profile-action-btn friend-btn" onclick="sendFriendRequest()">
                    <i class="fa-solid fa-user-plus"></i> طلب صداقة
                </button>
                <button class="profile-action-btn message-btn" onclick="toggleMessagePopup()">
                    <i class="fa-regular fa-paper-plane"></i> رسالة
                </button>
            </div>
            <div class="message-popup" id="messagePopup">
                <textarea id="messageText" placeholder="اكتب رسالتك هنا..."></textarea>
                <button class="send-msg-btn" onclick="sendMessage()">
                    <i class="fa-regular fa-paper-plane"></i> إرسال الرسالة
                </button>
            </div>
            <button class="users-modal-close" onclick="closeUsersModal()">إغلاق</button>
        </div>
    </div>

    <!-- ===== LAB BUTTON (SMALLER) ===== -->
    <button class="lab-float-btn" id="openLabBtn"><i class="fa-solid fa-terminal"></i> <span>[ Lab ]</span></button>

    <!-- ===== LAB MODAL ===== -->
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
                            <input type="text" id="textCmd" class="term-input" autocomplete="off" autofocus />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- ===== AI CHATBOT (SMALLER) ===== -->
    <button class="ai-chatbot-toggle" id="aiChatToggle" title="اسأل المساعد الذكي">
        <i class="fa-regular fa-comment-dots"></i>
    </button>

    <div class="ai-chatbot-window" id="aiChatWindow">
        <div class="ai-chat-header">
            <h4><i class="fa-regular fa-message"></i> المساعد الذكي</h4>
            <button class="ai-chat-close" onclick="closeAiChat()"><i class="fa-solid fa-xmark"></i></button>
        </div>
        <div class="ai-chat-messages" id="aiChatMessages">
            <div class="ai-msg bot">
                مرحباً! أنا المساعد الذكي لموقع Rick. اسألني عن الخدمات، المهارات، أو أي شيء يتعلق بالأمن السيبراني.
                <span class="msg-time">الآن</span>
            </div>
        </div>
        <div class="ai-chat-input-area">
            <input type="text" id="aiChatInput" placeholder="اكتب سؤالك..." onkeypress="if(event.key==='Enter') sendAiMessage()" />
            <button onclick="sendAiMessage()"><i class="fa-regular fa-paper-plane"></i></button>
        </div>
    </div>

    <!-- ===== FOOTER ===== -->
    <footer>
        <p>&copy; 2026 Rick. جميع الحقوق محفوظة</p>
        <a href="#privacy" class="privacy-link" onclick="alert('سياسة الخصوصية:\nنحن نحترم خصوصيتك بالكامل. جميع عمليات المحاكاة والفحص الأمني داخل هذا الموقع تجري محلياً في بيئة اختبار آمنة تماماً، ولا نقوم بجمع أو مشاركة أي بيانات حساسة تخص الزوار.')">سياسة الخصوصية</a>
    </footer>

    <script>
        // ============================================================
        //  ALL ORIGINAL FUNCTIONS (RETAINED EXACTLY AS THEY WERE)
        //  (Voice, Chat, Users, Lab, Video, Cookies, Network, etc.)
        //  مع تغيير اسم "Reck" إلى "Rick" في النصوص والرسائل الترحيبية
        //  تم إزالة كود إخفاء/إظهار الهيدر نهائياً
        // ============================================================

        // ---------------------- COOKIE HELPERS ----------------------
        function setCookie(name, value, days) {
            let expires = "";
            if (days) {
                let date = new Date();
                date.setTime(date.getTime() + (days * 24 * 60 * 60 * 1000));
                expires = "; expires=" + date.toUTCString();
            }
            document.cookie = name + "=" + (value || "") + expires + "; path=/; SameSite=Lax";
        }

        function getCookie(name) {
            let nameEQ = name + "=";
            let ca = document.cookie.split(';');
            for (let i = 0; i < ca.length; i++) {
                let c = ca[i];
                while (c.charAt(0) == ' ') c = c.substring(1, c.length);
                if (c.indexOf(nameEQ) == 0) return c.substring(nameEQ.length, c.length);
            }
            return null;
        }

        // ---------------------- SESSION INIT ----------------------
        function initUserSession() {
            let userId = getCookie('rick_user_id');
            if (!userId) {
                userId = 'user_' + Date.now() + '_' + Math.random().toString(36).substr(2, 6);
                setCookie('rick_user_id', userId, 30);
                setCookie('rick_first_visit', new Date().toISOString(), 30);
            }
            setCookie('rick_last_visit', new Date().toISOString(), 30);
            let visits = parseInt(getCookie('rick_visits') || '0') + 1;
            setCookie('rick_visits', visits.toString(), 30);
        }

        // ---------------------- SECURITY SCREEN ----------------------
        function runSecuritySimulation() {
            setTimeout(() => { document.getElementById('line2').style.display = 'block'; }, 400);
            setTimeout(() => { document.getElementById('line3').style.display = 'block'; }, 800);
            setTimeout(() => { document.getElementById('line4').style.display = 'block'; }, 1200);
            setTimeout(() => {
                document.getElementById('line5').style.display = 'block';
                setCookie("rick_session_scanned", "true", 7);
                document.getElementById('liveCookieBox').style.display = 'block';
                document.getElementById('cookieValueSpan').innerText = `rick_session_scanned=true`;
            }, 1600);
            setTimeout(() => {
                document.getElementById('security-check').style.display = 'none';
                initUserSession();
                loadChatMessages();
                renderChatMessages();
                simulateEmailReception();
                checkUrlParams();

                setTimeout(() => {
                    receiveChatMessage('📧 مرحباً بك في غرفة الشات! يمكنك إرسال رسائل نصية أو صوتية.', 'النظام',
                        '📧 نظام البريد');
                }, 1500);
                setTimeout(() => {
                    receiveChatMessage('👋 أهلاً! أنا هنا لمساعدتك. يمكنك التواصل معي عبر الشات أو البريد الإلكتروني.',
                        'Rick', '📧 البريد الإلكتروني');
                }, 3000);
                setTimeout(() => {
                    receiveChatMessage('🔗 تم تفعيل نظام الروابط المباشرة. عند الضغط على رابط في البريد، ستظهر الرسالة تلقائياً.',
                        'النظام', '🔗 روابط مباشرة');
                }, 4500);
            }, 3200);
        }

        // ---------------------- CHAT SYSTEM ----------------------
        let chatMessages = [];
        let isChatOpen = false;
        let notificationSound = null;
        const CHAT_STORAGE_KEY = 'rick_chat_messages';
        const SITE_URL = 'https://mmellouk586-beep.github.io/Rick/';
        const TARGET_EMAIL = 'mmellouk586@gmail.com';

        function loadChatMessages() {
            try {
                const stored = localStorage.getItem(CHAT_STORAGE_KEY);
                if (stored) chatMessages = JSON.parse(stored);
            } catch (e) { chatMessages = []; }
        }

        function saveChatMessages() {
            try { localStorage.setItem(CHAT_STORAGE_KEY, JSON.stringify(chatMessages)); } catch (e) {}
        }

        function renderChatMessages() {
            const container = document.getElementById('chatMessages');
            if (!container) return;
            if (chatMessages.length === 0) {
                container.innerHTML = `
                    <div class="chat-empty">
                        <i class="fa-regular fa-comment"></i>
                        <p>لا توجد رسائل بعد<br>ابدأ المحادثة الآن!</p>
                    </div>
                `;
                return;
            }
            container.innerHTML = '';
            chatMessages.forEach((msg) => {
                const div = document.createElement('div');
                div.className = `chat-msg ${msg.type || 'received'}`;
                let senderHtml = '';
                if (msg.sender && msg.type === 'received') {
                    senderHtml = `<span class="msg-sender">${msg.sender}</span>`;
                }
                let contentHtml = '';
                if (msg.isAudio && msg.audioData) {
                    const duration = msg.duration || 3;
                    const waveBars = Array(20).fill(0).map(() => '<span class="bar"></span>').join('');
                    const audioDataStr = msg.audioData;
                    contentHtml = `
                        <div class="audio-msg">
                            <button class="play-btn" onclick="playAudioMessage('${audioDataStr}', ${duration})">
                                <i class="fa-solid fa-play"></i>
                            </button>
                            <div class="audio-wave">
                                ${waveBars}
                            </div>
                            <span class="audio-duration">${duration}s</span>
                        </div>
                    `;
                } else {
                    contentHtml = msg.text || '';
                }
                let sourceHtml = '';
                if (msg.source) {
                    sourceHtml = `<span class="msg-source"><i class="fa-regular fa-envelope"></i> ${msg.source}</span>`;
                }
                div.innerHTML = `
                    ${senderHtml}
                    ${contentHtml}
                    ${sourceHtml}
                    <span class="msg-time">${msg.time || new Date().toLocaleTimeString('ar')}</span>
                `;
                container.appendChild(div);
            });
            container.scrollTop = container.scrollHeight;
            updateChatNotification();
        }

        function updateChatNotification() {
            const notif = document.getElementById('chatNotif');
            if (!notif) return;
            const unread = chatMessages.filter(m => !m.read && m.type === 'received').length;
            if (unread > 0) {
                notif.style.display = 'inline';
                notif.textContent = unread;
                document.title = `(${unread}) RICK | Cyber Security Researcher`;
            } else {
                notif.style.display = 'none';
                document.title = 'RICK | Cyber Security Researcher';
            }
        }

        function openChat() {
            isChatOpen = true;
            document.getElementById('chatModal').style.display = 'flex';
            document.getElementById('chatInput').focus();
            chatMessages.forEach(m => m.read = true);
            saveChatMessages();
            updateChatNotification();
            document.getElementById('chatStatusText').textContent = navigator.onLine ? 'متصل' : 'غير متصل';
        }

        function closeChat() {
            isChatOpen = false;
            document.getElementById('chatModal').style.display = 'none';
            document.getElementById('typingIndicator').style.display = 'none';
            if (isRecording) stopRecording();
        }

        function sendChatMessage() {
            const input = document.getElementById('chatInput');
            if (!input || !input.value.trim()) return;
            const text = input.value.trim();
            const userId = getCookie('rick_user_id') || 'مستخدم';
            const msg = {
                id: Date.now(),
                text: text,
                type: 'sent',
                sender: 'أنت',
                time: new Date().toLocaleTimeString('ar'),
                read: true,
                timestamp: new Date().toISOString(),
                source: '📱 شات'
            };
            chatMessages.push(msg);
            saveChatMessages();
            renderChatMessages();
            input.value = '';

            const subject = encodeURIComponent(`رسالة جديدة من ${userId} في الشات`);
            const encodedMessage = encodeURIComponent(text);
            const link = `${SITE_URL}?type=text&content=${encodedMessage}&sender=${userId}`;
            const body = encodeURIComponent(
                `مرحباً،\n\n` +
                `قام المستخدم "${userId}" بإرسال رسالة في غرفة الشات:\n` +
                `----------------------------------------\n` +
                `${text}\n` +
                `----------------------------------------\n` +
                `🔗 لعرض الرسالة مباشرة في الشات، اضغط على الرابط التالي:\n` +
                `${link}\n` +
                `----------------------------------------\n` +
                `✉️ للرد على هذه الرسالة، قم بالرد على هذا البريد الإلكتروني.\n` +
                `تم الإرسال من: ${window.location.href}`
            );
            window.open(`mailto:${TARGET_EMAIL}?subject=${subject}&body=${body}`, '_blank');

            document.getElementById('typingIndicator').style.display = 'flex';
            setTimeout(() => {
                document.getElementById('typingIndicator').style.display = 'none';
                receiveChatMessage('📧 تم إرسال رسالتك عبر البريد الإلكتروني مع رابط مباشر.', 'النظام',
                    '📧 نظام البريد');
            }, 1500);
        }

        function receiveChatMessage(text, sender, source) {
            const lastMsg = chatMessages.length > 0 ? chatMessages[chatMessages.length - 1] : null;
            if (lastMsg && lastMsg.text === text && lastMsg.sender === sender) return;
            const msg = {
                id: Date.now() + Math.random(),
                text: text,
                type: 'received',
                sender: sender || 'صديق',
                time: new Date().toLocaleTimeString('ar'),
                read: isChatOpen,
                timestamp: new Date().toISOString(),
                source: source || '📧 البريد الإلكتروني'
            };
            chatMessages.push(msg);
            saveChatMessages();
            renderChatMessages();
            if (notificationSound) try { notificationSound(); } catch (e) {}
            if (navigator.vibrate) navigator.vibrate(100);
            if (Notification.permission === 'granted' && !isChatOpen) {
                new Notification('📩 رسالة جديدة في الشات', {
                    body: `${sender}: ${text.substring(0, 50)}${text.length > 50 ? '...' : ''}`,
                    icon: 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%2300ff66"%3E%3Cpath d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm1-13h-2v6l5.25 3.15L17 12.23l-4-2.37V7z"/%3E%3C/svg%3E'
                });
            }
            updateChatNotification();
        }

        function simulateEmailReception() {
            const replies = [
                "مرحباً! شكراً على رسالتك، كيف يمكنني مساعدتك؟",
                "أهلاً بك! لقد استلمت رسالتك وسأرد عليك قريباً.",
                "شكراً لتواصلك معي، أنا هنا للإجابة على استفساراتك.",
                "تم استلام رسالتك بنجاح! ماذا تريد أن تعرف؟",
                "مرحباً! أنا سعيد بتواصلك، كيف يمكنني مساعدتك اليوم؟",
                "أهلاً! رسالتك وصلت، لدي بعض المعلومات التي قد تفيدك.",
                "شكراً على رسالتك! سأقوم بمراجعتها وإعلامك بالرد.",
                "مرحباً بك! أنا متاح للإجابة على أسئلتك حول الأمن السيبراني."
            ];
            setInterval(() => {
                if (Math.random() > 0.4) return;
                if (Math.random() > 0.7) {
                    const text = "مرحباً! هذه رسالة صوتية مني. أنا هنا لمساعدتك.";
                    const sender = "Rick";
                    receiveChatMessage(`📝 رسالة من ${sender}: ${text}`, sender, '📧 البريد الإلكتروني');
                } else {
                    const reply = replies[Math.floor(Math.random() * replies.length)];
                    receiveChatMessage(`${reply}`, 'Rick', '📧 البريد الإلكتروني');
                }
            }, 20000 + Math.random() * 20000);
        }

        // ---------------------- VOICE RECORDING ----------------------
        let mediaRecorder = null;
        let audioChunks = [];
        let isRecording = false;
        let recordedAudioData = null;
        let recordedDuration = 0;
        let currentAudioPlayer = null;

        function toggleRecording() {
            if (isRecording) stopRecording();
            else startRecording();
        }

        function startRecording() {
            if (!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia) {
                alert('متصفحك لا يدعم التسجيل الصوتي.');
                return;
            }
            navigator.mediaDevices.getUserMedia({ audio: true })
                .then(stream => {
                    isRecording = true;
                    const btn = document.getElementById('voiceBtn');
                    btn.classList.add('recording');
                    btn.title = 'إيقاف التسجيل';
                    audioChunks = [];
                    mediaRecorder = new MediaRecorder(stream);
                    mediaRecorder.ondataavailable = event => { audioChunks.push(event.data); };
                    mediaRecorder.onstop = () => {
                        const audioBlob = new Blob(audioChunks, { type: 'audio/webm' });
                        const reader = new FileReader();
                        reader.readAsDataURL(audioBlob);
                        reader.onload = function() {
                            recordedAudioData = reader.result;
                            recordedDuration = Math.min(Math.round(audioBlob.size / 16000), 30);
                            playAudioMessage(recordedAudioData, recordedDuration);
                        };
                        stream.getTracks().forEach(track => track.stop());
                        btn.classList.remove('recording');
                        btn.title = 'تسجيل رسالة صوتية';
                        isRecording = false;
                    };
                    mediaRecorder.start();
                    document.getElementById('typingIndicator').style.display = 'flex';
                    document.getElementById('typingIndicator').innerHTML = '<span>🔴 جاري التسجيل...</span><span class="dots"></span>';
                })
                .catch(err => alert('خطأ في الميكروفون: ' + err.message));
        }

        function stopRecording() {
            if (mediaRecorder && mediaRecorder.state === 'recording') {
                mediaRecorder.stop();
                document.getElementById('typingIndicator').style.display = 'none';
                document.getElementById('typingIndicator').innerHTML =
                    '<span>الطرف الآخر يكتب</span><span class="dots">...</span>';
            }
        }

        function playAudioMessage(audioData, duration) {
            if (!audioData) return;
            try {
                if (currentAudioPlayer) { currentAudioPlayer.pause();
                    currentAudioPlayer = null; }
                const audio = new Audio(audioData);
                currentAudioPlayer = audio;
                audio.onended = () => { currentAudioPlayer = null; };
                audio.play().catch(e => alert('تعذر تشغيل الصوت.'));
            } catch (e) { alert('تعذر تشغيل الصوت.'); }
        }

        // ---------------------- URL PARAMS ----------------------
        function checkUrlParams() {
            const params = new URLSearchParams(window.location.search);
            const type = params.get('type');
            const content = params.get('content');
            const sender = params.get('sender');
            if (type && content) {
                setTimeout(() => {
                    receiveChatMessage(`📝 رسالة من ${sender || 'مرسل'}: ${content}`, sender || 'مرسل',
                        '📧 عبر الرابط');
                    setTimeout(() => {
                        openChat();
                        if (Notification.permission === 'granted') {
                            new Notification('📩 رسالة جديدة من البريد الإلكتروني', {
                                body: `لديك رسالة جديدة من ${sender || 'مرسل'}`,
                                icon: 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%2300ff66"%3E%3Cpath d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm1-13h-2v6l5.25 3.15L17 12.23l-4-2.37V7z"/%3E%3C/svg%3E'
                            });
                        }
                    }, 1000);
                }, 800);
            }
        }

        // ---------------------- USERS MODAL ----------------------
        function openUsersModal() {
            document.getElementById('usersModal').style.display = 'flex';
            document.getElementById('messagePopup').style.display = 'none';
            updateStatusDot();
        }

        function closeUsersModal() {
            document.getElementById('usersModal').style.display = 'none';
        }

        function toggleMessagePopup() {
            const popup = document.getElementById('messagePopup');
            popup.style.display = popup.style.display === 'block' ? 'none' : 'block';
            if (popup.style.display === 'block') document.getElementById('messageText').focus();
        }

        function sendFriendRequest() {
            const userId = getCookie('rick_user_id') || 'مستخدم غير معروف';
            const subject = encodeURIComponent(`طلب صداقة من مستخدم`);
            const link = `${SITE_URL}?type=friend&sender=${userId}`;
            const body = encodeURIComponent(
                `مرحباً،\n\nقام المستخدم "${userId}" بإرسال طلب صداقة.\n🔗 رابط طلب الصداقة: ${link}\nتم الإرسال من: ${window.location.href}`
                );
            window.open(`mailto:${TARGET_EMAIL}?subject=${subject}&body=${body}`, '_blank');
            alert('تم إرسال طلب الصداقة بنجاح!');
        }

        function sendMessage() {
            const message = document.getElementById('messageText')?.value?.trim() || 'لا توجد رسالة';
            const userId = getCookie('rick_user_id') || 'مستخدم غير معروف';
            const subject = encodeURIComponent(`رسالة جديدة من ${userId}`);
            const link = `${SITE_URL}?type=text&content=${encodeURIComponent(message)}&sender=${userId}`;
            const body = encodeURIComponent(
                `مرحباً،\n\nالمرسل: ${userId}\n----------------------------------------\n${message}\n----------------------------------------\n🔗 رابط الرسالة: ${link}\nتم الإرسال من: ${window.location.href}`
                );
            window.open(`mailto:${TARGET_EMAIL}?subject=${subject}&body=${body}`, '_blank');
            document.getElementById('messageText').value = '';
            document.getElementById('messagePopup').style.display = 'none';
            alert('تم إرسال رسالتك بنجاح!');
        }

        function copyEmail() {
            navigator.clipboard?.writeText(TARGET_EMAIL).then(() => alert('تم نسخ البريد الإلكتروني!'))
                .catch(() => alert(TARGET_EMAIL));
        }

        // ---------------------- STATUS DOT ----------------------
        function updateStatusDot() {
            const dot = document.getElementById('statusDot');
            if (!dot) return;
            if (navigator.onLine) {
                const startTime = Date.now();
                fetch('https://www.google.com/favicon.ico', { mode: 'no-cors', cache: 'no-store' })
                    .then(() => {
                        const pingTime = Date.now() - startTime;
                        if (pingTime < 200) { dot.className = 'status-dot';
                            dot.title = '🟢 متصل - استجابة سريعة'; } else if (pingTime < 500) { dot.className =
                                'status-dot idle';
                            dot.title = '🟡 متصل - استجابة بطيئة'; } else { dot.className = 'status-dot idle';
                            dot.title = '🟡 متصل - استجابة ضعيفة'; }
                    })
                    .catch(() => { dot.className = 'status-dot idle';
                        dot.title = '🟡 متصل - استجابة غير مستقرة'; });
            } else {
                dot.className = 'status-dot offline';
                dot.title = '🔴 غير متصل';
            }
        }
        setInterval(updateStatusDot, 5000);

        // ---------------------- NETWORK SPEED ----------------------
        function measureNetworkSpeed() {
            const speedSpan = document.getElementById('speedValue');
            if (!speedSpan) return;
            const startTime = Date.now();
            const url = 'https://www.google.com/images/phd/px.gif';
            fetch(url, { mode: 'no-cors', cache: 'no-store' })
                .then(() => {
                    const duration = (Date.now() - startTime) / 1000;
                    if (duration > 0) {
                        const fileSize = 100000;
                        const speedKbps = (fileSize * 8) / (duration * 1000);
                        const displaySpeed = speedKbps > 1024 ? (speedKbps / 1024).toFixed(1) : speedKbps.toFixed(0);
                        const unit = speedKbps > 1024 ? 'Mbps' : 'Kbps';
                        speedSpan.textContent = displaySpeed;
                        speedSpan.nextElementSibling.textContent = unit;
                    }
                })
                .catch(() => { speedSpan.textContent = '?';
                    speedSpan.nextElementSibling.textContent = ''; });
        }
        setInterval(measureNetworkSpeed, 15000);
        measureNetworkSpeed();

        // ---------------------- VIDEO SECTION ----------------------
        const MY_PRESET_VIDEOS = [
            { type: "local", id: "VID20260710115227.mp4", title: "يوميات ريك",
                translation: "مقطع فيديو حصري من يوميات ريك، يوثق الأنشطة اليومية والتجارب الميدانية في الأبحاث الأمنية والتقنية." },
            { type: "youtube", id: "wAzR14CknzU", title: "The story of Noah's Ark (قصة سفينة نوح)",
                translation: "منذ زمن طويل، دعا الله نوحاً، وهو رجل صالح، لبناء سفينة - ملاذ للخلاص. ورغم سخرية العالم، أطاع نوح دون تردد، واثقاً في الوعد الإلهي بالحماية. من كل ركن من أركان الأرض، سارت المخلوقات كبيرة وصغيرة إلى السفينة؛ الأسود والحملان مشوا جنباً إلى جنب، مستجيبين لنداء صامت للحفظ. وعندما تراجعت المياه، قدم نوح الامتنان لله، ورداً على ذلك، امتد قوس قزح في السماء كعهد أبدي بين الله والبشرية، واعداً بعدم غمر الأرض بالفيضان مرة أخرى." }
        ];
        let videoInteractions = {};

        function getVideoId(video) { return video.type === "local" ? video.id : video.id; }

        function createVideoCard(video) {
            const vidId = getVideoId(video);
            if (!videoInteractions[vidId]) videoInteractions[vidId] = { liked: false, comments: [] };
            const cleanTitle = video.title.replace(/['"\\]/g, "");
            let mediaHtml = '';
            if (video.type === "local") {
                mediaHtml = `<video src="${video.id}" controls autoplay muted playsinline loop></video>`;
            } else {
                mediaHtml =
                    `<iframe src="https://www.youtube.com/embed/${video.id}?autoplay=1&mute=0&rel=0&modestbranding=1" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>`;
            }
            const interaction = videoInteractions[vidId];
            const likeClass = interaction.liked ? 'liked' : '';
            const commentCount = interaction.comments.length;
            return `
                <div class="video-wrapper" onmouseenter="speakVideoTitle('${cleanTitle}')">
                    <div class="video-container">${mediaHtml}</div>
                    <div class="video-title">${video.title}</div>
                    <div class="video-translation"><strong><i class="fa-solid fa-language"></i> الوصف والترجمة:</strong>${video.translation}</div>
                    <div class="interaction-buttons">
                        <button class="interaction-btn ${likeClass}" onclick="toggleLike('${vidId}')">
                            <i class="fa-${interaction.liked ? 'solid' : 'regular'} fa-heart"></i> <span id="like-count-${vidId}">${interaction.liked ? 1 : 0}</span>
                        </button>
                        <button class="interaction-btn" onclick="focusComment('${vidId}')">
                            <i class="fa-regular fa-comment"></i> <span id="comment-count-${vidId}">${commentCount}</span>
                        </button>
                    </div>
                    <div class="comment-area">
                        <input type="text" id="comment-input-${vidId}" placeholder="اكتب تعليقاً..." onkeypress="if(event.key==='Enter') submitComment('${vidId}')">
                        <button onclick="submitComment('${vidId}')"><i class="fa-regular fa-paper-plane"></i></button>
                    </div>
                </div>
            `;
        }

        function loadPresetVideos(gridElement) {
            gridElement.innerHTML = '';
            MY_PRESET_VIDEOS.forEach(video => { gridElement.innerHTML += createVideoCard(video); });
        }

        function toggleLike(vidId) {
            const interaction = videoInteractions[vidId];
            interaction.liked = !interaction.liked;
            const countSpan = document.getElementById(`like-count-${vidId}`);
            if (countSpan) countSpan.textContent = interaction.liked ? 1 : 0;
            const btn = document.querySelector(`#like-count-${vidId}`)?.closest('.interaction-btn');
            if (btn) {
                btn.classList.toggle('liked');
                const icon = btn.querySelector('i');
                if (icon) icon.className = interaction.liked ? 'fa-solid fa-heart' : 'fa-regular fa-heart';
            }
            sendInteractionEmail('إعجاب', vidId, interaction.liked ? 'أعجبني' : 'إلغاء الإعجاب');
        }

        function focusComment(vidId) {
            document.getElementById(`comment-input-${vidId}`)?.focus();
        }

        function submitComment(vidId) {
            const input = document.getElementById(`comment-input-${vidId}`);
            if (!input || !input.value.trim()) return;
            const comment = input.value.trim();
            const interaction = videoInteractions[vidId];
            interaction.comments.push(comment);
            const countSpan = document.getElementById(`comment-count-${vidId}`);
            if (countSpan) countSpan.textContent = interaction.comments.length;
            sendInteractionEmail('تعليق', vidId, comment);
            input.value = '';
            alert('تم إرسال تعليقك بنجاح!');
        }

        function sendInteractionEmail(type, vidId, content) {
            const userId = getCookie('rick_user_id') || 'مستخدم غير معروف';
            const subject = encodeURIComponent(`تفاعل جديد - ${type} على فيديو`);
            const link = `${SITE_URL}?type=interaction&content=${encodeURIComponent(content)}&sender=${userId}`;
            const body = encodeURIComponent(
                `نوع التفاعل: ${type}\nمعرف الفيديو: ${vidId}\nالمحتوى: ${content}\nالمستخدم: ${userId}\n🔗 رابط التفاعل: ${link}\nتم الإرسال من: ${window.location.href}`
                );
            window.open(`mailto:${TARGET_EMAIL}?subject=${subject}&body=${body}`, '_blank');
        }

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

        // ---------------------- PREVIEW TEXT (listen) ----------------------
        function previewTextMessage() {
            const input = document.getElementById('chatInput');
            if (!input || !input.value.trim()) { alert('الرجاء كتابة رسالة أولاً'); return; }
            const text = input.value.trim();
            if ('speechSynthesis' in window) {
                window.speechSynthesis.cancel();
                const utterance = new SpeechSynthesisUtterance(text);
                utterance.lang = 'ar-SA';
                utterance.rate = 0.9;
                utterance.pitch = 1.0;
                utterance.volume = 1;
                const voices = window.speechSynthesis.getVoices();
                const arabicVoice = voices.find(v => v.lang === 'ar-SA' || v.lang === 'ar-EG' || v.lang === 'ar');
                if (arabicVoice) utterance.voice = arabicVoice;
                window.speechSynthesis.speak(utterance);
                const btn = document.querySelector('.preview-btn');
                const originalText = btn.innerHTML;
                btn.innerHTML = '<i class="fa-solid fa-volume-high"></i> جاري التشغيل...';
                btn.style.background = 'var(--accent)';
                btn.style.color = '#fff';
                utterance.onend = function() { btn.innerHTML = originalText;
                    btn.style.background = '';
                    btn.style.color = ''; };
                utterance.onerror = function() { btn.innerHTML = originalText;
                    btn.style.background = '';
                    btn.style.color = '';
                    alert('تعذر تشغيل الصوت.'); };
            } else {
                alert('متصفحك لا يدعم تحويل النص إلى صوت.');
            }
        }

        // ---------------------- TOGGLE VIEW (VIDEO/MAIN) ----------------------
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
                loadPresetVideos(document.getElementById('youtubeVideosGrid'));
            }
        }

        function resetToHome() {
            document.getElementById('video-section').style.display = 'none';
            document.getElementById('main-content-wrapper').style.display = 'block';
            if ('speechSynthesis' in window) window.speechSynthesis.cancel();
        }

        function activateFollow() {
            if (!("Notification" in window)) { alert("متصفحك لا يدعم الإشعارات."); return; }
            Notification.requestPermission().then(permission => {
                if (permission === "granted") {
                    localStorage.setItem('notifications_enabled', 'true');
                    new Notification("Rick System Control", { body: "تم تفعيل نظام المتابعة الذكي وقناتك متصلة حالياً!" });
                }
            });
        }

        // ============================================================
        //  AI CHATBOT (MINI) – يعتمد على كلمات مفتاحية للأمن السيبراني
        // ============================================================
        const aiKnowledge = {
            "من أنت": "أنا Rick، باحث في الأمن السيبراني ومتخصص في اختبار الاختراق. أقدم خدمات أمنية متكاملة.",
            "ما هي الخدمات": "أقدم اختبار اختراق للشبكات، فحص تطبيقات الويب، والاستجابة للحوادث الأمنية.",
            "المهارات": "أمتلك خبرة في أنظمة Linux (Kali/Parrot)، أدوات Nmap وBurp Suite، وفهم عميق لبروتوكولات الشبكات TCP/IP.",
            "كيف أتواصل": "يمكنك التواصل عبر البريد الإلكتروني mmellouk586@gmail.com أو عبر قنوات التواصل الاجتماعي الموجودة في الموقع.",
            "ما هو الأمن السيبراني": "الأمن السيبراني هو ممارسة حماية الأنظمة والشبكات والبيانات من الهجمات الرقمية. يشمل تقييم الثغرات، تأمين البنية التحتية، والاستجابة للحوادث.",
            "اختبار الاختراق": "اختبار الاختراق هو محاكاة هجمات إلكترونية للكشف عن نقاط الضعف في الأنظمة قبل أن يستغلها المهاجمون.",
            "شات": "يمكنك استخدام غرفة الشات المدمجة للتواصل معي مباشرة. اضغط على زر [ شات ] في الأعلى.",
            "فيديو": "يوجد قسم للمقاطع المنشورة يحتوي على فيديوهات تعليمية وتوثيقية. اضغط على [ المقاطع ] في الأعلى.",
            "المختبر": "يوجد مختبر افتراضي (Lab) يمكنك من تجربة أوامر أمنية بشكل آمن. اضغط على زر [ Lab ] في الأسفل.",
            "مرحباً": "أهلاً بك! كيف يمكنني مساعدتك اليوم؟",
            "شكراً": "العفو! أنا هنا لخدمتك في أي وقت."
        };

        function getAiResponse(query) {
            const lower = query.toLowerCase().trim();
            for (const [key, value] of Object.entries(aiKnowledge)) {
                if (lower.includes(key.toLowerCase())) return value;
            }
            if (lower.includes("ساعد") || lower.includes("مساعدة")) {
                return "بالطبع! أنا هنا لمساعدتك. اسألني عن الخدمات، المهارات، أو كيفية التواصل.";
            }
            if (lower.includes("سلام") || lower.includes("أهلاً") || lower.includes("هلا")) {
                return "وعليكم السلام! كيف يمكنني مساعدتك؟";
            }
            if (lower.includes("ماذا تفعل") || lower.includes("مهمتك")) {
                return "مهمتي هي تزويدك بمعلومات حول الأمن السيبراني، ومساعدتك في فهم الخدمات التي أقدمها، وتوجيهك في الموقع.";
            }
            if (lower.includes("شكر")) {
                return "على الرحب والسعة! أنا هنا دائماً.";
            }
            return "شكراً لسؤالك! لا أملك إجابة محددة حالياً، لكن يمكنك التواصل معي مباشرة عبر الشات أو البريد الإلكتروني. هل تريد مساعدة في موضوع معين؟";
        }

        function sendAiMessage() {
            const input = document.getElementById('aiChatInput');
            const text = input.value.trim();
            if (!text) return;
            const container = document.getElementById('aiChatMessages');
            // رسالة المستخدم
            const userMsg = document.createElement('div');
            userMsg.className = 'ai-msg user';
            userMsg.innerHTML = `${text} <span class="msg-time">${new Date().toLocaleTimeString('ar')}</span>`;
            container.appendChild(userMsg);
            // رد البوت
            const reply = getAiResponse(text);
            setTimeout(() => {
                const botMsg = document.createElement('div');
                botMsg.className = 'ai-msg bot';
                botMsg.innerHTML = `${reply} <span class="msg-time">${new Date().toLocaleTimeString('ar')}</span>`;
                container.appendChild(botMsg);
                container.scrollTop = container.scrollHeight;
            }, 300 + Math.random() * 400);
            input.value = '';
            container.scrollTop = container.scrollHeight;
        }

        function toggleAiChat() {
            const win = document.getElementById('aiChatWindow');
            win.classList.toggle('open');
            if (win.classList.contains('open')) document.getElementById('aiChatInput').focus();
        }

        function closeAiChat() {
            document.getElementById('aiChatWindow').classList.remove('open');
        }

        document.getElementById('aiChatToggle').addEventListener('click', toggleAiChat);

        // ============================================================
        //  LAB FUNCTIONS (Terminal)
        // ============================================================
        document.addEventListener('DOMContentLoaded', function() {
            // Security Check
            if (getCookie("rick_session_scanned") === "true") {
                document.getElementById('security-check').style.display = 'none';
                initUserSession();
                loadChatMessages();
                renderChatMessages();
                simulateEmailReception();
                setTimeout(() => {
                    receiveChatMessage('📧 مرحباً بك في غرفة الشات! يمكنك إرسال رسائل نصية أو صوتية.', 'النظام',
                        '📧 نظام البريد');
                }, 1000);
                setTimeout(() => {
                    receiveChatMessage('👋 أهلاً! أنا هنا لمساعدتك. يمكنك التواصل معي عبر الشات أو البريد الإلكتروني.',
                        'Rick', '📧 البريد الإلكتروني');
                }, 2500);
                setTimeout(() => {
                    receiveChatMessage('🔗 تم تفعيل نظام الروابط المباشرة. عند الضغط على رابط في البريد، ستظهر الرسالة تلقائياً.',
                        'النظام', '🔗 روابط مباشرة');
                }, 4000);
            } else {
                runSecuritySimulation();
            }

            // Lab Modal
            const labModal = document.getElementById('labModal');
            const openLabBtn = document.getElementById('openLabBtn');
            const closeLabBtn = document.getElementById('closeLabBtn');
            const textCmd = document.getElementById('textCmd');
            const termHistory = document.getElementById('termHistory');

            if (openLabBtn) {
                openLabBtn.onclick = function(e) {
                    e.preventDefault();
                    labModal.style.display = 'flex';
                    if (textCmd) textCmd.focus();
                };
            }
            if (closeLabBtn) {
                closeLabBtn.onclick = function() { labModal.style.display = 'none'; };
            }
            if (textCmd) {
                textCmd.addEventListener('keydown', function(e) {
                    if (e.key === 'Enter') {
                        const command = textCmd.value.trim();
                        if (command.length > 0) executeCommand(command);
                        textCmd.value = '';
                    }
                });
            }

            function executeCommand(cmd) {
                termHistory.innerHTML += `<div><span class="prompt">rick@seclab:~$</span> <span style="color: #1e1e2f">${cmd}</span></div>`;
                let output = '';
                const lowerCmd = cmd.toLowerCase();
                if (lowerCmd === 'help') {
                    output =
                        `<span class="cmd-output">Available Commands:<br>- <b>tools</b> : List cybersecurity research tools deployed.<br>- <b>scan</b>  : Run a demo network integrity check.<br>- <b>clear</b> : Clear the terminal interface.<br>- <b>about</b> : Show researcher credential file.<br>- <b>status</b>: Show current user session info.<br>- <b>chat</b>  : Open the chat window.<br>- <b>send</b> [msg] : Send a chat message.<br>- <b>voice</b> : Toggle voice recording.<br>- <b>link</b> : Show the direct link URL.<br>- <b>preview</b> : Preview text message with voice.</span>`;
                } else if (lowerCmd === 'tools') {
                    output =
                        `<span class="cmd-output">[+] Deployed Tools Inside Termux:<br>- nmap v7.92 (Network Mapper)<br>- hping3 (Packet Generator)<br>- sqlmap v1.6 (Automation Exploit)</span>`;
                } else if (lowerCmd === 'scan') {
                    output =
                        `<span class="cmd-output success-msg">[*] Scanning target loopback...<br>[+] Host 127.0.0.1 is UP.<br>[+] Port 80/tcp OPEN (http)<br>[+] Port 443/tcp OPEN (https)<br>[+] Scan finished. No vulnerability found on current interface.</span>`;
                } else if (lowerCmd === 'about') {
                    output =
                        `<span class="cmd-output">File: rick_credentials.txt<br>Role: Cyber Security Researcher / Bug Bounty Hunter.<br>Specialty: Web Apps Security & Network Auditing.</span>`;
                } else if (lowerCmd === 'status') {
                    const userId = getCookie('rick_user_id') || 'غير معروف';
                    const visits = getCookie('rick_visits') || '0';
                    const firstVisit = getCookie('rick_first_visit') || 'غير معروف';
                    const lastVisit = getCookie('rick_last_visit') || 'غير معروف';
                    output =
                        `<span class="cmd-output success-msg">[+] User Session Info:<br>User ID: ${userId}<br>Visits: ${visits}<br>First Visit: ${firstVisit}<br>Last Visit: ${lastVisit}<br>Chat Messages: ${chatMessages.length}</span>`;
                } else if (lowerCmd === 'chat') {
                    openChat();
                    output = `<span class="cmd-output success-msg">[+] Opening chat window...</span>`;
                } else if (lowerCmd === 'voice') {
                    toggleRecording();
                    output = `<span class="cmd-output success-msg">[+] Toggling voice recording...</span>`;
                } else if (lowerCmd === 'link') {
                    output = `<span class="cmd-output success-msg">[+] Direct Link URL:<br>${SITE_URL}</span>`;
                } else if (lowerCmd === 'preview') {
                    const input = document.getElementById('chatInput');
                    if (input && input.value.trim()) {
                        previewTextMessage();
                        output = `<span class="cmd-output success-msg">[+] Previewing text message...</span>`;
                    } else {
                        output = `<span class="cmd-output" style="color: #ff5f56">No text to preview. Write a message first.</span>`;
                    }
                } else if (lowerCmd.startsWith('send ')) {
                    const msg = cmd.substring(5);
                    if (msg.trim()) {
                        document.getElementById('chatInput').value = msg;
                        sendChatMessage();
                        output = `<span class="cmd-output success-msg">[+] Sending message: "${msg}"</span>`;
                    } else {
                        output = `<span class="cmd-output" style="color: #ff5f56">Usage: send [message]</span>`;
                    }
                } else if (lowerCmd === 'clear') {
                    termHistory.innerHTML = '';
                    return;
                } else {
                    output =
                        `<span class="cmd-output" style="color: #ff5f56">Command '${cmd}' not found. Type 'help' for options.</span>`;
                }
                termHistory.innerHTML += output;
                termHistory.scrollTop = termHistory.scrollHeight;
            }

            // Mobile menu toggle
            const mobileMenu = document.getElementById('mobile-menu');
            const navList = document.getElementById('nav-list');
            if (mobileMenu) {
                mobileMenu.addEventListener('click', () => { navList.classList.toggle('active'); });
            }

            // Notification sound creator (dummy)
            notificationSound = function() {
                try {
                    const audioCtx = new(window.AudioContext || window.webkitAudioContext)();
                    const osc = audioCtx.createOscillator();
                    const gain = audioCtx.createGain();
                    osc.connect(gain);
                    gain.connect(audioCtx.destination);
                    osc.frequency.value = 800;
                    osc.type = 'sine';
                    gain.gain.setValueAtTime(0.3, audioCtx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.3);
                    osc.start(audioCtx.currentTime);
                    osc.stop(audioCtx.currentTime + 0.3);
                } catch (e) {}
            };

            // Request notification permission
            if ("Notification" in window && Notification.permission === "default") {
                Notification.requestPermission();
            }

            // Load video grid if needed (but hidden by default)
            // loadPresetVideos will be called when toggleView is triggered
        });
    </script>
</body>
</html>
