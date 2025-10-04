<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sai Ouldrading - Unity Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0a0e27 0%, #1a1a2e 50%, #16213e 100%);
            color: #fff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow-x: hidden;
        }

        .stars {
            position: fixed;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        .header {
            text-align: center;
            padding: 60px 20px;
            background: linear-gradient(135deg, rgba(0, 217, 255, 0.1), rgba(255, 107, 53, 0.1));
            border-radius: 20px;
            margin-bottom: 40px;
            border: 2px solid rgba(0, 217, 255, 0.3);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(0, 217, 255, 0.1) 0%, transparent 70%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .title {
            font-size: 3.5em;
            font-weight: bold;
            background: linear-gradient(90deg, #00d9ff, #ff6b35, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
            animation: glow 2s ease-in-out infinite;
            position: relative;
            z-index: 1;
        }

        @keyframes glow {
            0%, 100% { filter: drop-shadow(0 0 20px rgba(0, 217, 255, 0.5)); }
            50% { filter: drop-shadow(0 0 40px rgba(0, 217, 255, 0.8)); }
        }

        .subtitle {
            font-size: 1.5em;
            color: #00d9ff;
            margin-bottom: 20px;
            position: relative;
            z-index: 1;
        }

        .typing-text {
            font-size: 1.2em;
            color: #ff6b35;
            min-height: 40px;
            position: relative;
            z-index: 1;
        }

        .section {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
            border: 1px solid rgba(0, 217, 255, 0.2);
            backdrop-filter: blur(10px);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 40px rgba(0, 217, 255, 0.3);
        }

        .section-title {
            font-size: 2em;
            margin-bottom: 20px;
            color: #00d9ff;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .skill-card {
            background: linear-gradient(135deg, rgba(0, 217, 255, 0.1), rgba(255, 107, 53, 0.1));
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            border: 1px solid rgba(0, 217, 255, 0.3);
            transition: all 0.3s;
            cursor: pointer;
        }

        .skill-card:hover {
            transform: scale(1.1);
            box-shadow: 0 0 30px rgba(0, 217, 255, 0.5);
        }

        .skill-icon {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(139, 0, 0, 0.2), rgba(0, 0, 0, 0.3));
            border: 2px solid #ff4444;
            border-radius: 15px;
            padding: 30px;
            margin-top: 20px;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '🧟';
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 4em;
            opacity: 0.1;
        }

        .progress-bar {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            height: 30px;
            margin: 10px 0;
            overflow: hidden;
            position: relative;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #00d9ff, #ff6b35);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            transition: width 2s ease;
        }

        .character-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .character-card {
            background: linear-gradient(135deg, rgba(0, 217, 255, 0.1), rgba(255, 107, 53, 0.1));
            border-radius: 15px;
            padding: 25px;
            border: 2px solid rgba(0, 217, 255, 0.3);
            transition: all 0.3s;
        }

        .character-card:hover {
            transform: translateY(-10px);
            border-color: #00d9ff;
            box-shadow: 0 10px 40px rgba(0, 217, 255, 0.4);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .stat-card {
            background: rgba(0, 217, 255, 0.1);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            border: 1px solid rgba(0, 217, 255, 0.3);
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: bold;
            color: #00d9ff;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .social-btn {
            padding: 15px 30px;
            border-radius: 10px;
            text-decoration: none;
            color: white;
            font-weight: bold;
            transition: all 0.3s;
            border: 2px solid;
        }

        .social-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 0 20px currentColor;
        }

        .linkedin { background: #0077B5; border-color: #0077B5; }
        .instagram { background: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%); border-color: #e6683c; }
        .github { background: #181717; border-color: #181717; }
        .email { background: #D14836; border-color: #D14836; }

        .quote {
            text-align: center;
            font-size: 1.5em;
            font-style: italic;
            color: #ffd700;
            margin: 40px 0;
            padding: 30px;
            background: rgba(255, 215, 0, 0.1);
            border-radius: 15px;
            border-left: 5px solid #ffd700;
        }

        .footer {
            text-align: center;
            padding: 40px;
            margin-top: 40px;
            border-top: 2px solid rgba(0, 217, 255, 0.3);
        }

        @media (max-width: 768px) {
            .title { font-size: 2em; }
            .section-title { font-size: 1.5em; }
            .skills-grid { grid-template-columns: repeat(auto-fit, minmax(120px, 1fr)); }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    
    <div class="container">
        <div class="header">
            <div class="title">👋 SAI OULDRADING</div>
            <div class="subtitle">Senior Unity Developer & Technical Architect</div>
            <div class="typing-text" id="typing"></div>
        </div>

        <div class="section">
            <div class="section-title">⚡ Technical Arsenal</div>
            <div class="skills-grid">
                <div class="skill-card"><div class="skill-icon">🎮</div>Unity Engine</div>
                <div class="skill-card"><div class="skill-icon">💻</div>C# Expert</div>
                <div class="skill-card"><div class="skill-icon">🔥</div>C++</div>
                <div class="skill-card"><div class="skill-icon">🐍</div>Python</div>
                <div class="skill-card"><div class="skill-icon">🎨</div>Blender</div>
                <div class="skill-card"><div class="skill-icon">📐</div>Cinema 4D</div>
                <div class="skill-card"><div class="skill-icon">🖼️</div>Photoshop</div>
                <div class="skill-card"><div class="skill-icon">🌐</div>AWS</div>
                <div class="skill-card"><div class="skill-icon">🔗</div>Git/GitHub</div>
                <div class="skill-card"><div class="skill-icon">📊</div>Jira/Trello</div>
                <div class="skill-card"><div class="skill-icon">🎯</div>Photon</div>
                <div class="skill-card"><div class="skill-icon">✨</div>After Effects</div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">🚀 Flagship Project: ASHES OF US</div>
            <div class="project-card">
                <h3 style="color: #ff4444; font-size: 1.8em; margin-bottom: 15px;">🧟‍♂️ ASHES OF US 🧟‍♀️</h3>
                <p style="font-size: 1.2em; font-style: italic; margin-bottom: 20px;">"When humanity falls, two souls must rise..."</p>
                <p style="margin-bottom: 20px;">Post-Apocalyptic Survival Horror | 2D Story-Driven | Unity 2022 LTS</p>
                
                <div style="margin-top: 30px;">
                    <h4 style="color: #00d9ff; margin-bottom: 15px;">Development Progress:</h4>
                    
                    <div>Core Gameplay Framework<div class="progress-bar"><div class="progress-fill" style="width: 100%">100%</div></div></div>
                    <div>Character Controller System<div class="progress-bar"><div class="progress-fill" style="width: 100%">100%</div></div></div>
                    <div>Advanced AI Behavior Trees<div class="progress-bar"><div class="progress-fill" style="width: 65%">65%</div></div></div>
                    <div>Dynamic Dialogue System<div class="progress-bar"><div class="progress-fill" style="width: 100%">100%</div></div></div>
                    <div>Procedural Environment<div class="progress-bar"><div class="progress-fill" style="width: 70%">70%</div></div></div>
                    <div>Combat & Gore System<div class="progress-bar"><div class="progress-fill" style="width: 55%">55%</div></div></div>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">👥 Character System</div>
            <div class="character-grid">
                <div class="character-card">
                    <h3 style="color: #00d9ff; margin-bottom: 15px;">🛡️ RIVEN - The Tactical Guardian</h3>
                    <p><strong>Role:</strong> Primary Combat & Strategy</p>
                    <p><strong>Specialization:</strong> Military Tactics, Weapon Mastery</p>
                    <p><strong>Focus:</strong> AI-driven combat behaviors</p>
                    <p style="margin-top: 15px; font-style: italic; color: #ffd700;">"Military precision meets survival instinct"</p>
                </div>
                <div class="character-card">
                    <h3 style="color: #ff6b35; margin-bottom: 15px;">❤️ THEO - The Emotional Anchor</h3>
                    <p><strong>Role:</strong> Narrative Driver & Support</p>
                    <p><strong>Specialization:</strong> Story Progression, Team Morale</p>
                    <p><strong>Focus:</strong> Dynamic dialogue systems</p>
                    <p style="margin-top: 15px; font-style: italic; color: #ffd700;">"Hope in the darkest times"</p>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">📊 Professional Metrics</div>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number">45+</div>
                    <div>Weekly Commits</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">98%</div>
                    <div>Bug Resolution</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">18</div>
                    <div>Months Dev Cycle</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">100%</div>
                    <div>Passion Level</div>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">🏆 Inspiration Sources</div>
            <div class="skills-grid">
                <div class="skill-card"><div class="skill-icon">🧟</div>Dying Light</div>
                <div class="skill-card"><div class="skill-icon">🤠</div>Red Dead 2</div>
                <div class="skill-card"><div class="skill-icon">💔</div>The Last of Us</div>
                <div class="skill-card"><div class="skill-icon">🌃</div>Cyberpunk 2077</div>
                <div class="skill-card"><div class="skill-icon">🗺️</div>Uncharted</div>
                <div class="skill-card"><div class="skill-icon">⚔️</div>God of War</div>
            </div>
        </div>

        <div class="quote">
            "Code is poetry written in logic. Every bug is a puzzle waiting to be solved. Dream in code, build in reality." 💫
        </div>

        <div class="section">
            <div class="section-title">🤝 Connect & Collaborate</div>
            <div class="social-links">
                <a href="https://www.linkedin.com/in/muhammad-saim-a26349358/" class="social-btn linkedin">LinkedIn</a>
                <a href="https://www.instagram.com/saimk.k18/" class="social-btn instagram">Instagram</a>
                <a href="https://github.com/saiouldrading" class="social-btn github">GitHub</a>
                <a href="mailto:Ouldrading@gmail.com" class="social-btn email">Email</a>
            </div>
            <div style="text-align: center; margin-top: 30px;">
                <p style="font-size: 1.2em; color: #00d9ff;">🌟 Open For:</p>
                <p style="margin-top: 10px;">Game Jams • Creative Projects • Technical Collaborations • Startup Ideas</p>
            </div>
        </div>

        <div class="footer">
            <h2 style="color: #00d9ff; margin-bottom: 20px;">🎯 Building tomorrow's gaming experiences, one line of code at a time!</h2>
            <p style="color: #ffd700; font-size: 1.2em;">⭐ Keep pushing the boundaries! ⭐</p>
        </div>
    </div>

    <script>
        // Create stars
        const starsContainer = document.getElementById('stars');
        for (let i = 0; i < 100; i++) {
            const star = document.createElement('div');
            star.className = 'star';
            star.style.left = Math.random() * 100 + '%';
            star.style.top = Math.random() * 100 + '%';
            star.style.animationDelay = Math.random() * 3 + 's';
            starsContainer.appendChild(star);
        }

        // Typing animation
        const phrases = [
            "GAME DEVELOPER",
            "UNITY WIZARD",
            "DIGITAL ARCHITECT",
            "SURVIVAL HORROR EXPERT"
        ];
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing');

        function type() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentPhrase.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
            }

            setTimeout(type, isDeleting ? 50 : 100);
        }

        type();

        // Animate progress bars on load
        window.addEventListener('load', () => {
            document.querySelectorAll('.progress-fill').forEach(bar => {
                const width = bar.style.width;
                bar.style.width = '0%';
                setTimeout(() => {
                    bar.style.width = width;
                }, 500);
            });
        });
    </script>
</body>
</html>
