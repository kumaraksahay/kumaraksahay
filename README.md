<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Akshay Kumar - Full Stack Architect</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0e27;
            color: #fff;
            overflow-x: hidden;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
            background: linear-gradient(45deg, #0a0e27, #1a1f3a, #0a0e27);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
        }

        .stars {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 2rem;
            position: relative;
        }

        .hero-content {
            max-width: 900px;
            z-index: 1;
        }

        .hero h1 {
            font-size: 5rem;
            font-weight: 800;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 1rem;
            animation: slideDown 1s ease;
        }

        .hero .subtitle {
            font-size: 1.8rem;
            color: #a0aec0;
            margin-bottom: 2rem;
            animation: slideUp 1s ease 0.3s backwards;
        }

        .typing-container {
            font-size: 1.3rem;
            color: #4fd1c5;
            margin-bottom: 3rem;
            min-height: 2em;
            animation: slideUp 1s ease 0.6s backwards;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: slideUp 1s ease 0.9s backwards;
        }

        .btn {
            padding: 1rem 2.5rem;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.6);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border: 2px solid #667eea;
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: rgba(102, 126, 234, 0.2);
            transform: translateY(-3px);
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
            animation: fadeIn 1s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px) scale(1.05);
            background: rgba(102, 126, 234, 0.1);
            border-color: #667eea;
            box-shadow: 0 20px 60px rgba(102, 126, 234, 0.3);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            background: linear-gradient(135deg, #4fd1c5, #667eea);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-label {
            font-size: 1.1rem;
            color: #a0aec0;
            margin-top: 0.5rem;
        }

        /* Skills Section */
        .section {
            padding: 5rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 3rem;
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(135deg, #667eea 0%, #f093fb 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .skill-category {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
            border: 1px solid rgba(102, 126, 234, 0.3);
            border-radius: 20px;
            padding: 2rem;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.5s;
        }

        .skill-category:hover::before {
            left: 100%;
        }

        .skill-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(102, 126, 234, 0.4);
            border-color: #667eea;
        }

        .skill-category h3 {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: #4fd1c5;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
        }

        .skill-tag {
            background: rgba(79, 209, 197, 0.1);
            border: 1px solid #4fd1c5;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            background: rgba(79, 209, 197, 0.3);
            transform: scale(1.1);
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 2rem;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, #667eea, #764ba2, #f093fb);
            transform: scaleX(0);
            transition: transform 0.4s ease;
        }

        .project-card:hover::after {
            transform: scaleX(1);
        }

        .project-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 25px 70px rgba(102, 126, 234, 0.5);
            border-color: #667eea;
        }

        .project-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .project-card h3 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
            color: #f093fb;
        }

        .project-card p {
            color: #a0aec0;
            line-height: 1.6;
            margin-bottom: 1.5rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .tech-badge {
            background: rgba(102, 126, 234, 0.2);
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.85rem;
            color: #4fd1c5;
        }

        .project-link {
            display: inline-block;
            color: #667eea;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            color: #f093fb;
            transform: translateX(5px);
        }

        /* Contact Section */
        .contact {
            text-align: center;
            padding: 5rem 2rem;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
            border-radius: 30px;
            max-width: 1200px;
            margin: 3rem auto;
        }

        .contact h2 {
            font-size: 3rem;
            margin-bottom: 1.5rem;
        }

        .contact p {
            font-size: 1.3rem;
            color: #a0aec0;
            margin-bottom: 3rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .social-icon {
            width: 60px;
            height: 60px;
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid #667eea;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .social-icon:hover {
            background: linear-gradient(135deg, #667eea, #764ba2);
            transform: translateY(-10px) rotate(360deg);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.5);
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        /* Scroll indicator */
        .scroll-indicator {
            position: absolute;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            40% {
                transform: translateX(-50%) translateY(-20px);
            }
            60% {
                transform: translateX(-50%) translateY(-10px);
            }
        }

        .scroll-indicator::after {
            content: '↓';
            font-size: 2rem;
            color: #667eea;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 3rem;
            }
            .hero .subtitle {
                font-size: 1.3rem;
            }
            .section-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>
    <div class="stars" id="stars"></div>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>AKSHAY KUMAR</h1>
            <div class="subtitle">Full Stack Developer | Mobile App Architect</div>
            <div class="typing-container" id="typing"></div>
            <div class="cta-buttons">
                <a href="#projects" class="btn btn-primary">View My Work</a>
                <a href="#contact" class="btn btn-secondary">Let's Connect</a>
            </div>
        </div>
        <div class="scroll-indicator"></div>
    </section>

    <!-- Stats Section -->
    <div class="stats">
        <div class="stat-card">
            <div class="stat-number">5+</div>
            <div class="stat-label">Years Experience</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">50+</div>
            <div class="stat-label">Projects Delivered</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">20+</div>
            <div class="stat-label">Technologies</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">100%</div>
            <div class="stat-label">Client Satisfaction</div>
        </div>
    </div>

    <!-- Skills Section -->
    <section class="section">
        <h2 class="section-title">💼 Technical Excellence</h2>
        <div class="skills-grid">
            <div class="skill-category">
                <h3>🎨 Frontend & Mobile</h3>
                <div class="skill-tags">
                    <span class="skill-tag">React</span>
                    <span class="skill-tag">Next.js</span>
                    <span class="skill-tag">React Native</span>
                    <span class="skill-tag">TypeScript</span>
                    <span class="skill-tag">Tailwind CSS</span>
                    <span class="skill-tag">Redux</span>
                </div>
            </div>
            <div class="skill-category">
                <h3>⚙️ Backend & Database</h3>
                <div class="skill-tags">
                    <span class="skill-tag">Node.js</span>
                    <span class="skill-tag">Express</span>
                    <span class="skill-tag">NestJS</span>
                    <span class="skill-tag">MongoDB</span>
                    <span class="skill-tag">PostgreSQL</span>
                    <span class="skill-tag">GraphQL</span>
                </div>
            </div>
            <div class="skill-category">
                <h3>🚀 DevOps & Cloud</h3>
                <div class="skill-tags">
                    <span class="skill-tag">Docker</span>
                    <span class="skill-tag">Kubernetes</span>
                    <span class="skill-tag">AWS</span>
                    <span class="skill-tag">CI/CD</span>
                    <span class="skill-tag">Nginx</span>
                    <span class="skill-tag">Firebase</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="section" id="projects">
        <h2 class="section-title">🏆 Featured Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-icon">🌱</div>
                <h3>Plant Care Hub</h3>
                <p>A comprehensive mobile application for smart plant management with AI-powered care reminders and community features.</p>
                <div class="project-tech">
                    <span class="tech-badge">React Native</span>
                    <span class="tech-badge">Firebase</span>
                    <span class="tech-badge">Push Notifications</span>
                </div>
                <a href="#" class="project-link">View Project →</a>
            </div>
            <div class="project-card">
                <div class="project-icon">🩺</div>
                <h3>Skin Scan Disease Detector</h3>
                <p>AI-powered health diagnostic tool using machine learning for skin disease detection and treatment recommendations.</p>
                <div class="project-tech">
                    <span class="tech-badge">Machine Learning</span>
                    <span class="tech-badge">React Native</span>
                    <span class="tech-badge">TensorFlow</span>
                </div>
                <a href="#" class="project-link">View Project →</a>
            </div>
            <div class="project-card">
                <div class="project-icon">🎯</div>
                <h3>Enterprise Solutions</h3>
                <p>Scalable full-stack applications serving thousands of users with real-time features and microservices architecture.</p>
                <div class="project-tech">
                    <span class="tech-badge">Next.js</span>
                    <span class="tech-badge">Node.js</span>
                    <span class="tech-badge">Microservices</span>
                </div>
                <a href="#" class="project-link">View Project →</a>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2>Let's Build Something Amazing</h2>
        <p>Open to opportunities • Available for collaboration • Ready to innovate</p>
        <div class="social-links">
            <div class="social-icon" title="LinkedIn">💼</div>
            <div class="social-icon" title="GitHub">💻</div>
            <div class="social-icon" title="Email">📧</div>
            <div class="social-icon" title="Instagram">📷</div>
        </div>
        <div style="margin-top: 2rem;">
            <a href="mailto:kumarakshaykolhi@gmail.com" class="btn btn-primary">Get In Touch</a>
        </div>
    </section>

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
            'Building scalable solutions 🚀',
            'Crafting beautiful interfaces 🎨',
            'Solving complex problems 💡',
            'Driving innovation forward ⚡'
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

            const speed = isDeleting ? 50 : 100;
            setTimeout(type, speed);
        }

        type();

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Animate on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeIn 1s ease forwards';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.skill-category, .project-card').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>
