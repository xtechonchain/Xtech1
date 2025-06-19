# Xtech1
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>X-Tech - The Future is Now</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated background particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #00d4ff;
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 1; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 0.5; }
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 50px;
            backdrop-filter: blur(20px);
            background: rgba(0, 0, 0, 0.3);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-size: 28px;
            font-weight: 800;
            background: linear-gradient(45deg, #00d4ff, #ff0080);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            gap: 40px;
        }

        .nav-links a {
            color: #ffffff;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #00d4ff;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(45deg, #00d4ff, #ff0080);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 800px;
            z-index: 2;
            animation: fadeInUp 1s ease-out;
        }

        .hero h1 {
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 900;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ffffff, #00d4ff, #ff0080);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            line-height: 1.1;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 40px;
            opacity: 0.9;
            font-weight: 300;
        }

        .cta-button {
            display: inline-block;
            padding: 15px 40px;
            background: linear-gradient(45deg, #00d4ff, #ff0080);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 212, 255, 0.5);
        }

        /* Countdown Timer */
        .countdown-section {
            padding: 100px 50px;
            text-align: center;
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
        }

        .countdown-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #00d4ff, #ff0080);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .countdown-timer {
            display: flex;
            justify-content: center;
            align-items: baseline;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 40px;
            font-family: 'Courier New', monospace;
        }

        .time-unit {
            text-align: center;
            transition: all 0.3s ease;
        }

        .time-unit:hover {
            transform: scale(1.1);
        }

        .time-number {
            font-size: clamp(4rem, 8vw, 7rem);
            font-weight: 900;
            background: linear-gradient(45deg, #00d4ff, #ff0080, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: block;
            line-height: 0.9;
            text-shadow: 0 0 30px rgba(0, 212, 255, 0.5);
            animation: pulse 2s ease-in-out infinite alternate;
        }

        .time-label {
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            opacity: 0.6;
            margin-top: 5px;
            font-weight: 400;
        }

        .time-separator {
            font-size: clamp(3rem, 6vw, 5rem);
            font-weight: 300;
            color: rgba(255, 255, 255, 0.3);
            margin: 0 10px;
            animation: blink 1s ease-in-out infinite;
        }

        @keyframes pulse {
            0% { 
                filter: brightness(1) saturate(1);
                transform: scale(1);
            }
            100% { 
                filter: brightness(1.2) saturate(1.3);
                transform: scale(1.02);
            }
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0.3; }
        }

        /* Features Section */
        .features {
            padding: 100px 50px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            font-weight: 800;
            margin-bottom: 60px;
            background: linear-gradient(45deg, #ffffff, #00d4ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .feature-card {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            background: rgba(0, 212, 255, 0.05);
            border-color: rgba(0, 212, 255, 0.2);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.1);
        }

        .feature-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(45deg, #00d4ff, #ff0080);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 15px;
            color: #00d4ff;
        }

        .feature-card p {
            opacity: 0.8;
            line-height: 1.6;
        }

        /* Stats Section */
        .stats {
            padding: 100px 50px;
            background: rgba(0, 0, 0, 0.3);
            text-align: center;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .stat-item {
            padding: 20px;
        }

        .stat-number {
            font-size: 3.5rem;
            font-weight: 900;
            color: #00d4ff;
            display: block;
            margin-bottom: 10px;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.8;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* CTA Section */
        .final-cta {
            padding: 100px 50px;
            text-align: center;
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.1), rgba(255, 0, 128, 0.1));
        }

        .final-cta h2 {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 20px;
        }

        .final-cta p {
            font-size: 1.2rem;
            margin-bottom: 40px;
            opacity: 0.9;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in {
            animation: fadeInUp 1s ease-out;
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                padding: 15px 20px;
            }
            
            .nav-links {
                gap: 20px;
            }
            
            .hero, .countdown-section, .features, .stats, .final-cta {
                padding: 60px 20px;
            }
            
            .countdown-timer {
                gap: 10px;
            }
            
            .time-separator {
                margin: 0 5px;
                font-size: clamp(2rem, 5vw, 3rem);
            }
            
            .time-number {
                font-size: clamp(2.5rem, 6vw, 4rem);
            }
            
            .time-label {
                font-size: 0.7rem;
                letter-spacing: 2px;
            }
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="particles" id="particles"></div>

    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo">X-TECH</div>
            <div class="nav-links">
                <a href="#about">About</a>
                <a href="#features">Features</a>
                <a href="#countdown">Launch</a>
                <a href="#contact">Contact</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>THE FUTURE IS X-TECH</h1>
            <p>Revolutionizing technology with cutting-edge solutions that transform industries and empower innovation.</p>
            <a href="#features" class="cta-button">Explore the Future</a>
        </div>
    </section>

    <!-- Countdown Section -->
    <section class="countdown-section" id="countdown">
        <h2 class="countdown-title">PLATFORM LAUNCH COUNTDOWN</h2>
        <p>The AI education revolution starts soon. Be first in line.</p>
        <div class="countdown-timer">
            <div class="time-unit">
                <span class="time-number" id="days">00</span>
                <span class="time-label">Days</span>
            </div>
            <div class="time-separator">:</div>
            <div class="time-unit">
                <span class="time-number" id="hours">00</span>
                <span class="time-label">Hours</span>
            </div>
            <div class="time-separator">:</div>
            <div class="time-unit">
                <span class="time-number" id="minutes">00</span>
                <span class="time-label">Minutes</span>
            </div>
            <div class="time-separator">:</div>
            <div class="time-unit">
                <span class="time-number" id="seconds">00</span>
                <span class="time-label">Seconds</span>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <h2 class="section-title">Revolutionary Features</h2>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">🚀</div>
                <h3>Next-Gen Performance</h3>
                <p>Unprecedented speed and efficiency powered by cutting-edge algorithms and optimized architecture that scales infinitely.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🧠</div>
                <h3>AI-Powered Intelligence
