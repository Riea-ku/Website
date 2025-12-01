
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
            background: var(--dark-purple);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        /* Header - Full Width Band */
        header {
            background-color: var(--dark-purple);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            width: 100%;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .header-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 36px;
            font-weight: 800;
            color: var(--white);
        }
        
        .logo-dot {
            display: inline-block;
            width: 16px;
            height: 16px;
            background: var(--purple);
            border-radius: 50%;
            margin-left: 10px;
            box-shadow: 0 0 15px var(--purple);
        }
        
        .nav-links {
            display: flex;
            list-style: none;
            align-items: center;
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
            color: var(--white);
            padding: 14px 28px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(0, 229, 196, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 229, 196, 0.4);
        }
        
        /* Sections - Full Width */
        section {
            width: 100%;
            padding: 80px 0;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Hero Section */
        .hero {
            background: var(--dark-purple);
            text-align: center;
            padding-top: 140px;
        }
        
        .hero-box {
            background: linear-gradient(145deg, var(--dark-purple), var(--gray));
            border-radius: 15px;
            padding: 60px 40px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero-box h1 {
            font-size: 2.8rem;
            margin-bottom: 20px;
            color: var(--white);
            font-weight: 700;
        }
        
        .hero-box p {
            font-size: 1.25rem;
            margin-bottom: 30px;
            color: var(--light-gray);
        }
        
        /* Features Section - FLOATING POPUP FIX */
        .features {
            background: var(--dark-purple);
            position: relative;
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
        
        .features-section {
            position: relative;
            width: 100%;
            min-height: 400px;
        }
        
        .feature-icons {
            display: flex;
            justify-content: center;
            gap: 40px;
            flex-wrap: wrap;
        }
        
        .feature-icon {
            cursor: pointer;
            transition: opacity 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 140px;
        }
        
        /* Hide other icons */
        .feature-icon.dimmed {
            opacity: 0;
            pointer-events: none;
        }
        
        .feature-icon i {
            font-size: 3rem;
            color: var(--turquoise);
            margin-bottom: 15px;
            background: rgba(0, 229, 196, 0.1);
            width: 100px;
            height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: all 0.3s ease;
        }
        
        .feature-icon.active i {
            transform: scale(1.2);
            background: var(--gradient);
            color: var(--black);
            box-shadow: 0 0 30px rgba(0, 229, 196, 0.6);
        }
        
        .feature-icon h3 {
            font-size: 1.1rem;
            color: var(--white);
            text-align: center;
            font-weight: 600;
        }
        
        /* THE POPUP MUST FLOAT ON TOP */
        .feature-popup {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.95);
            width: 450px;
            padding: 30px;
            background: rgba(26, 16, 61, 0.95);
            border-radius: 16px;
            color: white;
            text-align: left;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease, transform 0.3s ease;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5);
            border: 2px solid var(--turquoise);
            z-index: 100;
        }
        
        /* Visible popup */
        .feature-popup.visible {
            opacity: 1;
            pointer-events: auto;
            transform: translate(-50%, -50%) scale(1);
        }
        
        .popup-header {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            gap: 15px;
        }
        
        .popup-icon {
            font-size: 2rem;
            color: var(--turquoise);
            background: rgba(0, 229, 196, 0.1);
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            flex-shrink: 0;
        }
        
        .popup-header h3 {
            font-size: 1.8rem;
            color: var(--turquoise);
            margin: 0;
        }
        
        .feature-popup p {
            color: var(--light-gray);
            font-size: 1.1rem;
            margin-left: 75px;
        }
        
        /* Solution Section - FLOATING POPUP FIX */
        .solution {
            background: var(--dark-purple);
            position: relative;
        }
        
        .solution-box {
            background: linear-gradient(145deg, var(--dark-purple), var(--gray));
            border-radius: 15px;
            padding: 60px 50px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
            max-width: 900px;
            margin: 0 auto 80px;
            text-align: center;
        }
        
        .solution-box h3 {
            font-size: 2.2rem;
            margin-bottom: 25px;
            color: var(--turquoise);
            font-weight: 700;
        }
        
        .solution-box p {
            color: var(--light-gray);
            font-size: 1.2rem;
            margin-bottom: 20px;
        }
        
        .solution-section {
            position: relative;
            width: 100%;
            min-height: 400px;
        }
        
        .solution-icons {
            display: flex;
            justify-content: center;
            gap: 40px;
            flex-wrap: wrap;
        }
        
        .solution-icon {
            cursor: pointer;
            transition: opacity 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 140px;
        }
        
        /* Hide other icons */
        .solution-icon.dimmed {
            opacity: 0;
            pointer-events: none;
        }
        
        .solution-icon i {
            font-size: 3rem;
            color: var(--turquoise);
            margin-bottom: 15px;
            background: rgba(0, 229, 196, 0.1);
            width: 100px;
            height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: all 0.3s ease;
        }
        
        .solution-icon.active i {
            transform: scale(1.2);
            background: var(--gradient);
            color: var(--black);
            box-shadow: 0 0 30px rgba(0, 229, 196, 0.6);
        }
        
        .solution-icon h3 {
            font-size: 1.1rem;
            color: var(--white);
            text-align: center;
            font-weight: 600;
        }
        
        /* THE POPUP MUST FLOAT ON TOP */
        .solution-popup {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.95);
            width: 450px;
            padding: 30px;
            background: rgba(26, 16, 61, 0.95);
            border-radius: 16px;
            color: white;
            text-align: left;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease, transform 0.3s ease;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5);
            border: 2px solid var(--turquoise);
            z-index: 100;
        }
        
        /* Visible popup */
        .solution-popup.visible {
            opacity: 1;
            pointer-events: auto;
            transform: translate(-50%, -50%) scale(1);
        }
        
        .solution-popup .popup-header {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            gap: 15px;
        }
        
        .solution-popup .popup-icon {
            font-size: 2rem;
            color: var(--turquoise);
            background: rgba(0, 229, 196, 0.1);
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            flex-shrink: 0;
        }
        
        .solution-popup .popup-header h3 {
            font-size: 1.8rem;
            color: var(--turquoise);
            margin: 0;
        }
        
        .solution-popup p {
            color: var(--light-gray);
            font-size: 1.1rem;
            margin-left: 75px;
        }
        
        /* CTA Section */
        .cta {
            background: linear-gradient(135deg, var(--purple) 0%, var(--dark-purple) 100%);
            text-align: center;
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
        
        /* Footer - FIXED ALIGNMENT */
        footer {
            background-color: var(--dark-purple);
            padding: 80px 0 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 50px;
            margin-bottom: 50px;
        }
        
        .footer-column {
            text-align: left;
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
            border-top: 1px solid rgba(255, 255, 255, 0.1);
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
            .hero-box h1 {
                font-size: 2.2rem;
            }
            
            .feature-icons, .solution-icons {
                gap: 30px;
            }
            
            .feature-icon, .solution-icon {
                width: 120px;
            }
            
            .feature-icon i, .solution-icon i {
                width: 80px;
                height: 80px;
                font-size: 2.5rem;
            }
            
            .feature-popup, .solution-popup {
                width: 380px;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero-box h1 {
                font-size: 1.8rem;
            }
            
            .feature-icons, .solution-icons {
                gap: 20px;
            }
            
            .feature-popup, .solution-popup {
                width: 320px;
                padding: 25px;
            }
            
            .popup-header {
                flex-direction: column;
                text-align: center;
                gap: 10px;
            }
            
            .feature-popup p, .solution-popup p {
                margin-left: 0;
                text-align: center;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
                gap: 30px;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header - Full Width Band -->
    <header>
        <div class="header-container">
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
            <div class="hero-box">
                <h1>Predictive Maintenance for Agriculture</h1>
                <p>From Reactive Breakdowns to Proactive Intelligence. Providentia is the AI-powered predictive maintenance platform that prevents equipment failures before they happen.</p>
                <a href="#contact" class="btn">Contact Us</a>
            </div>
        </div>
    </section>

    <!-- Features Section - FLOATING POPUP FIX -->
    <section id="features" class="features">
        <div class="container">
            <div class="section-title">
                <h2>Comprehensive Agricultural Equipment Protection</h2>
                <p>Every aspect of your farm equipment monitoring, powered by AI that never sleeps</p>
            </div>
            
            <div class="features-section">
                <div class="feature-icons">
                    <div class="feature-icon" data-title="Predictive Failure Detection" data-desc="AI-powered predictions that identify equipment issues before they cause breakdowns" data-icon="brain">
                        <i class="fas fa-brain"></i>
                        <h3>Predictive Failure Detection</h3>
                    </div>
                    <div class="feature-icon" data-title="Maintenance Scheduling" data-desc="Optimize maintenance routines and reduce downtime with intelligent scheduling" data-icon="calendar-check">
                        <i class="fas fa-calendar-check"></i>
                        <h3>Maintenance Scheduling</h3>
                    </div>
                    <div class="feature-icon" data-title="Equipment Monitoring" data-desc="Real-time monitoring of pumps, tractors, and irrigation systems with instant alerts" data-icon="broadcast-tower">
                        <i class="fas fa-broadcast-tower"></i>
                        <h3>Equipment Monitoring</h3>
                    </div>
                    <div class="feature-icon" data-title="Performance Analytics" data-desc="Comprehensive insights and KPI tracking across all your agricultural equipment" data-icon="chart-bar">
                        <i class="fas fa-chart-bar"></i>
                        <h3>Performance Analytics</h3>
                    </div>
                    <div class="feature-icon" data-title="Anomaly Detection" data-desc="Identify unusual patterns in equipment behavior that signal potential failures" data-icon="exclamation-triangle">
                        <i class="fas fa-exclamation-triangle"></i>
                        <h3>Anomaly Detection</h3>
                    </div>
                    <div class="feature-icon" data-title="Cost Optimization" data-desc="Reduce emergency repair costs and prevent crop losses from equipment failures" data-icon="piggy-bank">
                        <i class="fas fa-piggy-bank"></i>
                        <h3>Cost Optimization</h3>
                    </div>
                </div>
                
                <!-- POPUP IS OUTSIDE THE ICONS CONTAINER -->
                <div class="feature-popup"></div>
            </div>
        </div>
    </section>

    <!-- Solution Section - FLOATING POPUP FIX -->
    <section id="solution" class="solution">
        <div class="container">
            <div class="solution-box">
                <h3>The predictive intelligence infrastructure for agriculture</h3>
                <p>An always-on partner that watches every machine, learns its behavior, and alerts farmers before breakdowns happen.</p>
                <p>We built the maintenance expert we always needed after experiencing devastating equipment failures on our own family farm.</p>
            </div>
            
            <div class="solution-section">
                <div class="solution-icons">
                    <div class="solution-icon" data-title="Lives in your pocket" data-desc="Mobile-first design that works where you work" data-icon="mobile-alt">
                        <i class="fas fa-mobile-alt"></i>
                        <h3>Lives in your pocket</h3>
                    </div>
                    <div class="solution-icon" data-title="Speaks your language" data-desc="Clear, actionable alerts in plain language, not technical jargon" data-icon="comments">
                        <i class="fas fa-comments"></i>
                        <h3>Speaks your language</h3>
                    </div>
                    <div class="solution-icon" data-title="Sees failures before they happen" data-desc="Proactive maintenance scheduling based on actual equipment condition" data-icon="eye">
                        <i class="fas fa-eye"></i>
                        <h3>Sees failures before they happen</h3>
                    </div>
                </div>
                
                <!-- POPUP IS OUTSIDE THE ICONS CONTAINER -->
                <div class="solution-popup"></div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section id="contact" class="cta">
        <div class="container">
            <div class="cta-content">
                <h2>Ready to protect your business from unexpected breakdowns?</h2>
                <p>Join Use Providentia to prevent equipment failures and maximize productivity.</p>
                <a href="https://providentia.pythonanywhere.com/" class="btn" target="_blank">View Live Demo</a>
            </div>
        </div>
    </section>

    <!-- Footer - FIXED ALIGNMENT -->
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
        // Features Section Interaction - FLOATING POPUP FIX
        const featureIcons = document.querySelectorAll('.feature-icon');
        const featurePopup = document.querySelector('.feature-popup');
        
        featureIcons.forEach(icon => {
            icon.addEventListener('mouseenter', () => {
                // Get content
                const title = icon.dataset.title;
                const desc = icon.dataset.desc;
                const iconClass = icon.dataset.icon;
                
                // Populate popup with icon
                featurePopup.innerHTML = `
                    <div class="popup-header">
                        <div class="popup-icon">
                            <i class="fas fa-${iconClass}"></i>
                        </div>
                        <h3>${title}</h3>
                    </div>
                    <p>${desc}</p>
                `;
                
                // Show popup
                featurePopup.classList.add('visible');
                
                // Add active class to hovered icon
                icon.classList.add('active');
                
                // Hide other icons
                featureIcons.forEach(i => {
                    if (i !== icon) i.classList.add('dimmed');
                });
            });
            
            icon.addEventListener('mouseleave', () => {
                // If mouse leaves icon but enters popup → do nothing
                featurePopup.addEventListener('mouseenter', () => {
                    featurePopup.classList.add('visible');
                });

                featurePopup.addEventListener('mouseleave', () => {
                    featurePopup.classList.remove('visible');
                    featureIcons.forEach(i => i.classList.remove('dimmed'));
                });
            });
        });
        
        // Solution Section Interaction - FLOATING POPUP FIX
        const solutionIcons = document.querySelectorAll('.solution-icon');
        const solutionPopup = document.querySelector('.solution-popup');
        
        solutionIcons.forEach(icon => {
            icon.addEventListener('mouseenter', () => {
                // Get content
                const title = icon.dataset.title;
                const desc = icon.dataset.desc;
                const iconClass = icon.dataset.icon;
                
                // Populate popup with icon
                solutionPopup.innerHTML = `
                    <div class="popup-header">
                        <div class="popup-icon">
                            <i class="fas fa-${iconClass}"></i>
                        </div>
                        <h3>${title}</h3>
                    </div>
                    <p>${desc}</p>
                `;
                
                // Show popup
                solutionPopup.classList.add('visible');
                
                // Add active class to hovered icon
                icon.classList.add('active');
                
                // Hide other icons
                solutionIcons.forEach(i => {
                    if (i !== icon) i.classList.add('dimmed');
                });
            });
            
            icon.addEventListener('mouseleave', () => {
                // If mouse leaves icon but enters popup → do nothing
                solutionPopup.addEventListener('mouseenter', () => {
                    solutionPopup.classList.add('visible');
                });

                solutionPopup.addEventListener('mouseleave', () => {
                    solutionPopup.classList.remove('visible');
                    solutionIcons.forEach(i => i.classList.remove('dimmed'));
                });
            });
        });
    </script>
</body>
</html>
