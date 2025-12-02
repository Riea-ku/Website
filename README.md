<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Providentia — Predictive Maintenance for Agriculture</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Montserrat:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
/* Embedded website.css - Providentia */
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
/* Scroll Progress Indicator */
.scroll-progress {
    position: fixed;
    top: 0;
    left: 0;
    width: 0%;
    height: 4px;
    background: var(--gradient);
    z-index: 1001;
    transition: width 0.1s ease;
}
/* Header - Full Width Band */
header {
    background-color: rgba(26, 16, 61, 0.95);
    backdrop-filter: blur(10px);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    z-index: 1000;
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    transition: all 0.3s ease;
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
    font-family: 'Montserrat', sans-serif;
    font-size: 32px;
    font-weight: 700;
    color: var(--white);
    letter-spacing: -0.5px;
    text-decoration: none;
}
.logo-dot {
    display: inline-block;
    width: 14px;
    height: 14px;
    background: var(--turquoise);
    border-radius: 50%;
    margin-left: 10px;
    box-shadow: 0 0 12px var(--turquoise);
    animation: pulse 2s infinite;
}
@keyframes pulse {
    0% { box-shadow: 0 0 12px var(--turquoise); }
    50% { box-shadow: 0 0 22px var(--turquoise); }
    100% { box-shadow: 0 0 12px var(--turquoise); }
}
.nav-links {
    display: flex;
    list-style: none;
    align-items: center;
    gap: 30px;
}
.nav-links a {
    text-decoration: none;
    color: var(--white);
    font-weight: 500;
    font-size: 1rem;
    transition: color 0.25s;
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
    transition: width 0.25s ease;
}
.nav-links a:hover:after { width: 100%; }
.nav-links a:hover { color: var(--turquoise); }
.btn {
    display: inline-block;
    background: var(--gradient);
    color: var(--black);
    padding: 12px 26px;
    border-radius: 50px;
    text-decoration: none;
    font-weight: 600;
    transition: transform 0.18s, box-shadow 0.18s;
    box-shadow: 0 6px 18px rgba(0, 229, 196, 0.18);
    border: none;
    cursor: pointer;
}
.btn:hover { transform: translateY(-3px); box-shadow: 0 12px 30px rgba(0,229,196,0.22); }
.mobile-menu-btn { display: none; background: none; border: none; color: var(--white); font-size: 1.4rem; cursor: pointer; z-index: 1002; }
/* Sections */
section { width: 100%; padding: 100px 0; opacity: 0; transform: translateY(18px); transition: opacity 0.6s ease, transform 0.6s ease; }
section.revealed { opacity: 1; transform: translateY(0); }
.container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
/* Hero */
.hero { background: var(--dark-purple); text-align: center; padding-top: 160px; }
.hero-box { background: linear-gradient(145deg, rgba(26,16,61,0.82), rgba(42,42,42,0.82)); border-radius: 18px; padding: 64px 36px; box-shadow: 0 18px 36px rgba(0,0,0,0.34); border: 1px solid rgba(255,255,255,0.06); max-width: 1000px; margin: 0 auto; backdrop-filter: blur(8px); }
.typewriter-container { margin-bottom: 22px; min-height: 84px; }
.typewriter-title { font-family: 'Montserrat', sans-serif; font-size: 2.6rem; font-weight: 700; color: var(--white); line-height: 1.12; overflow: hidden; white-space: nowrap; margin: 0 auto; border-right: 3px solid var(--turquoise); display: inline-block; }
.typing { animation: typing 3.5s steps(40,end) forwards, blink-caret .75s step-end infinite; }
@keyframes typing { from { width: 0 } to { width: 100% } }
@keyframes blink-caret { from, to { border-color: transparent } 50% { border-color: var(--turquoise); } }
.hero-box p { font-size: 1.12rem; margin-bottom: 24px; color: var(--light-gray); font-weight: 300; max-width: 760px; margin-left: auto; margin-right: auto; }
.hero-image { margin-top: 14px; border-radius: 12px; overflow: hidden; box-shadow: 0 18px 40px rgba(0,0,0,0.5); }
.hero-image img { width: 100%; height: auto; display: block; max-height: 360px; object-fit: cover; }
/* Features */
.features { background: var(--dark-purple); position: relative; }
.section-title { text-align: center; margin-bottom: 56px; }
.section-title h2 { font-family: 'Montserrat', sans-serif; font-size: 2.4rem; color: var(--white); margin-bottom: 12px; font-weight: 700; display: inline-block; position: relative; }
.section-title h2:after { content: ''; position: absolute; width: 56px; height: 4px; background: var(--gradient); bottom: -10px; left: 50%; transform: translateX(-50%); border-radius: 2px; }
.section-title p { color: var(--light-gray); max-width: 720px; margin: 18px auto 0; font-size: 1.05rem; font-weight: 300; }
.features-section { position: relative; width: 100%; }
.feature-icons { display:flex; justify-content:center; gap:30px; flex-wrap:wrap; }
.feature-icon { cursor:pointer; transition:all .22s ease; display:flex; flex-direction:column; align-items:center; width:150px; }
.feature-icon i { font-size:2.6rem; color:var(--turquoise); margin-bottom:14px; background: rgba(0,229,196,0.08); width:96px; height:96px; display:flex; align-items:center; justify-content:center; border-radius:50%; transition:all .22s ease; }
.feature-icon.active i { transform:scale(1.14); background:var(--gradient); color:var(--black); box-shadow:0 0 22px rgba(0,229,196,0.38); }
.feature-icon h3 { font-size:1.05rem; color:var(--white); font-weight:600; text-align:center; }
.feature-icon.dimmed { opacity:.28; transform:scale(.96); pointer-events:none; }
.feature-popup { position:absolute; top:50%; left:50%; transform:translate(-50%,-50%) scale(.98); width:480px; padding:28px; background:rgba(26,16,61,0.96); backdrop-filter:blur(8px); border-radius:14px; color:white; text-align:left; opacity:0; pointer-events:none; transition:opacity .22s ease, transform .22s ease; box-shadow:0 28px 56px rgba(0,0,0,0.56); border:2px solid var(--turquoise); z-index:100; }
.feature-popup.visible { opacity:1; pointer-events:auto; transform:translate(-50%,-50%) scale(1); }
.popup-header { display:flex; align-items:center; gap:16px; margin-bottom:12px; }
.popup-icon { font-size:1.8rem; color:var(--turquoise); background:rgba(0,229,196,0.08); width:62px; height:62px; display:flex; align-items:center; justify-content:center; border-radius:50%; }
.popup-header h3 { font-family:'Montserrat',sans-serif; font-size:1.4rem; color:var(--turquoise); margin:0; font-weight:600; }
.feature-popup p { color:var(--light-gray); font-size:1rem; margin-left:84px; font-weight:300; line-height:1.6; }
/* Solution */
.solution { background: var(--dark-purple); position: relative; }
.solution-box { background: linear-gradient(145deg, rgba(26,16,61,0.82), rgba(42,42,42,0.82)); border-radius:16px; padding:60px 36px; box-shadow:0 18px 36px rgba(0,0,0,0.34); border:1px solid rgba(255,255,255,0.06); max-width:980px; margin:0 auto 80px; text-align:center; }
.solution-box h3 { font-family:'Montserrat',sans-serif; font-size:1.9rem; margin-bottom:18px; color:var(--turquoise); font-weight:700; }
.solution-box p { color:var(--light-gray); font-size:1.05rem; margin-bottom:12px; font-weight:300; max-width:820px; margin-left:auto; margin-right:auto; }
.solution-icons { display:flex; justify-content:center; gap:46px; flex-wrap:wrap; }
.solution-icon { width:160px; display:flex; flex-direction:column; align-items:center; cursor:pointer; }
.solution-icon i { font-size:2.8rem; color:var(--turquoise); margin-bottom:14px; background:rgba(0,229,196,0.08); width:100px; height:100px; display:flex; align-items:center; justify-content:center; border-radius:50%; }
.solution-icon.active i { transform:scale(1.12); background:var(--gradient); color:var(--black); box-shadow:0 0 22px rgba(0,229,196,0.38); }
.solution-popup { position:absolute; top:50%; left:50%; transform:translate(-50%,-50%) scale(.98); width:480px; padding:28px; background:rgba(26,16,61,0.96); backdrop-filter:blur(8px); border-radius:14px; color:white; text-align:left; opacity:0; pointer-events:none; transition:opacity .22s ease, transform .22s ease; box-shadow:0 28px 56px rgba(0,0,0,0.56); border:2px solid var(--turquoise); z-index:100; }
.solution-popup.visible { opacity:1; pointer-events:auto; transform:translate(-50%,-50%) scale(1); }
/* Demo grid */
.demo-grid { display:grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap:18px; margin-top:28px; }
.demo-card { background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border-radius:12px; overflow:hidden; border:1px solid rgba(255,255,255,0.04); }
.demo-card img { width:100%; display:block; height:160px; object-fit:cover; }
.demo-card .card-body { padding:12px 14px; color:var(--light-gray); font-size:0.98rem; }
/* Pricing */
.pricing { background: linear-gradient(180deg, rgba(26,16,61,0.95), rgba(19,10,48,0.95)); padding:72px 0; }
.pricing .section-title { margin-bottom: 18px; }
.pricing-grid { display:grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap:20px; max-width:1100px; margin:28px auto 0; }
.plan-card { background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border-radius:12px; padding:20px; border:1px solid rgba(255,255,255,0.04); text-align:center; box-shadow:0 12px 30px rgba(0,0,0,0.45); }
.plan-badge { display:inline-block; padding:6px 12px; background:rgba(0,229,196,0.08); color:var(--turquoise); border-radius:999px; font-weight:600; font-size:0.85rem; margin-bottom:12px; }
.plan-price { font-size:2rem; font-weight:800; color:var(--white); margin:8px 0; }
.plan-period { color:var(--light-gray); font-size:0.95rem; margin-bottom:12px; }
.plan-features { text-align:left; margin:12px 0 16px; color:var(--light-gray); font-size:0.95rem; }
.plan-features li { margin-bottom:8px; }
.plan-cta { margin-top:12px; }
.plan-popular { border: 2px solid rgba(0,229,196,0.14); box-shadow: 0 20px 40px rgba(0,229,196,0.06); transform: translateY(-6px); }
/* Trust section */
.trust { background: transparent; padding:64px 0; }
.trust-inner { max-width:1100px; margin:0 auto; display:grid; grid-template-columns: 1fr 420px; gap:28px; align-items:start; }
.trust-card { background: linear-gradient(180deg, rgba(26,16,61,0.9), rgba(19,10,48,0.9)); border-radius:12px; padding:22px; border:1px solid rgba(255,255,255,0.04); }
.trust h3 { color:var(--turquoise); margin-bottom:10px; font-size:1.4rem; }
.trust p { color:var(--light-gray); margin-bottom:12px; }
.trust-cta { margin-top:14px; }
/* CTA */
.cta { background: linear-gradient(135deg, rgba(58,28,140,0.9) 0%, rgba(26,16,61,0.9) 100%); text-align:center; padding:80px 0; }
.cta h2 { font-family:'Montserrat',sans-serif; font-size:2.2rem; margin-bottom:14px; font-weight:700; }
.cta p { font-size:1.02rem; max-width:760px; margin:0 auto 30px; color:var(--light-gray); font-weight:300; }
/* Footer */
footer { background-color: var(--dark-purple); padding: 80px 0 36px; border-top:1px solid rgba(255,255,255,0.06); }
.footer-content { display:grid; grid-template-columns: repeat(auto-fit, minmax(220px,1fr)); gap:40px; margin-bottom:40px; }
.footer-column h3 { font-family:'Montserrat',sans-serif; font-size:1.1rem; margin-bottom:14px; color:var(--turquoise); font-weight:600; }
.footer-column p, .footer-links a { color:var(--light-gray); font-weight:300; text-decoration:none; }
.copyright { text-align:center; padding-top:20px; border-top:1px solid rgba(255,255,255,0.06); color:var(--light-gray); font-size:0.92rem; }
/* Responsive */
@media (max-width: 1024px) {
    .typewriter-title { font-size:2rem; }
    .hero-box { padding:40px 28px; }
}
@media (max-width: 768px) {
    .nav-links { display:none; }
    .mobile-menu-btn { display:block; }
    .mobile-menu { position:fixed; top:0; left:0; right:0; bottom:0; background:rgba(26,16,61,0.98); backdrop-filter:blur(10px); display:flex; flex-direction:column; justify-content:center; align-items:center; gap:20px; transform:translateX(-100%); opacity:0; transition:all .22s ease; z-index:1001; padding:20px; }
    .mobile-menu.active { transform:translateX(0); opacity:1; }
    .mobile-menu a { color:var(--white); text-decoration:none; font-size:1.4rem; padding:10px 0; width:100%; text-align:center; border-bottom:1px solid rgba(255,255,255,0.06); }
    .typewriter-title { font-size:1.6rem; white-space:normal; border-right:none; animation:none; width:100%; }
    .feature-popup, .solution-popup { width:90%; padding:18px; }
    .feature-popup p, .solution-popup p { margin-left:0; text-align:center; }
    .footer-content { grid-template-columns:1fr; text-align:center; }
}
/* Modal / Opt-in */
.modal { position: fixed; inset: 0; display: none; align-items: center; justify-content: center; z-index: 1100; }
.modal.open { display: flex; }
.modal-overlay { position: absolute; inset: 0; background: rgba(4,6,16,0.6); backdrop-filter: blur(4px); }
.modal-panel { position: relative; z-index: 1101; width: 98%; max-width: 720px; background: linear-gradient(180deg, rgba(26,16,61,0.98), rgba(19,10,48,0.98)); border-radius: 12px; padding: 22px; border: 1px solid rgba(255,255,255,0.06); box-shadow: 0 30px 60px rgba(0,0,0,0.6); }
.modal-panel h3 { margin-top: 0; color: var(--turquoise); font-size: 1.3rem; }
.modal-panel p { color: var(--light-gray); margin-bottom: 12px; }
.modal-panel fieldset { border: 1px dashed rgba(255,255,255,0.04); padding: 12px; border-radius:8px; margin-bottom:12px; }
.modal-panel label { display: block; color: var(--light-gray); margin-bottom:8px; font-size:0.95rem; }
.modal-panel .modal-accept { margin-top:8px; display:flex; align-items:center; gap:10px; }
.modal-panel .modal-actions { display:flex; gap:10px; margin-top:12px; }
.modal-close { position:absolute; right:12px; top:10px; background:transparent; border:none; color:var(--light-gray); font-size:1.6rem; cursor:pointer; }
/* Responsive tweak for trust layout */
@media (max-width: 1024px) {
    .typewriter-title { font-size:2rem; }
    .hero-box { padding:40px 28px; }
    .trust-inner { grid-template-columns: 1fr; }
}
/* small utilities */
.muted { color: var(--light-gray); }
.caps { text-transform:uppercase; letter-spacing:1px; font-size:0.85rem; }
    </style>
</head>
<body>
    <div class="scroll-progress"></div>

    <header>
        <div class="header-container">
            <nav>
                <a href="#hero" class="logo">Providentia<span class="logo-dot"></span></a>
                <ul class="nav-links">
                    <li><a href="#features">Features</a></li>
                    <li><a href="#solution">How It Works</a></li>
                    <li><a href="#pricing">Pricing</a></li>
                    <li><a href="#trust">Trust &amp; Data</a></li>
                    <li><a href="#contact" class="btn">Contact Us</a></li>
                </ul>
                <button class="mobile-menu-btn"><i class="fas fa-bars"></i></button>
            </nav>
        </div>
    </header>

    <div class="mobile-menu">
        <a href="#features">Features</a>
        <a href="#solution">How It Works</a>
        <a href="#pricing">Pricing</a>
        <a href="#trust">Trust &amp; Data</a>
        <a href="#contact" class="btn">Contact Us</a>
    </div>

    <!-- Pricing Section -->
    <section id="pricing" class="pricing">
        <div class="container">
            <div class="section-title">
                <h2>Pricing</h2>
                <p>Simple, transparent plans that protect your farm — start small and scale as you grow.</p>
            </div>

            <div class="pricing-grid">
                <div class="plan-card">
                    <div class="plan-badge">Basic</div>
                    <div class="plan-price">$29</div>
                    <div class="plan-period">per month • 1 equipment type</div>
                    <ul class="plan-features">
                        <li>Essential failure detection & alerts</li>
                        <li>Basic maintenance scheduling</li>
                        <li>Email support</li>
                    </ul>
                    <div class="plan-cta"><a class="btn" href="#contact">Get Basic</a></div>
                </div>

                <div class="plan-card plan-popular">
                    <div class="plan-badge">Professional</div>
                    <div class="plan-price">$79</div>
                    <div class="plan-period">per month • All equipment types</div>
                    <ul class="plan-features">
                        <li>Full AI co-pilot with predictive analytics</li>
                        <li>Advanced diagnostics & priority alerts</li>
                        <li>SMS + email support</li>
                    </ul>
                    <div class="plan-cta"><a class="btn" href="#contact">Get Professional</a></div>
                </div>

                <div class="plan-card">
                    <div class="plan-badge">Enterprise</div>
                    <div class="plan-price">$199</div>
                    <div class="plan-period">per month • Farm-wide</div>
                    <ul class="plan-features">
                        <li>Farm-wide operational intelligence</li>
                        <li>Dedicated support team</li>
                        <li>Custom alerts & SLA</li>
                    </ul>
                    <div class="plan-cta"><a class="btn" href="#contact">Contact Sales</a></div>
                </div>
            </div>
        </div>
    </section>

    <!-- Trust & Token Network Section -->
    <section id="trust" class="trust">
        <div class="trust-inner">
            <div class="trust-card">
                <h3>Trust-First Data Partnership</h3>
                <p>Providentia is built on the principle that farmers control their data. We start by offering protection with zero data-sharing requirements.</p>
                <p>Over time, farmers may opt in to anonymized data sharing that powers community intelligence. Participation is entirely voluntary and transparent.</p>
                <p>Participating farms receive token rewards for anonymized contributions, access to community dashboards, and improved local models — a true neighborhood network of trust.</p>
                <div class="trust-cta"><button class="btn" id="open-optin">Learn More / Opt-In</button></div>
            </div>

            <aside class="trust-card">
                <h3>How it works</h3>
                <ul class="plan-features">
                    <li>Opt-in anonymized telemetry only</li>
                    <li>Tokens issued for approved contributions</li>
                    <li>Local-model improvements & neighborhood alerts</li>
                    <li>Full transparency: what is shared and how it's used</li>
                </ul>
                <p class="muted">We never sell raw farm data. Manufacturers or insurers access aggregated insights only when farmers opt in.</p>
            </aside>
        </div>
    </section>

    <section id="hero" class="hero">
        <div class="container">
            <div class="hero-box">
                <div class="typewriter-container">
                    <h1 class="typewriter-title" id="typewriter-text">Predictive Maintenance for Agriculture</h1>
                </div>
                <p>From reactive breakdowns to proactive intelligence — Providentia prevents equipment failures and protects harvests.</p>
                <a href="#contact" class="btn">Contact Us</a>

                <div class="hero-image">
                    <img src="https://images.unsplash.com/photo-1501004318641-b39e6451bec6?q=80&w=1600&auto=format&fit=crop" alt="farm irrigation and solar pump"/>
                </div>
            </div>
        </div>
    </section>

    <section id="features" class="features">
        <div class="container">
            <div class="section-title">
                <h2>Comprehensive Agricultural Equipment Protection</h2>
                <p>Every aspect of your farm equipment monitoring, powered by AI that never sleeps.</p>
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
                    <div class="feature-icon" data-title="Performance Analytics" data-desc="Comprehensive insights and KPI tracking across all your agricultural equipment" data-icon="chart-line">
                        <i class="fas fa-chart-line"></i>
                        <h3>Performance Analytics</h3>
                    </div>
                    <div class="feature-icon" data-title="Anomaly Detection" data-desc="Identify unusual patterns in equipment behavior that signal potential failures" data-icon="triangle-exclamation">
                        <i class="fas fa-triangle-exclamation"></i>
                        <h3>Anomaly Detection</h3>
                    </div>
                    <div class="feature-icon" data-title="Cost Optimization" data-desc="Reduce emergency repair costs and prevent crop losses from equipment failures" data-icon="piggy-bank">
                        <i class="fas fa-piggy-bank"></i>
                        <h3>Cost Optimization</h3>
                    </div>
                </div>

                <div class="feature-popup"></div>
            </div>
        </div>
    </section>

    <section id="solution" class="solution">
        <div class="container">
            <div class="solution-box">
                <h3>The predictive intelligence infrastructure for agriculture</h3>
                <p>An always-on partner that watches every machine, learns its behavior, and alerts farmers before breakdowns happen.</p>
                <p>Complex AI, made simple enough for people with dirt on their hands.</p>
            </div>

            <div class="solution-section">
                <div class="solution-icons">
                    <div class="solution-icon" data-title="Lives in your pocket" data-desc="Mobile-first design that works where you work" data-icon="mobile-alt">
                        <i class="fas fa-mobile-alt"></i>
                        <h3>Lives in your pocket</h3>
                    </div>
                    <div class="solution-icon" data-title="Speaks your language" data-desc="Clear, actionable alerts in plain language" data-icon="comments">
                        <i class="fas fa-comments"></i>
                        <h3>Speaks your language</h3>
                    </div>
                    <div class="solution-icon" data-title="Sees failures before they happen" data-desc="Proactive maintenance scheduling based on actual equipment condition" data-icon="eye">
                        <i class="fas fa-eye"></i>
                        <h3>Sees failures before they happen</h3>
                    </div>
                </div>

                <div class="solution-popup"></div>
            </div>

            <div class="container">
                <div class="section-title" style="margin-top:36px;">
                    <h2>Proof & Demo</h2>
                    <p>Simulated validation, real results — explore a few examples from our simulation and demo app.</p>
                </div>

                <div class="demo-grid">
                    <div class="demo-card">
                        <img src="https://images.unsplash.com/photo-1504881549-3441d6e07b57?q=80&w=1200&auto=format&fit=crop" alt="pump sensor"/>
                        <div class="card-body">Simulation: early bearing-wear signature detected 10 days before failure.</div>
                    </div>
                    <div class="demo-card">
                        <img src="https://images.unsplash.com/photo-1517976487492-0b0a56f0a7f6?q=80&w=1200&auto=format&fit=crop" alt="tractor in field"/>
                        <div class="card-body">Field-style dashboard with prioritized maintenance actions.</div>
                    </div>
                    <div class="demo-card">
                        <img src="https://images.unsplash.com/photo-1518823886215-2b25f6c7f3e2?q=80&w=1200&auto=format&fit=crop" alt="iot sensors"/>
                        <div class="card-body">Sensor integration pipeline: live telemetry to predictive engine.</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="cta">
        <div class="container">
            <div class="cta-content">
                <h2>Ready to protect your business from unexpected breakdowns?</h2>
                <p>See a live demo or schedule a walkthrough with Meryem, our founder and predictive systems expert.</p>
                <a href="https://providentia.pythonanywhere.com/" class="btn" target="_blank">View Live Demo</a>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Providentia</h3>
                    <p>AI-Powered Predictive Maintenance for Sustainable Agriculture</p>
                    <div class="contact-info"><a href="mailto:meryem.mardouli@outlook.com">meryem.mardouli@outlook.com</a></div>
                </div>
                <div class="footer-column">
                    <h3>Product</h3>
                    <ul class="footer-links">
                        <li><a href="#features">Features</a></li>
                        <li><a href="#solution">How It Works</a></li>
                        <li><a href="https://providentia.pythonanywhere.com/" target="_blank">Live Demo</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Company</h3>
                    <ul class="footer-links">
                        <li><a href="#solution">Our Story</a></li>
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
                <p>&copy; 2025 Providentia. All Rights Reserved.</p>
                <ul class="legal-links">
                    <li><a href="#">Terms</a></li>
                    <li><a href="#">Privacy</a></li>
                </ul>
            </div>
        </div>
    </footer>

    <!-- Opt-in Modal -->
    <div class="modal" id="optin-modal" aria-hidden="true" role="dialog" aria-modal="true">
        <div class="modal-overlay" data-close></div>
        <div class="modal-panel" role="document" aria-labelledby="optin-title">
            <button class="modal-close" aria-label="Close modal">&times;</button>
            <h3 id="optin-title">Privacy & Opt-in</h3>
            <p>Providentia prioritizes your control. Opting in shares only anonymized, aggregated telemetry that helps improve local models and community alerts. Participation is voluntary and transparent.</p>
            <fieldset>
                <label><input type="checkbox" id="telemetry-optin"> Share anonymized telemetry (no raw data)</label>
                <small class="muted">Only aggregated metrics are used for model improvements. No raw farm data is sold.</small>
            </fieldset>
            <fieldset>
                <label><input type="checkbox" id="consent-terms"> I consent to the opt-in terms and token reward program</label>
            </fieldset>
            <div class="modal-actions">
                <button class="btn" id="confirm-optin">Confirm Opt-in</button>
                <button class="btn" id="decline-optin" style="background:transparent;color:var(--white);border:1px solid rgba(255,255,255,0.06)">Not Now</button>
            </div>
            <div id="optin-success" style="display:none;margin-top:12px;color:var(--turquoise)">Thanks — you're enrolled! Token details and dashboard access will follow by email.</div>
        </div>
    </div>

    <script>
        // Keep original JS interactions — typewriter, popups, mobile menu, scroll
        let isTypingStarted = false;

        function startTypewriter() {
            if (isTypingStarted) return;
            const typewriterText = document.getElementById('typewriter-text');
            if (!typewriterText) return;
            typewriterText.classList.add('typing');
            isTypingStarted = true;
        }

        function revealOnScroll() {
            const sections = document.querySelectorAll('section');
            sections.forEach(section => {
                const sectionTop = section.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                if (sectionTop < windowHeight * 0.75) {
                    section.classList.add('revealed');
                    if (section.id === 'hero') setTimeout(startTypewriter, 300);
                }
            });
        }

        function updateScrollProgress() {
            const scrollProgress = document.querySelector('.scroll-progress');
            const scrollTop = document.documentElement.scrollTop;
            const scrollHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrollPercentage = (scrollTop / Math.max(scrollHeight, 1)) * 100;
            if (scrollProgress) scrollProgress.style.width = `${scrollPercentage}%`;
        }

        function setupMobileMenu() {
            const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
            const mobileMenu = document.querySelector('.mobile-menu');
            const body = document.body;
            if (!mobileMenuBtn || !mobileMenu) return;
            mobileMenuBtn.addEventListener('click', (e) => {
                e.stopPropagation();
                mobileMenu.classList.toggle('active');
                mobileMenuBtn.innerHTML = mobileMenu.classList.contains('active') ? '<i class="fas fa-times"></i>' : '<i class="fas fa-bars"></i>';
                body.style.overflow = mobileMenu.classList.contains('active') ? 'hidden' : '';
            });
            mobileMenu.querySelectorAll('a').forEach(link => {
                link.addEventListener('click', () => { mobileMenu.classList.remove('active'); mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>'; body.style.overflow = ''; });
            });
            document.addEventListener('click', (e) => {
                if (mobileMenu.classList.contains('active') && !mobileMenu.contains(e.target) && !mobileMenuBtn.contains(e.target)) {
                    mobileMenu.classList.remove('active'); mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>'; body.style.overflow = '';
                }
            });
        }

        function setupFeatureInteractions() {
            const featureIcons = document.querySelectorAll('.feature-icon');
            const featurePopup = document.querySelector('.feature-popup');
            let popupTimeout;
            featureIcons.forEach(icon => {
                icon.addEventListener('mouseenter', () => {
                    clearTimeout(popupTimeout);
                    const title = icon.dataset.title; const desc = icon.dataset.desc; const iconClass = icon.dataset.icon;
                    if (!featurePopup) return;
                    featurePopup.innerHTML = `<div class="popup-header"><div class="popup-icon"><i class="fas fa-${iconClass}"></i></div><h3>${title}</h3></div><p>${desc}</p>`;
                    featurePopup.classList.add('visible'); icon.classList.add('active');
                    featureIcons.forEach(i => { if (i !== icon) i.classList.add('dimmed'); });
                });
                icon.addEventListener('mouseleave', () => {
                    popupTimeout = setTimeout(() => { if (!featurePopup.matches(':hover')) { featurePopup.classList.remove('visible'); featureIcons.forEach(i => { i.classList.remove('active'); i.classList.remove('dimmed'); }); } }, 120);
                });
            });
            if (featurePopup) {
                featurePopup.addEventListener('mouseenter', () => clearTimeout(popupTimeout));
                featurePopup.addEventListener('mouseleave', () => { featurePopup.classList.remove('visible'); document.querySelectorAll('.feature-icon').forEach(i => { i.classList.remove('active'); i.classList.remove('dimmed'); }); });
            }
        }

        function setupSolutionInteractions() {
            const solutionIcons = document.querySelectorAll('.solution-icon');
            const solutionPopup = document.querySelector('.solution-popup');
            let popupTimeout;
            solutionIcons.forEach(icon => {
                icon.addEventListener('mouseenter', () => {
                    clearTimeout(popupTimeout);
                    const title = icon.dataset.title; const desc = icon.dataset.desc; const iconClass = icon.dataset.icon;
                    if (!solutionPopup) return;
                    solutionPopup.innerHTML = `<div class="popup-header"><div class="popup-icon"><i class="fas fa-${iconClass}"></i></div><h3>${title}</h3></div><p>${desc}</p>`;
                    solutionPopup.classList.add('visible'); icon.classList.add('active'); solutionIcons.forEach(i => { if (i !== icon) i.classList.add('dimmed'); });
                });
                icon.addEventListener('mouseleave', () => { popupTimeout = setTimeout(() => { if (!solutionPopup.matches(':hover')) { solutionPopup.classList.remove('visible'); solutionIcons.forEach(i => { i.classList.remove('active'); i.classList.remove('dimmed'); }); } }, 120); });
            });
            if (solutionPopup) {
                solutionPopup.addEventListener('mouseenter', () => clearTimeout(popupTimeout));
                solutionPopup.addEventListener('mouseleave', () => { solutionPopup.classList.remove('visible'); document.querySelectorAll('.solution-icon').forEach(i => { i.classList.remove('active'); i.classList.remove('dimmed'); }); });
            }
        }

        function setupHeaderScroll() {
            const header = document.querySelector('header');
            if (!header) return;
            window.addEventListener('scroll', () => { const currentScroll = window.pageYOffset; header.style.boxShadow = currentScroll <= 0 ? 'none' : '0 5px 20px rgba(0,0,0,0.1)'; });
        }

        // Modal wiring
        function setupOptinModal() {
            const openBtn = document.getElementById('open-optin');
            const modal = document.getElementById('optin-modal');
            if (!openBtn || !modal) return;
            const overlay = modal.querySelector('.modal-overlay');
            const closeBtn = modal.querySelector('.modal-close');
            const confirmBtn = document.getElementById('confirm-optin');
            const declineBtn = document.getElementById('decline-optin');
            const telemetryCheckbox = document.getElementById('telemetry-optin');
            const consentCheckbox = document.getElementById('consent-terms');
            const successEl = document.getElementById('optin-success');
            let previousActive = null;

            function openModal() {
                previousActive = document.activeElement;
                modal.classList.add('open');
                modal.setAttribute('aria-hidden', 'false');
                // focus first interactive element
                setTimeout(() => {
                    if (telemetryCheckbox) telemetryCheckbox.focus();
                }, 50);
                document.addEventListener('keydown', handleKeydown);
            }
            function closeModal() {
                modal.classList.remove('open');
                modal.setAttribute('aria-hidden', 'true');
                document.removeEventListener('keydown', handleKeydown);
                if (previousActive && typeof previousActive.focus === 'function') previousActive.focus();
            }
            function handleKeydown(e) {
                if (e.key === 'Escape') { closeModal(); }
                if (e.key === 'Tab') {
                    // basic focus trap
                    const focusable = modal.querySelectorAll('a[href], button:not([disabled]), input, textarea, [tabindex]:not([tabindex="-1"])');
                    if (!focusable.length) return;
                    const first = focusable[0];
                    const last = focusable[focusable.length - 1];
                    if (e.shiftKey && document.activeElement === first) { e.preventDefault(); last.focus(); }
                    else if (!e.shiftKey && document.activeElement === last) { e.preventDefault(); first.focus(); }
                }
            }

            openBtn.addEventListener('click', (e) => { e.preventDefault(); openModal(); });
            overlay.addEventListener('click', () => closeModal());
            closeBtn.addEventListener('click', () => closeModal());
            declineBtn.addEventListener('click', () => closeModal());

            confirmBtn.addEventListener('click', () => {
                // Require both boxes for a clear consent flow
                if (!telemetryCheckbox.checked || !consentCheckbox.checked) {
                    // simple inline feedback
                    confirmBtn.innerText = 'Please check both boxes';
                    confirmBtn.disabled = true;
                    setTimeout(() => { confirmBtn.innerText = 'Confirm Opt-in'; confirmBtn.disabled = false; }, 1600);
                    return;
                }
                // Show success state
                successEl.style.display = 'block';
                telemetryCheckbox.disabled = true; consentCheckbox.disabled = true; confirmBtn.disabled = true; declineBtn.disabled = true;
                // In a real app, we'd post to an API here. For now just show success and close after a delay.
                setTimeout(() => { closeModal(); }, 1600);
            });
        }

        document.addEventListener('DOMContentLoaded', () => {
            setupMobileMenu(); setupFeatureInteractions(); setupSolutionInteractions(); setupHeaderScroll(); revealOnScroll(); setupOptinModal();
            window.addEventListener('scroll', () => { revealOnScroll(); updateScrollProgress(); });
            setTimeout(revealOnScroll, 100);
        });
    </script>
</body>
</html>
