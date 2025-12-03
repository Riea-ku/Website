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
    
    /* Design tokens */
    --border-radius: 12px;
    --transition-speed: 0.22s;
    --shadow-light: 0 6px 18px rgba(0, 229, 196, 0.18);
    --shadow-medium: 0 12px 30px rgba(0, 229, 196, 0.22);
    --shadow-heavy: 0 18px 36px rgba(0, 0, 0, 0.34);
    --shadow-modal: 0 30px 60px rgba(0, 0, 0, 0.6);
    
    /* Breakpoints */
    --bp-mobile: 768px;
    --bp-tablet: 1024px;
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

/* Skip link for accessibility */
.skip-link {
    position: absolute;
    top: -40px;
    left: 0;
    background: var(--gradient);
    color: var(--black);
    padding: 8px 16px;
    border-radius: var(--border-radius);
    text-decoration: none;
    font-weight: 600;
    z-index: 9999;
    transition: top 0.3s ease;
}

.skip-link:focus {
    top: 10px;
    outline: 2px solid var(--turquoise);
    outline-offset: 2px;
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
    transition: color var(--transition-speed);
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
    transition: width var(--transition-speed) ease;
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
    color: var(--black) !important;
    padding: 12px 26px;
    border-radius: 50px;
    text-decoration: none;
    font-weight: 600;
    transition: transform 0.18s, box-shadow 0.18s;
    box-shadow: var(--shadow-light);
    border: none;
    cursor: pointer;
}

.btn:hover {
    transform: translateY(-3px);
    box-shadow: var(--shadow-medium);
}

.btn:focus {
    outline: 2px solid var(--turquoise);
    outline-offset: 2px;
}

.mobile-menu-btn {
    display: none;
    background: none;
    border: none;
    color: var(--white);
    font-size: 1.4rem;
    cursor: pointer;
    z-index: 1002;
    padding: 8px;
    border-radius: 4px;
}

.mobile-menu-btn:focus {
    outline: 2px solid var(--turquoise);
    outline-offset: 2px;
}

/* Sections */
section {
    width: 100%;
    padding: 100px 0;
    opacity: 0;
    transform: translateY(18px);
    transition: opacity 0.6s ease, transform 0.6s ease;
}

section.revealed {
    opacity: 1;
    transform: translateY(0);
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Hero */
.hero {
    background: var(--dark-purple);
    text-align: center;
    padding-top: 160px;
}

.hero-box {
    background: linear-gradient(145deg, rgba(26,16,61,0.82), rgba(42,42,42,0.82));
    border-radius: var(--border-radius);
    padding: 64px 36px;
    box-shadow: var(--shadow-heavy);
    border: 1px solid rgba(255,255,255,0.06);
    max-width: 1000px;
    margin: 0 auto;
    backdrop-filter: blur(8px);
}

.typewriter-container {
    margin-bottom: 22px;
    min-height: 84px;
}

.typewriter-title {
    font-family: 'Montserrat', sans-serif;
    font-size: 2.6rem;
    font-weight: 700;
    color: var(--white);
    line-height: 1.12;
    overflow: hidden;
    white-space: nowrap;
    margin: 0 auto;
    border-right: 3px solid var(--turquoise);
    display: inline-block;
}

.typing {
    animation: typing 3.5s steps(40,end) forwards, blink-caret .75s step-end infinite;
}

@keyframes typing {
    from { width: 0; }
    to { width: 100%; }
}

@keyframes blink-caret {
    from, to { border-color: transparent; }
    50% { border-color: var(--turquoise); }
}

.hero-box p {
    font-size: 1.12rem;
    margin-bottom: 24px;
    color: var(--light-gray);
    font-weight: 300;
    max-width: 760px;
    margin-left: auto;
    margin-right: auto;
}

.hero-image {
    margin-top: 14px;
    border-radius: var(--border-radius);
    overflow: hidden;
    box-shadow: 0 18px 40px rgba(0,0,0,0.5);
}

.hero-image img {
    width: 100%;
    height: auto;
    display: block;
    max-height: 360px;
    object-fit: cover;
}

/* Features */
.features {
    background: var(--dark-purple);
    position: relative;
}

.section-title {
    text-align: center;
    margin-bottom: 56px;
}

.section-title h2 {
    font-family: 'Montserrat', sans-serif;
    font-size: 2.4rem;
    color: var(--white);
    margin-bottom: 12px;
    font-weight: 700;
    display: inline-block;
    position: relative;
}

.section-title h2:after {
    content: '';
    position: absolute;
    width: 56px;
    height: 4px;
    background: var(--gradient);
    bottom: -10px;
    left: 50%;
    transform: translateX(-50%);
    border-radius: 2px;
}

.section-title p {
    color: var(--light-gray);
    max-width: 720px;
    margin: 18px auto 0;
    font-size: 1.05rem;
    font-weight: 300;
}

.features-section {
    position: relative;
    width: 100%;
}

.feature-icons {
    display: flex;
    justify-content: center;
    gap: 30px;
    flex-wrap: wrap;
}

.feature-icon {
    cursor: pointer;
    transition: all var(--transition-speed) ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 150px;
    padding: 10px;
    border-radius: var(--border-radius);
}

.feature-icon:hover {
    background: rgba(255, 255, 255, 0.02);
}

.feature-icon i {
    font-size: 2.6rem;
    color: var(--turquoise);
    margin-bottom: 14px;
    background: rgba(0,229,196,0.08);
    width: 96px;
    height: 96px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    transition: all var(--transition-speed) ease;
}

.feature-icon.active i {
    transform: scale(1.14);
    background: var(--gradient);
    color: var(--black);
    box-shadow: 0 0 22px rgba(0,229,196,0.38);
}

.feature-icon h3 {
    font-size: 1.05rem;
    color: var(--white);
    font-weight: 600;
    text-align: center;
}

.feature-icon.dimmed {
    opacity: 0.28;
    transform: scale(0.96);
    pointer-events: none;
}

.feature-popup {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%) scale(0.98);
    width: 480px;
    padding: 28px;
    background: rgba(26,16,61,0.96);
    backdrop-filter: blur(8px);
    border-radius: 14px;
    color: white;
    text-align: left;
    opacity: 0;
    pointer-events: none;
    transition: opacity var(--transition-speed) ease, transform var(--transition-speed) ease;
    box-shadow: 0 28px 56px rgba(0,0,0,0.56);
    border: 2px solid var(--turquoise);
    z-index: 100;
}

.feature-popup.visible {
    opacity: 1;
    pointer-events: auto;
    transform: translate(-50%,-50%) scale(1);
}

.popup-header {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 12px;
}

.popup-icon {
    font-size: 1.8rem;
    color: var(--turquoise);
    background: rgba(0,229,196,0.08);
    width: 62px;
    height: 62px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
}

.popup-header h3 {
    font-family: 'Montserrat', sans-serif;
    font-size: 1.4rem;
    color: var(--turquoise);
    margin: 0;
    font-weight: 600;
}

.feature-popup p {
    color: var(--light-gray);
    font-size: 1rem;
    margin-left: 84px;
    font-weight: 300;
    line-height: 1.6;
}

/* Solution */
.solution {
    background: var(--dark-purple);
    position: relative;
}

.solution-box {
    background: linear-gradient(145deg, rgba(26,16,61,0.82), rgba(42,42,42,0.82));
    border-radius: var(--border-radius);
    padding: 60px 36px;
    box-shadow: var(--shadow-heavy);
    border: 1px solid rgba(255,255,255,0.06);
    max-width: 980px;
    margin: 0 auto 80px;
    text-align: center;
}

.solution-box h3 {
    font-family: 'Montserrat', sans-serif;
    font-size: 1.9rem;
    margin-bottom: 18px;
    color: var(--turquoise);
    font-weight: 700;
}

.solution-box p {
    color: var(--light-gray);
    font-size: 1.05rem;
    margin-bottom: 12px;
    font-weight: 300;
    max-width: 820px;
    margin-left: auto;
    margin-right: auto;
}

.solution-icons {
    display: flex;
    justify-content: center;
    gap: 46px;
    flex-wrap: wrap;
}

.solution-icon {
    width: 160px;
    display: flex;
    flex-direction: column;
    align-items: center;
    cursor: pointer;
    padding: 10px;
    border-radius: var(--border-radius);
}

.solution-icon:hover {
    background: rgba(255, 255, 255, 0.02);
}

.solution-icon i {
    font-size: 2.8rem;
    color: var(--turquoise);
    margin-bottom: 14px;
    background: rgba(0,229,196,0.08);
    width: 100px;
    height: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    transition: all var(--transition-speed) ease;
}

.solution-icon.active i {
    transform: scale(1.12);
    background: var(--gradient);
    color: var(--black);
    box-shadow: 0 0 22px rgba(0,229,196,0.38);
}

.solution-popup {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%) scale(0.98);
    width: 480px;
    padding: 28px;
    background: rgba(26,16,61,0.96);
    backdrop-filter: blur(8px);
    border-radius: 14px;
    color: white;
    text-align: left;
    opacity: 0;
    pointer-events: none;
    transition: opacity var(--transition-speed) ease, transform var(--transition-speed) ease;
    box-shadow: 0 28px 56px rgba(0,0,0,0.56);
    border: 2px solid var(--turquoise);
    z-index: 100;
}

.solution-popup.visible {
    opacity: 1;
    pointer-events: auto;
    transform: translate(-50%,-50%) scale(1);
}

/* Demo grid */
.demo-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 18px;
    margin-top: 28px;
}

.demo-card {
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius: var(--border-radius);
    overflow: hidden;
    border: 1px solid rgba(255,255,255,0.04);
    transition: transform var(--transition-speed) ease;
}

.demo-card:hover {
    transform: translateY(-5px);
}

.demo-card img {
    width: 100%;
    display: block;
    height: 160px;
    object-fit: cover;
}

.demo-card .card-body {
    padding: 12px 14px;
    color: var(--light-gray);
    font-size: 0.98rem;
}

/* Pricing */
.pricing {
    background: linear-gradient(180deg, rgba(26,16,61,0.95), rgba(19,10,48,0.95));
    padding: 72px 0;
}

.pricing .section-title {
    margin-bottom: 18px;
}

.pricing-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
    max-width: 1100px;
    margin: 28px auto 0;
}

.plan-card {
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius: var(--border-radius);
    padding: 20px;
    border: 1px solid rgba(255,255,255,0.04);
    text-align: center;
    box-shadow: 0 12px 30px rgba(0,0,0,0.45);
    transition: transform var(--transition-speed) ease;
}

.plan-card:hover {
    transform: translateY(-5px);
}

.plan-badge {
    display: inline-block;
    padding: 6px 12px;
    background: rgba(0,229,196,0.08);
    color: var(--turquoise);
    border-radius: 999px;
    font-weight: 600;
    font-size: 0.85rem;
    margin-bottom: 12px;
}

.plan-price {
    font-size: 2rem;
    font-weight: 800;
    color: var(--white);
    margin: 8px 0;
}

.plan-period {
    color: var(--light-gray);
    font-size: 0.95rem;
    margin-bottom: 12px;
}

.plan-features {
    text-align: left;
    margin: 12px 0 16px;
    color: var(--light-gray);
    font-size: 0.95rem;
    list-style-position: inside;
}

.plan-features li {
    margin-bottom: 8px;
    position: relative;
    padding-left: 20px;
}

.plan-features li:before {
    content: "✓";
    color: var(--turquoise);
    position: absolute;
    left: 0;
}

.plan-cta {
    margin-top: 12px;
}

.plan-popular {
    border: 2px solid rgba(0,229,196,0.14);
    box-shadow: 0 20px 40px rgba(0,229,196,0.06);
    transform: translateY(-6px);
}

/* Trust section */
.trust {
    background: transparent;
    padding: 64px 0;
}

.trust-inner {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 420px;
    gap: 28px;
    align-items: start;
}

.trust-card {
    background: linear-gradient(180deg, rgba(26,16,61,0.9), rgba(19,10,48,0.9));
    border-radius: var(--border-radius);
    padding: 22px;
    border: 1px solid rgba(255,255,255,0.04);
}

.trust h3 {
    color: var(--turquoise);
    margin-bottom: 10px;
    font-size: 1.4rem;
}

.trust p {
    color: var(--light-gray);
    margin-bottom: 12px;
}

.trust-cta {
    margin-top: 14px;
}

/* CTA */
.cta {
    background: linear-gradient(135deg, rgba(58,28,140,0.9) 0%, rgba(26,16,61,0.9) 100%);
    text-align: center;
    padding: 80px 0;
}

.cta h2 {
    font-family: 'Montserrat', sans-serif;
    font-size: 2.2rem;
    margin-bottom: 14px;
    font-weight: 700;
}

.cta p {
    font-size: 1.02rem;
    max-width: 760px;
    margin: 0 auto 30px;
    color: var(--light-gray);
    font-weight: 300;
}

/* Footer */
footer {
    background-color: var(--dark-purple);
    padding: 80px 0 36px;
    border-top: 1px solid rgba(255,255,255,0.06);
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px,1fr));
    gap: 40px;
    margin-bottom: 40px;
}

.footer-column h3 {
    font-family: 'Montserrat', sans-serif;
    font-size: 1.1rem;
    margin-bottom: 14px;
    color: var(--turquoise);
    font-weight: 600;
}

.footer-column p, .footer-links a {
    color: var(--light-gray);
    font-weight: 300;
    text-decoration: none;
}

.footer-links {
    list-style: none;
}

.footer-links li {
    margin-bottom: 8px;
}

.footer-links a:hover {
    color: var(--turquoise);
}

.copyright {
    text-align: center;
    padding-top: 20px;
    border-top: 1px solid rgba(255,255,255,0.06);
    color: var(--light-gray);
    font-size: 0.92rem;
}

.legal-links {
    list-style: none;
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 10px;
}

.legal-links a {
    color: var(--light-gray);
    text-decoration: none;
}

.legal-links a:hover {
    color: var(--turquoise);
}

/* Mobile Menu */
.mobile-menu {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(26,16,61,0.98);
    backdrop-filter: blur(10px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 20px;
    transform: translateX(-100%);
    opacity: 0;
    transition: all var(--transition-speed) ease;
    z-index: 1001;
    padding: 20px;
}

.mobile-menu.active {
    transform: translateX(0);
    opacity: 1;
}

.mobile-menu a {
    color: var(--white);
    text-decoration: none;
    font-size: 1.4rem;
    padding: 10px 0;
    width: 100%;
    text-align: center;
    border-bottom: 1px solid rgba(255,255,255,0.06);
    transition: color var(--transition-speed) ease;
}

.mobile-menu a:hover {
    color: var(--turquoise);
}

/* Modal / Opt-in */
.modal {
    position: fixed;
    inset: 0;
    display: none;
    align-items: center;
    justify-content: center;
    z-index: 1100;
}

.modal.open {
    display: flex;
}

.modal-overlay {
    position: absolute;
    inset: 0;
    background: rgba(4,6,16,0.6);
    backdrop-filter: blur(4px);
}

.modal-panel {
    position: relative;
    z-index: 1101;
    width: 98%;
    max-width: 720px;
    background: linear-gradient(180deg, rgba(26,16,61,0.98), rgba(19,10,48,0.98));
    border-radius: var(--border-radius);
    padding: 22px;
    border: 1px solid rgba(255,255,255,0.06);
    box-shadow: var(--shadow-modal);
}

.modal-panel h3 {
    margin-top: 0;
    color: var(--turquoise);
    font-size: 1.3rem;
    margin-right: 30px;
}

.modal-panel p {
    color: var(--light-gray);
    margin-bottom: 12px;
}

.modal-panel fieldset {
    border: 1px dashed rgba(255,255,255,0.04);
    padding: 12px;
    border-radius: 8px;
    margin-bottom: 12px;
}

.modal-panel label {
    display: block;
    color: var(--light-gray);
    margin-bottom: 8px;
    font-size: 0.95rem;
    cursor: pointer;
    display: flex;
    align-items: flex-start;
    gap: 10px;
}

.modal-panel input[type="checkbox"] {
    margin-top: 3px;
    accent-color: var(--turquoise);
}

.modal-panel .modal-accept {
    margin-top: 8px;
    display: flex;
    align-items: center;
    gap: 10px;
}

.modal-panel .modal-actions {
    display: flex;
    gap: 10px;
    margin-top: 12px;
    flex-wrap: wrap;
}

.modal-close {
    position: absolute;
    right: 12px;
    top: 10px;
    background: transparent;
    border: none;
    color: var(--light-gray);
    font-size: 1.6rem;
    cursor: pointer;
    padding: 5px;
    border-radius: 4px;
}

.modal-close:hover {
    color: var(--turquoise);
}

.modal-close:focus {
    outline: 2px solid var(--turquoise);
    outline-offset: 2px;
}

/* Print styles */
@media print {
    .btn, .mobile-menu-btn, .modal, .scroll-progress, .mobile-menu {
        display: none !important;
    }
    
    .hero {
        padding-top: 20px;
    }
    
    section {
        padding: 40px 0;
        opacity: 1;
        transform: none;
    }
}

/* Responsive */
@media (max-width: 1024px) {
    .typewriter-title {
        font-size: 2rem;
    }
    
    .hero-box {
        padding: 40px 28px;
    }
    
    .trust-inner {
        grid-template-columns: 1fr;
    }
    
    .feature-popup,
    .solution-popup {
        width: 90%;
        max-width: 500px;
    }
    
    .feature-popup p,
    .solution-popup p {
        margin-left: 0;
        text-align: center;
    }
    
    .popup-header {
        flex-direction: column;
        text-align: center;
        gap: 12px;
    }
}

@media (max-width: 768px) {
    .nav-links {
        display: none;
    }
    
    .mobile-menu-btn {
        display: block;
    }
    
    .typewriter-title {
        font-size: 1.6rem;
        white-space: normal;
        border-right: none;
        animation: none;
        width: 100%;
        overflow: visible;
    }
    
    .hero {
        padding-top: 120px;
    }
    
    section {
        padding: 60px 0;
    }
    
    .feature-icons,
    .solution-icons {
        gap: 20px;
    }
    
    .feature-icon,
    .solution-icon {
        width: 130px;
    }
    
    .feature-icon i {
        width: 80px;
        height: 80px;
        font-size: 2.2rem;
    }
    
    .solution-icon i {
        width: 80px;
        height: 80px;
        font-size: 2.2rem;
    }
    
    .feature-popup,
    .solution-popup {
        width: 95%;
        padding: 18px;
        position: fixed;
        top: 50%;
        left: 50%;
    }
    
    .footer-content {
        grid-template-columns: 1fr;
        text-align: center;
    }
    
    .footer-links {
        padding: 0;
    }
    
    .legal-links {
        flex-direction: column;
        gap: 10px;
    }
    
    .modal-panel .modal-actions {
        flex-direction: column;
    }
    
    .modal-panel .modal-actions .btn {
        width: 100%;
    }
}

@media (max-width: 480px) {
    .typewriter-title {
        font-size: 1.4rem;
    }
    
    .section-title h2 {
        font-size: 1.8rem;
    }
    
    .hero-box {
        padding: 30px 20px;
    }
    
    .feature-icons,
    .solution-icons {
        gap: 15px;
    }
    
    .feature-icon,
    .solution-icon {
        width: 110px;
    }
    
    .feature-icon h3,
    .solution-icon h3 {
        font-size: 0.9rem;
    }
    
    .pricing-grid {
        grid-template-columns: 1fr;
    }
}

/* small utilities */
.muted {
    color: var(--light-gray);
}

.caps {
    text-transform: uppercase;
    letter-spacing: 1px;
    font-size: 0.85rem;
}

.visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
}
    </style>
</head>
<body>
    <a href="#main-content" class="skip-link">Skip to main content</a>
    <div class="scroll-progress" aria-hidden="true"></div>

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
                <button class="mobile-menu-btn" aria-label="Open menu" aria-expanded="false">
                    <i class="fas fa-bars"></i>
                </button>
            </nav>
        </div>
    </header>

    <div class="mobile-menu" aria-label="Mobile navigation" aria-hidden="true">
        <a href="#features">Features</a>
        <a href="#solution">How It Works</a>
        <a href="#pricing">Pricing</a>
        <a href="#trust">Trust &amp; Data</a>
        <a href="#contact">Contact Us</a>
    </div>

    <main id="main-content">
        <section id="hero" class="hero">
            <div class="container">
                <div class="hero-box">
                    <div class="typewriter-container">
                        <h1 class="typewriter-title" id="typewriter-text">Predictive Maintenance for Agriculture</h1>
                    </div>
                    <p>From reactive breakdowns to proactive intelligence — Providentia prevents equipment failures and protects harvests.</p>
                    <a href="#contact" class="btn">Contact Us</a>

                    <div class="hero-image">
                        <img 
                            src="https://images.unsplash.com/photo-1501004318641-b39e6451bec6?q=80&w=800&auto=format&fit=crop&h=400" 
                            alt="Smart farm monitoring system showing IoT sensors and data visualization"
                            loading="lazy"
                            srcset="
                                https://images.unsplash.com/photo-1501004318641-b39e6451bec6?w=400&auto=format 400w,
                                https://images.unsplash.com/photo-1501004318641-b39e6451bec6?w=800&auto=format 800w
                            "
                            sizes="(max-width: 768px) 100vw, 800px">
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
                        <div class="feature-icon" data-title="Predictive Failure Detection" data-desc="AI-powered predictions that identify equipment issues before they cause breakdowns. Our machine learning algorithms analyze sensor data to detect patterns indicative of future failures, giving you time to schedule repairs during non-critical periods." data-icon="brain">
                            <i class="fas fa-brain"></i>
                            <h3>Predictive Failure Detection</h3>
                        </div>
                        <div class="feature-icon" data-title="Maintenance Scheduling" data-desc="Optimize maintenance routines and reduce downtime with intelligent scheduling based on actual equipment usage patterns rather than fixed intervals. Save up to 40% on maintenance costs while extending equipment lifespan." data-icon="calendar-check">
                            <i class="fas fa-calendar-check"></i>
                            <h3>Maintenance Scheduling</h3>
                        </div>
                        <div class="feature-icon" data-title="Equipment Monitoring" data-desc="Real-time monitoring of pumps, tractors, and irrigation systems with instant alerts for abnormal conditions. Track temperature, vibration, pressure, and performance metrics across all critical equipment." data-icon="broadcast-tower">
                            <i class="fas fa-broadcast-tower"></i>
                            <h3>Equipment Monitoring</h3>
                        </div>
                        <div class="feature-icon" data-title="Performance Analytics" data-desc="Comprehensive insights and KPI tracking across all your agricultural equipment. Identify trends, compare performance across similar equipment, and make data-driven decisions about replacements and upgrades." data-icon="chart-line">
                            <i class="fas fa-chart-line"></i>
                            <h3>Performance Analytics</h3>
                        </div>
                        <div class="feature-icon" data-title="Anomaly Detection" data-desc="Identify unusual patterns in equipment behavior that signal potential failures before they become critical. Our system learns your specific equipment's normal behavior and alerts you to deviations." data-icon="triangle-exclamation">
                            <i class="fas fa-triangle-exclamation"></i>
                            <h3>Anomaly Detection</h3>
                        </div>
                        <div class="feature-icon" data-title="Cost Optimization" data-desc="Reduce emergency repair costs and prevent crop losses from equipment failures. Our customers report an average 35% reduction in unplanned downtime and 28% lower maintenance expenses." data-icon="piggy-bank">
                            <i class="fas fa-piggy-bank"></i>
                            <h3>Cost Optimization</h3>
                        </div>
                    </div>

                    <div class="feature-popup" role="tooltip" aria-hidden="true"></div>
                </div>
            </div>
        </section>

        <section id="solution" class="solution">
            <div class="container">
                <div class="solution-box">
                    <h3>The Predictive Intelligence Infrastructure for Agriculture</h3>
                    <p>An always-on partner that watches every machine, learns its behavior, and alerts farmers before breakdowns happen.</p>
                    <p>Enterprise-grade AI, designed for simplicity and reliability in the field.</p>
                </div>

                <div class="solution-section">
                    <div class="solution-icons">
                        <div class="solution-icon" data-title="Lives in your pocket" data-desc="Mobile-first design that works where you work. Get real-time alerts, view equipment status, and approve maintenance actions from your smartphone. No need to be at a desktop computer to manage your farm's equipment health." data-icon="mobile-alt">
                            <i class="fas fa-mobile-alt"></i>
                            <h3>Lives in your pocket</h3>
                        </div>
                        <div class="solution-icon" data-title="Speaks your language" data-desc="Clear, actionable alerts in plain language. No technical jargon or confusing codes. Get straightforward instructions like 'Tractor #3: Oil change recommended within next 48 hours' instead of cryptic error messages." data-icon="comments">
                            <i class="fas fa-comments"></i>
                            <h3>Speaks your language</h3>
                        </div>
                        <div class="solution-icon" data-title="Sees failures before they happen" data-desc="Proactive maintenance scheduling based on actual equipment condition rather than arbitrary time intervals. Our predictive models can forecast failures 10-14 days in advance with 92% accuracy, giving you ample time to plan." data-icon="eye">
                            <i class="fas fa-eye"></i>
                            <h3>Sees failures before they happen</h3>
                        </div>
                    </div>

                    <div class="solution-popup" role="tooltip" aria-hidden="true"></div>
                </div>

                <div class="container">
                    <div class="section-title" style="margin-top:36px;">
                        <h2>Proof & Demo</h2>
                        <p>Simulated validation, real results — explore a few examples from our simulation and demo app.</p>
                    </div>

                    <div class="demo-grid">
                        <div class="demo-card">
                            <img 
                                src="https://images.unsplash.com/photo-1504881549696-cd4bea4d2e2b?q=80&w=600&auto=format&fit=crop&h=300" 
                                alt="Equipment sensor monitoring dashboard showing vibration analytics"
                                loading="lazy">
                            <div class="card-body">Predictive Analytics: Early warning system detects equipment degradation 10+ days before failure.</div>
                        </div>
                        <div class="demo-card">
                            <img 
                                src="https://images.unsplash.com/photo-1517976487492-0b0a56f0a7f6?q=80&w=600&auto=format&fit=crop&h=300" 
                                alt="Farm dashboard interface with equipment status overview"
                                loading="lazy">
                            <div class="card-body">Intuitive Dashboard: Prioritized alerts and maintenance actions at a glance.</div>
                        </div>
                        <div class="demo-card">
                            <img 
                                src="https://images.unsplash.com/photo-1518823886215-2b25f6c7f3e2?q=80&w=600&auto=format&fit=crop&h=300" 
                                alt="IoT sensor technology installed on agricultural equipment"
                                loading="lazy">
                            <div class="card-body">Real-Time Integration: Sensor data flows seamlessly to our predictive engine.</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

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
                        <div class="plan-price">$29/month</div>
                        <div class="plan-period">1 equipment type</div>
                        <ul class="plan-features">
                            <li>Essential failure detection & alerts</li>
                            <li>Basic maintenance scheduling</li>
                            <li>Email support</li>
                            <li>Up to 5 equipment units</li>
                        </ul>
                        <div class="plan-cta"><a class="btn" href="#contact">Get Basic</a></div>
                    </div>

                    <div class="plan-card plan-popular">
                        <div class="plan-badge">Professional</div>
                        <div class="plan-price">$79/month</div>
                        <div class="plan-period">All equipment types</div>
                        <ul class="plan-features">
                            <li>Full AI co-pilot with predictive analytics</li>
                            <li>Advanced diagnostics & priority alerts</li>
                            <li>SMS + email support</li>
                            <li>Up to 25 equipment units</li>
                            <li>Historical data analysis</li>
                        </ul>
                        <div class="plan-cta"><a class="btn" href="#contact">Get Professional</a></div>
                    </div>

                    <div class="plan-card">
                        <div class="plan-badge">Enterprise</div>
                        <div class="plan-price">$199/month</div>
                        <div class="plan-period">Farm-wide</div>
                        <ul class="plan-features">
                            <li>Farm-wide operational intelligence</li>
                            <li>Dedicated support team</li>
                            <li>Custom alerts & SLA</li>
                            <li>Unlimited equipment units</li>
                            <li>API access & custom integrations</li>
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
                    <h3>How It Works</h3>
                    <ul class="plan-features">
                        <li>Opt-in anonymized telemetry only</li>
                        <li>Tokens issued for approved contributions</li>
                        <li>Local-model improvements & neighborhood alerts</li>
                        <li>Full transparency: what is shared and how it's used</li>
                        <li>Data never sold to third parties</li>
                    </ul>
                    <p class="muted">We never sell raw farm data. Manufacturers or insurers access aggregated insights only when farmers opt in.</p>
                </aside>
            </div>
        </section>

        <section id="contact" class="cta">
            <div class="container">
                <div class="cta-content">
                    <h2>Ready to Transform Equipment Maintenance?</h2>
                    <p>Schedule a walkthrough with our team or explore the platform with a live demo.</p>
                    <a href="https://providentia.pythonanywhere.com/" class="btn" target="_blank" rel="noopener noreferrer">View Live Demo</a>
                </div>
            </div>
        </section>
    </main>

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
                        <li><a href="https://providentia.pythonanywhere.com/" target="_blank" rel="noopener noreferrer">Live Demo</a></li>
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
                        <li><a href="https://www.linkedin.com/in/meryem-m-477149244" target="_blank" rel="noopener noreferrer">LinkedIn</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 Providentia. All Rights Reserved.</p>
                <ul class="legal-links">
                    <li><a href="#">Terms of Service</a></li>
                    <li><a href="#">Privacy Policy</a></li>
                    <li><a href="#">Cookie Policy</a></li>
                </ul>
            </div>
        </div>
    </footer>

    <!-- Opt-in Modal -->
    <div class="modal" id="optin-modal" aria-hidden="true" role="dialog" aria-modal="false" aria-labelledby="optin-title">
        <div class="modal-overlay" data-close></div>
        <div class="modal-panel" role="document">
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
        // Store cleanup functions
        const cleanupFunctions = [];
        let isTypingStarted = false;

        function startTypewriter() {
            if (isTypingStarted) return;
            const typewriterText = document.getElementById('typewriter-text');
            if (!typewriterText) return;
            
            // Check if mobile
            if (window.innerWidth <= 768) {
                typewriterText.style.animation = 'none';
                typewriterText.style.borderRight = 'none';
                typewriterText.style.opacity = '1';
            } else {
                typewriterText.classList.add('typing');
            }
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
            if (!scrollProgress) return;
            
            const scrollTop = document.documentElement.scrollTop;
            const scrollHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrollPercentage = (scrollTop / Math.max(scrollHeight, 1)) * 100;
            scrollProgress.style.width = `${scrollPercentage}%`;
        }

        function setupMobileMenu() {
            const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
            const mobileMenu = document.querySelector('.mobile-menu');
            const body = document.body;
            
            if (!mobileMenuBtn || !mobileMenu) return;
            
            function toggleMenu() {
                const isActive = mobileMenu.classList.toggle('active');
                mobileMenuBtn.setAttribute('aria-expanded', isActive);
                mobileMenu.setAttribute('aria-hidden', !isActive);
                mobileMenuBtn.innerHTML = isActive ? '<i class="fas fa-times"></i>' : '<i class="fas fa-bars"></i>';
                body.style.overflow = isActive ? 'hidden' : '';
                
                if (isActive) {
                    // Focus first link in mobile menu
                    const firstLink = mobileMenu.querySelector('a');
                    if (firstLink) firstLink.focus();
                }
            }
            
            mobileMenuBtn.addEventListener('click', (e) => {
                e.stopPropagation();
                toggleMenu();
            });
            
            mobileMenu.querySelectorAll('a').forEach(link => {
                link.addEventListener('click', () => {
                    mobileMenu.classList.remove('active');
                    mobileMenuBtn.setAttribute('aria-expanded', 'false');
                    mobileMenu.setAttribute('aria-hidden', 'true');
                    mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>';
                    body.style.overflow = '';
                });
            });
            
            document.addEventListener('click', (e) => {
                if (mobileMenu.classList.contains('active') && 
                    !mobileMenu.contains(e.target) && 
                    !mobileMenuBtn.contains(e.target)) {
                    toggleMenu();
                }
            });
            
            // Close on escape
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape' && mobileMenu.classList.contains('active')) {
                    toggleMenu();
                }
            });
        }

        function setupFeatureInteractions() {
            const featureIcons = document.querySelectorAll('.feature-icon');
            const featurePopup = document.querySelector('.feature-popup');
            if (!featureIcons.length || !featurePopup) return;
            
            let popupTimeout;
            let activeIcon = null;
            
            function showPopup(icon) {
                clearTimeout(popupTimeout);
                const title = icon.dataset.title;
                const desc = icon.dataset.desc;
                const iconClass = icon.dataset.icon;
                
                featurePopup.innerHTML = `
                    <div class="popup-header">
                        <div class="popup-icon"><i class="fas fa-${iconClass}"></i></div>
                        <h3>${title}</h3>
                    </div>
                    <p>${desc}</p>
                `;
                featurePopup.classList.add('visible');
                featurePopup.setAttribute('aria-hidden', 'false');
                icon.classList.add('active');
                activeIcon = icon;
                
                featureIcons.forEach(i => {
                    if (i !== icon) i.classList.add('dimmed');
                });
            }
            
            function hidePopup() {
                popupTimeout = setTimeout(() => {
                    if (!featurePopup.matches(':hover') && activeIcon !== featurePopup) {
                        featurePopup.classList.remove('visible');
                        featurePopup.setAttribute('aria-hidden', 'true');
                        featureIcons.forEach(i => {
                            i.classList.remove('active');
                            i.classList.remove('dimmed');
                        });
                        activeIcon = null;
                    }
                }, 120);
            }
            
            featureIcons.forEach(icon => {
                // Mouse events for desktop
                icon.addEventListener('mouseenter', () => showPopup(icon));
                icon.addEventListener('mouseleave', hidePopup);
                
                // Touch events for mobile
                icon.addEventListener('touchstart', (e) => {
                    if (window.innerWidth <= 768) {
                        e.preventDefault();
                        if (activeIcon === icon) {
                            // If same icon tapped, hide popup
                            featurePopup.classList.remove('visible');
                            featurePopup.setAttribute('aria-hidden', 'true');
                            icon.classList.remove('active');
                            activeIcon = null;
                            featureIcons.forEach(i => i.classList.remove('dimmed'));
                        } else {
                            showPopup(icon);
                        }
                    }
                }, { passive: false });
                
                // Keyboard support
                icon.addEventListener('focus', () => showPopup(icon));
                icon.addEventListener('blur', hidePopup);
                icon.setAttribute('tabindex', '0');
                icon.setAttribute('role', 'button');
                icon.setAttribute('aria-describedby', 'feature-popup-desc');
            });
            
            featurePopup.addEventListener('mouseenter', () => clearTimeout(popupTimeout));
            featurePopup.addEventListener('mouseleave', hidePopup);
            
            // Add ID for aria-describedby
            featurePopup.id = 'feature-popup-desc';
        }

        function setupSolutionInteractions() {
            const solutionIcons = document.querySelectorAll('.solution-icon');
            const solutionPopup = document.querySelector('.solution-popup');
            if (!solutionIcons.length || !solutionPopup) return;
            
            let popupTimeout;
            let activeIcon = null;
            
            function showPopup(icon) {
                clearTimeout(popupTimeout);
                const title = icon.dataset.title;
                const desc = icon.dataset.desc;
                const iconClass = icon.dataset.icon;
                
                solutionPopup.innerHTML = `
                    <div class="popup-header">
                        <div class="popup-icon"><i class="fas fa-${iconClass}"></i></div>
                        <h3>${title}</h3>
                    </div>
                    <p>${desc}</p>
                `;
                solutionPopup.classList.add('visible');
                solutionPopup.setAttribute('aria-hidden', 'false');
                icon.classList.add('active');
                activeIcon = icon;
                
                solutionIcons.forEach(i => {
                    if (i !== icon) i.classList.add('dimmed');
                });
            }
            
            function hidePopup() {
                popupTimeout = setTimeout(() => {
                    if (!solutionPopup.matches(':hover') && activeIcon !== solutionPopup) {
                        solutionPopup.classList.remove('visible');
                        solutionPopup.setAttribute('aria-hidden', 'true');
                        solutionIcons.forEach(i => {
                            i.classList.remove('active');
                            i.classList.remove('dimmed');
                        });
                        activeIcon = null;
                    }
                }, 120);
            }
            
            solutionIcons.forEach(icon => {
                // Mouse events for desktop
                icon.addEventListener('mouseenter', () => showPopup(icon));
                icon.addEventListener('mouseleave', hidePopup);
                
                // Touch events for mobile
                icon.addEventListener('touchstart', (e) => {
                    if (window.innerWidth <= 768) {
                        e.preventDefault();
                        if (activeIcon === icon) {
                            // If same icon tapped, hide popup
                            solutionPopup.classList.remove('visible');
                            solutionPopup.setAttribute('aria-hidden', 'true');
                            icon.classList.remove('active');
                            activeIcon = null;
                            solutionIcons.forEach(i => i.classList.remove('dimmed'));
                        } else {
                            showPopup(icon);
                        }
                    }
                }, { passive: false });
                
                // Keyboard support
                icon.addEventListener('focus', () => showPopup(icon));
                icon.addEventListener('blur', hidePopup);
                icon.setAttribute('tabindex', '0');
                icon.setAttribute('role', 'button');
                icon.setAttribute('aria-describedby', 'solution-popup-desc');
            });
            
            solutionPopup.addEventListener('mouseenter', () => clearTimeout(popupTimeout));
            solutionPopup.addEventListener('mouseleave', hidePopup);
            
            // Add ID for aria-describedby
            solutionPopup.id = 'solution-popup-desc';
        }

        function setupHeaderScroll() {
            const header = document.querySelector('header');
            if (!header) return;
            
            function updateHeader() {
                const currentScroll = window.pageYOffset;
                header.style.boxShadow = currentScroll <= 0 ? 'none' : '0 5px 20px rgba(0,0,0,0.1)';
            }
            
            window.addEventListener('scroll', updateHeader);
            cleanupFunctions.push(() => window.removeEventListener('scroll', updateHeader));
        }

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
            
            // Get all focusable elements in modal
            function getFocusableElements() {
                return modal.querySelectorAll(
                    'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
                );
            }
            
            function trapFocus(e) {
                if (!modal.classList.contains('open')) return;
                
                const focusable = getFocusableElements();
                if (!focusable.length) return;
                
                const first = focusable[0];
                const last = focusable[focusable.length - 1];
                
                if (e.key === 'Tab') {
                    if (e.shiftKey) {
                        if (document.activeElement === first) {
                            e.preventDefault();
                            last.focus();
                        }
                    } else {
                        if (document.activeElement === last) {
                            e.preventDefault();
                            first.focus();
                        }
                    }
                }
            }
            
            function openModal() {
                previousActive = document.activeElement;
                modal.classList.add('open');
                modal.setAttribute('aria-hidden', 'false');
                modal.setAttribute('aria-modal', 'true');
                
                // Focus first interactive element
                setTimeout(() => {
                    const focusable = getFocusableElements();
                    if (focusable.length > 0) focusable[0].focus();
                }, 50);
                
                document.addEventListener('keydown', trapFocus);
                document.body.style.overflow = 'hidden';
            }
            
            function closeModal() {
                modal.classList.remove('open');
                modal.setAttribute('aria-hidden', 'true');
                modal.setAttribute('aria-modal', 'false');
                document.removeEventListener('keydown', trapFocus);
                document.body.style.overflow = '';
                
                if (previousActive && typeof previousActive.focus === 'function') {
                    previousActive.focus();
                }
                
                // Reset form state
                if (telemetryCheckbox) telemetryCheckbox.checked = false;
                if (consentCheckbox) consentCheckbox.checked = false;
                if (successEl) successEl.style.display = 'none';
                if (confirmBtn) {
                    confirmBtn.disabled = false;
                    confirmBtn.textContent = 'Confirm Opt-in';
                }
                if (declineBtn) declineBtn.disabled = false;
            }
            
            openBtn.addEventListener('click', (e) => {
                e.preventDefault();
                openModal();
            });
            
            overlay.addEventListener('click', closeModal);
            closeBtn.addEventListener('click', closeModal);
            declineBtn.addEventListener('click', closeModal);
            
            // Close on escape
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape' && modal.classList.contains('open')) {
                    closeModal();
                }
            });
            
            confirmBtn.addEventListener('click', () => {
                // Require both boxes for a clear consent flow
                if (!telemetryCheckbox.checked || !consentCheckbox.checked) {
                    confirmBtn.textContent = 'Please check both boxes';
                    confirmBtn.disabled = true;
                    setTimeout(() => {
                        confirmBtn.textContent = 'Confirm Opt-in';
                        confirmBtn.disabled = false;
                    }, 1600);
                    return;
                }
                
                // Show success state
                successEl.style.display = 'block';
                telemetryCheckbox.disabled = true;
                consentCheckbox.disabled = true;
                confirmBtn.disabled = true;
                declineBtn.disabled = true;
                
                // In a real app, we'd post to an API here
                console.log('Opt-in confirmed:', {
                    telemetry: telemetryCheckbox.checked,
                    terms: consentCheckbox.checked,
                    timestamp: new Date().toISOString()
                });
                
                // Close after delay
                setTimeout(() => {
                    closeModal();
                }, 1600);
            });
            
            // Cleanup
            cleanupFunctions.push(() => {
                openBtn.removeEventListener('click', openModal);
                overlay.removeEventListener('click', closeModal);
                closeBtn.removeEventListener('click', closeModal);
                declineBtn.removeEventListener('click', closeModal);
                document.removeEventListener('keydown', trapFocus);
            });
        }

        function setupSmoothScroll() {
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        const headerHeight = document.querySelector('header').offsetHeight;
                        const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset - headerHeight;
                        
                        window.scrollTo({
                            top: targetPosition,
                            behavior: 'smooth'
                        });
                        
                        // Update URL without scrolling
                        history.pushState(null, null, targetId);
                    }
                });
            });
        }

        function setupImageLoading() {
            const images = document.querySelectorAll('img[loading="lazy"]');
            if ('loading' in HTMLImageElement.prototype) {
                // Browser supports native lazy loading
                return;
            }
            
            // Fallback for browsers without native lazy loading
            const imageObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const img = entry.target;
                        img.src = img.dataset.src;
                        if (img.dataset.srcset) {
                            img.srcset = img.dataset.srcset;
                        }
                        imageObserver.unobserve(img);
                    }
                });
            });
            
            images.forEach(img => {
                if (img.dataset.src) {
                    imageObserver.observe(img);
                }
            });
            
            cleanupFunctions.push(() => imageObserver.disconnect());
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', () => {
            try {
                setupMobileMenu();
                setupFeatureInteractions();
                setupSolutionInteractions();
                setupHeaderScroll();
                setupOptinModal();
                setupSmoothScroll();
                setupImageLoading();
                
                // Initial reveal
                revealOnScroll();
                updateScrollProgress();
                
                // Set up scroll listeners
                window.addEventListener('scroll', () => {
                    revealOnScroll();
                    updateScrollProgress();
                });
                
                // Clean up on page unload
                window.addEventListener('beforeunload', () => {
                    cleanupFunctions.forEach(cleanup => {
                        if (typeof cleanup === 'function') cleanup();
                    });
                });
                
                // Start typewriter with delay
                setTimeout(revealOnScroll, 100);
                
            } catch (error) {
                console.error('Error during initialization:', error);
            }
        });

        // Handle window resize for typewriter
        window.addEventListener('resize', () => {
            const typewriterText = document.getElementById('typewriter-text');
            if (typewriterText && window.innerWidth <= 768) {
                typewriterText.style.animation = 'none';
                typewriterText.style.borderRight = 'none';
            }
        });
    </script>
</body>
</html>
