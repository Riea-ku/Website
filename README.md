
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
            display: flex;
            align-items: center;
            font-size: 32px;
            font-weight: 800;
            color: var(--white);
        }
        
        .logo-dot {
            display: inline-block;
            width: 12px;
            height: 12px;
            background: var(--purple);
            border-radius: 50%;
            margin-left: 8px;
            box-shadow: 0 0 10px var(--purple);
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
            text-align: center;
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
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin: 0 auto;
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
        }
        
        /* Interactive Features Section */
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
        
        .features-interactive {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-top: 60px;
            position: relative;
            height: 300px;
        }
        
        .feature-icons {
            display: flex;
            justify-content: center;
            gap: 40px;
            transition: all 0.5s ease;
        }
        
        .feature-icon {
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100px;
        }
        
        .feature-icon i {
            font-size: 2.5rem;
            color: var(--turquoise);
            margin-bottom: 15px;
            transition: all 0.3s ease;
            background: rgba(0, 229, 196, 0.1);
            width: 80px;
            height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .feature-icon.active i {
            transform: scale(1.2);
            background: var(--gradient);
            color: var(--black);
            box-shadow: 0 0 20px rgba(0, 229, 196, 0.5);
        }
        
        .feature-icon h3 {
            font-size: 1rem;
            color: var(--white);
            text-align: center;
            transition: all 0.3s ease;
        }
        
        .feature-content {
            position: absolute;
            top: 120px;
            left: 0;
            right: 0;
            text-align: center;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
            max-width: 600px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .feature-content.active {
            opacity: 1;
            transform: translateY(0);
        }
        
        .feature-content h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: var(--turquoise);
        }
        
        .feature-content p {
            color: var(--light-gray);
            font-size: 1.1rem;
        }
        
        /* Solution Section */
        .solution {
            padding: 100px 0;
            background-color: var(--dark-gray);
        }
        
        .solution-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }
        
        .solution-box {
            background: linear-gradient(145deg, var(--dark-purple), var(--gray));
            border-radius: 15px;
            padding: 50px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
            margin-bottom: 60px;
        }
        
        .solution-box h3 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--turquoise);
            font-weight: 700;
        }
        
        .solution-box p {
            color: var(--light-gray);
            font-size: 1.1rem;
            margin-bottom: 15px;
        }
        
        .solution-interactive {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-top: 60px;
            position: relative;
            height: 300px;
        }
        
        .solution-icons {
            display: flex;
            justify-content: center;
            gap: 40px;
            transition: all 0.5s ease;
        }
        
        .solution-icon {
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100px;
        }
        
        .solution-icon i {
            font-size: 2.5rem;
            color: var(--turquoise);
            margin-bottom: 15px;
            transition: all 0.3s ease;
            background: rgba(0, 229, 196, 0.1);
            width: 80px;
            height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .solution-icon.active i {
            transform: scale(1.2);
            background: var(--gradient);
            color: var(--black);
            box-shadow: 0 0 20px rgba(0, 229, 196, 0.5);
        }
        
        .solution-icon h3 {
            font-size: 1rem;
            color: var(--white);
            text-align: center;
            transition: all 0.3s ease;
        }
        
        .solution-content-text {
            position: absolute;
            top: 120px;
            left: 0;
            right: 0;
            text-align: center;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
            max-width: 600px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .solution-content-text.active {
            opacity: 1;
            transform: translateY(0);
        }
        
        .solution-content-text h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: var(--turquoise);
        }
        
        .solution-content-text p {
            color: var(--light-gray);
            font-size: 1.1rem;
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
        
        /* Responsive */
        @media (max-width: 968px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .feature-icons, .solution-icons {
                gap: 20px;
            }
            
            .feature-icon, .solution-icon {
                width: 80px;
            }
            
            .feature-icon i, .solution-icon i {
                width: 60px;
                height: 60px;
                font-size: 2rem;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .feature-icons, .solution-icons {
                flex-wrap: wrap;
                gap: 15px;
            }
            
            .features-interactive, .solution-interactive {
                height: 400px;
            }
            
            .feature-content, .solution-content-text {
                top: 150px;
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
                    Providentia<span class="logo-dot"></span>
                </div>
                <ul class="nav-links">
                    <li><a href="#features">Features</a></li>
                    <li><a href="#solution">How It Works</a></li>
                    <li><a href="#contact" class="btn">Contact Us</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Predictive Maintenance for Agriculture</h1>
                <p>From Reactive Breakdowns to Proactive Intelligence. Providentia is the AI-powered predictive maintenance platform that prevents equipment failures before they happen.</p>
                <a href="#contact" class="btn">Contact Us</a>
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
            
            <div class="features-interactive">
                <div class="feature-icons">
                    <div class="feature-icon active" data-index="0">
                        <i class="fas fa-brain"></i>
                        <h3>Predictive Failure Detection</h3>
                    </div>
                    <div class="feature-icon" data-index="1">
                        <i class="fas fa-calendar-check"></i>
                        <h3>Maintenance Scheduling</h3>
                    </div>
                    <div class="feature-icon" data-index="2">
                        <i class="fas fa-broadcast-tower"></i>
                        <h3>Equipment Monitoring</h3>
                    </div>
                    <div class="feature-icon" data-index="3">
                        <i class="fas fa-chart-bar"></i>
                        <h3>Performance Analytics</h3>
                    </div>
                    <div class="feature-icon" data-index="4">
                        <i class="fas fa-exclamation-triangle"></i>
                        <h3>Anomaly Detection</h3>
                    </div>
                    <div class="feature-icon" data-index="5">
                        <i class="fas fa-piggy-bank"></i>
                        <h3>Cost Optimization</h3>
                    </div>
                </div>
                
                <div class="feature-content active" data-index="0">
                    <h3>Predictive Failure Detection</h3>
                    <p>AI-powered predictions that identify equipment issues before they cause breakdowns</p>
                </div>
                <div class="feature-content" data-index="1">
                    <h3>Maintenance Scheduling</h3>
                    <p>Optimize maintenance routines and reduce downtime with intelligent scheduling</p>
                </div>
                <div class="feature-content" data-index="2">
                    <h3>Equipment Monitoring</h3>
                    <p>Real-time monitoring of pumps, tractors, and irrigation systems with instant alerts</p>
                </div>
                <div class="feature-content" data-index="3">
                    <h3>Performance Analytics</h3>
                    <p>Comprehensive insights and KPI tracking across all your agricultural equipment</p>
                </div>
                <div class="feature-content" data-index="4">
                    <h3>Anomaly Detection</h3>
                    <p>Identify unusual patterns in equipment behavior that signal potential failures</p>
                </div>
                <div class="feature-content" data-index="5">
                    <h3>Cost Optimization</h3>
                    <p>Reduce emergency repair costs and prevent crop losses from equipment failures</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Solution Section -->
    <section id="solution" class="solution">
        <div class="container">
            <div class="solution-content">
                <div class="solution-box">
                    <h3>The predictive intelligence infrastructure for agriculture</h3>
                    <p>An always-on partner that watches every machine, learns its behavior, and alerts farmers before breakdowns happen.</p>
                    <p>We built the maintenance expert we always needed after experiencing devastating equipment failures on our own family farm.</p>
                </div>
                
                <div class="solution-interactive">
                    <div class="solution-icons">
                        <div class="solution-icon active" data-index="0">
                            <i class="fas fa-mobile-alt"></i>
                            <h3>Lives in your pocket</h3>
                        </div>
                        <div class="solution-icon" data-index="1">
                            <i class="fas fa-comments"></i>
                            <h3>Speaks your language</h3>
                        </div>
                        <div class="solution-icon" data-index="2">
                            <i class="fas fa-eye"></i>
                            <h3>Sees failures before they happen</h3>
                        </div>
                    </div>
                    
                    <div class="solution-content-text active" data-index="0">
                        <h3>Lives in your pocket</h3>
                        <p>Mobile-first design that works where you work</p>
                    </div>
                    <div class="solution-content-text" data-index="1">
                        <h3>Speaks your language</h3>
                        <p>Clear, actionable alerts in plain language, not technical jargon</p>
                    </div>
                    <div class="solution-content-text" data-index="2">
                        <h3>Sees failures before they happen</h3>
                        <p>Proactive maintenance scheduling based on actual equipment condition</p>
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
        
        // Interactive Features
        const featureIcons = document.querySelectorAll('.feature-icon');
        const featureContents = document.querySelectorAll('.feature-content');
        
        featureIcons.forEach(icon => {
            icon.addEventListener('mouseenter', function() {
                const index = this.getAttribute('data-index');
                
                // Remove active class from all icons and contents
                featureIcons.forEach(i => i.classList.remove('active'));
                featureContents.forEach(c => c.classList.remove('active'));
                
                // Add active class to current icon and content
                this.classList.add('active');
                document.querySelector(`.feature-content[data-index="${index}"]`).classList.add('active');
            });
        });
        
        // Interactive Solution
        const solutionIcons = document.querySelectorAll('.solution-icon');
        const solutionContents = document.querySelectorAll('.solution-content-text');
        
        solutionIcons.forEach(icon => {
            icon.addEventListener('mouseenter', function() {
                const index = this.getAttribute('data-index');
                
                // Remove active class from all icons and contents
                solutionIcons.forEach(i => i.classList.remove('active'));
                solutionContents.forEach(c => c.classList.remove('active'));
                
                // Add active class to current icon and content
                this.classList.add('active');
                document.querySelector(`.solution-content-text[data-index="${index}"]`).classList.add('active');
            });
        });
    </script>
</body>
</html>
