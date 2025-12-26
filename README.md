<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aby Babu - Flutter Developer</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-dark: #0a0e1a;
            --bg-secondary: #141824;
            --accent-blue: #0ea5e9;
            --accent-cyan: #06b6d4;
            --accent-orange: #f97316;
            --text-primary: #f1f5f9;
            --text-secondary: #94a3b8;
            --gradient-start: #1e293b;
            --gradient-end: #0f172a;
        }

        body {
            font-family: 'Outfit', sans-serif;
            background: var(--bg-dark);
            color: var(--text-primary);
            line-height: 1.7;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Header Section */
        header {
            padding: 3rem 0 2rem;
            background: linear-gradient(135deg, var(--gradient-start) 0%, var(--gradient-end) 100%);
            border-bottom: 1px solid rgba(14, 165, 233, 0.1);
        }

        .header-content {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .logo {
            font-size: 2rem;
            filter: hue-rotate(200deg) brightness(1.2);
        }

        h1 {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--accent-cyan), var(--accent-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Connect Buttons */
        .connect-section {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .connect-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.75rem;
            padding: 0.875rem 1.75rem;
            border: none;
            border-radius: 0.5rem;
            font-family: 'Outfit', sans-serif;
            font-size: 0.95rem;
            font-weight: 600;
            text-decoration: none;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .connect-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            transition: left 0.5s;
        }

        .connect-btn:hover::before {
            left: 100%;
        }

        .btn-linkedin {
            background: linear-gradient(135deg, #0077b5 0%, #005885 100%);
            color: white;
            box-shadow: 0 4px 15px rgba(0, 119, 181, 0.3);
        }

        .btn-linkedin:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 25px rgba(0, 119, 181, 0.5);
        }

        .btn-email {
            background: linear-gradient(135deg, #ea4335 0%, #c5221f 100%);
            color: white;
            box-shadow: 0 4px 15px rgba(234, 67, 53, 0.3);
        }

        .btn-email:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 25px rgba(234, 67, 53, 0.5);
        }

        .btn-icon {
            font-size: 1.2rem;
            display: flex;
            align-items: center;
        }

        /* Hero Section */
        .hero {
            padding: 4rem 0;
            text-align: center;
        }

        .hero h2 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            animation: fadeInUp 0.8s ease-out;
        }

        .hero .greeting {
            font-size: 1.5rem;
            color: var(--accent-cyan);
            margin-bottom: 0.5rem;
        }

        .hero .title {
            font-size: 2rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .hero .description {
            font-size: 1.2rem;
            color: var(--text-secondary);
            max-width: 700px;
            margin: 0 auto 3rem;
            line-height: 1.8;
        }

        /* Quote Sections */
        .quote-section {
            margin: 3rem 0;
            padding: 2.5rem;
            background: linear-gradient(135deg, rgba(14, 165, 233, 0.05) 0%, rgba(6, 182, 212, 0.05) 100%);
            border-left: 4px solid var(--accent-cyan);
            border-radius: 0.75rem;
            position: relative;
            overflow: hidden;
            animation: fadeInUp 0.8s ease-out;
        }

        .quote-section::before {
            content: '"';
            position: absolute;
            top: -10px;
            left: 20px;
            font-size: 8rem;
            font-weight: 700;
            color: rgba(14, 165, 233, 0.1);
            font-family: 'Georgia', serif;
        }

        .quote-section .icon {
            font-size: 2rem;
            margin-bottom: 1rem;
            display: block;
        }

        .quote-text {
            font-size: 1.4rem;
            font-weight: 300;
            line-height: 1.8;
            color: var(--accent-cyan);
            margin-bottom: 1.5rem;
            font-style: italic;
            position: relative;
            z-index: 1;
        }

        .quote-author {
            font-size: 1.1rem;
            color: var(--accent-blue);
            font-weight: 600;
            text-align: right;
            font-style: normal;
        }

        /* About Section */
        .about-section {
            margin: 4rem 0;
            padding: 3rem;
            background: var(--bg-secondary);
            border-radius: 1rem;
            border: 1px solid rgba(14, 165, 233, 0.1);
        }

        .about-section h3 {
            font-size: 2rem;
            margin-bottom: 2rem;
            color: var(--accent-cyan);
        }

        .about-list {
            list-style: none;
            display: grid;
            gap: 1rem;
        }

        .about-list li {
            padding-left: 2rem;
            position: relative;
            font-size: 1.1rem;
            color: var(--text-secondary);
        }

        .about-list li::before {
            content: '▹';
            position: absolute;
            left: 0;
            color: var(--accent-cyan);
            font-size: 1.5rem;
        }

        /* Tech Stack Section */
        .tech-section {
            margin: 4rem 0;
        }

        .tech-section h3 {
            font-size: 2rem;
            margin-bottom: 2rem;
            text-align: center;
            color: var(--accent-cyan);
        }

        .tech-category {
            margin-bottom: 3rem;
        }

        .tech-category h4 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            color: var(--text-primary);
        }

        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .badge {
            padding: 0.6rem 1.2rem;
            background: linear-gradient(135deg, rgba(14, 165, 233, 0.1) 0%, rgba(6, 182, 212, 0.1) 100%);
            border: 1px solid var(--accent-cyan);
            border-radius: 0.5rem;
            color: var(--text-primary);
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .badge:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 20px rgba(14, 165, 233, 0.3);
            background: linear-gradient(135deg, rgba(14, 165, 233, 0.2) 0%, rgba(6, 182, 212, 0.2) 100%);
        }

        /* Footer */
        footer {
            margin-top: 4rem;
            padding: 3rem 0;
            text-align: center;
            border-top: 1px solid rgba(14, 165, 233, 0.1);
            background: var(--bg-secondary);
        }

        .footer-message {
            font-size: 1.2rem;
            color: var(--text-secondary);
            margin-bottom: 1rem;
        }

        .footer-location {
            color: var(--accent-cyan);
            font-weight: 600;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h2 {
                font-size: 2.5rem;
            }

            .hero .title {
                font-size: 1.5rem;
            }

            .quote-text {
                font-size: 1.2rem;
            }

            .connect-section {
                flex-direction: column;
            }

            .connect-btn {
                width: 100%;
                justify-content: center;
            }

            .about-section,
            .quote-section {
                padding: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <span class="logo">📱</span>
                <h1>Connect With Me</h1>
            </div>
            
            <div class="connect-section">
                <a href="https://www.linkedin.com/in/aby-babu-241964325" class="connect-btn btn-linkedin" target="_blank" rel="noopener noreferrer">
                    <span class="btn-icon">
                        <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                        </svg>
                    </span>
                    LINKEDIN
                </a>
                
                <a href="mailto:abyb4613@gmail.com" class="connect-btn btn-email">
                    <span class="btn-icon">
                        <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                            <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
                        </svg>
                    </span>
                    EMAIL
                </a>
            </div>
        </div>
    </header>

    <main>
        <section class="hero">
            <div class="container">
                <p class="greeting">Hi 👋, I'm Aby Babu</p>
                <p class="title">Flutter Mobile Application Developer</p>
                <p class="description">Passionate Flutter developer crafting fast, scalable, and beautiful mobile applications</p>
            </div>
        </section>

        <div class="container">
            <div class="quote-section">
                <span class="icon">💬</span>
                <p class="quote-text">"The more varieties of different kinds of notations are still useful — don't only read the people who code like you."</p>
                <p class="quote-author">- Donald Knuth</p>
            </div>

            <div class="quote-section">
                <span class="icon">🚀</span>
                <p class="quote-text">"First, solve the problem. Then, write the code."</p>
                <p class="quote-author">- John Johnson</p>
            </div>

            <section class="about-section">
                <h3>👨‍💻 About Me</h3>
                <ul class="about-list">
                    <li>📱 Flutter Mobile Application Developer (Android & iOS)</li>
                    <li>🚀 Experienced in building production-ready apps with clean architecture</li>
                    <li>💡 Love turning business ideas into smooth, user-friendly applications</li>
                    <li>🧠 Focused on performance optimization, state management & scalable UI</li>
                    <li>☕ Fun fact: Debugging feels easier after a cup of coffee</li>
                </ul>
            </section>

            <section class="tech-section">
                <h3>🛠️ Tech Stack</h3>
                
                <div class="tech-category">
                    <h4>📱 Mobile Development</h4>
                    <div class="tech-badges">
                        <span class="badge">Flutter</span>
                        <span class="badge">Dart</span>
                        <span class="badge">Android</span>
                        <span class="badge">iOS</span>
                    </div>
                </div>

                <div class="tech-category">
                    <h4>⚙️ State Management & Architecture</h4>
                    <div class="tech-badges">
                        <span class="badge">Provider</span>
                        <span class="badge">MVC</span>
                        <span class="badge">Clean Architecture</span>
                    </div>
                </div>

                <div class="tech-category">
                    <h4>🔧 Tools & Services</h4>
                    <div class="tech-badges">
                        <span class="badge">Firebase</span>
                        <span class="badge">REST API</span>
                        <span class="badge">Git</span>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <footer>
        <div class="container">
            <p class="footer-message">💙 Open to collaboration on mobile projects!</p>
            <p class="footer-location">📍 India</p>
            <p style="margin-top: 1rem; color: var(--text-secondary);">📧 Open to freelance & full-time opportunities</p>
        </div>
    </footer>
</body>
</html>
