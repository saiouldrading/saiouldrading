<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SAI OULDRADING - Senior Unity Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --primary: #00D9FF;
            --secondary: #FF6B35;
            --dark: #0D1117;
            --darker: #090C10;
            --light: #C9D1D9;
            --accent: #8B4513;
            --success: #00FF00;
            --warning: #FFD700;
            --danger: #FF4444;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--dark);
            color: var(--light);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Header Styles */
        .header {
            text-align: center;
            padding: 40px 0;
            background: linear-gradient(135deg, var(--darker) 0%, var(--dark) 100%);
            border-bottom: 2px solid var(--primary);
            position: relative;
            overflow: hidden;
        }
        
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid var(--primary);
            margin: 0 auto 20px;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            color: white;
        }
        
        .typing-container {
            height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 20px 0;
        }
        
        .typing-text {
            font-family: 'Orbitron', monospace;
            font-size: 28px;
            color: var(--primary);
            border-right: 3px solid var(--primary);
            white-space: nowrap;
            overflow: hidden;
            animation: typing 4s steps(40, end), blink-caret 0.75s step-end infinite;
        }
        
        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: var(--primary) }
        }
        
        .capsule {
            background: linear-gradient(90deg, #274c26, #1a3319);
            padding: 20px;
            border-radius: 50px;
            margin: 20px 0;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }
        
        /* Section Styles */
        .section {
            background-color: var(--darker);
            border-radius: 10px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            border-left: 4px solid var(--primary);
        }
        
        .section-title {
            color: var(--primary);
            font-size: 28px;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid rgba(0,217,255,0.3);
            display: flex;
            align-items: center;
        }
        
        .section-title i {
            margin-right: 15px;
        }
        
        /* Grid Layouts */
        .grid-2 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
            gap: 20px;
        }
        
        .grid-3 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .grid-4 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }
        
        /* Card Styles */
        .card {
            background: rgba(255,255,255,0.05);
            border-radius: 8px;
            padding: 20px;
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.4);
            border-color: var(--primary);
        }
        
        .card-title {
            color: var(--primary);
            font-size: 20px;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }
        
        .card-title i {
            margin-right: 10px;
        }
        
        /* Progress Bars */
        .progress-container {
            margin: 15px 0;
        }
        
        .progress-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }
        
        .progress-bar {
            height: 10px;
            background-color: rgba(255,255,255,0.1);
            border-radius: 5px;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 5px;
            transition: width 1.5s ease-in-out;
        }
        
        /* Badge Styles */
        .badge {
            display: inline-block;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
            margin: 5px;
        }
        
        .badge-primary {
            background-color: var(--primary);
            color: var(--dark);
        }
        
        .badge-secondary {
            background-color: var(--secondary);
            color: white;
        }
        
        .badge-success {
            background-color: var(--success);
            color: var(--dark);
        }
        
        .badge-warning {
            background-color: var(--warning);
            color: var(--dark);
        }
        
        .badge-danger {
            background-color: var(--danger);
            color: white;
        }
        
        /* Code Block Styles */
        .code-block {
            background-color: rgba(0,0,0,0.3);
            border-radius: 8px;
            padding: 20px;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            overflow-x: auto;
            border-left: 4px solid var(--primary);
            margin: 15px 0;
        }
        
        .code-keyword {
            color: var(--primary);
        }
        
        .code-class {
            color: var(--secondary);
        }
        
        .code-comment {
            color: #6A9955;
        }
        
        .code-string {
            color: #CE9178;
        }
        
        /* Table Styles */
        .table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        .table th, .table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }
        
        .table th {
            color: var(--primary);
            font-weight: 600;
        }
        
        .table tr:hover {
            background-color: rgba(255,255,255,0.05);
        }
        
        /* Footer Styles */
        .footer {
            text-align: center;
            padding: 40px 0;
            margin-top: 40px;
            background: linear-gradient(135deg, var(--dark) 0%, var(--darker) 100%);
            border-top: 2px solid var(--primary);
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }
        
        .social-link {
            display: inline-block;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            text-decoration: none;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .social-link:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,217,255,0.4);
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .fade-in {
            animation: fadeIn 1s ease-out;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .grid-2, .grid-3, .grid-4 {
                grid-template-columns: 1fr;
            }
            
            .typing-text {
                font-size: 20px;
            }
            
            .section {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header Section -->
        <header class="header fade-in">
            <div class="profile-img">
                <i class="fas fa-code"></i>
            </div>
            <h1>SAI OULDRADING</h1>
            <h3>Senior Unity Developer & Technical Architect</h3>
            
            <div class="typing-container">
                <div class="typing-text">GAME DEVELOPER | UNITY WIZARD | DIGITAL ARCHITECT</div>
            </div>
            
            <div class="capsule">
                <h2>CODE + CREATIVITY</h2>
                <p>Building Tomorrow's Gaming Experience</p>
            </div>
        </header>
        
        <!-- Professional Profile Section -->
        <section class="section fade-in">
            <h2 class="section-title"><i class="fas fa-user-tie"></i> PROFESSIONAL PROFILE</h2>
            
            <div class="grid-2">
                <div class="card">
                    <div class="code-block">
                        <span class="code-keyword">public class</span> <span class="code-class">SeniorUnityDeveloper</span> : <span class="code-class">MonoBehaviour</span><br>
                        {<br>
                        &nbsp;&nbsp;[<span class="code-class">SerializeField</span>] <span class="code-keyword">private string</span> developerName = <span class="code-string">"Sai Ouldrading"</span>;<br>
                        &nbsp;&nbsp;[<span class="code-class">SerializeField</span>] <span class="code-keyword">private string</span> title = <span class="code-string">"Unity Technical Lead"</span>;<br>
                        &nbsp;&nbsp;[<span class="code-class">SerializeField</span>] <span class="code-keyword">private string</span> specialization = <span class="code-string">"Survival Horror & Narrative Games"</span>;<br>
                        <br>
                        &nbsp;&nbsp;[<span class="code-class">Header</span>(<span class="code-string">"Core Competencies"</span>)]<br>
                        &nbsp;&nbsp;<span class="code-keyword">private string</span>[] technicalExpertise = {<br>
                        &nbsp;&nbsp;&nbsp;&nbsp;<span class="code-string">"Unity Engine Architecture"</span>,<br>
                        &nbsp;&nbsp;&nbsp;&nbsp;<span class="code-string">"Advanced C# Programming"</span>, <br>
                        &nbsp;&nbsp;&nbsp;&nbsp;<span class="code-string">"Performance Optimization"</span>,<br>
                        &nbsp;&nbsp;&nbsp;&nbsp;<span class="code-string">"Gameplay Systems Design"</span><br>
                        &nbsp;&nbsp;};<br>
                        }
                    </div>
                </div>
                
                <div class="card">
                    <h3 class="card-title"><i class="fas fa-trophy"></i> CERTIFICATIONS</h3>
                    <ul>
                        <li>Unity Certified Professional</li>
                        <li>Agile Scrum Master</li>
                        <li>C# Advanced Programming</li>
                        <li>Game Design Principles</li>
                    </ul>
                    
                    <h3 class="card-title" style="margin-top: 20px;"><i class="fas fa-cogs"></i> DEVELOPMENT METHODOLOGY</h3>
                    <div class="progress-container">
                        <div class="progress-label">
                            <span>Agile Development</span>
                            <span>95%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" style="width: 95%"></div>
                        </div>
                    </div>
                    
                    <div class="progress-container">
                        <div class="progress-label">
                            <span>Scrum Framework</span>
                            <span>90%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" style="width: 90%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Technical Mastery Section -->
        <section class="section fade-in">
            <h2 class="section-title"><i class="fas fa-tools"></i> TECHNICAL MASTERY</h2>
            
            <div class="card">
                <h3 class="card-title"><i class="fas fa-gamepad"></i> Game Development Stack</h3>
                <div class="grid-4">
                    <div class="badge badge-primary">Unity</div>
                    <div class="badge badge-primary">C#</div>
                    <div class="badge badge-primary">C++</div>
                    <div class="badge badge-primary">Python</div>
                    <div class="badge badge-secondary">Blender</div>
                    <div class="badge badge-secondary">Photoshop</div>
                    <div class="badge badge-secondary">VS Code</div>
                    <div class="badge badge-secondary">Git</div>
                    <div class="badge badge-success">GitHub</div>
                    <div class="badge badge-success">Figma</div>
                    <div class="badge badge-success">AWS</div>
                    <div class="badge badge-success">Visual Studio</div>
                </div>
            </div>
            
            <div class="card" style="margin-top: 20px;">
                <h3 class="card-title"><i class="fas fa-layer-group"></i> Specialized Frameworks & Tools</h3>
                <div class="grid-3">
                    <div class="card">
                        <h4><i class="fas fa-paint-roller"></i> Unity URP</h4>
                        <p>Universal Render Pipeline for optimized graphics</p>
                    </div>
                    <div class="card">
                        <h4><i class="fas fa-cube"></i> Cinema 4D</h4>
                        <p>3D modeling and animation</p>
                    </div>
                    <div class="card">
                        <h4><i class="fas fa-film"></i> After Effects</h4>
                        <p>Visual effects and motion graphics</p>
                    </div>
                    <div class="card">
                        <h4><i class="fas fa-tasks"></i> Jira</h4>
                        <p>Project management and issue tracking</p>
                    </div>
                    <div class="card">
                        <h4><i class="fas fa-columns"></i> Trello</h4>
                        <p>Agile workflow management</p>
                    </div>
                    <div class="card">
                        <h4><i class="fas fa-network-wired"></i> Photon Engine</h4>
                        <p>Multiplayer and networking solutions</p>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Flagship Project Section -->
        <section class="section fade-in">
            <h2 class="section-title"><i class="fas fa-rocket"></i> FLAGSHIP PROJECT: ASHES OF US</h2>
            
            <div class="card">
                <div class="code-block" style="text-align: center; font-size: 18px; background: linear-gradient(90deg, #1a1a1a, #2a1a1a);">
                    🧟‍♂️ ASHES OF US - Post-Apocalyptic Survival RPG<br>
                    "When humanity falls, two souls must rise from the ashes..."
                </div>
                
                <h3 class="card-title"><i class="fas fa-info-circle"></i> Project Overview</h3>
                <table class="table">
                    <tr>
                        <th>Metric</th>
                        <th>Specification</th>
                    </tr>
                    <tr>
                        <td>Platform</td>
                        <td>PC (Steam) → Console Ports</td>
                    </tr>
                    <tr>
                        <td>Engine</td>
                        <td>Unity 2022 LTS</td>
                    </tr>
                    <tr>
                        <td>Team Size</td>
                        <td>2 (Core Development)</td>
                    </tr>
                    <tr>
                        <td>Development Cycle</td>
                        <td>18 Months</td>
                    </tr>
                    <tr>
                        <td>Target Release</td>
                        <td>Q4 2024</td>
                    </tr>
                </table>
            </div>
            
            <div class="card" style="margin-top: 20px;">
                <h3 class="card-title"><i class="fas fa-tasks"></i> Development Progress Tracker</h3>
                <table class="table">
                    <tr>
                        <th>System Module</th>
                        <th>Status</th>
                        <th>Completion</th>
                    </tr>
                    <tr>
                        <td>Core Gameplay Framework</td>
                        <td><span class="badge badge-success">Complete</span></td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 100%"></div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td>Character Controller System</td>
                        <td><span class="badge badge-success">Complete</span></td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 100%"></div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td>Advanced AI Behavior Trees</td>
                        <td><span class="badge badge-warning">In Progress</span></td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 85%"></div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td>Dynamic Dialogue System</td>
                        <td><span class="badge badge-success">Complete</span></td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 100%"></div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td>Procedural Environment Generation</td>
                        <td><span class="badge badge-warning">In Progress</span></td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 70%"></div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td>Combat & Gore System</td>
                        <td><span class="badge badge-warning">In Progress</span></td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 75%"></div>
                            </div>
                        </td>
                    </tr>
                </table>
            </div>
        </section>
        
        <!-- Character System Design -->
        <section class="section fade-in">
            <h2 class="section-title"><i class="fas fa-users"></i> CHARACTER SYSTEM DESIGN</h2>
            
            <div class="grid-2">
                <div class="card">
                    <h3 class="card-title"><i class="fas fa-shield-alt"></i> RIVEN - The Tactical Guardian</h3>
                    <div class="code-block">
                        [<span class="code-class">System</span>.<span class="code-class">Serializable</span>]<br>
                        <span class="code-keyword">public class</span> <span class="code-class">CharacterRiven</span> : <span class="code-class">BaseCharacter</span><br>
                        {<br>
                        &nbsp;&nbsp;[<span class="code-class">Header</span>(<span class="code-string">"Combat Specialization"</span>)]<br>
                        &nbsp;&nbsp;<span class="code-keyword">public</span> <span class="code-class">CombatStyle</span> primaryStyle = <span class="code-class">CombatStyle</span>.Tactical;<br>
                        &nbsp;&nbsp;<span class="code-keyword">public</span> <span class="code-class">WeaponProficiency</span>[] weaponSkills;<br>
                        &nbsp;&nbsp;<span class="code-keyword">public</span> <span class="code-class">SurvivalInstinct</span> survivalTraits;<br>
                        }
                    </div>
                    <ul style="margin-top: 15px;">
                        <li><strong>Role:</strong> Primary Combat & Strategy</li>
                        <li><strong>Specialization:</strong> Military Tactics, Weapon Mastery</li>
                        <li><strong>Development Focus:</strong> AI-driven combat behaviors</li>
                    </ul>
                </div>
                
                <div class="card">
                    <h3 class="card-title"><i class="fas fa-heart"></i> THEO - The Emotional Anchor</h3>
                    <div class="code-block">
                        [<span class="code-class">System</span>.<span class="code-class">Serializable</span>]<br>
                        <span class="code-keyword">public class</span> <span class="code-class">CharacterTheo</span> : <span class="code-class">BaseCharacter</span><br>
                        {<br>
                        &nbsp;&nbsp;[<span class="code-class">Header</span>(<span class="code-string">"Narrative Specialization"</span>)]<br>
                        &nbsp;&nbsp;<span class="code-keyword">public</span> <span class="code-class">DialogueTree</span> personalStory;<br>
                        &nbsp;&nbsp;<span class="code-keyword">public</span> <span class="code-class">RelationshipSystem</span> relationships;<br>
                        &nbsp;&nbsp;<span class="code-keyword">public</span> <span class="code-class">EmotionalState</span> emotionalArc;<br>
                        }
                    </div>
                    <ul style="margin-top: 15px;">
                        <li><strong>Role:</strong> Narrative Driver & Support</li>
                        <li><strong>Specialization:</strong> Story Progression, Team Morale</li>
                        <li><strong>Development Focus:</strong> Dynamic dialogue systems</li>
                    </ul>
                </div>
            </div>
        </section>
        
        <!-- Professional Metrics -->
        <section class="section fade-in">
            <h2 class="section-title"><i class="fas fa-chart-line"></i> PROFESSIONAL METRICS</h2>
            
            <div class="grid-2">
                <div class="card">
                    <h3 class="card-title"><i class="fas fa-code-branch"></i> GitHub Development Analytics</h3>
                    <canvas id="commitChart" width="400" height="200"></canvas>
                </div>
                
                <div class="card">
                    <h3 class="card-title"><i class="fas fa-language"></i> Top Languages</h3>
                    <canvas id="languageChart" width="400" height="200"></canvas>
                </div>
            </div>
            
            <div class="card" style="margin-top: 20px;">
                <h3 class="card-title"><i class="fas fa-tachometer-alt"></i> Productivity Metrics</h3>
                <div class="code-block">
                    {<br>
                    &nbsp;&nbsp;"weekly_commit_avg": <span class="code-string">"45+ commits"</span>,<br>
                    &nbsp;&nbsp;"code_review_activity": <span class="code-string">"High"</span>,<br>
                    &nbsp;&nbsp;"project_contribution": <span class="code-string">"Full-Stack"</span>,<br>
                    &nbsp;&nbsp;"technical_documentation": <span class="code-string">"Comprehensive"</span>,<br>
                    &nbsp;&nbsp;"bug_resolution_rate": <span class="code-string">"98%"</span>,<br>
                    &nbsp;&nbsp;"feature_completion": <span class="code-string">"Ahead of Schedule"</span><br>
                    }
                </div>
            </div>
        </section>
        
        <!-- Industry Analysis -->
        <section class="section fade-in">
            <h2 class="section-title"><i class="fas fa-search"></i> INDUSTRY ANALYSIS & RESEARCH</h2>
            
            <div class="card">
                <h3 class="card-title"><i class="fas fa-book"></i> Active Technical Research</h3>
                <div class="grid-4">
                    <div class="card">
                        <h4><i class="fas fa-cubes"></i> Unity DOTS</h4>
                        <p>Performance Optimization</p>
                    </div>
                    <div class="card">
                        <h4><i class="fas fa-robot"></i> Advanced AI</h4>
                        <p>Behavior Tree Optimization</p>
                    </div>
                    <div class="card">
                        <h4><i class="fas fa-mountain"></i> Procedural Generation</h4>
                        <p>World Building Techniques</p>
                    </div>
                    <div class="card">
                        <h4><i class="fas fa-network-wired"></i> Multiplayer Architecture</h4>
                        <p>Netcode Solutions</p>
                    </div>
                </div>
            </div>
            
            <div class="card" style="margin-top: 20px;">
                <h3 class="card-title"><i class="fas fa-gamepad"></i> Current Gaming Analysis</h3>
                <table class="table">
                    <tr>
                        <th>Game Title</th>
                        <th>Research Focus</th>
                        <th>Technical Insights</th>
                    </tr>
                    <tr>
                        <td>Dying Light</td>
                        <td>Parkour & Combat</td>
                        <td>Movement physics, enemy AI patterns</td>
                    </tr>
                    <tr>
                        <td>Red Dead Redemption 2</td>
                        <td>Open World Immersion</td>
                        <td>Environmental storytelling, NPC routines</td>
                    </tr>
                    <tr>
                        <td>The Last of Us</td>
                        <td>Narrative & Gameplay</td>
                        <td>Character development, emotional pacing</td>
                    </tr>
                    <tr>
                        <td>Cyberpunk 2077</td>
                        <td>Urban Environment</td>
                        <td>Verticality, lighting systems</td>
                    </tr>
                </table>
            </div>
        </section>
        
        <!-- Footer -->
        <footer class="footer fade-in">
            <h2>KEEP CREATING</h2>
            <p>"Building tomorrow's gaming experiences, one line of code at a time!"</p>
            
            <div class="social-links">
                <a href="https://www.linkedin.com/in/muhammad-saim-a26349358/" class="social-link">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="https://www.instagram.com/saimk.k18/" class="social-link">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="mailto:Ouldrading@gmail.com" class="social-link">
                    <i class="fas fa-envelope"></i>
                </a>
                <a href="https://github.com/saiouldrading" class="social-link">
                    <i class="fab fa-github"></i>
                </a>
            </div>
            
            <p>Open For: <span class="badge badge-primary">Game Jams</span> <span class="badge badge-secondary">Creative Projects</span> <span class="badge badge-success">Technical Collaborations</span> <span class="badge badge-warning">Startup Ideas</span></p>
            
            <p style="margin-top: 20px; font-size: 14px; color: #888;">
                <i class="fas fa-eye"></i> Profile Views: <span id="viewCount">1,247</span>
            </p>
        </footer>
    </div>

    <script>
        // Initialize charts when the page loads
        document.addEventListener('DOMContentLoaded', function() {
            // Commit Activity Chart
            const commitCtx = document.getElementById('commitChart').getContext('2d');
            const commitChart = new Chart(commitCtx, {
                type: 'bar',
                data: {
                    labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'],
                    datasets: [{
                        label: 'Monthly Commits',
                        data: [45, 52, 48, 61, 58, 67],
                        backgroundColor: 'rgba(0, 217, 255, 0.7)',
                        borderColor: 'rgba(0, 217, 255, 1)',
                        borderWidth: 1
                    }]
                },
                options: {
                    responsive: true,
                    scales: {
                        y: {
                            beginAtZero: true,
                            grid: {
                                color: 'rgba(255, 255, 255, 0.1)'
                            },
                            ticks: {
                                color: '#C9D1D9'
                            }
                        },
                        x: {
                            grid: {
                                color: 'rgba(255, 255, 255, 0.1)'
                            },
                            ticks: {
                                color: '#C9D1D9'
                            }
                        }
                    },
                    plugins: {
                        legend: {
                            labels: {
                                color: '#C9D1D9'
                            }
                        }
                    }
                }
            });
            
            // Language Usage Chart
            const languageCtx = document.getElementById('languageChart').getContext('2d');
            const languageChart = new Chart(languageCtx, {
                type: 'doughnut',
                data: {
                    labels: ['C#', 'Python', 'C++', 'JavaScript', 'HTML/CSS', 'Other'],
                    datasets: [{
                        data: [45, 20, 15, 10, 7, 3],
                        backgroundColor: [
                            'rgba(0, 217, 255, 0.7)',
                            'rgba(255, 107, 53, 0.7)',
                            'rgba(139, 69, 19, 0.7)',
                            'rgba(255, 215, 0, 0.7)',
                            'rgba(0, 255, 0, 0.7)',
                            'rgba(128, 128, 128, 0.7)'
                        ],
                        borderColor: [
                            'rgba(0, 217, 255, 1)',
                            'rgba(255, 107, 53, 1)',
                            'rgba(139, 69, 19, 1)',
                            'rgba(255, 215, 0, 1)',
                            'rgba(0, 255, 0, 1)',
                            'rgba(128, 128, 128, 1)'
                        ],
                        borderWidth: 1
                    }]
                },
                options: {
                    responsive: true,
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                color: '#C9D1D9',
                                padding: 15
                            }
                        }
                    }
                }
            });
            
            // Animate progress bars on scroll
            const progressBars = document.querySelectorAll('.progress-fill');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const width = entry.target.style.width;
                        entry.target.style.width = '0%';
                        setTimeout(() => {
                            entry.target.style.width = width;
                        }, 300);
                    }
                });
            }, { threshold: 0.5 });
            
            progressBars.forEach(bar => {
                observer.observe(bar);
            });
            
            // Simulate view count increase
            let views = 1247;
            setInterval(() => {
                views += Math.floor(Math.random() * 3);
                document.getElementById('viewCount').textContent = views.toLocaleString();
            }, 10000);
        });
    </script>
</body>
</html>
