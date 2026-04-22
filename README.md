``html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sarthak Vyas | Portfolio</title>
  <meta name="description" content="Portfolio of Sarthak Vyas — B.Tech CSE student, web developer, and creative designer." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Manrope:wght@500;600;700;800&display=swap" rel="stylesheet">

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --bg: #0b0f19;
      --bg-soft: #111827;
      --surface: rgba(17, 24, 39, 0.72);
      --surface-2: #121a2b;
      --card: rgba(255, 255, 255, 0.04);
      --card-hover: rgba(255, 255, 255, 0.07);
      --border: rgba(255, 255, 255, 0.10);
      --border-strong: rgba(255, 255, 255, 0.18);
      --text: #f3f4f6;
      --muted: #9ca3af;
      --muted-2: #cbd5e1;
      --primary: #3b82f6;
      --primary-2: #60a5fa;
      --accent: #22c55e;
      --shadow: 0 10px 30px rgba(0, 0, 0, 0.30);
      --radius: 18px;
      --radius-sm: 12px;
      --max: 1180px;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Inter', sans-serif;
      background:
        radial-gradient(circle at top left, rgba(59, 130, 246, 0.18), transparent 28%),
        radial-gradient(circle at 85% 20%, rgba(34, 197, 94, 0.12), transparent 24%),
        linear-gradient(180deg, #0a0f1a 0%, #0b1020 50%, #0a0d16 100%);
      color: var(--text);
      overflow-x: hidden;
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    .container {
      width: min(var(--max), calc(100% - 2rem));
      margin: 0 auto;
    }

    .blur-orb {
      position: fixed;
      width: 380px;
      height: 380px;
      border-radius: 50%;
      filter: blur(80px);
      opacity: 0.18;
      pointer-events: none;
      z-index: 0;
    }

    .orb-1 {
      top: 10%;
      left: -90px;
      background: var(--primary);
      animation: floatY 11s ease-in-out infinite;
    }

    .orb-2 {
      right: -100px;
      top: 50%;
      background: #14b8a6;
      animation: floatY 14s ease-in-out infinite reverse;
    }

    @keyframes floatY {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-30px); }
    }

    .grid-bg {
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(255,255,255,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.03) 1px, transparent 1px);
      background-size: 42px 42px;
      mask-image: linear-gradient(to bottom, rgba(0,0,0,0.7), transparent);
      pointer-events: none;
      z-index: 0;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 1000;
      backdrop-filter: blur(14px);
      background: rgba(10, 15, 26, 0.70);
      border-bottom: 1px solid rgba(255,255,255,0.06);
    }

    .nav {
      width: min(var(--max), calc(100% - 2rem));
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      min-height: 76px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 0.85rem;
      font-family: 'Manrope', sans-serif;
      font-weight: 800;
      letter-spacing: 0.02em;
    }

    .brand-badge {
      width: 40px;
      height: 40px;
      display: grid;
      place-items: center;
      border-radius: 12px;
      background: linear-gradient(135deg, var(--primary), var(--primary-2));
      color: white;
      box-shadow: 0 10px 24px rgba(59,130,246,0.35);
      font-size: 0.95rem;
    }

    .brand-text {
      font-size: 1rem;
      color: var(--text);
    }

    .nav-links {
      list-style: none;
      display: flex;
      align-items: center;
      gap: 1.5rem;
    }

    .nav-links a {
      color: var(--muted-2);
      font-size: 0.95rem;
      font-weight: 500;
      transition: color 0.25s ease, transform 0.25s ease;
    }

    .nav-links a:hover,
    .nav-links a.active {
      color: #ffffff;
      transform: translateY(-1px);
    }

    .nav-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.85rem 1.15rem;
      border-radius: 12px;
      background: linear-gradient(135deg, var(--primary), var(--primary-2));
      color: white;
      font-weight: 600;
      box-shadow: 0 12px 24px rgba(59,130,246,0.25);
      transition: transform 0.25s ease, box-shadow 0.25s ease;
    }

    .nav-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 16px 32px rgba(59,130,246,0.35);
    }

    section {
      position: relative;
      z-index: 1;
    }

    #hero {
      min-height: calc(100vh - 76px);
      display: flex;
      align-items: center;
      padding: 5.5rem 0 4rem;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 3rem;
      align-items: center;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 0.65rem;
      padding: 0.45rem 0.85rem;
      border: 1px solid rgba(96,165,250,0.25);
      background: rgba(59,130,246,0.10);
      color: #bfdbfe;
      border-radius: 999px;
      font-size: 0.9rem;
      font-weight: 600;
      margin-bottom: 1.2rem;
      animation: fadeUp 0.8s ease both;
    }

    .eyebrow::before {
      content: "";
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: var(--accent);
      box-shadow: 0 0 14px rgba(34,197,94,0.7);
    }

    .hero h1 {
      font-family: 'Manrope', sans-serif;
      font-size: clamp(2.8rem, 6vw, 5.6rem);
      line-height: 1.02;
      letter-spacing: -0.04em;
      margin-bottom: 1.2rem;
      animation: fadeUp 0.9s ease 0.08s both;
    }

    .hero h1 .gradient {
      background: linear-gradient(135deg, #ffffff, #93c5fd 55%, #60a5fa);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .hero p {
      max-width: 650px;
      font-size: 1.08rem;
      color: var(--muted-2);
      margin-bottom: 1.8rem;
      animation: fadeUp 0.95s ease 0.16s both;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      margin-bottom: 2rem;
      animation: fadeUp 1s ease 0.24s both;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.6rem;
      padding: 0.95rem 1.25rem;
      border-radius: 14px;
      font-weight: 600;
      transition: transform 0.25s ease, box-shadow 0.25s ease, background 0.25s ease, border-color 0.25s ease;
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--primary), var(--primary-2));
      color: white;
      box-shadow: 0 14px 32px rgba(59,130,246,0.28);
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 18px 36px rgba(59,130,246,0.38);
    }

    .btn-secondary {
      border: 1px solid var(--border);
      background: rgba(255,255,255,0.03);
      color: var(--text);
    }

    .btn-secondary:hover {
      transform: translateY(-2px);
      background: rgba(255,255,255,0.06);
      border-color: var(--border-strong);
    }

    .hero-points {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      animation: fadeUp 1.05s ease 0.32s both;
    }

    .pill {
      padding: 0.75rem 0.95rem;
      border-radius: 999px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      color: var(--muted-2);
      font-size: 0.95rem;
    }

    .hero-card {
      position: relative;
      background: linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,255,255,0.03));
      border: 1px solid rgba(255,255,255,0.10);
      border-radius: 28px;
      padding: 1.3rem;
      box-shadow: var(--shadow);
      animation: fadeScale 1s ease 0.2s both;
      overflow: hidden;
    }

    .hero-card::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(59,130,246,0.16), transparent 35%, rgba(255,255,255,0.02));
      pointer-events: none;
    }

    .hero-panel {
      border-radius: 22px;
      padding: 1.6rem;
      background:
        linear-gradient(180deg, rgba(255,255,255,0.05), rgba(255,255,255,0.02)),
        rgba(11, 15, 25, 0.9);
      border: 1px solid rgba(255,255,255,0.08);
    }

    .mini-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 1.2rem;
    }

    .dots {
      display: flex;
      gap: 0.45rem;
    }

    .dots span {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      display: block;
    }

    .dots span:nth-child(1) { background: #ef4444; }
    .dots span:nth-child(2) { background: #f59e0b; }
    .dots span:nth-child(3) { background: #22c55e; }

    .panel-label {
      font-size: 0.88rem;
      color: var(--muted);
    }

    .code-line {
      font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
      color: #dbeafe;
      font-size: 0.95rem;
      margin-bottom: 0.85rem;
      opacity: 0;
      transform: translateY(8px);
      animation: revealCode 0.7s ease forwards;
    }

    .code-line:nth-child(2) { animation-delay: 0.45s; }
    .code-line:nth-child(3) { animation-delay: 0.7s; }
    .code-line:nth-child(4) { animation-delay: 0.95s; }
    .code-line:nth-child(5) { animation-delay: 1.2s; }

    .token-key { color: #93c5fd; }
    .token-string { color: #86efac; }
    .token-value { color: #f9a8d4; }

    .section {
      padding: 6rem 0;
    }

    .section-head {
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 1rem;
      margin-bottom: 2.2rem;
    }

    .kicker {
      color: #93c5fd;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      font-size: 0.8rem;
      font-weight: 700;
      margin-bottom: 0.6rem;
    }

    .section-title {
      font-family: 'Manrope', sans-serif;
      font-size: clamp(2rem, 4.2vw, 3.2rem);
      line-height: 1.05;
      letter-spacing: -0.03em;
    }

    .section-subtext {
      max-width: 620px;
      color: var(--muted-2);
      font-size: 1rem;
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      gap: 1.5rem;
    }

    .card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.5rem;
      box-shadow: var(--shadow);
      backdrop-filter: blur(10px);
    }

    .about-text p {
      color: var(--muted-2);
      margin-bottom: 1rem;
      font-size: 1rem;
    }

    .about-points {
      display: grid;
      gap: 0.9rem;
      margin-top: 1.4rem;
    }

    .about-point {
      display: flex;
      gap: 0.8rem;
      align-items: flex-start;
      color: var(--muted-2);
    }

    .about-point .icon {
      flex: 0 0 34px;
      width: 34px;
      height: 34px;
      display: grid;
      place-items: center;
      border-radius: 10px;
      background: rgba(59,130,246,0.12);
      color: #bfdbfe;
      border: 1px solid rgba(59,130,246,0.18);
      font-size: 0.95rem;
    }

    .stats {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
    }

    .stat {
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 16px;
      padding: 1.25rem;
      transition: transform 0.25s ease, border-color 0.25s ease, background 0.25s ease;
    }

    .stat:hover {
      transform: translateY(-4px);
      border-color: rgba(96,165,250,0.28);
      background: rgba(255,255,255,0.05);
    }

    .stat h3 {
      font-family: 'Manrope', sans-serif;
      font-size: 2rem;
      margin-bottom: 0.3rem;
    }

    .stat p {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1rem;
    }

    .skill-card h3 {
      font-size: 1.05rem;
      margin-bottom: 1rem;
      font-family: 'Manrope', sans-serif;
    }

    .skill-list {
      display: flex;
      flex-wrap: wrap;
      gap: 0.7rem;
    }

    .tag {
      padding: 0.65rem 0.9rem;
      border-radius: 999px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      color: var(--muted-2);
      font-size: 0.92rem;
      transition: transform 0.2s ease, border-color 0.2s ease, background 0.2s ease;
    }

    .tag:hover {
      transform: translateY(-2px);
      border-color: rgba(96,165,250,0.28);
      background: rgba(59,130,246,0.08);
    }

    .projects-list {
      display: grid;
      gap: 1rem;
    }

    .project {
      display: grid;
      grid-template-columns: 70px 1fr auto;
      gap: 1.2rem;
      align-items: center;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 1.35rem;
      box-shadow: var(--shadow);
      transition: transform 0.28s ease, border-color 0.28s ease, background 0.28s ease;
      cursor: default;
    }

    .project:hover {
      transform: translateY(-5px);
      border-color: rgba(96,165,250,0.28);
      background: rgba(255,255,255,0.05);
    }

    .project-index {
      width: 56px;
      height: 56px;
      border-radius: 16px;
      display: grid;
      place-items: center;
      font-family: 'Manrope', sans-serif;
      font-weight: 800;
      color: #bfdbfe;
      background: rgba(59,130,246,0.10);
      border: 1px solid rgba(59,130,246,0.18);
    }

    .project h3 {
      font-size: 1.18rem;
      margin-bottom: 0.35rem;
      font-family: 'Manrope', sans-serif;
    }

    .project p {
      color: var(--muted-2);
      margin-bottom: 0.8rem;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.55rem;
    }

    .project .arrow {
      font-size: 1.3rem;
      color: #93c5fd;
      padding-right: 0.4rem;
    }

    .contact-wrap {
      text-align: center;
      padding: 3rem 1.5rem;
      background:
        radial-gradient(circle at top, rgba(59,130,246,0.18), transparent 32%),
        rgba(255,255,255,0.03);
      border: 1px solid var(--border);
      border-radius: 28px;
      box-shadow: var(--shadow);
    }

    .contact-wrap h2 {
      font-family: 'Manrope', sans-serif;
      font-size: clamp(2.2rem, 5vw, 4rem);
      line-height: 1.05;
      margin-bottom: 0.9rem;
    }

    .contact-wrap p {
      color: var(--muted-2);
      max-width: 680px;
      margin: 0 auto 1.5rem;
    }

    .email-link {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.95rem 1.25rem;
      border-radius: 14px;
      border: 1px solid var(--border);
      background: rgba(255,255,255,0.04);
      color: #ffffff;
      font-weight: 600;
      margin-bottom: 1.5rem;
      transition: transform 0.25s ease, border-color 0.25s ease, background 0.25s ease;
      word-break: break-word;
    }

    .email-link:hover {
      transform: translateY(-2px);
      border-color: rgba(96,165,250,0.28);
      background: rgba(59,130,246,0.08);
    }

    .socials {
      display: flex;
      justify-content: center;
      gap: 0.9rem;
      flex-wrap: wrap;
    }

    .social {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-width: 130px;
      padding: 0.9rem 1.1rem;
      border-radius: 14px;
      border: 1px solid var(--border);
      background: rgba(255,255,255,0.04);
      color: var(--text);
      font-weight: 600;
      transition: transform 0.25s ease, border-color 0.25s ease, background 0.25s ease, box-shadow 0.25s ease;
    }

    .social:hover {
      transform: translateY(-3px);
      border-color: rgba(96,165,250,0.28);
      background: rgba(59,130,246,0.08);
      box-shadow: 0 10px 24px rgba(0,0,0,0.2);
    }

    footer {
      padding: 1.5rem 0 2.5rem;
      color: var(--muted);
      text-align: center;
      font-size: 0.95rem;
      width: 100%;
      position: relative;
      z-index: 1;
    }

    .reveal {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity 0.8s ease, transform 0.8s ease;
    }

    .reveal.show {
      opacity: 1;
      transform: translateY(0);
    }

    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(24px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes fadeScale {
      from {
        opacity: 0;
        transform: translateY(24px) scale(0.98);
      }
      to {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    @keyframes revealCode {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @media (max-width: 980px) {
      .hero-grid,
      .about-grid,
      .skills-grid {
        grid-template-columns: 1fr;
      }

      .section-head {
        align-items: start;
        flex-direction: column;
      }

      .project {
        grid-template-columns: 1fr;
      }

      .project .arrow {
        padding-right: 0;
      }
    }

    @media (max-width: 760px) {
      .nav {
        min-height: 72px;
      }

      .nav-links {
        display: none;
      }

      #hero {
        padding-top: 3.5rem;
      }

      .hero h1 {
        font-size: clamp(2.5rem, 11vw, 4rem);
      }

      .stats {
        grid-template-columns: 1fr;
      }

      .socials {
        flex-direction: column;
        align-items: stretch;
      }

      .social {
        width: 100%;
      }
    }
  </style>
</head>
<body>
  <div class="grid-bg"></div>
  <div class="blur-orb orb-1"></div>
  <div class="blur-orb orb-2"></div>

  <header>
    <nav class="nav">
      <a href="#hero" class="brand" aria-label="Sarthak Vyas home">
        <span class="brand-badge">SV</span>
        <span class="brand-text">Sarthak Vyas</span>
      </a>

      <ul class="nav-links">
        <li><a href="#about" class="nav-link">About</a></li>
        <li><a href="#skills" class="nav-link">Skills</a></li>
        <li><a href="#projects" class="nav-link">Projects</a></li>
        <li><a href="#contact" class="nav-link">Contact</a></li>
      </ul>

      <a href="#contact" class="nav-btn">Hire Me</a>
    </nav>
  </header>

  <main>
    <section id="hero">
      <div class="container hero">
        <div class="hero-grid">
          <div>
            <div class="eyebrow">B.Tech CSE Student • Web Developer • Creative Designer</div>

            <h1>
              Building clean, modern and
              <span class="gradient">professional digital experiences.</span>
            </h1>

            <p>
              I’m <strong>Sarthak Vyas</strong>, a Computer Science student at Gautam Buddha University with a strong interest in web development, UI design, and creative problem solving. I like building websites that are visually strong, easy to use, and polished enough to feel production-ready.
            </p>

            <div class="hero-actions">
              <a href="#projects" class="btn btn-primary">View Projects</a>
              <a href="#contact" class="btn btn-secondary">Get In Touch</a>
            </div>

            <div class="hero-points">
              <span class="pill">Based in Greater Noida, India</span>
              <span class="pill">Open to internships</span>
              <span class="pill">Focused on frontend development</span>
            </div>
          </div>

          <div class="hero-card">
            <div class="hero-panel">
              <div class="mini-top">
                <div class="dots">
                  <span></span><span></span><span></span>
                </div>
                <div class="panel-label">portfolio.js</div>
              </div>

              <div class="code-line"><span class="token-key">const</span> developer = {</div>
              <div class="code-line">&nbsp;&nbsp;<span class="token-key">name</span>: <span class="token-string">"Sarthak Vyas"</span>,</div>
              <div class="code-line">&nbsp;&nbsp;<span class="token-key">role</span>: <span class="token-string">"Web Developer"</span>,</div>
              <div class="code-line">&nbsp;&nbsp;<span class="token-key">focus</span>: <span class="token-value">["HTML", "CSS", "JavaScript", "Design"]</span>,</div>
              <div class="code-line">};</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="about" class="section">
      <div class="container">
        <div class="section-head reveal">
          <div>
            <div class="kicker">About</div>
            <h2 class="section-title">Who I Am</h2>
          </div>
          <p class="section-subtext">
            A developer with a growing technical foundation and a strong eye for design, clarity, and presentation.
          </p>
        </div>

        <div class="about-grid">
          <div class="card reveal">
            <div class="about-text">
              <p>
                I am pursuing a <strong>B.Tech in Computer Science</strong> at <strong>Gautam Buddha University</strong>. My main interests are web development, programming, and building interfaces that feel modern and professional.
              </p>
              <p>
                Over the last few years, I’ve been improving my skills across frontend technologies, design tools, and practical projects. I enjoy learning by building and continuously refining my work.
              </p>
              <p>
                Outside of coding, I’m also interested in <strong>photography, video editing, and digital content creation</strong>, which helps me bring a creative perspective to technical projects.
              </p>
            </div>

            <div class="about-points">
              <div class="about-point">
                <div class="icon">🎓</div>
                <div>Currently studying at Gautam Buddha University</div>
              </div>
              <div class="about-point">
                <div class="icon">📍</div>
                <div>Based in Greater Noida, India</div>
              </div>
              <div class="about-point">
                <div class="icon">🤝</div>
                <div>Open to internships, freelance work, and collaborations</div>
              </div>
            </div>
          </div>

          <div class="card reveal">
            <div class="stats">
              <div class="stat">
                <h3>1+</h3>
                <p>Years of learning and building</p>
              </div>
              <div class="stat">
                <h3>3+</h3>
                <p>Projects completed</p>
              </div>
              <div class="stat">
                <h3>2+</h3>
                <p>Core programming languages practiced</p>
              </div>
              <div class="stat">
                <h3>∞</h3>
                <p>Curiosity and willingness to improve</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="skills" class="section">
      <div class="container">
        <div class="section-head reveal">
          <div>
            <div class="kicker">Skills</div>
            <h2 class="section-title">What I Work With</h2>
          </div>
          <p class="section-subtext">
            A combination of development, tools, and creative skills that support both design and implementation.
          </p>
        </div>

        <div class="skills-grid">
          <div class="card skill-card reveal">
            <h3>Languages</h3>
            <div class="skill-list">
              <span class="tag">HTML</span>
              <span class="tag">CSS</span>
              <span class="tag">JavaScript</span>
              <span class="tag">Python</span>
              <span class="tag">C++</span>
              <span class="tag">Java</span>
            </div>
          </div>

          <div class="card skill-card reveal">
            <h3>Tools & Platforms</h3>
            <div class="skill-list">
              <span class="tag">GitHub</span>
              <span class="tag">VS Code</span>
              <span class="tag">Canva</span>
              <span class="tag">Linux</span>
              <span class="tag">Figma</span>
              <span class="tag">GitHub Pages</span>
            </div>
          </div>

          <div class="card skill-card reveal">
            <h3>Creative Skills</h3>
            <div class="skill-list">
              <span class="tag">Web Design</span>
              <span class="tag">Video Editing</span>
              <span class="tag">Photography</span>
              <span class="tag">Content Creation</span>
              <span class="tag">Visual Storytelling</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="projects" class="section">
      <div class="container">
        <div class="section-head reveal">
          <div>
            <div class="kicker">Projects</div>
            <h2 class="section-title">Selected Work</h2>
          </div>
          <p class="section-subtext">
            Projects that show my interest in frontend development, presentation, and practical problem solving.
          </p>
        </div>

        <div class="projects-list">
          <div class="project reveal">
            <div class="project-index">01</div>
            <div>
              <h3>Portfolio Website</h3>
              <p>Personal portfolio built with HTML and CSS, focused on responsive layout, clean visual hierarchy, and professional presentation.</p>
              <div class="project-tags">
                <span class="tag">HTML</span>
                <span class="tag">CSS</span>
                <span class="tag">Responsive Design</span>
              </div>
            </div>
            <div class="arrow">•</div>
          </div>

          <div class="project reveal">
            <div class="project-index">02</div>
            <div>
              <h3>Digital Resume</h3>
              <p>A professionally designed resume created in Canva and optimized for clear communication, clean structure, and job applications.</p>
              <div class="project-tags">
                <span class="tag">Canva</span>
                <span class="tag">Resume Design</span>
                <span class="tag">PDF</span>
              </div>
            </div>
            <div class="arrow">•</div>
          </div>

          <div class="project reveal">
            <div class="project-index">03</div>
            <div>
              <h3>Fire Fighter Robot</h3>
              <p>A robotics project focused on detecting fire and extinguishing it automatically. Built as a practical problem-solving concept using hardware and programming logic.</p>
              <div class="project-tags">
                <span class="tag">Robotics</span>
                <span class="tag">Embedded Logic</span>
                <span class="tag">Problem Solving</span>
              </div>
            </div>
            <div class="arrow">•</div>
          </div>
        </div>
      </div>
    </section>

    <section id="contact" class="section">
      <div class="container">
        <div class="contact-wrap reveal">
          <div class="kicker">Contact</div>
          <h2>Let’s Build Something Meaningful</h2>
          <p>
            If you’re looking for a motivated student developer for internships, collaborations, or freelance opportunities, I’d be glad to connect.
          </p>

          <a href="mailto:vyassarthak444@gmail.com" class="email-link">vyassarthak444@gmail.com</a>

          <div class="socials">
            <a class="social" href="https://instagram.com/sarthakvyas_15" target="blank" rel="noopener noreferrer">Instagram</a>
            <a class="social" href="https://www.linkedin.com/in/sarthak-vyas-8977653a9" target="blank" rel="noopener noreferrer">LinkedIn</a>
            <a class="social" href="https://github.com/vyadsatyhak-bit" target="blank" rel="noopener noreferrer">GitHub</a>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    © 2026 Sarthak Vyas • Built with HTML, CSS and JavaScript
  </footer>

  <script>
    const reveals = document.querySelectorAll('.reveal');

    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('show');
        }
      });
    }, {
      threshold: 0.12
    });

    reveals.forEach((el) => observer.observe(el));

    const sections = document.querySelectorAll('section[id]');
    const navLinks = document.querySelectorAll('.nav-link');

    function setActiveLink() {
      let current = 'hero';

      sections.forEach((section) => {
        const sectionTop = section.offsetTop - 140;
        if (window.scrollY >= sectionTop) {
          current = section.getAttribute('id');
        }
      });

      navLinks.forEach((link) => {
        link.classList.toggle('active', link.getAttribute('href') === '#' + current);
      });
    }

    window.addEventListener('scroll', setActiveLink);
    window.addEventListener('load', setActiveLink);
  </script>
</body>
</html>
``
