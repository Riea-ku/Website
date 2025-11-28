
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Providentia - AI-Powered Predictive Maintenance for Agriculture</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --dark-purple: #1a103d;
            --purple: #3a1c8c;
            --light-purple: #5a34b8;
            --turquoise: #00e5c4;
            --light-turquoise: #4dfee8;
            --black: #0a0a0a;
            --dark-gray: #1a1a1a;
            --gray: #2a2a2a;
            --light-gray: #e5e5e5;
            --white: #ffffff;
            --gradient: linear-gradient(135deg, var(--purple) 0%, var(--turquoise) 100%);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            color: var(--white);
            background-color: var(--black);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header & Navigation */
        header {
            background-color: rgba(26, 16, 61, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            transition: all 0.3s ease;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        header.scrolled {
            padding: 10px 0;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            transition: all 0.3s ease;
        }
        
        header.scrolled nav {
            padding: 5px 0;
        }
        
        .logo {
            font-size: 28px;
            font-weight: 800;
            color: var(--turquoise);
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            font-size: 24px;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 30px;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--white);
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }
        
        .nav-links a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: var(--turquoise);
            transition: width 0.3s ease;
        }
        
        .nav-links a:hover:after {
            width: 100%;
        }
        
        .nav-links a:hover {
            color: var(--turquoise);
        }
        
        .btn {
            display: inline-block;
            background: var(--gradient);
            color: var(--black);
            padding: 14px 28px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(0, 229, 196, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .btn:before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
            transition: left 0.5s;
        }
        
        .btn:hover:before {
            left: 100%;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 229, 196, 0.4);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--dark-purple) 0%, var(--black) 100%);
            padding: 180px 0 100px;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000" opacity="0.03"><polygon fill="%2300e5c4" points="0,1000 1000,0 1000,1000"/></svg>');
            background-size: cover;
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: relative;
            z-index: 1;
        }
        
        .hero-text {
            flex: 1;
            padding-right: 50px;
            animation: fadeInUp 1s ease;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
            font-weight: 800;
            background: linear-gradient(to right, var(--white) 0%, var(--turquoise) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .hero p {
            font-size: 1.25rem;
            margin-bottom: 40px;
            color: var(--light-gray);
            max-width: 600px;
        }
        
        .hero-image {
            flex: 1;
            text-align: center;
            animation: fadeIn 1.5s ease;
        }
        
        .dashboard-preview {
            width: 100%;
            max-width: 600px;
            border-radius: 15px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
            transform: perspective(1000px) rotateY(-5deg) rotateX(5deg);
            transition: transform 0.5s ease;
        }
        
        .dashboard-preview:hover {
            transform: perspective(1000px) rotateY(0) rotateX(0);
        }
        
        /* Stats Section */
        .stats {
            background-color: var(--dark-gray);
            padding: 80px 0;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 30px;
        }
        
        .stat-card {
            text-align: center;
            padding: 30px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            transition: transform 0.3s ease;
        }
        
        .stat-card:hover {
            transform: translateY(-10px);
        }
        
        .stat-icon {
            font-size: 2.5rem;
            color: var(--turquoise);
            margin-bottom: 15px;
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 10px;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .stat-text {
            color: var(--light-gray);
            font-size: 0.9rem;
        }
        
        /* Features Section */
        .features {
            padding: 100px 0;
            background-color: var(--black);
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--white);
            margin-bottom: 15px;
            font-weight: 700;
        }
        
        .section-title p {
            color: var(--light-gray);
            max-width: 700px;
            margin: 0 auto;
            font-size: 1.1rem;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background: linear-gradient(145deg, var(--dark-purple), var(--gray));
            border-radius: 15px;
            padding: 40px 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .feature-card:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient);
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
        }
        
        .feature-icon {
            background: rgba(0, 229, 196, 0.1);
            color: var(--turquoise);
            width: 70px;
            height: 70px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 25px;
            font-size: 28px;
        }
        
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--white);
        }
        
        .feature-card p {
            color: var(--light-gray);
        }
        
        /* Solution Section */
        .solution {
            padding: 100px 0;
            background-color: var(--dark-gray);
        }
        
        .solution-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }
        
        .solution-text h3 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--turquoise);
            font-weight: 700;
        }
        
        .solution-text p {
            margin-bottom: 20px;
            color: var(--light-gray);
            font-size: 1.1rem;
        }
        
        .solution-features {
            margin-top: 30px;
        }
        
        .solution-feature {
            display: flex;
            align-items: flex-start;
            margin-bottom: 25px;
        }
        
        .solution-feature i {
            color: var(--turquoise);
            margin-right: 15px;
            font-size: 24px;
            margin-top: 3px;
            flex-shrink: 0;
        }
        
        .solution-feature div h4 {
            font-size: 1.2rem;
            margin-bottom: 5px;
            color: var(--white);
        }
        
        .solution-feature div p {
            color: var(--light-gray);
            margin: 0;
        }
        
        .solution-image {
            text-align: center;
        }
        
        .tech-visual {
            width: 100%;
            max-width: 500px;
            border-radius: 15px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
        }
        
        /* CTA Section */
        .cta {
            background: linear-gradient(135deg, var(--purple) 0%, var(--dark-purple) 100%);
            text-align: center;
            padding: 120px 0;
            position: relative;
            overflow: hidden;
        }
        
        .cta:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000" opacity="0.05"><circle fill="%2300e5c4" cx="500" cy="500" r="400"/></svg>');
            background-size: cover;
        }
        
        .cta-content {
            position: relative;
            z-index: 1;
        }
        
        .cta h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            font-weight: 700;
        }
        
        .cta p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 40px;
            color: var(--light-gray);
        }
        
        /* Footer */
        footer {
            background-color: var(--black);
            padding: 80px 0 30px;
            border-top: 1px solid var(--gray);
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 50px;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 25px;
            color: var(--turquoise);
            font-weight: 600;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 12px;
        }
        
        .footer-links a {
            color: var(--light-gray);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: var(--turquoise);
        }
        
        .contact-info {
            margin-top: 20px;
        }
        
        .contact-info a {
            color: var(--turquoise);
            text-decoration: none;
            font-weight: 500;
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid var(--gray);
            color: var(--light-gray);
            font-size: 0.9rem;
        }
        
        .legal-links {
            display: flex;
            justify-content: center;
            list-style: none;
            margin-top: 15px;
        }
        
        .legal-links li {
            margin: 0 15px;
        }
        
        .legal-links a {
            color: var(--light-gray);
            text-decoration: none;
            transition: color 0.3s;
            font-size: 0.9rem;
        }
        
        .legal-links a:hover {
            color: var(--turquoise);
        }
        
        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }
        
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Responsive */
        @media (max-width: 968px) {
            .hero-content {
                flex-direction: column;
                text-align: center;
            }
            
            .hero-text {
                padding-right: 0;
                margin-bottom: 50px;
            }
            
            .solution-content {
                grid-template-columns: 1fr;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header id="header">
        <div class="container">
            <nav>
                <div class="logo">
                    <i class="fas fa-seedling"></i>
                    Providentia
                </div>
                <ul class="nav-links">
                    <li><a href="#features">Features</a></li>
                    <li><a href="#solution">How It Works</a></li>
                    <li><a href="#demo">Demo</a></li>
                    <li><a href="#contact" class="btn">Contact Us</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>From Reactive Breakdowns to Proactive Intelligence</h1>
                    <p>Providentia is the AI-powered predictive maintenance platform that prevents agricultural equipment failures before they happen, saving farms thousands in lost crops and emergency repairs.</p>
                    <a href="#contact" class="btn">Get Started Today</a>
                </div>
                <div class="hero-image">
                    <div class="dashboard-preview" style="background: var(--gradient); height: 400px; display: flex; align-items: center; justify-content: center; color: white; font-size: 18px; border: 1px solid rgba(255,255,255,0.2);">
                        <div style="text-align: center;">
                            <i class="fas fa-tachometer-alt" style="font-size: 48px; margin-bottom: 20px;"></i>
                            <h3>Providentia Dashboard</h3>
                            <p>Real-time equipment monitoring</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
        <div class="container">
            <div class="stats-grid">
                <div class="stat-card fade-in">
                    <div class="stat-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <div class="stat-number">99.8%</div>
                    <div class="stat-text">Failure Detection Accuracy</div>
                </div>
                <div class="stat-card fade-in">
                    <div class="stat-icon">
                        <i class="fas fa-dollar-sign"></i>
                    </div>
                    <div class="stat-number">$20K+</div>
                    <div class="stat-text">Saved Per Equipment Failure</div>
                </div>
                <div class="stat-card fade-in">
                    <div class="stat-icon">
                        <i class="fas fa-clock"></i>
                    </div>
                    <div class="stat-number">24/7</div>
                    <div class="stat-text">Equipment Monitoring</div>
                </div>
                <div class="stat-card fade-in">
                    <div class="stat-icon">
                        <i class="fas fa-robot"></i>
                    </div>
                    <div class="stat-number">AI</div>
                    <div class="stat-text">Powered Predictive Analytics</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="features">
        <div class="container">
            <div class="section-title">
                <h2>Comprehensive Agricultural Equipment Protection</h2>
                <p>Every aspect of your farm equipment monitoring, powered by AI that never sleeps</p>
            </div>
            <div class="features-grid">
                <div class="feature-card fade-in">
                    <div class="feature-icon">
                        <i class="fas fa-brain"></i>
                    </div>
                    <h3>Predictive Failure Detection</h3>
                    <p>Our AI identifies equipment issues days or weeks before they cause breakdowns, giving you time to schedule maintenance.</p>
                </div>
                <div class="feature-card fade-in">
                    <div class="feature-icon">
                        <i class="fas fa-calendar-check"></i>
                    </div>
                    <h3>Maintenance Scheduling</h3>
                    <p>Optimize maintenance routines and reduce downtime with intelligent, data-driven scheduling.</p>
                </div>
                <div class="feature-card fade-in">
                    <div class="feature-icon">
                        <i class="fas fa-broadcast-tower"></i>
                    </div>
                    <h3>Equipment Monitoring</h3>
                    <p>Real-time monitoring of pumps, tractors, and irrigation systems with instant alerts sent directly to your phone.</p>
                </div>
                <div class="feature-card fade-in">
                    <div class="feature-icon">
                        <i class="fas fa-chart-bar"></i>
                    </div>
                    <h3>Performance Analytics</h3>
                    <p>Comprehensive insights and KPI tracking across all your agricultural equipment in one dashboard.</p>
                </div>
                <div class="feature-card fade-in">
                    <div class="feature-icon">
                        <i class="fas fa-exclamation-triangle"></i>
                    </div>
                    <h3>Anomaly Detection</h3>
                    <p>Identify unusual patterns in equipment behavior that signal potential failures before they occur.</p>
                </div>
                <div class="feature-card fade-in">
                    <div class="feature-icon">
                        <i class="fas fa-piggy-bank"></i>
                    </div>
                    <h3>Cost Optimization</h3>
                    <p>Reduce emergency repair costs by up to 75% and prevent crop losses from unexpected equipment failures.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Solution Section -->
    <section id="solution" class="solution">
        <div class="container">
            <div class="section-title">
                <h2>How Providentia Works</h2>
                <p>Complex AI, made simple enough for people with dirt on their hands, not engineering degrees</p>
            </div>
            <div class="solution-content">
                <div class="solution-text">
                    <h3>The predictive intelligence infrastructure for agriculture</h3>
                    <p>An always-on partner that watches every machine, learns its behavior, and alerts farmers before breakdowns happen.</p>
                    <p>We built the maintenance expert we always needed after experiencing devastating equipment failures on our own family farm that cost us thousands in lost crops.</p>
                    
                    <div class="solution-features">
                        <div class="solution-feature">
                            <i class="fas fa-mobile-alt"></i>
                            <div>
                                <h4>Lives in your pocket</h4>
                                <p>Mobile-first design that works where you work, with offline capabilities for remote farm areas.</p>
                            </div>
                        </div>
                        <div class="solution-feature">
                            <i class="fas fa-comments"></i>
                            <div>
                                <h4>Speaks your language</h4>
                                <p>Clear, actionable alerts in plain language, not technical jargon. "Pump bearing failing in 7-10 days" not "Anomaly detected at 3.7σ".</p>
                            </div>
                        </div>
                        <div class="solution-feature">
                            <i class="fas fa-eye"></i>
                            <div>
                                <h4>Sees failures before they happen</h4>
                                <p>Proactive maintenance scheduling based on actual equipment condition, not arbitrary time intervals.</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="solution-image">
                    <div class="tech-visual" style="background: linear-gradient(145deg, var(--dark-purple), var(--purple)); height: 400px; display: flex; align-items: center; justify-content: center; color: white; font-size: 18px; border: 1px solid rgba(255,255,255,0.2);">
                        <div style="text-align: center;">
                            <i class="fas fa-network-wired" style="font-size: 48px; margin-bottom: 20px;"></i>
                            <h3>AI Technology Stack</h3>
                            <p>Machine Learning + Rule-Based Systems</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section id="contact" class="cta">
        <div class="container">
            <div class="cta-content">
                <h2>Ready to protect your farm from unexpected breakdowns?</h2>
                <p>Join forward-thinking farms already using Providentia to prevent equipment failures and maximize productivity.</p>
                <a href="https://providentia.pythonanywhere.com/" class="btn" target="_blank">View Live Demo</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Providentia</h3>
                    <p>AI-Powered Predictive Maintenance for Sustainable Agriculture</p>
                    <div class="contact-info">
                        <a href="mailto:meryem.mardouli@outlook.com">meryem.mardouli@outlook.com</a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Product</h3>
                    <ul class="footer-links">
                        <li><a href="#features">Features</a></li>
                        <li><a href="#solution">How It Works</a></li>
                        <li><a href="#demo">Live Demo</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Company</h3>
                    <ul class="footer-links">
                        <li><a href="#about">About Us</a></li>
                        <li><a href="#story">Our Story</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Connect</h3>
                    <ul class="footer-links">
                        <li><a href="https://www.linkedin.com/in/meryem-m-477149244" target="_blank">LinkedIn</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; Copyright 2023 Providentia. All Rights Reserved.</p>
                <ul class="legal-links">
                    <li><a href="#">Terms of Service</a></li>
                    <li><a href="#">Privacy Policy</a></li>
                    <li><a href="#">Cookie Policy</a></li>
                </ul>
            </div>
        </div>
    </footer>

    <script>
        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });
        
        // Fade in animation on scroll
        const fadeElements = document.querySelectorAll('.fade-in');
        
        const fadeInOnScroll = function() {
            fadeElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                
                if (elementTop < window.innerHeight - elementVisible) {
                    element.classList.add('visible');
                }
            });
        };
        
        window.addEventListener('scroll', fadeInOnScroll);
        // Initial check in case elements are already in view
        fadeInOnScroll();
    </script>
</body>
</html>
