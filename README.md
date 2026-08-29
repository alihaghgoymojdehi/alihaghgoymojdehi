<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ali.dev — Developer Profile</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&display=swap" rel="stylesheet">

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg: #020609;
            --panel: #050b0f;
            --panel-2: #071116;
            --border: #12323b;
            --text: #e8f1f3;
            --muted: #769099;
            --green: #00e887;
            --cyan: #00d9ff;
            --purple: #9b7cff;
        }

        body {
            min-height: 100vh;
            background:
                radial-gradient(circle at 80% 0%, rgba(0, 217, 255, .07), transparent 30%),
                radial-gradient(circle at 10% 50%, rgba(0, 232, 135, .035), transparent 25%),
                var(--bg);
            color: var(--text);
            font-family: "JetBrains Mono", monospace;
            padding: 30px 20px;
        }

        body::before {
            content: "";
            position: fixed;
            inset: 0;
            pointer-events: none;
            opacity: .25;
            background-image:
                linear-gradient(rgba(255,255,255,.015) 1px, transparent 1px),
                linear-gradient(90deg, rgba(255,255,255,.015) 1px, transparent 1px);
            background-size: 40px 40px;
        }

        .container {
            width: min(1100px, 100%);
            margin: auto;
            border: 1px solid var(--border);
            border-radius: 14px;
            overflow: hidden;
            background: rgba(2, 7, 10, .88);
            box-shadow:
                0 0 80px rgba(0, 217, 255, .025),
                inset 0 0 80px rgba(0, 232, 135, .015);
        }

        /* HEADER */

        header {
            height: 66px;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 25px;
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 14px;
            font-size: 19px;
            font-weight: 700;
        }

        .terminal-icon {
            width: 35px;
            height: 35px;
            display: grid;
            place-items: center;
            border-radius: 6px;
            background: #07151b;
            color: var(--green);
            border: 1px solid #0c2931;
            font-size: 18px;
        }

        .brand span {
            color: var(--cyan);
        }

        .available {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--green);
            font-size: 13px;
        }

        .dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: var(--green);
            box-shadow: 0 0 12px var(--green);
            animation: pulse 1.8s infinite;
        }

        @keyframes pulse {
            50% {
                opacity: .35;
            }
        }

        /* HERO */

        .hero {
            padding: 55px 42px 35px;
            display: grid;
            grid-template-columns: 1.2fr .8fr;
            gap: 30px;
            position: relative;
        }

        .hero::after {
            content: "</>";
            position: absolute;
            right: 45px;
            top: 30px;
            font-size: 150px;
            font-weight: 700;
            color: rgba(0, 217, 255, .025);
            pointer-events: none;
        }

        .hero h1 {
            direction: ltr;
            text-align: left;
            font-size: clamp(32px, 5vw, 55px);
            line-height: 1.15;
            letter-spacing: -2px;
            max-width: 650px;
        }

        .hero h1::before {
            content: "> ";
            color: var(--green);
        }

        .hero-sub {
            margin-top: 25px;
            color: var(--cyan);
            font-size: 16px;
            direction: ltr;
            text-align: left;
        }

        .skills-line {
            margin-top: 10px;
            color: #a5b8be;
            font-size: 14px;
            direction: ltr;
            text-align: left;
        }

        .buttons {
            margin-top: 30px;
            display: flex;
            gap: 12px;
            direction: ltr;
        }

        .btn {
            border: 1px solid var(--border);
            background: #061016;
            color: #cce4e9;
            padding: 12px 20px;
            border-radius: 6px;
            text-decoration: none;
            font-size: 13px;
            transition: .2s;
        }

        .btn:hover {
            border-color: var(--cyan);
            color: var(--cyan);
            box-shadow: 0 0 20px rgba(0, 217, 255, .08);
            transform: translateY(-2px);
        }

        .btn.primary {
            border-color: var(--green);
            color: var(--green);
        }

        /* STATS */

        .stats {
            grid-column: 1 / -1;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            border-top: 1px solid var(--border);
            padding-top: 25px;
            margin-top: 5px;
        }

        .stat {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 0 25px;
            border-left: 1px solid var(--border);
        }

        .stat:first-child {
            border-left: 0;
        }

        .stat-icon {
            color: var(--cyan);
            font-size: 22px;
        }

        .stat-number {
            font-size: 20px;
            color: #fff;
        }

        .stat-label {
            margin-top: 5px;
            color: var(--muted);
            font-size: 11px;
        }

        /* TERMINAL */

        .terminal {
            margin: 0 22px 22px;
            border: 1px solid var(--border);
            border-radius: 7px;
            overflow: hidden;
            background: #02080b;
        }

        .terminal-head {
            height: 40px;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 15px;
            color: var(--green);
            font-size: 12px;
            direction: ltr;
        }

        .traffic {
            display: flex;
            gap: 8px;
        }

        .traffic i {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: #28353a;
        }

        .terminal-body {
            padding: 22px;
            display: grid;
            grid-template-columns: 1fr .9fr;
            min-height: 250px;
        }

        .code {
            direction: ltr;
            text-align: left;
            line-height: 1.9;
            font-size: 13px;
        }

        .prompt {
            color: var(--green);
        }

        .comment {
            color: var(--muted);
        }

        .highlight {
            color: var(--cyan);
        }

        .progress {
            display: inline-flex;
            gap: 2px;
            margin-left: 8px;
        }

        .progress i {
            display: block;
            width: 9px;
            height: 12px;
            background: var(--green);
        }

        .progress i.off {
            background: #172329;
        }

        .workstation {
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 100px;
            opacity: .18;
            color: var(--cyan);
        }

        /* GRID */

        .grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 22px;
            padding: 0 22px 22px;
        }

        .panel {
            border: 1px solid var(--border);
            border-radius: 7px;
            overflow: hidden;
            background: rgba(4, 12, 16, .7);
        }

        .panel-title {
            height: 42px;
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 0 17px;
            border-bottom: 1px solid var(--border);
            font-size: 12px;
            direction: ltr;
        }

        .panel-title span {
            color: var(--cyan);
        }

        /* STACK */

        .stack {
            padding: 20px;
        }

        .tech {
            display: grid;
            grid-template-columns: 115px 1fr 35px;
            gap: 10px;
            align-items: center;
            margin-bottom: 17px;
            direction: ltr;
            font-size: 12px;
        }

        .bar {
            height: 9px;
            background: #17252b;
            border-radius: 2px;
            overflow: hidden;
        }

        .bar i {
            display: block;
            height: 100%;
            background: linear-gradient(90deg, #00a86b, var(--green));
        }

        .percentage {
            color: var(--muted);
            text-align: right;
        }

        /* PROJECTS */

        .project {
            padding: 18px;
            border-bottom: 1px solid var(--border);
            display: flex;
            gap: 15px;
            direction: ltr;
            transition: .2s;
        }

        .project:last-child {
            border-bottom: 0;
        }

        .project:hover {
            background: rgba(0, 217, 255, .025);
        }

        .project-icon {
            width: 52px;
            height: 52px;
            flex: 0 0 52px;
            border: 1px solid #17424d;
            border-radius: 8px;
            display: grid;
            place-items: center;
            color: var(--cyan);
            font-size: 23px;
        }

        .project h3 {
            color: var(--cyan);
            font-size: 15px;
            margin-bottom: 5px;
        }

        .project small {
            color: #b0c0c4;
            font-size: 11px;
        }

        .project p {
            color: var(--muted);
            font-size: 10px;
            line-height: 1.7;
            margin: 7px 0;
        }

        .tags {
            display: flex;
            gap: 5px;
            flex-wrap: wrap;
        }

        .tag {
            border: 1px solid #17343d;
            padding: 3px 7px;
            border-radius: 3px;
            color: #80aab4;
            font-size: 9px;
        }

        /* ACTIVITY */

        .activity {
            padding: 20px;
        }

        .heatmap {
            display: grid;
            grid-template-columns: repeat(24, 1fr);
            gap: 4px;
            direction: ltr;
        }

        .heatmap i {
            aspect-ratio: 1;
            border-radius: 2px;
            background: #10252b;
        }

        .heatmap i:nth-child(3n) {
            background: #07583e;
        }

        .heatmap i:nth-child(5n) {
            background: #009f67;
        }

        .heatmap i:nth-child(7n) {
            background: var(--green);
        }

        .activity-footer {
            margin-top: 15px;
            display: flex;
            justify-content: space-between;
            color: var(--muted);
            font-size: 10px;
        }

        /* STATUS */

        .status {
            padding: 25px;
            min-height: 150px;
            display: flex;
            align-items: center;
            justify-content: center;
            direction: ltr;
            text-align: left;
        }

        .status code {
            font-size: 13px;
            line-height: 2;
        }

        .purple {
            color: var(--purple);
        }

        .yellow {
            color: #ffd34e;
        }

        .orange {
            color: #ff7347;
        }

        /* FOOTER */

        footer {
            margin: 0 22px;
            border: 1px solid var(--border);
            border-radius: 6px 6px 0 0;
            padding: 18px 22px;
            display: flex;
            justify-content: space-between;
            color: var(--muted);
            font-size: 10px;
            direction: ltr;
        }

        footer span {
            color: #b4c8cd;
        }

        @media (max-width: 800px) {
            body {
                padding: 10px;
            }

            .hero {
                grid-template-columns: 1fr;
                padding: 40px 25px 25px;
            }

            .stats {
                grid-template-columns: repeat(2, 1fr);
                gap: 20px;
            }

            .stat {
                border-left: 0;
            }

            .terminal-body {
                grid-template-columns: 1fr;
            }

            .workstation {
                display: none;
            }

            .grid {
                grid-template-columns: 1fr;
            }

            footer {
                flex-direction: column;
                gap: 10px;
            }
        }

        @media (max-width: 500px) {
            .available {
                display: none;
            }

            .stats {
                grid-template-columns: 1fr 1fr;
            }

            .buttons {
                flex-wrap: wrap;
            }

            .heatmap {
                gap: 2px;
            }

            .tech {
                grid-template-columns: 95px 1fr 30px;
            }
        }
    </style>
</head>

<body>

<div class="container">

    <!-- HEADER -->
    <header>
        <div class="brand">
            <div class="terminal-icon">›_</div>
            ALI<span>.DEV</span>
        </div>

        <div class="available">
            <i class="dot"></i>
            AVAILABLE FOR WORK
        </div>
    </header>


    <!-- HERO -->
    <section class="hero">

        <div>
            <h1>I build things<br>for the web.</h1>

            <div class="hero-sub">
                Full-Stack Developer
            </div>

            <div class="skills-line">
                PHP · WordPress · JavaScript · UI/UX
            </div>

            <div class="buttons">
                <a href="#" class="btn primary">◉ GITHUB</a>
                <a href="#projects" class="btn">⌁ PROJECTS</a>
                <a href="#" class="btn">✉ CONTACT</a>
            </div>
        </div>

        <!-- STATS -->
        <div class="stats">

            <div class="stat">
                <div class="stat-icon">▣</div>
                <div>
                    <div class="stat-number">27</div>
                    <div class="stat-label">Repositories</div>
                </div>
            </div>

            <div class="stat">
                <div class="stat-icon">〽</div>
                <div>
                    <div class="stat-number">1.2k+</div>
                    <div class="stat-label">Contributions</div>
                </div>
            </div>

            <div class="stat">
                <div class="stat-icon">♧</div>
                <div>
                    <div class="stat-number">42</div>
                    <div class="stat-label">Followers</div>
                </div>
            </div>

            <div class="stat">
                <div class="stat-icon">&lt;/&gt;</div>
                <div>
                    <div class="stat-number">12</div>
                    <div class="stat-label">Projects</div>
                </div>
            </div>

        </div>

    </section>


    <!-- TERMINAL -->
    <section class="terminal">

        <div class="terminal-head">
            <span>›_ terminal</span>

            <div class="traffic">
                <i></i>
                <i></i>
                <i></i>
            </div>
        </div>

        <div class="terminal-body">

            <div class="code">

                <div>
                    <span class="prompt">$ whoami</span>
                </div>

                <div>ali</div>
                <div>web developer</div>

                <br>

                <div>
                    <span class="comment">located_in:</span>
                    Iran
                </div>

                <div>
                    <span class="comment">focus:</span>
                    backend, frontend, devops
                </div>

                <div>
                    <span class="comment">currently_building:</span>
                    <span class="highlight">samlite</span>
                </div>

                <div>
                    <span class="comment">status:</span>

                    <span class="progress">
                        <i></i><i></i><i></i><i></i><i></i>
                        <i></i><i></i><i></i><i></i><i></i>
                        <i></i><i></i><i></i><i></i><i></i>
                        <i></i><i></i><i></i>
                        <i class="off"></i>
                        <i class="off"></i>
                    </span>

                    <span class="highlight">90%</span>
                </div>

                <br>

                <div>
                    <span class="prompt">$</span>
                    <span class="cursor">█</span>
                </div>

            </div>

            <div class="workstation">
                &lt;/&gt;
            </div>

        </div>
    </section>


    <!-- MAIN GRID -->
    <div class="grid">

        <!-- TECH STACK -->
        <section class="panel">

            <div class="panel-title">
                <span>&lt;/&gt;</span>
                TECH STACK
            </div>

            <div class="stack">

                <div class="tech">
                    <span>PHP</span>
                    <div class="bar"><i style="width:95%"></i></div>
                    <span class="percentage">95%</span>
                </div>

                <div class="tech">
                    <span>WordPress</span>
                    <div class="bar"><i style="width:90%"></i></div>
                    <span class="percentage">90%</span>
                </div>

                <div class="tech">
                    <span>JavaScript</span>
                    <div class="bar"><i style="width:85%"></i></div>
                    <span class="percentage">85%</span>
                </div>

                <div class="tech">
                    <span>Tailwind CSS</span>
                    <div class="bar"><i style="width:80%"></i></div>
                    <span class="percentage">80%</span>
                </div>

                <div class="tech">
                    <span>MySQL</span>
                    <div class="bar"><i style="width:75%"></i></div>
                    <span class="percentage">75%</span>
                </div>

                <div class="tech">
                    <span>Linux / Bash</span>
                    <div class="bar"><i style="width:70%"></i></div>
                    <span class="percentage">70%</span>
                </div>

                <div class="tech">
                    <span>Git & GitHub</span>
                    <div class="bar"><i style="width:90%"></i></div>
                    <span class="percentage">90%</span>
                </div>

                <div class="tech">
                    <span>Three.js</span>
                    <div class="bar"><i style="width:65%"></i></div>
                    <span class="percentage">65%</span>
                </div>

            </div>
        </section>


        <!-- PROJECTS -->
        <section class="panel" id="projects">

            <div class="panel-title">
                <span>☆</span>
                FEATURED PROJECTS
            </div>

            <div class="project">

                <div class="project-icon">S</div>

                <div>
                    <h3>SAMLITE</h3>
                    <small>Web Hosting Platform</small>

                    <p>
                        Reseller hosting platform with WHMCS,
                        cPanel integration and custom modules.
                    </p>

                    <div class="tags">
                        <span class="tag">PHP</span>
                        <span class="tag">WHMCS</span>
                        <span class="tag">MySQL</span>
                    </div>
                </div>

            </div>


            <div class="project">

                <div class="project-icon">🤖</div>

                <div>
                    <h3>SAMPLAY BOTS</h3>
                    <small>Telegram Bot Builder</small>

                    <p>
                        No-code bot builder with AI integration,
                        automation and powerful APIs.
                    </p>

                    <div class="tags">
                        <span class="tag">PHP</span>
                        <span class="tag">JavaScript</span>
                        <span class="tag">API</span>
                    </div>
                </div>

            </div>


            <div class="project">

                <div class="project-icon">⌘</div>

                <div>
                    <h3>GAME SERVER</h3>
                    <small>MTA:SA Server</small>

                    <p>
                        Anti-cheat systems and custom scripts
                        for multiplayer game servers.
                    </p>

                    <div class="tags">
                        <span class="tag">Lua</span>
                        <span class="tag">MTA</span>
                        <span class="tag">MySQL</span>
                    </div>
                </div>

            </div>

        </section>


        <!-- ACTIVITY -->
        <section class="panel">

            <div class="panel-title">
                <span>⌁</span>
                GITHUB ACTIVITY
            </div>

            <div class="activity">

                <div class="heatmap">

                    <!-- 96 cells -->
                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>
                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>
                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>

                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>
                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>
                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>

                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>
                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>
                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>

                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>
                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>
                    <i></i><i></i><i></i><i></i><i></i><i></i><i></i><i></i>

                </div>

                <div class="activity-footer">
                    <span>1,238 contributions in the last year</span>
                    <span>Less ░ ▒ ▓ More</span>
                </div>

            </div>

        </section>


        <!-- STATUS -->
        <section class="panel">

            <div class="panel-title">
                <span>◉</span>
                CURRENT STATUS
            </div>

            <div class="status">

                <code>
                    <span class="purple">const</span>
                    success =
                    <span class="purple">()</span>
                    =>
                    <span class="purple">{</span>
                    <br>

                    &nbsp;&nbsp;&nbsp;&nbsp;
                    <span class="yellow">return</span>
                    <span class="orange">'Code. Learn. Build. Repeat.'</span>;
                    <br>

                    <span class="purple">};</span>
                </code>

            </div>

        </section>

    </div>


    <!-- FOOTER -->
    <footer>
        <span>⌖ IRAN</span>
        <span>✉ hello@ali.dev</span>
        <span>⌁ github.com/ali</span>
        <span>Last updated: 2026</span>
    </footer>

</div>

</body>
</html>
