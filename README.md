
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Providentia - AI-Powered Predictive Maintenance for Agriculture</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --dark-purple: #2d1b69;
            --purple: #4a2c8d;
            --turquoise: #2dd4bf;
            --light-turquoise: #5eead4;
            --black: #0f0f0f;
            --dark-gray: #1a1a1a;
            --light-gray: #f5f5f5;
            --white: #ffffff;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            color: var(--white);
            background-color: var(--black);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        header {
            background-color: var(--dark-purple);
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }
        
        .logo {
            font-size: 28px;
            font-weight: 700;
            color: var(--turquoise);
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
        }
        
        .nav-links a:hover {
            color: var(--turquoise);
        }
        
        .btn {
            display: inline-block;
            background-color: var(--turquoise);
            color: var(--black);
            padding: 12px 24px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .btn:hover {
            background-color: var(--light-turquoise);
            transform: translateY(-2px);
        }
        
        .hero {
            background: linear-gradient(135deg, var(--dark-purple) 0%, var(--black) 100%);
            padding: 100px 0;
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000" opacity="0.05"><polygon fill="%232dd4bf" points="0,1000 1000,0 1000,1000"/></svg>');
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
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
            color: var(--light-gray);
        }
        
        .hero-image {
            flex: 1;
            text-align: center;
        }
        
        .app-image {
            width: 100%;
            max-width: 500px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        
        section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .section-title h2 {
            font-size: 36px;
            color: var(--turquoise);
            margin-bottom: 15px;
        }
        
        .section-title p {
            color: var(--light-gray);
            max-width: 700px;
            margin: 0 auto;
        }
        
        .features {
            background-color: var(--dark-gray);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background: linear-gradient(145deg, var(--dark-purple), var(--purple));
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            transition: transform 0.3s;
        }
        
        .feature-card:hover {
            transform: translateY(-5px);
        }
        
        .feature-icon {
            background-color: var(--turquoise);
            color: var(--black);
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            font-size: 24px;
        }
        
        .feature-card h3 {
            font-size: 22px;
            margin-bottom: 15px;
            color: var(--white);
        }
        
        .feature-card p {
            color: var(--light-gray);
        }
        
        .solution-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }
        
        .solution-text h3 {
            font-size: 28px;
            margin-bottom: 20px;
            color: var(--turquoise);
        }
        
        .solution-text p {
            margin-bottom: 20px;
            color: var(--light-gray);
        }
        
        .solution-features {
            margin-top: 30px;
        }
        
        .solution-feature {
            display: flex;
            align-items: flex-start;
            margin-bottom: 20px;
        }
        
        .solution-feature i {
            color: var(--turquoise);
            margin-right: 15px;
            font-size: 20px;
            margin-top: 3px;
        }
        
        .cta {
            background: linear-gradient(135deg, var(--purple) 0%, var(--dark-purple) 100%);
            text-align: center;
            padding: 100px 0;
        }
        
        .cta h2 {
            font-size: 36px;
            margin-bottom: 20px;
        }
        
        .cta p {
            font-size: 18px;
            max-width: 700px;
            margin: 0 auto 30px;
            color: var(--light-gray);
        }
        
        footer {
            background-color: var(--black);
            padding: 60px 0 30px;
            border-top: 1px solid var(--dark-gray);
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 18px;
            margin-bottom: 20px;
            color: var(--turquoise);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: var(--light-gray);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: var(--turquoise);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid var(--dark-gray);
            color: var(--light-gray);
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
        }
        
        .legal-links a:hover {
            color: var(--turquoise);
        }
        
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
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 36px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav>
                <div class="logo">Providentia</div>
                <ul class="nav-links">
                    <li><a href="#features">Features</a></li>
                    <li><a href="#solution">How It Works</a></li>
                    <li><a href="#demo">Demo</a></li>
                    <li><a href="#contact" class="btn">Contact Us</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Always-on Predictive Maintenance for Agriculture</h1>
                    <p>From Reactive Breakdowns to Proactive Intelligence. Providentia is the AI-powered predictive maintenance platform that prevents equipment failures before they happen.</p>
                    <a href="#contact" class="btn">Contact Us</a>
                </div>
                <div class="hero-image">
                    <div class="app-image" style="background: linear-gradient(145deg, var(--purple), var(--turquoise)); height: 400px; display: flex; align-items: center; justify-content: center; color: white; font-size: 18px;">
                        Providentia Dashboard Preview
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="features" class="features">
        <div class="container">
            <div class="section-title">
                <h2>Comprehensive Agricultural Equipment Protection</h2>
                <p>Every aspect of your farm equipment monitoring, powered by AI that never sleeps</p>
            </div>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3>Predictive Failure Detection</h3>
                    <p>AI-powered predictions that identify equipment issues before they cause breakdowns</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-tools"></i>
                    </div>
                    <h3>Maintenance Scheduling</h3>
                    <p>Optimize maintenance routines and reduce downtime with intelligent scheduling</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-bolt"></i>
                    </div>
                    <h3>Equipment Monitoring</h3>
                    <p>Real-time monitoring of pumps, tractors, and irrigation systems with instant alerts</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-cogs"></i>
                    </div>
                    <h3>Performance Analytics</h3>
                    <p>Comprehensive insights and KPI tracking across all your agricultural equipment</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-exclamation-triangle"></i>
                    </div>
                    <h3>Anomaly Detection</h3>
                    <p>Identify unusual patterns in equipment behavior that signal potential failures</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-dollar-sign"></i>
                    </div>
                    <h3>Cost Optimization</h3>
                    <p>Reduce emergency repair costs and prevent crop losses from equipment failures</p>
                </div>
            </div>
        </div>
    </section>

    <section id="solution">
        <div class="container">
            <div class="section-title">
                <h2>How Providentia Works</h2>
                <p>Complex AI, made simple enough for people with dirt on their hands, not engineering degrees</p>
            </div>
            <div class="solution-content">
                <div class="solution-text">
                    <h3>The predictive intelligence infrastructure for agriculture</h3>
                    <p>An always-on partner that watches every machine, learns its behavior, and alerts farmers before breakdowns happen.</p>
                    <p>We built the maintenance expert we always needed after experiencing devastating equipment failures on our own family farm.</p>
                    
                    <div class="solution-features">
                        <div class="solution-feature">
                            <i class="fas fa-mobile-alt"></i>
                            <div>
                                <h4>Lives in your pocket</h4>
                                <p>Mobile-first design that works where you work</p>
                            </div>
                        </div>
                        <div class="solution-feature">
                            <i class="fas fa-comments"></i>
                            <div>
                                <h4>Speaks your language</h4>
                                <p>Clear, actionable alerts in plain language, not technical jargon</p>
                            </div>
                        </div>
                        <div class="solution-feature">
                            <i class="fas fa-eye"></i>
                            <div>
                                <h4>Sees failures before they happen</h4>
                                <p>Proactive maintenance scheduling based on actual equipment condition</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="solution-image">
                    <div style="width: 100%; height: 400px; background: linear-gradient(145deg, var(--dark-purple), var(--purple)); border-radius: 10px; display: flex; align-items: center; justify-content: center; color: white; font-size: 18px;">
                        Providentia Technology Visualization
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="cta">
        <div class="container">
            <h2>Ready to protect your farm from unexpected breakdowns?</h2>
            <p>Join forward-thinking farms already using Providentia to prevent equipment failures and maximize productivity.</p>
            <a href="https://providentia.pythonanywhere.com/" class="btn" target="_blank">View Live Demo</a>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Providentia</h3>
                    <p>AI-Powered Predictive Maintenance for Sustainable Agriculture</p>
                    <div style="margin-top: 20px;">
                        <a href="mailto:meryem.mardouli@outlook.com" style="color: var(--turquoise);">meryem.mardouli@outlook.com</a>
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
</body>
</html>
