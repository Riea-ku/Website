<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Improved Full-Page Layout</title>

    <!-- FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

    <style>
        /* ------------------ GLOBAL STYLES ------------------ */
        :root {
            --purple: #6a00ff;
            --purple-light: #9b4dff;
            --dark: #0f0f17;
            --gray: #1a1a26;
            --text-light: #e6e6ff;
            --text-muted: #b9b9d4;
        }

        body {
            margin: 0;
            background: var(--dark);
            color: var(--text-light);
            font-family: "Inter", sans-serif;
            overflow-x: hidden;
        }

        h1, h2, h3 {
            margin: 0;
            font-weight: 700;
        }

        /* ------------------ FULL PAGE SECTIONS ------------------ */
        section {
            width: 100%;
            padding: 100px 60px;
        }

        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #6a00ff55, #00000055);
            text-align: center;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-muted);
        }

        /* ------------------ ICON GRID ------------------ */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
            grid-gap: 40px;
            width: 100%;
            margin-top: 60px;
        }

        .icon-box {
            background: var(--gray);
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            cursor: pointer;
            transition: 0.3s ease;
            position: relative;
        }

        .icon-box i {
            font-size: 2.6rem;
            margin-bottom: 15px;
            display: block;
            color: var(--purple-light);
        }

        .icon-box h3 {
            font-size: 1.2rem;
        }

        .icon-box.dimmed {
            opacity: 0.25;
            filter: blur(1px);
        }

        .icon-box.active {
            outline: 2px solid var(--purple);
            outline-offset: 5px;
            transform: scale(1.05);
        }

        /* ------------------ CENTER POPUP ------------------ */
        .popup-box {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.7);
            background: #0d0d14;
            padding: 40px;
            width: 480px;
            max-width: 90%;
            border-radius: 20px;
            box-shadow: 0 25px 80px rgba(0,0,0,0.7);
            opacity: 0;
            pointer-events: none;
            transition: 0.25s ease;
            z-index: 999;
        }

        .popup-box.visible {
            opacity: 1;
            transform: translate(-50%, -50%) scale(1);
            pointer-events: auto;
        }

        .popup-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            gap: 15px;
        }

        .popup-icon i {
            font-size: 2.2rem;
            color: var(--purple-light);
        }

        .popup-title {
            font-size: 1.5rem;
        }

        .popup-desc {
            margin-top: 10px;
            color: var(--text-muted);
            line-height: 1.5;
        }

        /* ------------------ OVERLAY ------------------ */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.55);
            opacity: 0;
            pointer-events: none;
            transition: 0.25s;
            z-index: 998;
        }

        .overlay.visible {
            opacity: 1;
            pointer-events: auto;
        }

        /* ------------------ MOBILE ------------------ */
        @media (max-width: 700px) {
            .hero h1 {
                font-size: 2.6rem;
            }
        }
    </style>
</head>

<body>

    <!-- ------------------ HERO ------------------ -->
    <section class="hero">
        <div>
            <h1>Your AI Platform</h1>
            <p>The intelligent system that predicts failures, optimizes operations, and automates workflows.</p>
        </div>
    </section>

    <!-- ------------------ FEATURES ------------------ -->
    <section>
        <h2>Features</h2>

        <div class="grid">

            <div class="icon-box" data-popup data-title="Predictive Failure Detection" data-desc="Uses AI to detect anomalies and predict breakdowns before they occur." data-icon="brain">
                <i class="fas fa-brain"></i>
                <h3>Predictive Failure Detection</h3>
            </div>

            <div class="icon-box" data-popup data-title="Real-Time Monitoring" data-desc="Live dashboards give continuous insights into your system’s performance." data-icon="gauge-high">
                <i class="fas fa-gauge-high"></i>
                <h3>Real-Time Monitoring</h3>
            </div>

            <div class="icon-box" data-popup data-title="Smart Reporting" data-desc="Automatically generates actionable reports based on real machine data." data-icon="chart-line">
                <i class="fas fa-chart-line"></i>
                <h3>Smart Reporting</h3>
            </div>

        </div>
    </section>

    <!-- ------------------ SOLUTIONS ------------------ -->
    <section>
        <h2>Solutions</h2>

        <div class="grid">

            <div class="icon-box" data-popup data-title="Manufacturing AI" data-desc="Optimize production, reduce downtime, and automate diagnostics." data-icon="industry">
                <i class="fas fa-industry"></i>
                <h3>Manufacturing AI</h3>
            </div>

            <div class="icon-box" data-popup data-title="Energy Optimization" data-desc="Smart energy usage predictions and consumption modeling." data-icon="bolt">
                <i class="fas fa-bolt"></i>
                <h3>Energy Optimization</h3>
            </div>

            <div class="icon-box" data-popup data-title="Automation Tools" data-desc="Powerful no-code tools to automate workflows across systems." data-icon="robot">
                <i class="fas fa-robot"></i>
                <h3>Automation Tools</h3>
            </div>

        </div>
    </section>

    <!-- ------------------ POPUP + OVERLAY ------------------ -->
    <div class="overlay" id="overlay"></div>

    <div class="popup-box" id="popup">
        <div class="popup-header">
            <div class="popup-icon"></div>
            <h3 class="popup-title"></h3>
        </div>
        <p class="popup-desc"></p>
    </div>

    <!-- ------------------ JS ------------------ -->
    <script>
        const icons = document.querySelectorAll("[data-popup]");
        const popup = document.getElementById("popup");
        const overlay = document.getElementById("overlay");

        icons.forEach(icon => {
            icon.addEventListener("mouseenter", () => {
                const title = icon.dataset.title;
                const desc = icon.dataset.desc;
                const symbol = icon.dataset.icon;

                // Fill popup
                popup.querySelector(".popup-title").textContent = title;
                popup.querySelector(".popup-desc").textContent = desc;
                popup.querySelector(".popup-icon").innerHTML = `<i class="fas fa-${symbol}"></i>`;

                // Dim others
                icons.forEach(i => {
                    if (i !== icon) i.classList.add("dimmed");
                });

                icon.classList.add("active");

                // Show popup + overlay
                popup.classList.add("visible");
                overlay.classList.add("visible");
            });

            icon.addEventListener("mouseleave", () => {
                icons.forEach(i => i.classList.remove("dimmed", "active"));
            });
        });

        // Close popup when clicking outside
        overlay.addEventListener("click", () => {
            popup.classList.remove("visible");
            overlay.classList.remove("visible");
            icons.forEach(i => i.classList.remove("dimmed", "active"));
        });
    </script>

</body>
</html>
