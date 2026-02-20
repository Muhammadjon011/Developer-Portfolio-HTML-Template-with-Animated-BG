<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="python.py">
    <title>DevVision | Creative Developer</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/js/all.min.js"></script>
    <style>
        :root {
            --bg: #0f172a;
            --primary: #38bdf8;
            --secondary: #818cf8;
            --text: #f8fafc;
            --card-bg: rgba(30, 41, 59, 0.7);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            overflow-x: hidden;
        }

        /* Animated Background */
        .bg-glow {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle at 50% 50%, #1e293b 0%, #0f172a 100%);
        }

        .blob {
            position: absolute;
            width: 500px;
            height: 500px;
            background: linear-gradient(135deg, rgba(56, 189, 248, 0.2), rgba(129, 140, 248, 0.2));
            filter: blur(80px);
            border-radius: 50%;
            z-index: -1;
            animation: move 20s infinite alternate;
        }

        @keyframes move {
            from { transform: translate(-10%, -10%); }
            to { transform: translate(20%, 20%); }
        }

        /* Navigation */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 2rem 10%;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(10px);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            letter-spacing: -1px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links a {
            color: var(--text);
            text-decoration: none;
            margin-left: 2rem;
            font-size: 0.9rem;
            transition: 0.3s;
            opacity: 0.8;
        }

        .nav-links a:hover {
            opacity: 1;
            color: var(--primary);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 1rem;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            line-height: 1.1;
        }

        .hero p {
            font-size: 1.2rem;
            color: #94a3b8;
            max-width: 600px;
            margin-bottom: 2rem;
        }

        .typing-text {
            color: var(--primary);
            border-right: 3px solid var(--primary);
            padding-right: 5px;
            animation: blink 0.75s step-end infinite;
        }

        @keyframes blink {
            from, to { border-color: transparent }
            50% { border-color: var(--primary); }
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
        }

        .btn {
            padding: 0.8rem 2rem;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
        }

        .btn-primary {
            background: var(--primary);
            color: var(--bg);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(56, 189, 248, 0.3);
        }

        .btn-outline {
            border: 1px solid rgba(255,255,255,0.1);
            color: var(--text);
        }

        .btn-outline:hover {
            background: rgba(255,255,255,0.05);
        }

        /* Features Section */
        .features {
            padding: 5rem 10%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .card {
            background: var(--card-bg);
            padding: 2.5rem;
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.05);
            transition: 0.4s;
            cursor: default;
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            background: rgba(30, 41, 59, 0.9);
        }

        .card i {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 1.5rem;
        }

        .card h3 {
            margin-bottom: 1rem;
        }

        .card p {
            color: #94a3b8;
            line-height: 1.6;
        }

        /* Code Block Animation */
        .code-window {
            background: #011627;
            border-radius: 10px;
            padding: 20px;
            margin-top: 4rem;
            box-shadow: 0 20px 50px rgba(0,0,0,0.5);
            width: 100%;
            max-width: 700px;
            text-align: left;
            font-family: 'Courier New', Courier, monospace;
            position: relative;
        }

        .dots {
            display: flex;
            gap: 8px;
            margin-bottom: 15px;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .red { background: #ff5f56; }
        .yellow { background: #ffbd2e; }
        .green { background: #27c93f; }

        .code-content {
            color: #d6deeb;
            font-size: 0.9rem;
        }

        .keyword { color: #c792ea; }
        .function { color: #82aaff; }
        .string { color: #ecc48d; }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>

    <div class="bg-glow"></div>
    <div class="blob"></div>

    <nav>
        <div class="logo"><DEV.VISION /></div>
        <div class="nav-links">
            <a href="#work">Work</a>
            <a href="#services">Services</a>
            <a href="#contact">Contact</a>
            <a href="#" class="btn btn-outline" style="padding: 0.5rem 1.2rem;">Resume</a>
        </div>
    </nav>

    <section class="hero">
        <h1>Building Digital <br><span class="typing-text" id="typewriter"></span></h1>
        <p>A full-stack developer specializing in building exceptional digital experiences that are fast, accessible, and visually stunning.</p>
        
        <div class="cta-buttons">
            <a href="#" class="btn btn-primary">View Projects</a>
            <a href="#" class="btn btn-outline">Let's Talk</a>
        </div>

        <div class="code-window">
            <div class="dots">
                <div class="dot red"></div>
                <div class="dot yellow"></div>
                <div class="dot green"></div>
            </div>
            <div class="code-content">
                <div><span class="keyword">const</span> developer = {</div>
                <div style="padding-left: 20px;">name: <span class="string">'Alex Rivera'</span>,</div>
                <div style="padding-left: 20px;">skills: [<span class="string">'React'</span>, <span class="string">'Node'</span>, <span class="string">'Three.js'</span>],</div>
                <div style="padding-left: 20px;"><span class="function">passion</span>: () => <span class="string">'Clean Code'</span></div>
                <div>};</div>
            </div>
        </div>
    </section>

    <section class="features" id="services">
        <div class="card">
            <i class="fas fa-code"></i>
            <h3>Frontend Dev</h3>
            <p>Creating responsive, high-performance user interfaces using modern frameworks like React and Vue.</p>
        </div>
        <div class="card">
            <i class="fas fa-server"></i>
            <h3>Backend Arch</h3>
            <p>Designing scalable server-side logic and robust API structures with Node.js and PostgreSQL.</p>
        </div>
        <div class="card">
            <i class="fas fa-mobile-alt"></i>
            <h3>Mobile First</h3>
            <p>Optimizing experiences for every screen size, ensuring your product looks great everywhere.</p>
        </div>
    </section>

    <script>
        // Typewriter Effect
        const textElement = document.getElementById('typewriter');
        const phrases = ['Experiences', 'Solutions', 'Interfaces', 'Ecosystems'];
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;

        function type() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                textElement.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
            } else {
                textElement.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
            }

            let typeSpeed = isDeleting ? 100 : 200;

            if (!isDeleting && charIndex === currentPhrase.length) {
                isDeleting = true;
                typeSpeed = 2000; // Pause at end
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
                typeSpeed = 500;
            }

            setTimeout(type, typeSpeed);
        }

        // Start animation
        document.addEventListener('DOMContentLoaded', () => {
            type();
            
            // Mouse move effect for the blob
            const blob = document.querySelector('.blob');
            document.addEventListener('mousemove', (e) => {
                const x = e.clientX;
                const y = e.clientY;
                blob.style.left = x - 250 + 'px';
                blob.style.top = y - 250 + 'px';
            });
        });
    </script>
</body>
</html>
            
