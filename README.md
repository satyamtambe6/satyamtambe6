<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Professional GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0d1117 0%, #161b22 100%);
            color: #e6edf3;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .profile-header {
            text-align: center;
            padding: 60px 0;
            position: relative;
            overflow: hidden;
        }

        .profile-header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(138, 43, 226, 0.1) 0%, transparent 70%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .profile-avatar {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: linear-gradient(45deg, #8b5cf6, #06b6d4, #10b981);
            padding: 4px;
            margin: 0 auto 30px;
            animation: pulse 2s ease-in-out infinite alternate;
            position: relative;
            z-index: 2;
        }

        .profile-avatar img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            background: #21262d;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(139, 92, 246, 0.7); }
            100% { box-shadow: 0 0 0 20px rgba(139, 92, 246, 0); }
        }

        .profile-name {
            font-size: 3rem;
            font-weight: 700;
            background: linear-gradient(45deg, #8b5cf6, #06b6d4, #10b981);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            position: relative;
            z-index: 2;
        }

        .profile-title {
            font-size: 1.2rem;
            color: #7c3aed;
            margin-bottom: 20px;
            position: relative;
            z-index: 2;
        }

        .typing-animation {
            border-right: 2px solid #8b5cf6;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 50% { border-color: transparent; }
            51%, 100% { border-color: #8b5cf6; }
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
            position: relative;
            z-index: 2;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            padding: 10px 20px;
            background: rgba(139, 92, 246, 0.1);
            border: 1px solid rgba(139, 92, 246, 0.3);
            border-radius: 25px;
            text-decoration: none;
            color: #e6edf3;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .social-link:hover {
            background: rgba(139, 92, 246, 0.2);
            border-color: rgba(139, 92, 246, 0.6);
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(139, 92, 246, 0.3);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 50px 0;
        }

        .stat-card {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid rgba(139, 92, 246, 0.3);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(139, 92, 246, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .stat-card:hover::before {
            left: 100%;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            border-color: rgba(139, 92, 246, 0.6);
            box-shadow: 0 20px 40px rgba(139, 92, 246, 0.2);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: #8b5cf6;
            margin-bottom: 10px;
            animation: countUp 2s ease-out;
        }

        .stat-label {
            color: #7d8590;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        @keyframes countUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .skills-section {
            margin: 60px 0;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 40px;
            background: linear-gradient(45deg, #8b5cf6, #06b6d4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
        }

        .skill-item {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid rgba(139, 92, 246, 0.3);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-item:hover {
            transform: translateY(-5px) rotate(5deg);
            border-color: rgba(139, 92, 246, 0.6);
            background: rgba(139, 92, 246, 0.1);
        }

        .skill-icon {
            font-size: 2rem;
            margin-bottom: 10px;
            display: block;
        }

        .projects-section {
            margin: 60px 0;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid rgba(139, 92, 246, 0.3);
            border-radius: 15px;
            padding: 30px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(45deg, #8b5cf6, #06b6d4, #10b981);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .project-card:hover::after {
            transform: scaleX(1);
        }

        .project-card:hover {
            transform: translateY(-10px);
            border-color: rgba(139, 92, 246, 0.6);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .project-title {
            font-size: 1.3rem;
            color: #8b5cf6;
            margin-bottom: 15px;
        }

        .project-description {
            color: #7d8590;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tech-tag {
            background: rgba(139, 92, 246, 0.2);
            color: #8b5cf6;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
            border: 1px solid rgba(139, 92, 246, 0.3);
        }

        .github-activity {
            margin: 60px 0;
            text-align: center;
        }

        .activity-graph {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid rgba(139, 92, 246, 0.3);
            border-radius: 15px;
            padding: 30px;
            margin: 30px 0;
        }

        .contribution-day {
            width: 12px;
            height: 12px;
            background: #161b22;
            border-radius: 2px;
            margin: 1px;
            display: inline-block;
            animation: fadeIn 0.5s ease-in-out;
        }

        .contribution-day.active-1 { background: rgba(139, 92, 246, 0.3); }
        .contribution-day.active-2 { background: rgba(139, 92, 246, 0.5); }
        .contribution-day.active-3 { background: rgba(139, 92, 246, 0.7); }
        .contribution-day.active-4 { background: rgba(139, 92, 246, 1); }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0); }
            to { opacity: 1; transform: scale(1); }
        }

        .floating-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .floating-element {
            position: absolute;
            opacity: 0.1;
            animation: float 15s infinite linear;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% { opacity: 0.1; }
            90% { opacity: 0.1; }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }

        @media (max-width: 768px) {
            .profile-name { font-size: 2rem; }
            .social-links { flex-direction: column; align-items: center; }
            .stats-grid { grid-template-columns: 1fr; }
            .projects-grid { grid-template-columns: 1fr; }
            .skills-grid { grid-template-columns: repeat(auto-fit, minmax(100px, 1fr)); }
        }
    </style>
</head>
<body>
    <div class="floating-elements">
        <div class="floating-element" style="left: 10%; animation-delay: 0s;">💻</div>
        <div class="floating-element" style="left: 20%; animation-delay: 2s;">🚀</div>
        <div class="floating-element" style="left: 30%; animation-delay: 4s;">⚡</div>
        <div class="floating-element" style="left: 40%; animation-delay: 6s;">🔥</div>
        <div class="floating-element" style="left: 50%; animation-delay: 8s;">💡</div>
        <div class="floating-element" style="left: 60%; animation-delay: 10s;">🌟</div>
        <div class="floating-element" style="left: 70%; animation-delay: 12s;">⚙️</div>
        <div class="floating-element" style="left: 80%; animation-delay: 14s;">🎯</div>
    </div>

    <div class="container">
        <div class="profile-header">
            <div class="profile-avatar">
                <div style="display: flex; align-items: center; justify-content: center; width: 100%; height: 100%; background: #21262d; border-radius: 50%;">
                    👨‍💻
                </div>
            </div>
            <h1 class="profile-name">Your Name</h1>
            <p class="profile-title">
                <span id="typing-text" class="typing-animation">Full Stack Developer</span>
            </p>
            
            <div class="social-links">
                <a href="#" class="social-link">🌐 Portfolio</a>
                <a href="#" class="social-link">💼 LinkedIn</a>
                <a href="#" class="social-link">🐦 Twitter</a>
                <a href="#" class="social-link">📧 Email</a>
            </div>
        </div>

        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-number" data-target="150">0</div>
                <div class="stat-label">Repositories</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-target="2500">0</div>
                <div class="stat-label">Contributions</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-target="50">0</div>
                <div class="stat-label">Projects</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-target="25">0</div>
                <div class="stat-label">Stars</div>
            </div>
        </div>

        <div class="skills-section">
            <h2 class="section-title">Tech Stack</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <span class="skill-icon">⚛️</span>
                    <div>React</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">💚</span>
                    <div>Node.js</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🐍</span>
                    <div>Python</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">☕</span>
                    <div>JavaScript</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🔷</span>
                    <div>TypeScript</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🗄️</span>
                    <div>MongoDB</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🐳</span>
                    <div>Docker</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">☁️</span>
                    <div>AWS</div>
                </div>
            </div>
        </div>

        <div class="projects-section">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3 class="project-title">🚀 AI-Powered Web App</h3>
                    <p class="project-description">
                        A full-stack application integrating machine learning models with modern web technologies to deliver intelligent user experiences.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">TensorFlow</span>
                        <span class="tech-tag">AWS</span>
                    </div>
                </div>
                
                <div class="project-card">
                    <h3 class="project-title">📱 Mobile-First Platform</h3>
                    <p class="project-description">
                        Cross-platform mobile application with real-time features, built using React Native and Firebase for seamless user experience.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">React Native</span>
                        <span class="tech-tag">Firebase</span>
                        <span class="tech-tag">TypeScript</span>
                        <span class="tech-tag">Redux</span>
                    </div>
                </div>
                
                <div class="project-card">
                    <h3 class="project-title">🔗 Blockchain Solution</h3>
                    <p class="project-description">
                        Decentralized application built on Ethereum blockchain with smart contracts and modern web3 integration.
                    </p>
                    <div class="project-tech">
                        <span class="tech-tag">Solidity</span>
                        <span class="tech-tag">Web3.js</span>
                        <span class="tech-tag">Next.js</span>
                        <span class="tech-tag">Ethereum</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="github-activity">
            <h2 class="section-title">Contribution Activity</h2>
            <div class="activity-graph">
                <p style="margin-bottom: 20px; color: #7d8590;">
                    🔥 365 days of consistent coding
                </p>
                <div id="contribution-graph"></div>
            </div>
        </div>
    </div>

    <script>
        // Typing animation
        const titles = [
            'Full Stack Developer',
            'AI Enthusiast',
            'Open Source Contributor',
            'Problem Solver',
            'Tech Innovator'
        ];
        
        let titleIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing-text');
        
        function typeTitle() {
            const currentTitle = titles[titleIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentTitle.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentTitle.substring(0, charIndex + 1);
                charIndex++;
            }
            
            if (!isDeleting && charIndex === currentTitle.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                titleIndex = (titleIndex + 1) % titles.length;
            }
            
            const speed = isDeleting ? 100 : 200;
            setTimeout(typeTitle, speed);
        }
        
        typeTitle();
        
        // Counter animation
        function animateCounters() {
            const counters = document.querySelectorAll('.stat-number');
            
            counters.forEach(counter => {
                const target = parseInt(counter.getAttribute('data-
