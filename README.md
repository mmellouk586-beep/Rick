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
            --accent-color: #00ff66;
            --text-color: #c9d1d9;
            --text-bright: #ffffff;
            --border-color: #30363d;
            --online-color: #00ff66;
            --offline-color: #ff4757;
            --chat-bg: #0d1117;
            --chat-msg-sent: #00ff66;
            --chat-msg-received: #161b22;
            --notification-bg: #ff6b6b;
            --recording-color: #00ff66;
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

        .logo-area { display: flex; align-items: center; gap: 8px; flex-wrap: wrap; }
        .logo { font-size: 24px; font-weight: 700; color: var(--text-bright); letter-spacing: 1px; }
        .logo span { color: var(--accent-color); }

        .network-speed {
            display: flex;
            align-items: center;
            gap: 4px;
            background: rgba(13, 17, 23, 0.8);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 2px 8px;
            font-size: 10px;
            color: var(--text-color);
            font-family: monospace;
            direction: ltr;
        }
        .network-speed i { font-size: 10px; color: var(--accent-color); }
        .network-speed .speed-value { 
            color: var(--accent-color); 
            font-weight: bold;
            min-width: 40px;
            text-align: center;
        }
        .network-speed .speed-unit { color: #8b949e; }

        .header-follow-btn {
            background: #21262d; border: 1px solid var(--accent-color); color: var(--accent-color);
            padding: 3px 10px; border-radius: 4px; font-size: 12px; cursor: pointer; font-weight: bold; transition: all 0.2s;
        }
        .header-follow-btn:hover { background: var(--accent-color); color: #000; box-shadow: 0 0 10px var(--accent-color); }

        .header-users-btn {
            background: #21262d; border: 1px solid #58a6ff; color: #58a6ff;
            padding: 3px 10px; border-radius: 4px; font-size: 12px; cursor: pointer; font-weight: bold; transition: all 0.2s;
        }
        .header-users-btn:hover { background: #58a6ff; color: #000; box-shadow: 0 0 10px #58a6ff; }

        .header-chat-btn {
            background: #21262d; border: 1px solid #ff6b6b; color: #ff6b6b;
            padding: 3px 10px; border-radius: 4px; font-size: 12px; cursor: pointer; font-weight: bold; transition: all 0.2s;
            display: flex;
            align-items: center;
            gap: 4px;
            position: relative;
        }
        .header-chat-btn:hover { background: #ff6b6b; color: #000; box-shadow: 0 0 10px #ff6b6b; }
        .header-chat-btn .chat-notification {
            background: #ff6b6b;
            color: #000;
            border-radius: 50%;
            padding: 0 5px;
            font-size: 9px;
            font-weight: bold;
            min-width: 18px;
            text-align: center;
        }

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

        .chat-modal {
            position: fixed;
            top: 0; left: 0; width: 100vw; height: 100vh;
            background: rgba(0,0,0,0.85);
            z-index: 40000;
            display: none;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        .chat-box {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            width: 100%;
            max-width: 500px;
            height: 80vh;
            max-height: 600px;
            display: flex;
            flex-direction: column;
            box-shadow: 0 0 40px rgba(255,107,107,0.15);
        }
        .chat-header {
            padding: 15px 20px;
            border-bottom: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(13,17,23,0.9);
            border-radius: 12px 12px 0 0;
        }
        .chat-header h3 {
            color: var(--text-bright);
            font-size: 18px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .chat-header h3 i { color: #ff6b6b; }
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
            0%, 100% { opacity: 1; }
            50% { opacity: 0.3; }
        }
        .chat-close-btn {
            background: none;
            border: none;
            color: var(--text-color);
            font-size: 20px;
            cursor: pointer;
            transition: 0.3s;
        }
        .chat-close-btn:hover { color: #ff6b6b; transform: rotate(90deg); }

        .chat-messages {
            flex: 1;
            overflow-y: auto;
            padding: 15px 20px;
            display: flex;
            flex-direction: column;
            gap: 8px;
            background: var(--bg-color);
        }
        .chat-messages::-webkit-scrollbar {
            width: 4px;
        }
        .chat-messages::-webkit-scrollbar-thumb {
            background: var(--border-color);
            border-radius: 4px;
        }

        .chat-msg {
            max-width: 85%;
            padding: 8px 14px;
            border-radius: 12px;
            font-size: 13px;
            word-wrap: break-word;
            animation: msgAppear 0.3s ease;
        }
        @keyframes msgAppear {
            from { opacity: 0; transform: translateY(10px) scale(0.95); }
            to { opacity: 1; transform: translateY(0) scale(1); }
        }
        .chat-msg.sent {
            background: var(--accent-color);
            color: #000;
            align-self: flex-end;
            border-bottom-right-radius: 4px;
        }
        .chat-msg.received {
            background: var(--card-bg);
            color: var(--text-color);
            align-self: flex-start;
            border-bottom-left-radius: 4px;
            border: 1px solid var(--border-color);
        }
        .chat-msg .msg-time {
            font-size: 9px;
            opacity: 0.6;
            display: block;
            margin-top: 4px;
        }
        .chat-msg .msg-sender {
            font-size: 10px;
            color: var(--accent-color);
            display: block;
            margin-bottom: 2px;
            font-weight: bold;
        }
        .chat-msg .msg-source {
            font-size: 9px;
            color: #58a6ff;
            display: block;
            margin-top: 2px;
        }

        .audio-msg {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 4px 0;
            width: 100%;
        }
        .audio-msg .play-btn {
            background: var(--accent-color);
            border: none;
            border-radius: 50%;
            width: 36px;
            height: 36px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            color: #000;
            transition: all 0.3s;
            flex-shrink: 0;
            font-size: 14px;
        }
        .audio-msg .play-btn:hover { 
            transform: scale(1.15); 
            box-shadow: 0 0 20px var(--accent-color);
        }
        .audio-msg .play-btn.playing { 
            background: #ff6b6b; 
            animation: pulse-play 0.5s infinite;
        }
        @keyframes pulse-play {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
        .audio-msg .audio-wave {
            flex: 1;
            height: 35px;
            display: flex;
            align-items: center;
            gap: 3px;
            padding: 0 5px;
            background: rgba(255,255,255,0.05);
            border-radius: 4px;
        }
        .audio-msg .audio-wave .bar {
            width: 4px;
            background: var(--accent-color);
            border-radius: 2px;
            transition: height 0.15s ease;
            height: 8px;
        }
        .audio-msg .audio-wave .bar.active {
            background: #ff6b6b;
        }
        .audio-msg .audio-wave .bar.playing {
            animation: wave-anim 0.3s infinite alternate;
        }
        @keyframes wave-anim {
            0% { height: 8px; }
            100% { height: 28px; }
        }
        .audio-msg .audio-duration {
            font-size: 11px;
            color: #8b949e;
            min-width: 35px;
            text-align: center;
        }

        .chat-input-area {
            padding: 12px 20px;
            border-top: 1px solid var(--border-color);
            display: flex;
            gap: 8px;
            align-items: center;
            background: rgba(13,17,23,0.9);
            border-radius: 0 0 12px 12px;
            flex-wrap: wrap;
        }
        .chat-input-area input {
            flex: 1;
            background: #0d1117;
            border: 1px solid var(--border-color);
            border-radius: 20px;
            padding: 8px 16px;
            color: var(--text-color);
            font-family: 'Cairo', sans-serif;
            outline: none;
            font-size: 13px;
            min-width: 100px;
        }
        .chat-input-area input:focus { border-color: var(--accent-color); }
        
        .chat-input-area .voice-btn {
            background: #21262d;
            border: 2px solid var(--accent-color);
            border-radius: 50%;
            width: 36px;
            height: 36px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            color: var(--accent-color);
            transition: all 0.3s;
            flex-shrink: 0;
        }
        .chat-input-area .voice-btn:hover { 
            background: var(--accent-color);
            color: #000;
            box-shadow: 0 0 15px var(--accent-color);
        }
        .chat-input-area .voice-btn.recording {
            background: var(--accent-color);
            border-color: var(--accent-color);
            color: #000;
            animation: pulse-rec 1s infinite;
        }
        @keyframes pulse-rec {
            0%, 100% { transform: scale(1); box-shadow: 0 0 10px var(--accent-color); }
            50% { transform: scale(1.1); box-shadow: 0 0 25px var(--accent-color); }
        }
        .chat-input-area .voice-btn .recording-dot {
            display: none;
            width: 10px;
            height: 10px;
            background: #ff4757;
            border-radius: 50%;
            animation: blink-dot 0.5s infinite;
        }
        @keyframes blink-dot {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }
        .chat-input-area .voice-btn.recording .recording-dot {
            display: block;
        }
        .chat-input-area .voice-btn.recording i {
            display: none;
        }
        
        .chat-input-area .chat-send-btn {
            background: var(--accent-color);
            border: none;
            color: #000;
            padding: 8px 16px;
            border-radius: 20px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
            font-size: 13px;
            flex-shrink: 0;
        }
        .chat-input-area .chat-send-btn:hover { opacity: 0.8; transform: scale(1.02); }

        .chat-empty {
            text-align: center;
            color: #8b949e;
            font-size: 13px;
            margin: auto;
        }
        .chat-empty i { font-size: 40px; color: var(--border-color); display: block; margin-bottom: 10px; }

        .typing-indicator {
            display: none;
            align-self: flex-start;
            padding: 8px 14px;
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            border-bottom-left-radius: 4px;
            font-size: 13px;
            color: #8b949e;
            animation: msgAppear 0.3s ease;
        }
        .typing-indicator .dots {
            display: inline-block;
            animation: typingDots 1.4s infinite;
        }
        @keyframes typingDots {
            0% { content: '.'; }
            33% { content: '..'; }
            66% { content: '...'; }
        }

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
            padding: 15px;
            width: 340px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            transition: border-color 0.3s;
        }
        .video-wrapper:hover {
            border-color: var(--accent-color);
        }

        .video-container {
            width: 100%;
            height: 450px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            overflow: hidden;
            background: #000;
        }

        .video-container iframe, .video-container video { width: 100%; height: 100%; border: none; object-fit: cover; }
        .video-title { font-size: 15px; font-weight: bold; color: var(--text-bright); margin-top: 10px; text-align: right; }
        
        .video-translation {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 4px;
            padding: 10px;
            margin-top: 10px;
            font-size: 12px;
            color: #8b949e;
            text-align: right;
            max-height: 120px;
            overflow-y: auto;
            line-height: 1.5;
        }
        .video-translation strong { color: var(--accent-color); display: block; margin-bottom: 4px; font-size: 13px; }

        .interaction-buttons {
            display: flex;
            gap: 12px;
            margin-top: 12px;
            justify-content: center;
        }
        .interaction-btn {
            background: #21262d;
            border: 1px solid var(--border-color);
            color: var(--text-color);
            padding: 5px 14px;
            border-radius: 20px;
            font-size: 13px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 6px;
        }
        .interaction-btn:hover { border-color: var(--accent-color); color: var(--accent-color); }
        .interaction-btn.liked { border-color: #ff6b6b; color: #ff6b6b; }
        .interaction-btn i { font-size: 14px; }

        .comment-area {
            margin-top: 10px;
            display: flex;
            gap: 8px;
            align-items: center;
        }
        .comment-area input {
            flex: 1;
            background: #0d1117;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            padding: 6px 10px;
            color: var(--text-color);
            font-size: 12px;
            outline: none;
        }
        .comment-area input:focus { border-color: var(--accent-color); }
        .comment-area button {
            background: var(--accent-color);
            border: none;
            color: #000;
            padding: 6px 12px;
            border-radius: 4px;
            font-weight: bold;
            cursor: pointer;
            font-size: 12px;
        }
        .comment-area button:hover { opacity: 0.8; }

        .users-modal {
            position: fixed;
            top: 0; left: 0; width: 100vw; height: 100vh;
            background: rgba(0,0,0,0.85);
            z-index: 30000;
            display: none;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        .users-modal-box {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 30px;
            max-width: 480px;
            width: 100%;
            text-align: center;
            box-shadow: 0 0 40px rgba(0,255,102,0.1);
        }
        .users-modal-box h2 {
            color: var(--text-bright);
            margin-bottom: 20px;
            font-size: 22px;
        }

        .profile-card {
            background: #0d1117;
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 25px 20px;
            margin-bottom: 20px;
            position: relative;
        }
        .profile-avatar-wrapper {
            position: relative;
            display: inline-block;
        }
        .profile-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: linear-gradient(135deg, #00ff66, #00ccff);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 12px;
            font-size: 36px;
            color: #0d1117;
            border: 3px solid var(--accent-color);
            box-shadow: 0 0 20px rgba(0,255,102,0.2);
        }
        .status-dot {
            position: absolute;
            bottom: 6px;
            right: -4px;
            width: 16px;
            height: 16px;
            border-radius: 50%;
            border: 2px solid var(--card-bg);
            transition: background-color 0.3s;
            background-color: var(--online-color);
            box-shadow: 0 0 10px rgba(0,255,102,0.5);
        }
        .status-dot.offline {
            background-color: var(--offline-color);
            box-shadow: 0 0 10px rgba(255,71,87,0.5);
        }
        .status-dot.idle {
            background-color: #ffa502;
            box-shadow: 0 0 10px rgba(255,165,2,0.5);
        }

        .profile-name {
            color: var(--text-bright);
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 4px;
        }
        .profile-email {
            color: #58a6ff;
            font-size: 14px;
            cursor: pointer;
            transition: 0.3s;
        }
        .profile-email:hover {
            text-shadow: 0 0 10px rgba(88,166,255,0.3);
        }
        .profile-bio {
            color: #8b949e;
            font-size: 13px;
            margin-top: 8px;
            padding-top: 8px;
            border-top: 1px solid var(--border-color);
        }

        .profile-actions {
            display: flex;
            gap: 6px;
            justify-content: center;
            margin-top: 12px;
            flex-wrap: wrap;
        }
        .profile-action-btn {
            background: #21262d;
            border: 1px solid var(--border-color);
            color: var(--text-color);
            padding: 4px 10px;
            border-radius: 4px;
            font-size: 11px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 4px;
        }
        .profile-action-btn:hover {
            border-color: var(--accent-color);
            color: var(--accent-color);
            transform: translateY(-1px);
        }
        .profile-action-btn i { font-size: 12px; }
        .profile-action-btn.friend-btn { border-color: #58a6ff; color: #58a6ff; }
        .profile-action-btn.friend-btn:hover { background: #58a6ff; color: #000; }
        .profile-action-btn.message-btn { border-color: #ffcc00; color: #ffcc00; }
        .profile-action-btn.message-btn:hover { background: #ffcc00; color: #000; }

        .message-popup {
            display: none;
            margin-top: 12px;
            padding: 12px;
            background: #0d1117;
            border: 1px solid var(--border-color);
            border-radius: 8px;
        }
        .message-popup textarea {
            width: 100%;
            background: #161b22;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            padding: 8px;
            color: var(--text-color);
            font-family: 'Cairo', sans-serif;
            resize: vertical;
            min-height: 50px;
            outline: none;
            font-size: 13px;
        }
        .message-popup textarea:focus { border-color: var(--accent-color); }
        .message-popup .send-msg-btn {
            margin-top: 8px;
            background: var(--accent-color);
            border: none;
            color: #000;
            padding: 6px 16px;
            border-radius: 4px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
            width: 100%;
            font-size: 13px;
        }
        .message-popup .send-msg-btn:hover { opacity: 0.8; }

        .users-modal-close {
            margin-top: 12px;
            background: transparent;
            border: 1px solid var(--border-color);
            color: var(--text-color);
            padding: 5px 16px;
            border-radius: 4px;
            cursor: pointer;
            transition: 0.3s;
            font-size: 13px;
        }
        .users-modal-close:hover { border-color: var(--accent-color); color: var(--accent-color); }

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

        .lab-float-btn { 
            position: fixed; bottom: 30px; left: 30px; background-color: var(--card-bg); 
            border: 2px solid var(--accent-color); color: var(--accent-color); padding: 12px 20px; 
            border-radius: 50px; font-size: 16px; font-weight: bold; cursor: pointer; 
            box-shadow: 0 4px 15px rgba(0, 255, 102, 0.3); z-index: 9999; display: flex; align-items: center; gap: 10px; transition: transform 0.3s; 
        }
        .lab-float-btn:hover { transform: scale(1.05); box-shadow: 0 0 20px var(--accent-color); }

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
            .profile-actions { flex-direction: row; flex-wrap: wrap; justify-content: center; }
            .network-speed { font-size: 8px; padding: 1px 5px; }
            .network-speed .speed-value { min-width: 30px; }
            .chat-box { max-height: 90vh; height: 90vh; }
            .chat-input-area input { min-width: 60px; }
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
            <h2 class="section-title">من أنا</h2>
            <div class="about-grid">
                <div class="profile-img-container">
                    <img src="IMG_20260710_104918.png" alt="Reck Profile" class="avatar-placeholder">
                </div>
                <div>
                    <p style="font-size: 18px; margin-bottom: 20px;">أنا <strong>Reck</strong>، باحث متخصص في الأمن السيبراني.</p>
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
                    <a href="mailto:rick@example.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
                </div>
            </div>
        </section>
    </div>

    <section id="video-section">
        <h2 class="section-title">المقاطع المنشورة</h2>
        <div class="videos-grid" id="youtubeVideosGrid"></div>
    </section>

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
                <input type="text" id="chatInput" placeholder="اكتب رسالتك..." onkeypress="if(event.key==='Enter') sendChatMessage()">
                <button class="voice-btn" id="voiceBtn" onclick="toggleRecording()" title="تسجيل رسالة صوتية">
                    <i class="fa-solid fa-microphone"></i>
                    <span class="recording-dot"></span>
                </button>
                <button class="chat-send-btn" onclick="sendChatMessage()"><i class="fa-regular fa-paper-plane"></i> إرسال</button>
            </div>
        </div>
    </div>

    <div class="users-modal" id="usersModal">
        <div class="users-modal-box">
            <h2><i class="fa-solid fa-user"></i> الملف الشخصي</h2>
            
            <div class="profile-card">
                <div class="profile-avatar-wrapper">
                    <div class="profile-avatar">
                        <i class="fa-solid fa-user-secret"></i>
                    </div>
                    <div class="status-dot" id="statusDot" title="الحالة"></div>
                </div>
                <div class="profile-name">Reck</div>
                <div class="profile-email" onclick="copyEmail()">
                    <i class="fa-regular fa-envelope"></i> mmellouk586@gmail.com
                </div>
                <div class="profile-bio">
                    <i class="fa-solid fa-shield-halved" style="color: var(--accent-color);"></i>
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
                            <span class="prompt">reck@seclab:~$</span>
                            <input type="text" id="textCmd" class="term-input" autocomplete="off" autofocus>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 Reck. جميع الحقوق محفوظة</p>
        <a href="#privacy" class="privacy-link" onclick="alert('سياسة الخصوصية:\nنحن نحترم خصوصيتك بالكامل. جميع عمليات المحاكاة والفحص الأمني داخل هذا الموقع تجري محلياً في بيئة اختبار آمنة تماماً، ولا نقوم بجمع أو مشاركة أي بيانات حساسة تخص الزوار.')">سياسة الخصوصية</a>
    </footer>

    <script>
        // ===== VOICE RECORDING SYSTEM =====
        let mediaRecorder = null;
        let audioChunks = [];
        let isRecording = false;
        let audioContext = null;
        let analyser = null;
        let animationId = null;
        let currentAudioPlayer = null;
        let isPlaying = false;

        const SITE_URL = 'https://mmellouk586-beep.github.io/Rick/';
        const TARGET_EMAIL = 'mmellouk586@gmail.com';

        // ===== توليد رسالة صوتية حقيقية باستخدام Web Audio API =====
        function generateRealVoiceMessage(text, callback) {
            try {
                const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                const duration = Math.min(text.length * 0.08 + 0.5, 8); // مدة الصوت بناءً على طول النص
                const sampleRate = audioCtx.sampleRate;
                const frameCount = sampleRate * duration;
                const audioBuffer = audioCtx.createBuffer(1, frameCount, sampleRate);
                const data = audioBuffer.getChannelData(0);
                
                // توليد صوت يشبه الكلام باستخدام مجموعة من الترددات
                const baseFreq = 180; // تردد أساسي
                const formants = [300, 600, 900, 1200]; // ترددات الرنين
                
                for (let i = 0; i < frameCount; i++) {
                    const t = i / sampleRate;
                    let sample = 0;
                    
                    // الموجة الأساسية
                    sample += Math.sin(baseFreq * 2 * Math.PI * t) * 0.4;
                    
                    // إضافة التوافقيات
                    for (let f = 2; f <= 5; f++) {
                        sample += Math.sin(baseFreq * f * 2 * Math.PI * t) * (0.15 / f);
                    }
                    
                    // إضافة ترددات الرنين (تشبه أصوات الحروف)
                    formants.forEach((freq, index) => {
                        const amplitude = 0.08 * (1 - index * 0.15);
                        sample += Math.sin(freq * 2 * Math.PI * t) * amplitude;
                    });
                    
                    // تعديل السعة لتشبه الكلام (ارتفاع وانخفاض)
                    const envelope = Math.sin(t * 2 * Math.PI * 0.5) * 0.3 + 0.7;
                    sample *= envelope;
                    
                    // إضافة تأثيرات تشبه الصوت البشري
                    if (i % 500 < 20) {
                        sample += (Math.random() - 0.5) * 0.03;
                    }
                    
                    // ترددات عشوائية خفيفة
                    if (i % 1000 < 10) {
                        sample += Math.sin((200 + Math.random() * 300) * 2 * Math.PI * t) * 0.02;
                    }
                    
                    data[i] = Math.max(-0.8, Math.min(0.8, sample));
                }
                
                // تحويل إلى WAV
                const wavBlob = audioBufferToWav(audioBuffer);
                const reader = new FileReader();
                reader.readAsDataURL(wavBlob);
                reader.onload = function() {
                    const audioData = reader.result;
                    const durationSec = Math.round(duration);
                    if (callback) callback(audioData, durationSec);
                };
                reader.onerror = function() {
                    // في حالة الفشل، نستخدم طريقة بديلة
                    generateFallbackVoiceMessage(text, callback);
                };
            } catch(e) {
                console.error('خطأ في توليد الصوت:', e);
                generateFallbackVoiceMessage(text, callback);
            }
        }

        // ===== طريقة بديلة لتوليد الصوت =====
        function generateFallbackVoiceMessage(text, callback) {
            try {
                const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                const duration = 2;
                const sampleRate = audioCtx.sampleRate;
                const frameCount = sampleRate * duration;
                const audioBuffer = audioCtx.createBuffer(1, frameCount, sampleRate);
                const data = audioBuffer.getChannelData(0);
                
                for (let i = 0; i < frameCount; i++) {
                    const t = i / sampleRate;
                    data[i] = Math.sin(440 * 2 * Math.PI * t) * 0.3 +
                              Math.sin(880 * 2 * Math.PI * t) * 0.15 +
                              Math.sin(220 * 2 * Math.PI * t) * 0.1;
                    if (i % 1000 < 50) {
                        data[i] += (Math.random() - 0.5) * 0.05;
                    }
                }
                
                const wavBlob = audioBufferToWav(audioBuffer);
                const reader = new FileReader();
                reader.readAsDataURL(wavBlob);
                reader.onload = function() {
                    const audioData = reader.result;
                    if (callback) callback(audioData, Math.round(duration));
                };
            } catch(e) {
                if (callback) callback(null, 0);
            }
        }

        // ===== تحويل AudioBuffer إلى WAV =====
        function audioBufferToWav(buffer) {
            const numChannels = 1;
            const sampleRate = buffer.sampleRate;
            const format = 1;
            const bitDepth = 16;
            
            const bytesPerSample = bitDepth / 8;
            const blockAlign = numChannels * bytesPerSample;
            
            const data = buffer.getChannelData(0);
            const samples = data.length;
            const dataSize = samples * bytesPerSample;
            
            const arrayBuffer = new ArrayBuffer(44 + dataSize);
            const view = new DataView(arrayBuffer);
            
            writeString(view, 0, 'RIFF');
            view.setUint32(4, 36 + dataSize, true);
            writeString(view, 8, 'WAVE');
            writeString(view, 12, 'fmt ');
            view.setUint32(16, 16, true);
            view.setUint16(20, format, true);
            view.setUint16(22, numChannels, true);
            view.setUint32(24, sampleRate, true);
            view.setUint32(28, sampleRate * blockAlign, true);
            view.setUint16(32, blockAlign, true);
            view.setUint16(34, bitDepth, true);
            writeString(view, 36, 'data');
            view.setUint32(40, dataSize, true);
            
            let offset = 44;
            for (let i = 0; i < samples; i++) {
                const sample = Math.max(-1, Math.min(1, data[i]));
                const int16 = sample < 0 ? sample * 0x8000 : sample * 0x7FFF;
                view.setInt16(offset, int16, true);
                offset += 2;
            }
            
            return new Blob([arrayBuffer], { type: 'audio/wav' });
        }

        function writeString(view, offset, string) {
            for (let i = 0; i < string.length; i++) {
                view.setUint8(offset + i, string.charCodeAt(i));
            }
        }

        // ===== تشغيل الصوت المحسن =====
        function playAudioMessage(audioData, duration) {
            if (!audioData) {
                alert('لا يوجد ملف صوتي للتشغيل');
                return;
            }

            try {
                if (currentAudioPlayer) {
                    currentAudioPlayer.pause();
                    currentAudioPlayer = null;
                    isPlaying = false;
                }

                const audio = new Audio(audioData);
                currentAudioPlayer = audio;
                
                audio.onplay = function() {
                    isPlaying = true;
                    updatePlayButton(true);
                    animateWaveBars(true);
                };
                
                audio.onpause = function() {
                    isPlaying = false;
                    updatePlayButton(false);
                    animateWaveBars(false);
                };
                
                audio.onended = function() {
                    isPlaying = false;
                    updatePlayButton(false);
                    animateWaveBars(false);
                    currentAudioPlayer = null;
                };
                
                audio.onerror = function(e) {
                    console.error('خطأ في تشغيل الصوت:', e);
                    isPlaying = false;
                    updatePlayButton(false);
                    animateWaveBars(false);
                    currentAudioPlayer = null;
                    alert('تعذر تشغيل الصوت. يرجى المحاولة مرة أخرى.');
                };
                
                const playPromise = audio.play();
                if (playPromise !== undefined) {
                    playPromise.catch(function(error) {
                        console.error('فشل تشغيل الصوت:', error);
                        isPlaying = false;
                        updatePlayButton(false);
                        animateWaveBars(false);
                        currentAudioPlayer = null;
                        alert('تعذر تشغيل الصوت. يرجى المحاولة مرة أخرى.');
                    });
                }
                
                updatePlayButton(true);
                animateWaveBars(true);
                
            } catch(e) {
                console.error('خطأ في تشغيل الصوت:', e);
                alert('تعذر تشغيل الصوت. يرجى المحاولة مرة أخرى.');
            }
        }

        function updatePlayButton(playing) {
            const buttons = document.querySelectorAll('.play-btn');
            buttons.forEach(btn => {
                if (playing) {
                    btn.classList.add('playing');
                    btn.innerHTML = '<i class="fa-solid fa-pause"></i>';
                    btn.title = 'إيقاف';
                } else {
                    btn.classList.remove('playing');
                    btn.innerHTML = '<i class="fa-solid fa-play"></i>';
                    btn.title = 'تشغيل';
                }
            });
        }

        function animateWaveBars(active) {
            const bars = document.querySelectorAll('.audio-wave .bar');
            bars.forEach((bar, index) => {
                if (active) {
                    bar.classList.add('playing');
                    const delay = index * 0.05;
                    bar.style.animationDelay = delay + 's';
                    bar.style.height = (8 + Math.random() * 20) + 'px';
                } else {
                    bar.classList.remove('playing');
                    bar.style.animationDelay = '0s';
                    bar.style.height = '8px';
                }
            });
        }

        // ===== فحص معلمات الرابط =====
        function checkUrlParams() {
            const params = new URLSearchParams(window.location.search);
            const type = params.get('type');
            const content = params.get('content');
            const sender = params.get('sender');
            const audio = params.get('audio');

            if (type && content) {
                setTimeout(() => {
                    if (type === 'voice' || audio === 'true') {
                        // توليد رسالة صوتية حقيقية
                        const text = content || 'رسالة صوتية من المرسل';
                        const senderName = sender || 'مرسل';
                        
                        receiveChatMessage(
                            `🎙️ رسالة صوتية من ${senderName}`, 
                            senderName, 
                            '📧 عبر الرابط'
                        );
                        
                        // توليد الصوت وإضافته كرسالة صوتية
                        generateRealVoiceMessage(text, function(audioData, duration) {
                            if (audioData) {
                                const msg = {
                                    id: Date.now() + Math.random(),
                                    text: `🎙️ رسالة صوتية: ${text}`,
                                    type: 'received',
                                    sender: senderName,
                                    time: new Date().toLocaleTimeString('ar'),
                                    read: isChatOpen,
                                    timestamp: new Date().toISOString(),
                                    source: '📧 عبر الرابط',
                                    isAudio: true,
                                    audioData: audioData,
                                    duration: duration || 3
                                };
                                chatMessages.push(msg);
                                saveChatMessages();
                                renderChatMessages();
                                
                                // تشغيل الصوت تلقائياً
                                setTimeout(() => {
                                    playAudioMessage(audioData, duration);
                                }, 500);
                            }
                        });
                    } else {
                        receiveChatMessage(
                            `📝 رسالة من ${sender || 'مرسل'}: ${content}`, 
                            sender || 'مرسل', 
                            '📧 عبر الرابط'
                        );
                    }
                    
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

        // ===== VOICE RECORDING =====
        function toggleRecording() {
            if (isRecording) {
                stopRecording();
            } else {
                startRecording();
            }
        }

        function startRecording() {
            if (!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia) {
                alert('متصفحك لا يدعم التسجيل الصوتي. يرجى استخدام متصفح حديث.');
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
                    
                    mediaRecorder.ondataavailable = event => {
                        audioChunks.push(event.data);
                    };
                    
                    mediaRecorder.onstop = () => {
                        const audioBlob = new Blob(audioChunks, { type: 'audio/webm' });
                        sendVoiceMessage(audioBlob);
                        stream.getTracks().forEach(track => track.stop());
                        btn.classList.remove('recording');
                        btn.title = 'تسجيل رسالة صوتية';
                        isRecording = false;
                        if (animationId) {
                            cancelAnimationFrame(animationId);
                            animationId = null;
                        }
                    };
                    
                    mediaRecorder.start();
                    
                    const indicator = document.getElementById('typingIndicator');
                    if (indicator) {
                        indicator.style.display = 'flex';
                        indicator.innerHTML = '<span>🔴 جاري التسجيل...</span><span class="dots"></span>';
                    }
                    
                    setupAudioVisualization(stream);
                })
                .catch(err => {
                    alert('خطأ في الوصول إلى الميكروفون: ' + err.message);
                });
        }

        function stopRecording() {
            if (mediaRecorder && mediaRecorder.state === 'recording') {
                mediaRecorder.stop();
                const indicator = document.getElementById('typingIndicator');
                if (indicator) {
                    indicator.style.display = 'none';
                    indicator.innerHTML = '<span>الطرف الآخر يكتب</span><span class="dots">...</span>';
                }
            }
        }

        function setupAudioVisualization(stream) {
            audioContext = new (window.AudioContext || window.webkitAudioContext)();
            const source = audioContext.createMediaStreamSource(stream);
            analyser = audioContext.createAnalyser();
            analyser.fftSize = 256;
            source.connect(analyser);
            
            const container = document.getElementById('chatMessages');
            const recordingMsg = document.createElement('div');
            recordingMsg.className = 'chat-msg received';
            recordingMsg.id = 'recordingIndicator';
            recordingMsg.innerHTML = `
                <span class="msg-sender">🎙️ أنت</span>
                <div class="audio-msg">
                    <span>🔴 جاري التسجيل...</span>
                    <div class="audio-wave" id="liveWave">
                        ${Array(20).fill(0).map(() => '<span class="bar"></span>').join('')}
                    </div>
                </div>
                <span class="msg-time">${new Date().toLocaleTimeString('ar')}</span>
            `;
            container.appendChild(recordingMsg);
            container.scrollTop = container.scrollHeight;
            
            function updateWave() {
                if (!analyser || !isRecording) return;
                
                const dataArray = new Uint8Array(analyser.frequencyBinCount);
                analyser.getByteFrequencyData(dataArray);
                
                const bars = document.querySelectorAll('#liveWave .bar');
                const step = Math.floor(dataArray.length / bars.length);
                
                bars.forEach((bar, index) => {
                    const value = dataArray[index * step] || 0;
                    const height = Math.max(5, (value / 255) * 25);
                    bar.style.height = height + 'px';
                    bar.style.background = value > 150 ? '#ff6b6b' : 'var(--accent-color)';
                });
                
                animationId = requestAnimationFrame(updateWave);
            }
            
            updateWave();
        }

        function sendVoiceMessage(audioBlob) {
            const reader = new FileReader();
            reader.readAsDataURL(audioBlob);
            reader.onload = function() {
                const audioData = reader.result;
                const durationSec = Math.min(Math.round(audioBlob.size / 16000), 30);
                
                const indicator = document.getElementById('recordingIndicator');
                if (indicator) indicator.remove();
                
                const msg = {
                    id: Date.now(),
                    type: 'sent',
                    sender: 'أنت',
                    time: new Date().toLocaleTimeString('ar'),
                    read: true,
                    timestamp: new Date().toISOString(),
                    source: '🎙️ صوتي',
                    isAudio: true,
                    audioData: audioData,
                    duration: durationSec
                };
                
                chatMessages.push(msg);
                saveChatMessages();
                renderChatMessages();
                
                // إرسال عبر البريد مع رابط صوتي
                const userId = getCookie('reck_user_id') || 'مستخدم';
                const subject = encodeURIComponent(`رسالة صوتية جديدة من ${userId}`);
                const encodedMessage = encodeURIComponent('رسالة صوتية مسجلة');
                const link = `${SITE_URL}?type=voice&content=${encodedMessage}&sender=${userId}&audio=true`;
                
                const body = encodeURIComponent(
                    `مرحباً،\n\n` +
                    `قام المستخدم "${userId}" بإرسال رسالة صوتية.\n` +
                    `مدة الرسالة: ${durationSec} ثانية\n` +
                    `----------------------------------------\n` +
                    `🔊 للاستماع إلى الرسالة الصوتية، اضغط على الرابط التالي:\n` +
                    `${link}\n` +
                    `----------------------------------------\n` +
                    `✉️ يمكنك الرد على هذه الرسالة بالرد على هذا البريد.\n` +
                    `تم الإرسال من: ${window.location.href}`
                );
                
                window.open(`mailto:${TARGET_EMAIL}?subject=${subject}&body=${body}`, '_blank');
            };
        }

        // ===== CHAT SYSTEM =====
        let chatMessages = [];
        let isChatOpen = false;
        let notificationSound = null;
        const CHAT_STORAGE_KEY = 'reck_chat_messages';

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
            for(let i=0;i < ca.length;i++) { 
                let c = ca[i]; 
                while (c.charAt(0)==' ') c = c.substring(1,c.length); 
                if (c.indexOf(nameEQ) == 0) return c.substring(nameEQ.length,c.length); 
            } 
            return null; 
        }

        function createNotificationSound() {
            try {
                const audioContext = new (window.AudioContext || window.webkitAudioContext)();
                function playSound() {
                    try {
                        const oscillator = audioContext.createOscillator();
                        const gainNode = audioContext.createGain();
                        oscillator.connect(gainNode);
                        gainNode.connect(audioContext.destination);
                        oscillator.frequency.value = 800;
                        oscillator.type = 'sine';
                        gainNode.gain.setValueAtTime(0.3, audioContext.currentTime);
                        gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.3);
                        oscillator.start(audioContext.currentTime);
                        oscillator.stop(audioContext.currentTime + 0.3);
                        setTimeout(() => {
                            const osc2 = audioContext.createOscillator();
                            const gain2 = audioContext.createGain();
                            osc2.connect(gain2);
                            gain2.connect(audioContext.destination);
                            osc2.frequency.value = 1000;
                            osc2.type = 'sine';
                            gain2.gain.setValueAtTime(0.2, audioContext.currentTime);
                            gain2.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.2);
                            osc2.start(audioContext.currentTime);
                            osc2.stop(audioContext.currentTime + 0.2);
                        }, 100);
                    } catch(e) {}
                }
                return playSound;
            } catch(e) {
                return function() {
                    try {
                        const audio = new Audio('data:audio/wav;base64,UklGRnoAAABXQVZFZm10IBAAAAABAAEAQB8AAEAfAAABAAgAZGF0YQoAAACBhYqFhYWFiYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhYOFhQ==');
                        audio.volume = 0.3;
                        audio.play().catch(() => {});
                    } catch(e) {}
                };
            }
        }

        notificationSound = createNotificationSound();

        function loadChatMessages() {
            try {
                const stored = localStorage.getItem(CHAT_STORAGE_KEY);
                if (stored) {
                    chatMessages = JSON.parse(stored);
                }
            } catch(e) {
                chatMessages = [];
            }
        }

        function saveChatMessages() {
            try {
                localStorage.setItem(CHAT_STORAGE_KEY, JSON.stringify(chatMessages));
            } catch(e) {}
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
                if (unread > 0) {
                    document.title = `(${unread}) RICK | Cyber Security Researcher`;
                } else {
                    document.title = 'RICK | Cyber Security Researcher';
                }
            } else {
                notif.style.display = 'none';
                document.title = 'RICK | Cyber Security Researcher';
            }
        }

        function showTypingIndicator(show) {
            const indicator = document.getElementById('typingIndicator');
            if (indicator) {
                if (show) {
                    indicator.style.display = 'flex';
                    indicator.innerHTML = '<span>الطرف الآخر يكتب</span><span class="dots">...</span>';
                    const messages = document.getElementById('chatMessages');
                    if (messages) messages.scrollTop = messages.scrollHeight;
                } else {
                    indicator.style.display = 'none';
                }
            }
        }

        function sendChatMessage() {
            const input = document.getElementById('chatInput');
            if (!input || !input.value.trim()) return;

            const text = input.value.trim();
            const userId = getCookie('reck_user_id') || 'مستخدم';
            
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
            
            showTypingIndicator(true);
            
            setTimeout(() => {
                showTypingIndicator(false);
                receiveChatMessage('📧 تم إرسال رسالتك عبر البريد الإلكتروني مع رابط مباشر.', 'النظام', '📧 نظام البريد');
            }, 1500);
        }

        function receiveChatMessage(text, sender, source) {
            const lastMsg = chatMessages.length > 0 ? chatMessages[chatMessages.length - 1] : null;
            if (lastMsg && lastMsg.text === text && lastMsg.sender === sender) {
                return;
            }

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
            
            if (notificationSound) {
                try { notificationSound(); } catch(e) {}
            }
            
            if (navigator.vibrate) {
                navigator.vibrate(100);
            }
            
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
                    // توليد رسالة صوتية حقيقية
                    const text = "مرحباً! هذه رسالة صوتية مني. أنا هنا لمساعدتك.";
                    const sender = "Reck";
                    
                    receiveChatMessage(
                        `🎙️ رسالة صوتية من ${sender}`, 
                        sender, 
                        '🎙️ صوتي'
                    );
                    
                    generateRealVoiceMessage(text, function(audioData, duration) {
                        if (audioData) {
                            const msg = {
                                id: Date.now() + Math.random(),
                                text: `🎙️ رسالة صوتية: ${text}`,
                                type: 'received',
                                sender: sender,
                                time: new Date().toLocaleTimeString('ar'),
                                read: isChatOpen,
                                timestamp: new Date().toISOString(),
                                source: '🎙️ صوتي',
                                isAudio: true,
                                audioData: audioData,
                                duration: duration || 3
                            };
                            chatMessages.push(msg);
                            saveChatMessages();
                            renderChatMessages();
                        }
                    });
                } else {
                    const reply = replies[Math.floor(Math.random() * replies.length)];
                    receiveChatMessage(
                        `${reply}`, 
                        'Reck', 
                        '📧 البريد الإلكتروني'
                    );
                }
            }, 20000 + Math.random() * 20000);
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
            showTypingIndicator(false);
            if (isRecording) {
                stopRecording();
            }
        }

        function updateStatusDot() {
            const dot = document.getElementById('statusDot');
            if (!dot) return;

            if (navigator.onLine) {
                const startTime = Date.now();
                fetch('https://www.google.com/favicon.ico', { 
                    mode: 'no-cors',
                    cache: 'no-store'
                })
                .then(() => {
                    const pingTime = Date.now() - startTime;
                    if (pingTime < 200) {
                        dot.className = 'status-dot';
                        dot.title = '🟢 متصل - استجابة سريعة';
                    } else if (pingTime < 500) {
                        dot.className = 'status-dot idle';
                        dot.title = '🟡 متصل - استجابة بطيئة';
                    } else {
                        dot.className = 'status-dot idle';
                        dot.title = '🟡 متصل - استجابة ضعيفة';
                    }
                })
                .catch(() => {
                    dot.className = 'status-dot idle';
                    dot.title = '🟡 متصل - استجابة غير مستقرة';
                });
            } else {
                dot.className = 'status-dot offline';
                dot.title = '🔴 غير متصل';
            }
        }

        setInterval(updateStatusDot, 5000);

        function measureNetworkSpeed() {
            const speedSpan = document.getElementById('speedValue');
            if (!speedSpan) return;

            const startTime = Date.now();
            const url = 'https://www.google.com/images/phd/px.gif';

            fetch(url, { 
                mode: 'no-cors',
                cache: 'no-store'
            })
            .then(() => {
                const endTime = Date.now();
                const duration = (endTime - startTime) / 1000;
                if (duration > 0) {
                    const fileSize = 100000;
                    const speedKbps = (fileSize * 8) / (duration * 1000);
                    const displaySpeed = speedKbps > 1024 ? (speedKbps / 1024).toFixed(1) : speedKbps.toFixed(0);
                    const unit = speedKbps > 1024 ? 'Mbps' : 'Kbps';
                    speedSpan.textContent = displaySpeed;
                    speedSpan.nextElementSibling.textContent = unit;
                }
            })
            .catch(() => {
                speedSpan.textContent = '?';
                speedSpan.nextElementSibling.textContent = '';
            });
        }

        setInterval(measureNetworkSpeed, 15000);
        measureNetworkSpeed();

        function initUserSession() {
            let userId = getCookie('reck_user_id');
            if (!userId) {
                userId = 'user_' + Date.now() + '_' + Math.random().toString(36).substr(2, 6);
                setCookie('reck_user_id', userId, 30);
                setCookie('reck_first_visit', new Date().toISOString(), 30);
            }
            setCookie('reck_last_visit', new Date().toISOString(), 30);
            let visits = parseInt(getCookie('reck_visits') || '0') + 1;
            setCookie('reck_visits', visits.toString(), 30);
        }

        // ===== MY PRESET VIDEOS =====
        const MY_PRESET_VIDEOS = [
            {
                type: "local",
                id: "VID20260710115227.mp4",
                title: "يوميات ريك",
                translation: "مقطع فيديو حصري من يوميات ريك، يوثق الأنشطة اليومية والتجارب الميدانية في الأبحاث الأمنية والتقنية."
            },
            { 
                type: "youtube",
                id: "wAzR14CknzU", 
                title: "The story of Noah's Ark (قصة سفينة نوح)",
                translation: "منذ زمن طويل، دعا الله نوحاً، وهو رجل صالح، لبناء سفينة - ملاذ للخلاص. ورغم سخرية العالم، أطاع نوح دون تردد، واثقاً في الوعد الإلهي بالحماية. من كل ركن من أركان الأرض، سارت المخلوقات كبيرة وصغيرة إلى السفينة؛ الأسود والحملان مشوا جنباً إلى جنب، مستجيبين لنداء صامت للحفظ. وعندما تراجعت المياه، قدم نوح الامتنان لله، ورداً على ذلك، امتد قوس قزح في السماء كعهد أبدي بين الله والبشرية، واعداً بعدم غمر الأرض بالفيضان مرة أخرى."
            }
        ];

        let videoInteractions = {};

        function getVideoId(video) {
            return video.type === "local" ? video.id : video.id;
        }

        function createVideoCard(video) {
            const vidId = getVideoId(video);
            if (!videoInteractions[vidId]) {
                videoInteractions[vidId] = { liked: false, comments: [] };
            }

            const cleanTitle = video.title.replace(/['"\\]/g, "");
            let mediaHtml = '';

            if (video.type === "local") {
                mediaHtml = `<video src="${video.id}" controls autoplay muted playsinline loop></video>`;
            } else {
                mediaHtml = `<iframe src="https://www.youtube.com/embed/${video.id}?autoplay=1&mute=0&rel=0&modestbranding=1" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>`;
            }

            const interaction = videoInteractions[vidId];
            const likeClass = interaction.liked ? 'liked' : '';
            const commentCount = interaction.comments.length;

            return `
                <div class="video-wrapper" onmouseenter="speakVideoTitle('${cleanTitle}')">
                    <div class="video-container">
                        ${mediaHtml}
                    </div>
                    <div class="video-title">${video.title}</div>
                    <div class="video-translation">
                        <strong><i class="fa-solid fa-language"></i> الوصف والترجمة:</strong>
                        ${video.translation}
                    </div>
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

        function toggleLike(vidId) {
            const interaction = videoInteractions[vidId];
            interaction.liked = !interaction.liked;
            const countSpan = document.getElementById(`like-count-${vidId}`);
            if (countSpan) {
                countSpan.textContent = interaction.liked ? 1 : 0;
            }
            const btn = document.querySelector(`#like-count-${vidId}`)?.closest('.interaction-btn');
            if (btn) {
                btn.classList.toggle('liked');
                const icon = btn.querySelector('i');
                if (icon) {
                    icon.className = interaction.liked ? 'fa-solid fa-heart' : 'fa-regular fa-heart';
                }
            }
            sendInteractionEmail('إعجاب', vidId, interaction.liked ? 'أعجبني' : 'إلغاء الإعجاب');
        }

        function focusComment(vidId) {
            const input = document.getElementById(`comment-input-${vidId}`);
            if (input) input.focus();
        }

        function submitComment(vidId) {
            const input = document.getElementById(`comment-input-${vidId}`);
            if (!input || !input.value.trim()) return;
            
            const comment = input.value.trim();
            const interaction = videoInteractions[vidId];
            interaction.comments.push(comment);
            
            const countSpan = document.getElementById(`comment-count-${vidId}`);
            if (countSpan) {
                countSpan.textContent = interaction.comments.length;
            }
            
            sendInteractionEmail('تعليق', vidId, comment);
            input.value = '';
            alert('تم إرسال تعليقك بنجاح!');
        }

        function sendInteractionEmail(type, vidId, content) {
            const userId = getCookie('reck_user_id') || 'مستخدم غير معروف';
            const subject = encodeURIComponent(`تفاعل جديد - ${type} على فيديو`);
            const link = `${SITE_URL}?type=interaction&content=${encodeURIComponent(content)}&sender=${userId}`;
            const body = encodeURIComponent(
                `نوع التفاعل: ${type}\n` +
                `معرف الفيديو: ${vidId}\n` +
                `المحتوى: ${content}\n` +
                `المستخدم: ${userId}\n` +
                `🔗 رابط التفاعل: ${link}\n` +
                `تم الإرسال من: ${window.location.href}`
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

        function copyEmail() {
            navigator.clipboard?.writeText(TARGET_EMAIL).then(() => {
                alert('تم نسخ البريد الإلكتروني!');
            }).catch(() => {
                alert(TARGET_EMAIL);
            });
        }

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
            if (popup.style.display === 'block') {
                document.getElementById('messageText').focus();
            }
        }

        function sendFriendRequest() {
            const userId = getCookie('reck_user_id') || 'مستخدم غير معروف';
            const subject = encodeURIComponent(`طلب صداقة من مستخدم`);
            const link = `${SITE_URL}?type=friend&sender=${userId}`;
            const body = encodeURIComponent(
                `مرحباً،\n\n` +
                `قام المستخدم "${userId}" بإرسال طلب صداقة.\n` +
                `🔗 رابط طلب الصداقة: ${link}\n` +
                `تم الإرسال من: ${window.location.href}`
            );
            window.open(`mailto:${TARGET_EMAIL}?subject=${subject}&body=${body}`, '_blank');
            alert('تم إرسال طلب الصداقة بنجاح!');
        }

        function sendMessage() {
            const message = document.getElementById('messageText')?.value?.trim() || 'لا توجد رسالة';
            const userId = getCookie('reck_user_id') || 'مستخدم غير معروف';
            const subject = encodeURIComponent(`رسالة جديدة من ${userId}`);
            const link = `${SITE_URL}?type=text&content=${encodeURIComponent(message)}&sender=${userId}`;
            const body = encodeURIComponent(
                `مرحباً،\n\n` +
                `المرسل: ${userId}\n` +
                `----------------------------------------\n` +
                `${message}\n` +
                `----------------------------------------\n` +
                `🔗 رابط الرسالة: ${link}\n` +
                `تم الإرسال من: ${window.location.href}`
            );
            window.open(`mailto:${TARGET_EMAIL}?subject=${subject}&body=${body}`, '_blank');
            document.getElementById('messageText').value = '';
            document.getElementById('messagePopup').style.display = 'none';
            alert('تم إرسال رسالتك بنجاح!');
        }

        function runSecuritySimulation() { 
            setTimeout(() => { document.getElementById('line2').style.display = 'block'; }, 400); 
            setTimeout(() => { document.getElementById('line3').style.display = 'block'; }, 800); 
            setTimeout(() => { document.getElementById('line4').style.display = 'block'; }, 1200); 
            setTimeout(() => { 
                document.getElementById('line5').style.display = 'block'; 
                setCookie("reck_session_scanned", "true", 7); 
                document.getElementById('liveCookieBox').style.display = 'block'; 
                document.getElementById('cookieValueSpan').innerText = `reck_session_scanned=true`; 
            }, 1600); 
            setTimeout(() => { 
                document.getElementById('security-check').style.display = 'none'; 
                initUserSession();
                loadChatMessages();
                renderChatMessages();
                simulateEmailReception();
                checkUrlParams();
                
                setTimeout(() => {
                    receiveChatMessage('📧 مرحباً بك في غرفة الشات! يمكنك إرسال رسائل نصية أو صوتية.', 'النظام', '📧 نظام البريد');
                }, 1500);
                
                setTimeout(() => {
                    receiveChatMessage('👋 أهلاً! أنا هنا لمساعدتك. يمكنك التواصل معي عبر الشات أو البريد الإلكتروني.', 'Reck', '📧 البريد الإلكتروني');
                }, 3000);
                
                setTimeout(() => {
                    receiveChatMessage('🔗 تم تفعيل نظام الروابط المباشرة. عند الضغط على رابط في البريد، ستظهر الرسالة تلقائياً.', 'النظام', '🔗 روابط مباشرة');
                }, 4500);
            }, 3200); 
        }

        document.addEventListener('DOMContentLoaded', () => {
            if ("Notification" in window && Notification.permission === "default") {
                Notification.requestPermission();
            }

            checkUrlParams();

            if (getCookie("reck_session_scanned") === "true") {
                document.getElementById('security-check').style.display = 'none';
                initUserSession();
                loadChatMessages();
                renderChatMessages();
                simulateEmailReception();
                
                setTimeout(() => {
                    receiveChatMessage('📧 مرحباً بك في غرفة الشات! يمكنك إرسال رسائل نصية أو صوتية.', 'النظام', '📧 نظام البريد');
                }, 1000);
                setTimeout(() => {
                    receiveChatMessage('👋 أهلاً! أنا هنا لمساعدتك. يمكنك التواصل معي عبر الشات أو البريد الإلكتروني.', 'Reck', '📧 البريد الإلكتروني');
                }, 2500);
                setTimeout(() => {
                    receiveChatMessage('🔗 تم تفعيل نظام الروابط المباشرة. عند الضغط على رابط في البريد، ستظهر الرسالة تلقائياً.', 'النظام', '🔗 روابط مباشرة');
                }, 4000);
            } else {
                runSecuritySimulation();
            }

            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape') {
                    closeChat();
                }
            });

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
                termHistory.innerHTML += `<div><span class="prompt">reck@seclab:~$</span> <span style="color: #fff">${cmd}</span></div>`;
                let output = '';
                const lowerCmd = cmd.toLowerCase();

                if (lowerCmd === 'help') {
                    output = `<span class="cmd-output">Available Commands:<br>
                    - <b>tools</b> : List cybersecurity research tools deployed.<br>
                    - <b>scan</b>  : Run a demo network integrity check.<br>
                    - <b>clear</b> : Clear the terminal interface.<br>
                    - <b>about</b> : Show researcher credential file.<br>
                    - <b>status</b>: Show current user session info.<br>
                    - <b>chat</b>  : Open the chat window.<br>
                    - <b>send</b> [msg] : Send a chat message.<br>
                    - <b>voice</b> : Toggle voice recording.<br>
                    - <b>link</b> : Show the direct link URL.</span>`;
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
                    output = `<span class="cmd-output">File: reck_credentials.txt<br>
                    Role: Cyber Security Researcher / Bug Bounty Hunter.<br>
                    Specialty: Web Apps Security & Network Auditing.</span>`;
                } else if (lowerCmd === 'status') {
                    const userId = getCookie('reck_user_id') || 'غير معروف';
                    const visits = getCookie('reck_visits') || '0';
                    const firstVisit = getCookie('reck_first_visit') || 'غير معروف';
                    const lastVisit = getCookie('reck_last_visit') || 'غير معروف';
                    output = `<span class="cmd-output success-msg">[+] User Session Info:<br>
                    User ID: ${userId}<br>
                    Visits: ${visits}<br>
                    First Visit: ${firstVisit}<br>
                    Last Visit: ${lastVisit}<br>
                    Chat Messages: ${chatMessages.length}</span>`;
                } else if (lowerCmd === 'chat') {
                    openChat();
                    output = `<span class="cmd-output success-msg">[+] Opening chat window...</span>`;
                } else if (lowerCmd === 'voice') {
                    toggleRecording();
                    output = `<span class="cmd-output success-msg">[+] Toggling voice recording...</span>`;
                } else if (lowerCmd === 'link') {
                    output = `<span class="cmd-output success-msg">[+] Direct Link URL:<br>${SITE_URL}</span>`;
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
            loadPresetVideos(grid);
        }

        function loadPresetVideos(gridElement) {
            gridElement.innerHTML = '';
            MY_PRESET_VIDEOS.forEach(video => {
                gridElement.innerHTML += createVideoCard(video);
            });
        }

        function activateFollow() {
            if (!("Notification" in window)) { alert("متصفحك لا يدعم الإشعارات."); return; }
            Notification.requestPermission().then(permission => {
                if (permission === "granted") {
                    localStorage.setItem('notifications_enabled', 'true');
                    new Notification("Reck System Control", { body: "تم تفعيل نظام المتابعة الذكي وقناتك متصلة حالياً!" });
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

        window.addEventListener('online', updateStatusDot);
        window.addEventListener('offline', updateStatusDot);

        const mobileMenu = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');
        if (mobileMenu) {
            mobileMenu.addEventListener('click', () => { navList.classList.toggle('active'); });
        }
    </script>
</body>
</html>
