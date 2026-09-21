# portfolio
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Muhammad Daoud - Professional Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #0a0a0f;
      --bg-secondary: #12121a;
      --card: rgba(255, 255, 255, 0.03);
      --card-hover: rgba(255, 255, 255, 0.05);
      --primary: #00d4ff;
      --secondary: #9b59b6;
      --accent: #ff6b6b;
      --text: #f0f0f5;
      --text-muted: #b0b0c0;
      --glow: rgba(0, 212, 255, 0.4);
      --shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
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
      font-family: 'Poppins', sans-serif;
      background: var(--bg);
      color: var(--text);
      overflow-x: hidden;
      line-height: 1.6;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    ul {
      list-style: none;
    }

    img {
      max-width: 100%;
      height: auto;
    }
    nav {
      position: fixed;
      top: 0;
      width: 100%;
      padding: 1rem 5%;
      background: rgba(10, 10, 15, 0.8);
      backdrop-filter: blur(20px);
      z-index: 1000;
      transition: background 0.3s ease;
    }

    .nav-container {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--primary);
      letter-spacing: 1px;
    }

    .nav-links {
      display: flex;
      gap: 2rem;
    }

    .nav-links a {
      font-size: 0.875rem;
      font-weight: 500;
      color: var(--text-muted);
      transition: color 0.3s ease;
      position: relative;
    }

    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--primary);
      transition: width 0.3s ease;
    }

    .nav-links a:hover {
      color: var(--primary);
    }

    .nav-links a:hover::after {
      width: 100%;
    }

    .menu-toggle {
      display: none;
      font-size: 1.5rem;
      color: var(--primary);
      cursor: pointer;
    }
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      padding: 8rem 5% 4rem;
    }

    .hero-bg {
      position: absolute;
      inset: 0;
      background: 
        radial-gradient(ellipse 80% 50% at 20% 20%, rgba(0, 212, 255, 0.15) 0%, transparent 50%),
        radial-gradient(ellipse 60% 40% at 80% 80%, rgba(155, 89, 182, 0.12) 0%, transparent 50%),
        var(--bg);
      overflow: hidden;
    }

    .hero-bg::before {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: 
        linear-gradient(45deg, transparent 49%, rgba(0, 212, 255, 0.03) 50%, transparent 51%),
        linear-gradient(-45deg, transparent 49%, rgba(155, 89, 182, 0.03) 50%, transparent 51%);
      animation: gridMove 20s linear infinite;
      pointer-events: none;
    }

    @keyframes gridMove {
      0% { transform: translate(0, 0); }
      100% { transform: translate(-1%, -1%); }
    }

    .hero-container {
      display: grid;
      grid-template-cols: 1fr 1fr;
      gap 2rem;
      align-items: center;
      max-width: 1200px;
      width: 100%;
    }

    .hero-content {
      max-width: 500px;
    }

    .hero-name {
      font-size: 3.5rem;
      font-weight: 700;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      letter-spacing: 2px;
      margin-bottom: 1rem;
    }

    .hero-title {
      font-size: 1.25rem;
      color: var(--text-muted);
      margin-bottom: 1.5rem;
      font-weight: 400;
    }

    .hero-intro {
      font-size: 1.125rem;
      color: var(--text-muted);
      margin-bottom: 2rem;
      max-width: 400px;
    }

    .cta-buttons {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn {
      padding: 0.875rem 1.75rem;
      border-radius: 4px;
      font-weight: 500;
      transition: all 0.3s ease;
      cursor: pointer;
      border: none;
      font-family: inherit;
    }

    .btn-primary {
      background: var(--primary);
      color: var(--bg);
      box-shadow: 0 4px 20px var(--glow);
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 30px var(--glow);
    }

    .btn-secondary {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--text-muted);
    }

    .btn-secondary:hover {
      background: var(--card-hover);
      border-color: var(--primary);
      color: var(--primary);
    }

    .hero-visual {
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .cube {
      width: 200px;
      height: 200px;
      position: relative;
      transform-style: preserve-3d;
      animation: float 6s ease-in-out infinite;
    }

    .cube:hover {
      animation: spin 20s linear infinite;
    }

    .cube-face {
      position: absolute;
      width: 200px;
      height: 200px;
      backface-visibility: hidden;
      border: 1px solid rgba(0, 212, 255, 0.3);
      background: linear-gradient(135deg, rgba(0, 212, 255, 0.1), rgba(155, 89, 182, 0.1));
    }

    .cube-face.front {
      transform: rotateY(0deg) translateZ(100px);
    }

    .cube-face.right {
      transform: rotateY(90deg) translateZ(100px);
    }

    .cube-face.back {
      transform: rotateY(180deg) translateZ(100px);
    }

    .cube-face.left {
      transform: rotateY(-90deg) translateZ(100px);
    }

    .cube-face.top {
      transform: rotateX(90deg) translateZ(100px);
    }

    .cube-face.bottom {
      transform: rotateX(-90deg) translateZ(100px);
    }

    @keyframes float {
      0%, 100% { transform: translateY(0) rotateX(0deg) rotateY(0deg); }
      50% { transform: translateY(-20px) rotateX(10deg) rotateY(10deg); }
    }

    @keyframes spin {
      from { transform: rotateY(0deg); }
      to { transform: rotateY(360deg); }
    }

    .hero-bg {
      perspective: 1000px;
    }

    .hero-bg:hover .hero-name {
      transform: translate3d(
        calc((var(--mouse-x) - 50%) * 0.1rem),
        calc((var(--mouse-y) - 50%) * 0.1rem),
        0
      );
    }
    section {
      padding: 6rem 5%;
    }

    .section-title {
      font-size: 2.5rem;
      text-align: center;
      margin-bottom: 3rem;
      color: var(--primary);
      position: relative;
    }

    .section-title::after {
      content: '';
      position: absolute;
      bottom: -8px;
      left: 50%;
      transform: translateX(-50%);
      width: 60px;
      height: 3px;
      background: var(--primary);
    }
    .about-container {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-cols: 1fr 1fr;
      gap: 3rem;
      align-items: center;
    }

    .about-img {
      position: relative;
      width: 350px;
      height: 350px;
      border-radius: 12px;
      overflow: hidden;
    }

    .about-img::before {
      content: '';
      position: absolute;
      inset: -4px;
      border-radius: 16px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      z-index: -1;
      filter: blur(20px);
    }

    .about-img img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .about-content h2 {
      font-size: 2rem;
      margin-bottom: 1rem;
    }

    .about-content p {
      color: var(--text-muted);
      margin-bottom: 1.5rem;
    }

    .about-skills {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }

    .skill-badge {
      background: rgba(0, 212, 255, 0.15);
      color: var(--primary);
      padding: 0.25rem 0.75rem;
      border-radius: 20px;
      font-size: 0.75rem;
      font-weight: 500;
    }
    .skills-grid {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 2rem;
    }

    .skill-card {
      background: var(--card);
      border-radius: 12px;
      padding: 2rem;
      position: relative;
      overflow: hidden;
      transition: transform 0.3s ease;
    }

    .skill-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 3px;
      background: linear-gradient(90deg, var(--primary), var(--secondary));
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.3s ease;
    }

    .skill-card:hover {
      transform: translateY(-10px);
    }

    .skill-card:hover::before {
      transform: scaleX(1);
    }

    .skill-card h3 {
      font-size: 1.25rem;
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .skill-card h3::before {
      content: '';
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: var(--primary);
    }

    .tech-list {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }

    .tech-tag {
      background: rgba(255, 255, 255, 0.05);
      color: var(--text-muted);
      padding: 0.4rem 0.8rem;
      border-radius: 4px;
      font-size: 0.75rem;
      transition: all 0.3s ease;
    }

    .tech-tag:hover {
      background: var(--primary);
      color: var(--bg);
    }

    .progress-bar {
      width: 100%;
      height: 8px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 4px;
      overflow: hidden;
      margin-top: 1rem;
    }

    .progress-fill {
      height: 100%;
      background: var(--primary);
      width: 90%;
      border-radius: 4px;
      transition: width 1s ease;
    }
    .timeline {
      max-width: 1200px;
      margin: 0 auto;
      position: relative;
    }

    .timeline::before {
      content: '';
      position: absolute;
      left: 50%;
      top: 0;
      bottom: 0;
      width: 2px;
      background: linear-gradient(to bottom, var(--primary), var(--secondary));
      transform: translateX(-50%);
    }

    .timeline-item {
      padding: 2rem 0;
      display: flex;
      align-items: center;
      gap: 2rem;
    }

    .timeline-item:nth-child(odd) {
      flex-direction: row-reverse;
    }

    .timeline-dot {
      width: 20px;
      height: 20px;
      border-radius: 50%;
      background: var(--primary);
      flex-shrink: 0;
      position: relative;
    }

    .timeline-item:nth-child(odd) .timeline-dot {
      margin-left: auto;
    }

    .timeline-content {
      background: var(--card);
      border-radius: 12px;
      padding: 1.5rem 2rem;
      width: 100%;
    }

    .timeline-content h4 {
      font-size: 1.25rem;
      margin-bottom: 0.5rem;
    }

    .timeline-content span {
      color: var(--secondary);
      font-size: 0.875rem;
    }

    .timeline-content p {
      color: var(--text-muted);
      margin-top: 0.5rem;
    }
    .projects-grid {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 2rem;
    }

    .project-card {
      background: var(--card);
      border-radius: 12px;
      overflow: hidden;
      transition: transform 0.3s ease;
    }

    .project-card:hover {
      transform: translateY(-10px);
    }

    .project-image {
      height: 200px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--bg);
      font-size: 1rem;
    }

    .project-content {
      padding: 1.5rem;
    }

    .project-content h3 {
      font-size: 1.25rem;
      margin-bottom: 0.5rem;
    }

    .project-content p {
      color: var(--text-muted);
      font-size: 0.875rem;
      margin-bottom: 1.5rem;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-top: 1rem;
    }

    .tag {
      background: rgba(255, 255, 255, 0.05);
      color: var(--primary);
      padding: 0.4rem 0.8rem;
      border-radius: 4px;
      font-size: 0.75rem;
    }

    .project-links {
      margin-top: 1rem;
      display: flex;
      gap: 0.75rem;
    }

    .project-links a {
      padding: 0.5rem 1rem;
      background: var(--primary);
      color: var(--bg);
      border-radius: 4px;
      font-size: 0.875rem;
      transition: transform 0.3s ease;
    }

    .project-links a:hover {
      transform: translateY(-2px);
    }
    .gallery-grid {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.5rem;
    }

    .gallery-item {
      border-radius: 12px;
      overflow: hidden;
      aspect-ratio: 16/10;
      position: relative;
    }

    .gallery-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.5s ease;
    }

    .gallery-item:hover img {
      transform: scale(1.05);
    }

    .gallery-item::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(0, 0, 0, 0.7) 0%, transparent 50%);
      opacity: 0;
      transition: opacity 0.3s ease;
    }

    .gallery-item:hover::after {
      opacity: 1;
    }

    .gallery-item .title {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 1rem;
      color: var(--text);
    }
    .services-grid {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.5rem;
    }

    .service-card {
      background: var(--card);
      border-radius: 12px;
      padding: 2rem;
      display: flex;
      align-items: flex-start;
      gap: 1rem;
      transition: transform 0.3s ease;
    }

    .service-card:hover {
      transform: translateX(10px);
    }

    .service-icon {
      width: 50px;
      height: 50px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
    }

    .service-icon svg {
      width: 24px;
      height: 24px;
      color: var(--bg);
    }

    .service-card h4 {
      font-size: 1.1rem;
      margin-bottom: 0.5rem;
    }

    .service-card p {
      color: var(--text-muted);
      font-size: 0.875rem;
    }

    .service-card .btn {
      margin-top: 1rem;
      width: 100%;
    }

    .values-grid {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.5rem;
    }

    .value-card {
      background: var(--card);
      border-radius: 12px;
      padding: 2rem;
      text-align: center;
      transition: background 0.3s ease;
    }

    .value-card:hover {
      background: var(--card-hover);
    }

    .value-icon {
      width: 60px;
      height: 60px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 1.5rem;
    }

    .value-icon svg {
      width: 30px;
      height: 30px;
      color: var(--bg);
    }

    .value-card h4 {
      font-size: 1.2rem;
      margin-bottom: 1rem;
    }

    .value-card p {
      color: var(--text-muted);
    }

    .contact-container {
      max-width: 800px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3rem;
    }

    .contact-form {
      background: var(--card);
      border-radius: 12px;
      padding: 2rem;
    }

    .form-group {
      margin-bottom: 1.5rem;
    }

    .form-group label {
      display: block;
      margin-bottom: 0.5rem;
      color: var(--text-muted);
    }

    .form-group input,
    .form-group textarea,
    .form-group select {
      width: 100%;
      padding: 0.875rem;
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 6px;
      color: var(--text);
      font-family: inherit;
      transition: border-color 0.3s ease;
    }

    .form-group input:focus,
    .form-group textarea:focus {
      outline: none;
      border-color: var(--primary);
    }

    .contact-info h3 {
      font-size: 1.5rem;
      margin-bottom: 2rem;
    }

    .contact-info p {
      margin-bottom: 1rem;
      color: var(--text-muted);
    }

    .contact-info a {
      color: var(--primary);
      transition: color 0.3s ease;
    }

    .contact-info a:hover {
      color: var(--secondary);
    }

    .social-links {
      display: flex;
      gap: 1rem;
      margin-top: 2rem;
    }

    .social-link {
      width: 40px;
      height: 40px;
      background: rgba(255, 255, 255, 0.05);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background 0.3s ease;
    }

    .social-link:hover {
      background: var(--primary);
    }

    .social-link:hover svg {
      path: 14px;
    }

    .social-link svg {
      width: 20px;
      height: 20px;
      transition: fill 0.3s ease;
    }

    .social-link:hover svg fill {
      fill: var(--bg);
    }

    footer {
      text-align: center;
      padding: 3rem 5%;
      color: var(--text-muted);
      background: rgba(10, 10, 15, 0.5);
    }

    @media (max-width: 900px) {
      .hero-container,
      .about-container,
      .contact-container {
        grid-template-columns: 1fr;
        text-align: center;
      }

      .hero-visual {
      justify-content: center;
    }

    .timeline-item {
      flex-direction: column;
      gap: 1rem;
    }

    .timeline-item:nth-child(odd) {
      flex-direction: column;
    }

    .timeline-dot {
      margin: 0 auto 0.5rem;
    }

    .nav-links {
      display: none;
    }

    .menu-toggle {
      display: block;
    }

    .nav-active {
      display: flex;
      position: absolute;
      top: 100%;
      left: 0;
      width: 100%;
      background: rgba(10, 10, 15, 0.98);
      backdrop-filter: blur(20px);
      flex-direction: column;
      padding: 2rem 5%;
    }
  </style>
</head>
<body>

  <!-- Navigation -->
  <nav>
    <div class="nav-container">
      <div class="logo">Muhammad Daoud</div>
      <a href="#menu" class="menu-toggle" onclick="toggleMenu()">☰</a>
      <ul class="nav-links" id="nav-links">
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </nav>

  <!-- Hero Section -->
  <section class="hero">
    <div class="hero-bg"></div>
    <div class="hero-container">
      <div class="hero-content">
        <h1 class="hero-name">Muhammad Daoud</h1>
        <p class="hero-title">Web Developer | Graphic Designer | SEO Executive | Data Science Enthusiast</p>
        <p class="hero-intro">Motivated and detail-oriented professional with practical experience in web development, graphic design, SEO optimization, and data analysis. Passionate about creating meaningful digital solutions and continuously expanding technical expertise.</p>
        <div class="cta-buttons">
          <button class="btn btn-primary">View My Work</button>
          <button class="btn btn-secondary">Contact Me</button>
        </div>
      </div>
      <div class="hero-visual">
        <div class="cube" id="cube">
          <div class="cube-face front">Front</div>
          <div class="cube-face right">Right</div>
          <div class="cube-face back">Back</div>
          <div class="cube-face left">Left</div>
          <div class="cube-face top">Top</div>
          <div class="cube-face bottom">Bottom</div>
        </div>
      </div>
    </div>
  </section>

  <!-- About Section -->
  <section id="about" class="about">
    <div class="about-container">
      <div class="about-img">
        <!-- Profile picture placeholder -->
        <div style="width: 100%; height: 100%; background: linear-gradient(135deg, var(--primary), var(--secondary)); display: flex; align-items: center; justify-content: center; color: var(--bg); font-size: 2rem;">
          MD
        </div>
      </div>
      <div class="about-content">
        <h2>About Me</h2>
        <p>I'm a motivated and detail-oriented professional with practical experience in web development, graphic design, SEO, and digital tools. I combine technical expertise with creative problem-solving to deliver clean, maintainable solutions. I enjoy turning complex requirements into intuitive interfaces and reliable code.</p>
        <div class="about-skills">
          <span class="skill-badge">Web Development</span>
          <span class="skill-badge">Graphic Design</span>
          <span class="skill-badge">SEO</span>
          <span class="skill-badge">Data Science</span>
          <span class="skill-badge">MS Office</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Skills Section -->
  <section id="skills" class="skills">
    <div class="section-title">Skills</div>
    <div class="skills-grid">
      <!-- Web Development Card -->
      <div class="skill-card">
        <h3>Web Development</h3>
        <div class="tech-list">
          <span class="tech-tag">HTML</span>
          <span class="tech-tag">CSS</span>
          <span class="tech-tag">JavaScript</span>
          <span class="tech-tag">Responsive Design</span>
        </div>
        <div class="progress-bar">
          <div class="progress-fill" style="width: 90%;"></div>
        </div>
      </div>

      <!-- Graphic Design Card -->
      <div class="skill-card">
        <h3>Graphic Design</h3>
        <div class="tech-list">
          <span class="tech-tag">Adobe Photoshop</span>
          <span class="tech-tag">Adobe Illustrator</span>
          <span class="tech-tag">Canva</span>
          <span class="tech-tag">Social Media Design</span>
        </div>
        <div class="progress-bar">
          <div class="progress-fill" style="width: 85%;"></div>
        </div>
      </div>

      <!-- SEO Card -->
      <div class="skill-card">
        <h3>SEO</h3>
        <div class="tech-list">
          <span class="tech-tag">On-Page SEO</span>
          <span class="tech-tag">Off-Page SEO</span>
          <span class="tech-tag">Keyword Research</span>
          <span class="tech-tag">Website Optimization</span>
        </div>
        <div class="progress-bar">
          <div class="progress-fill" style="width:
