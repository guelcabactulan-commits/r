<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    Elano Miguel C. | Deep Space Portal</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@200;400;700&family=Syncopate:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-black: #000002;
            --neon-cyan: #00f2ff;
            --deep-blue: #050a1a;
            --glass: rgba(0, 242, 255, 0.03);
            --border: rgba(0, 242, 255, 0.2);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; cursor: crosshair; }

        body {
            background-color: var(--bg-black);
            color: #fff;
            font-family: 'Montserrat', sans-serif;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            background-image: 
                radial-gradient(1.5px 1.5px at 20% 30%, #fff, transparent),
                radial-gradient(1px 1px at 70% 80%, #fff, transparent),
                radial-gradient(2px 2px at 10% 90%, rgba(0, 242, 255, 0.2), transparent);
        }

        /* SCANLINE EFFECT */
        body::before {
            content: " ";
            display: block;
            position: absolute;
            top: 0; left: 0; bottom: 0; right: 0;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.15) 50%), 
                        linear-gradient(90deg, rgba(255, 0, 0, 0.02), rgba(0, 255, 0, 0.01), rgba(0, 0, 255, 0.02));
            z-index: 500;
            background-size: 100% 3px, 3px 100%;
            pointer-events: none;
        }

        .viewport-container {
            width: 390px;
            height: 800px;
            background: radial-gradient(circle at center, var(--deep-blue) 0%, var(--bg-black) 100%);
            border: 1px solid var(--border);
            border-radius: 35px;
            position: relative;
            display: flex;
            flex-direction: column;
            box-shadow: 0 0 60px rgba(0, 242, 255, 0.1);
            overflow: hidden;
        }

        /* NAVIGATION */
        nav { 
            padding: 40px 20px 20px; 
            display: flex; 
            justify-content: space-around; 
            z-index: 100;
            border-bottom: 1px solid var(--border);
        }
        .nav-link { 
            font-size: 9px; letter-spacing: 4px; color: var(--neon-cyan); 
            text-transform: uppercase; font-weight: 400; cursor: pointer;
        }

        /* PAGES */
        .page {
            position: absolute;
            top: 100px; left: 0; width: 100%; height: calc(100% - 100px);
            padding: 30px;
            transition: 0.6s cubic-bezier(0.19, 1, 0.22, 1);
        }
        .hidden { opacity: 0; transform: translateX(30px); pointer-events: none; }
        .active { opacity: 1; transform: translateX(0); z-index: 10; }

        /* CONTENT STYLES */
        .label { font-size: 8px; color: var(--neon-cyan); letter-spacing: 5px; text-transform: uppercase; margin-bottom: 10px; opacity: 0.7; }
        .title { font-family: 'Syncopate', sans-serif; font-size: 20px; line-height: 1.2; }
        
        .glass-panel {
            background: var(--glass);
            border-left: 1px solid var(--neon-cyan);
            padding: 20px;
            margin-bottom: 30px;
            backdrop-filter: blur(10px);
        }

        .data-row { display: flex; justify-content: space-between; font-size: 11px; padding: 10px 0; border-bottom: 1px solid rgba(0,242,255,0.05); }

        /* EXPLORE BOXES */
        .explore-card {
            background: rgba(255,255,255,0.02);
            border: 1px solid rgba(0, 242, 255, 0.1);
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 15px;
            cursor: pointer;
            transition: 0.3s;
        }
        .explore-card:hover { border-color: var(--neon-cyan); background: rgba(0, 242, 255, 0.05); }
        .explore-card h3 { font-size: 14px; color: var(--neon-cyan); margin-bottom: 5px; font-family: 'Syncopate'; }
        .explore-card p { font-size: 10px; color: #777; }

        /* DETAIL PAGES */
        .back-btn {
            font-size: 9px; color: var(--neon-cyan); text-transform: uppercase;
            margin-bottom: 20px; cursor: pointer; display: inline-block;
            border: 1px solid var(--neon-cyan); padding: 5px 10px; border-radius: 5px;
        }
        .detail-text { font-size: 13px; line-height: 1.8; color: #ccc; margin-top: 20px; }

        /* COMMS */
        .gmail-trigger {
            display: flex; flex-direction: column; align-items: center;
            text-decoration: none; color: #fff; margin-top: 40px;
        }
        .icon-ring {
            width: 50px; height: 50px; border: 1px dashed var(--neon-cyan);
            border-radius: 50%; display: flex; justify-content: center; align-items: center;
            margin-bottom: 10px; transition: 0.8s;
        }
        .gmail-trigger:hover .icon-ring { transform: rotate(180deg); box-shadow: 0 0 20px var(--neon-cyan); }
    </style>
</head>
<body>

    <div class="viewport-container">
        <nav>
            <div class="nav-link" onclick="showPage('intro')">// INTRO</div>
            <div class="nav-link" onclick="showPage('explore')">// EXPLORE</div>
        </nav>

        <div id="intro" class="page active">
            <p class="label">Identity Terminal</p>
            <h1 class="title">ELANO <br> MIGUEL C.</h1>
            
            <div class="glass-panel" style="margin-top: 30px;">
                <div class="data-row"><span>AGE</span><span>14</span></div>
                <div class="data-row"><span>SECTOR</span><span>Pandi, Bulacan</span></div>
                <div class="data-row"><span>PASSION</span><span>Astronomics</span></div>
            </div>

            <p style="font-size: 11px; color: #888; line-height: 1.8;">
                Scanning the stars from the Philippines. Engineering logic to bridge the gap between Earth and the cosmos.
            </p>

            <a href="mailto:guelcabactulan@gmail.com" class="gmail-trigger">
                <div class="icon-ring">✉</div>
                <span class="label">guelcabactulan@gmail.com</span>
            </a>
        </div>

        <div id="explore" class="page hidden">
            <p class="label">Mission Sectors</p>
            <h1 class="title" style="margin-bottom: 30px;">EXPLORATION</h1>

            <div class="explore-card" onclick="showPage('astro-detail')">
                <h3>ASTRONOMY</h3>
                <p>Click to expand celestial data and passion.</p>
            </div>

            <div class="explore-card" onclick="showPage('robo-detail')">
                <h3>ROBOTICS</h3>
                <p>Click to expand mechanical logic and design.</p>
            </div>
        </div>

        <div id="astro-detail" class="page hidden">
            <div class="back-btn" onclick="showPage('explore')">← Back to Explore</div>
            <h1 class="title" style="color: var(--neon-cyan);">ASTRO<br>NOMICS</h1>
            <p class="detail-text">
                Astronomy is my window to the infinite. I am fascinated by how our universe is composed of mathematical patterns. From Pandi, Bulacan, I look at the stars and wonder about the physics of black holes, the lifecycle of stars, and the possibility of life beyond our atmosphere. It's not just a hobby; it's a mission to understand where we come from.
            </p>
        </div>

        <div id="robo-detail" class="page hidden">
            <div class="back-btn" onclick="showPage('explore')">← Back to Explore</div>
            <h1 class="title" style="color: var(--neon-cyan);">ROBO<br>TICS</h1>
            <p class="detail-text">
                Robotics is how we touch the stars. I focus on building autonomous systems—machines that can think and survive in the harsh environments of space. For a 14-year-old, the challenge is in the code. I aim to develop rovers that can navigate Martian soil or icy moons without human help, using precision and logic.
            </p>
        </div>

    </div>

    <script>
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
                page.classList.add('hidden');
            });
            const selected = document.getElementById(pageId);
            selected.classList.remove('hidden');
            selected.classList.add('active');
        }
    </script>
</body>
</html>
