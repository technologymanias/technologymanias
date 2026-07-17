<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>MIT SONPAR - Banner</title>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;600;700;800&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: #0d1117;
            font-family: 'Fira Code', monospace;
        }

        /* ── Banner Container ── */
        .banner {
            width: 1280px;
            max-width: 100%;
            height: 340px;
            background: linear-gradient(145deg, #0d1117 0%, #161b22 50%, #0d1117 100%);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.06);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.8), inset 0 1px 0 rgba(255, 255, 255, 0.05);
            padding: 36px 48px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        /* ── Animated Background Glow ── */
        .banner::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle at 30% 40%, rgba(0, 191, 255, 0.04) 0%, transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(123, 66, 188, 0.04) 0%, transparent 50%);
            animation: glowShift 12s ease-in-out infinite alternate;
            pointer-events: none;
        }

        @keyframes glowShift {
            0% {
                transform: translate(0, 0) scale(1);
            }
            100% {
                transform: translate(2%, 2%) scale(1.1);
            }
        }

        /* ── Grid Overlay ── */
        .banner::after {
            content: '';
            position: absolute;
            inset: 0;
            background-image:
                linear-gradient(rgba(255, 255, 255, 0.02) 1px, transparent 1px),
                linear-gradient(90deg, rgba(255, 255, 255, 0.02) 1px, transparent 1px);
            background-size: 40px 40px;
            pointer-events: none;
        }

        /* ── Banner Content ── */
        .banner-content {
            display: flex;
            align-items: center;
            gap: 44px;
            position: relative;
            z-index: 2;
            height: 100%;
        }

        /* ── Avatar ── */
        .avatar-wrapper {
            position: relative;
            flex-shrink: 0;
        }

        .avatar-ring {
            width: 130px;
            height: 130px;
            border-radius: 50%;
            padding: 3px;
            background: conic-gradient(from 0deg, #00BFFF, #7B42BC, #FF6B00, #00BFFF);
            animation: spinRing 10s linear infinite;
            box-shadow: 0 0 50px rgba(0, 191, 255, 0.15);
        }

        @keyframes spinRing {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }

        .avatar-ring .avatar {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: #0d1117;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 52px;
            font-weight: 800;
            color: #fff;
            letter-spacing: 2px;
            overflow: hidden;
        }

        .avatar-ring .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* ── Online Status Dot ── */
        .status-dot {
            position: absolute;
            bottom: 6px;
            right: 6px;
            width: 18px;
            height: 18px;
            background: #2ea043;
            border-radius: 50%;
            border: 3px solid #0d1117;
            animation: pulseDot 2s ease-in-out infinite;
        }

        @keyframes pulseDot {
            0%,
            100% {
                transform: scale(1);
                box-shadow: 0 0 0 0 rgba(46, 160, 67, 0.5);
            }
            50% {
                transform: scale(1.1);
                box-shadow: 0 0 20px rgba(46, 160, 67, 0.3);
            }
        }

        /* ── Info ── */
        .info {
            flex: 1;
        }

        .info .name {
            font-size: 44px;
            font-weight: 800;
            letter-spacing: 3px;
            background: linear-gradient(135deg, #ffffff 0%, #8b949e 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 4px;
            text-shadow: 0 0 40px rgba(255, 255, 255, 0.05);
        }

        .info .title {
            font-size: 18px;
            font-weight: 600;
            color: #58a6ff;
            margin-bottom: 2px;
            letter-spacing: 1px;
        }

        .info .subtitle {
            font-size: 14px;
            color: #8b949e;
            margin-bottom: 14px;
            letter-spacing: 0.5px;
        }

        .info .subtitle span {
            color: #c9d1d9;
        }

        /* ── Stats Row ── */
        .stats-row {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .stat-item {
            display: flex;
            align-items: center;
            gap: 8px;
            background: rgba(255, 255, 255, 0.04);
            padding: 6px 16px 6px 12px;
            border-radius: 30px;
            border: 1px solid rgba(255, 255, 255, 0.06);
            transition: all 0.3s ease;
            cursor: default;
        }

        .stat-item:hover {
            background: rgba(255, 255, 255, 0.08);
            border-color: rgba(0, 191, 255, 0.2);
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
        }

        .stat-item .icon {
            font-size: 16px;
            color: #58a6ff;
        }

        .stat-item .label {
            font-size: 11px;
            font-weight: 400;
            color: #8b949e;
            letter-spacing: 0.3px;
        }

        .stat-item .value {
            font-size: 13px;
            font-weight: 700;
            color: #f0f6fc;
        }

        /* ── Tech Stack Bar ── */
        .tech-bar {
            margin-top: 16px;
            display: flex;
            align-items: center;
            gap: 6px;
            flex-wrap: wrap;
            padding-top: 14px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }

        .tech-bar .tech-label {
            font-size: 10px;
            font-weight: 400;
            color: #8b949e;
            letter-spacing: 1px;
            text-transform: uppercase;
            margin-right: 6px;
        }

        .tech-bar .tech-item {
            font-size: 11px;
            font-weight: 500;
            color: #c9d1d9;
            background: rgba(255, 255, 255, 0.05);
            padding: 3px 12px;
            border-radius: 30px;
            border: 1px solid rgba(255, 255, 255, 0.06);
            transition: all 0.3s ease;
            cursor: default;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .tech-bar .tech-item:hover {
            background: rgba(0, 191, 255, 0.1);
            border-color: rgba(0, 191, 255, 0.2);
            transform: translateY(-1px);
        }

        .tech-bar .tech-item .dot {
            width: 6px;
            height: 6px;
            border-radius: 50%;
            display: inline-block;
        }

        .dot-blue {
            background: #00BFFF;
        }
        .dot-purple {
            background: #7B42BC;
        }
        .dot-orange {
            background: #FF6B00;
        }
        .dot-green {
            background: #2ea043;
        }
        .dot-yellow {
            background: #d29922;
        }
        .dot-red {
            background: #da3633;
        }
        .dot-teal {
            background: #3fb950;
        }
        .dot-pink {
            background: #f778ba;
        }

        /* ── Right Side Decoration ── */
        .right-decoration {
            flex-shrink: 0;
            display: flex;
            flex-direction: column;
            align-items: flex-end;
            gap: 8px;
        }

        .badge-group {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
            justify-content: flex-end;
        }

        .badge-item {
            font-size: 10px;
            font-weight: 600;
            padding: 4px 14px;
            border-radius: 20px;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            background: rgba(255, 255, 255, 0.04);
            border: 1px solid rgba(255, 255, 255, 0.06);
            color: #8b949e;
            transition: all 0.3s ease;
        }

        .badge-item:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
        }

        .badge-item.blue {
            border-color: rgba(0, 191, 255, 0.3);
            color: #58a6ff;
        }
        .badge-item.purple {
            border-color: rgba(123, 66, 188, 0.3);
            color: #a371f7;
        }
        .badge-item.orange {
            border-color: rgba(255, 107, 0, 0.3);
            color: #ff8c42;
        }
        .badge-item.green {
            border-color: rgba(46, 160, 67, 0.3);
            color: #3fb950;
        }

        /* ── Floating Particles ── */
        .particle {
            position: absolute;
            border-radius: 50%;
            background: rgba(0, 191, 255, 0.15);
            pointer-events: none;
            animation: floatParticle 20s infinite alternate ease-in-out;
        }

        .particle:nth-child(1) {
            width: 120px;
            height: 120px;
            top: -30px;
            right: -20px;
            animation-duration: 25s;
        }
        .particle:nth-child(2) {
            width: 80px;
            height: 80px;
            bottom: -10px;
            left: 30%;
            background: rgba(123, 66, 188, 0.08);
            animation-duration: 18s;
            animation-delay: -5s;
        }
        .particle:nth-child(3) {
            width: 60px;
            height: 60px;
            top: 20%;
            right: 30%;
            background: rgba(255, 107, 0, 0.06);
            animation-duration: 22s;
            animation-delay: -10s;
        }

        @keyframes floatParticle {
            0% {
                transform: translate(0, 0) scale(1);
                opacity: 0.3;
            }
            50% {
                transform: translate(30px, -20px) scale(1.2);
                opacity: 0.6;
            }
            100% {
                transform: translate(-20px, 30px) scale(0.8);
                opacity: 0.3;
            }
        }

        /* ── Responsive ── */
        @media (max-width: 1024px) {
            .banner {
                height: auto;
                padding: 32px 28px;
            }
            .banner-content {
                flex-direction: column;
                gap: 24px;
                align-items: center;
                text-align: center;
            }
            .info {
                text-align: center;
            }
            .stats-row {
                justify-content: center;
            }
            .tech-bar {
                justify-content: center;
            }
            .right-decoration {
                align-items: center;
            }
            .badge-group {
                justify-content: center;
            }
        }

        @media (max-width: 600px) {
            .banner {
                padding: 24px 16px;
                border-radius: 12px;
            }
            .info .name {
                font-size: 28px;
            }
            .info .title {
                font-size: 15px;
            }
            .avatar-ring {
                width: 90px;
                height: 90px;
            }
            .avatar-ring .avatar {
                font-size: 32px;
            }
            .stat-item {
                padding: 4px 12px 4px 8px;
            }
            .stat-item .label {
                font-size: 9px;
            }
            .stat-item .value {
                font-size: 11px;
            }
            .tech-bar .tech-item {
                font-size: 9px;
                padding: 2px 10px;
            }
            .badge-item {
                font-size: 8px;
                padding: 3px 10px;
            }
            .particle {
                display: none;
            }
        }
    </style>
</head>
<body>

    <!-- ═══ BANNER ═══ -->
    <div class="banner">

        <!-- Floating Particles -->
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>

        <!-- ═══ CONTENT ═══ -->
        <div class="banner-content">

            <!-- ── Avatar ── -->
            <div class="avatar-wrapper">
                <div class="avatar-ring">
                    <div class="avatar">
                        <!-- Replace src with your actual photo -->
                        <img src="https://ui-avatars.com/api/?name=Mit+Sonpar&size=200&background=0d1117&color=00BFFF&bold=true" alt="Mit Sonpar" />
                    </div>
                </div>
                <div class="status-dot"></div>
            </div>

            <!-- ── Info ── -->
            <div class="info">
                <div class="name">MIT SONPAR</div>
                <div class="title">Lead Software Engineer</div>
                <div class="subtitle">
                    <span>Backend</span> &bull;
                    <span>AI/LLM</span> &bull;
                    <span>Cloud</span> &bull;
                    <span>DevOps</span>
                </div>

                <!-- Stats -->
                <div class="stats-row">
                    <div class="stat-item">
                        <span class="icon">⏳</span>
                        <span class="label">Experience</span>
                        <span class="value">10+ Years</span>
                    </div>
                    <div class="stat-item">
                        <span class="icon">☁️</span>
                        <span class="label">AWS</span>
                        <span class="value">Certified</span>
                    </div>
                    <div class="stat-item">
                        <span class="icon">🛠️</span>
                        <span class="label">SDK</span>
                        <span class="value">Expert</span>
                    </div>
                    <div class="stat-item">
                        <span class="icon">🤖</span>
                        <span class="label">AI/ML</span>
                        <span class="value">Builder</span>
                    </div>
                </div>

                <!-- Tech Stack -->
                <div class="tech-bar">
                    <span class="tech-label">Tech Stack</span>
                    <span class="tech-item"><span class="dot dot-blue"></span>AWS</span>
                    <span class="tech-item"><span class="dot dot-yellow"></span>Python</span>
                    <span class="tech-item"><span class="dot dot-blue"></span>TypeScript</span>
                    <span class="tech-item"><span class="dot dot-orange"></span>Rust</span>
                    <span class="tech-item"><span class="dot dot-purple"></span>Terraform</span>
                    <span class="tech-item"><span class="dot dot-blue"></span>Docker</span>
                    <span class="tech-item"><span class="dot dot-red"></span>Java</span>
                    <span class="tech-item"><span class="dot dot-purple"></span>C#</span>
                </div>
            </div>

            <!-- ── Right Decoration ── -->
            <div class="right-decoration">
                <div class="badge-group">
                    <span class="badge-item blue">🏆 10+ Years</span>
                    <span class="badge-item purple">☁️ AWS</span>
                    <span class="badge-item orange">🛠️ SDK Expert</span>
                    <span class="badge-item green">🤖 AI/ML</span>
                </div>
                <div class="badge-group" style="margin-top: 4px;">
                    <span class="badge-item blue">👨‍💼 Team Lead (22)</span>
                    <span class="badge-item purple">📦 5+ SaaS/yr</span>
                    <span class="badge-item orange">⚡ 99.9% Uptime</span>
                </div>
            </div>

        </div>
    </div>

</body>
</html>
