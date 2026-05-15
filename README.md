<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Kunal Singh — Graphic & Product Designer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0a0a0a;
      --surface: #111111;
      --surface2: #161616;
      --border: rgba(255,255,255,0.08);
      --text: #f0f0f0;
      --muted: #888;
      --accent: #c8ff00;
      --accent2: #e8e8e8;
      --radius: 16px;
      --font-display: 'Syne', sans-serif;
      --font-body: 'DM Sans', sans-serif;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--font-body);
      font-size: 16px;
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 20px 48px;
      background: rgba(10,10,10,0.85);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }
    .nav-logo {
      display: flex; align-items: center; gap: 10px;
      text-decoration: none; color: var(--text);
      font-family: var(--font-display); font-weight: 700; font-size: 15px;
    }
    .nav-logo img {
      width: 36px; height: 36px; border-radius: 50%; object-fit: cover;
      border: 2px solid var(--border);
    }
    .nav-links { display: flex; align-items: center; gap: 36px; }
    .nav-links a {
      text-decoration: none; color: var(--muted);
      font-size: 14px; font-weight: 400;
      transition: color .2s;
    }
    .nav-links a:hover { color: var(--text); }
    .nav-cta {
      background: var(--text); color: #000 !important;
      padding: 9px 20px; border-radius: 100px;
      font-weight: 600; font-size: 13px !important;
      transition: background .2s, transform .15s !important;
    }
    .nav-cta:hover { background: var(--accent) !important; transform: scale(1.03); }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex; flex-direction: column;
      justify-content: center; align-items: flex-start;
      padding: 140px 48px 80px;
      position: relative; overflow: hidden;
    }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      border: 1px solid var(--border); border-radius: 100px;
      padding: 6px 16px; font-size: 13px; color: var(--muted);
      margin-bottom: 32px;
    }
    .hero-badge span { width: 6px; height: 6px; border-radius: 50%; background: var(--accent); display: inline-block; animation: pulse 2s infinite; }
    @keyframes pulse { 0%,100%{opacity:1}50%{opacity:.4} }

    .hero h1 {
      font-family: var(--font-display);
      font-size: clamp(42px, 6vw, 88px);
      font-weight: 800; line-height: 1.05;
      letter-spacing: -0.03em;
      max-width: 800px;
      margin-bottom: 28px;
    }
    .hero h1 em { font-style: normal; color: var(--muted); }
    .hero p {
      color: var(--muted); font-size: 17px; max-width: 480px;
      margin-bottom: 40px; line-height: 1.7;
    }
    .hero-actions { display: flex; gap: 16px; align-items: center; }
    .btn-primary {
      background: var(--text); color: #000;
      padding: 14px 32px; border-radius: 100px;
      font-family: var(--font-display); font-weight: 700; font-size: 15px;
      text-decoration: none; transition: background .2s, transform .15s;
      display: inline-block;
    }
    .btn-primary:hover { background: var(--accent); transform: translateY(-2px); }
    .btn-outline {
      border: 1px solid var(--border); color: var(--text);
      padding: 14px 32px; border-radius: 100px;
      font-family: var(--font-display); font-weight: 600; font-size: 15px;
      text-decoration: none; transition: border-color .2s, transform .15s;
      display: inline-block;
    }
    .btn-outline:hover { border-color: var(--text); transform: translateY(-2px); }

    /* hero bg orb */
    .hero-orb {
      position: absolute; right: -100px; top: 50%;
      transform: translateY(-50%);
      width: 600px; height: 600px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(200,255,0,0.08) 0%, transparent 70%);
      pointer-events: none;
    }
    .hero-img {
      position: absolute; right: 80px; bottom: 0;
      width: 380px; opacity: 0.18;
      pointer-events: none;
    }

    /* stats bar */
    .stats-bar {
      display: flex; gap: 0;
      border: 1px solid var(--border);
      border-radius: var(--radius);
      overflow: hidden;
      margin-top: 64px;
    }
    .stat {
      flex: 1; padding: 24px 32px;
      border-right: 1px solid var(--border);
    }
    .stat:last-child { border-right: none; }
    .stat-num {
      font-family: var(--font-display);
      font-size: 36px; font-weight: 800;
      color: var(--text); line-height: 1;
      margin-bottom: 4px;
    }
    .stat-label { font-size: 13px; color: var(--muted); }

    /* ── SECTIONS ── */
    section { padding: 100px 48px; }
    .section-label {
      font-size: 12px; font-weight: 600; letter-spacing: 0.12em;
      text-transform: uppercase; color: var(--muted);
      margin-bottom: 16px;
    }
    .section-title {
      font-family: var(--font-display);
      font-size: clamp(32px, 4vw, 54px);
      font-weight: 800; line-height: 1.1;
      letter-spacing: -0.02em;
      margin-bottom: 48px;
    }

    /* ── PORTFOLIO ── */
    #portfolio { background: var(--surface); }
    .portfolio-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
    }
    .project-card {
      background: var(--surface2);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      overflow: hidden;
      cursor: pointer;
      transition: transform .25s, border-color .25s;
      text-decoration: none; color: inherit;
      display: block;
    }
    .project-card:hover { transform: translateY(-6px); border-color: rgba(255,255,255,0.2); }
    .project-card-img {
      width: 100%; aspect-ratio: 16/10;
      background: linear-gradient(135deg, #1a1a1a 0%, #222 100%);
      display: flex; align-items: center; justify-content: center;
      font-size: 48px; position: relative; overflow: hidden;
    }
    .project-card-img::after {
      content: ''; position: absolute; inset: 0;
      background: linear-gradient(to bottom, transparent 60%, rgba(0,0,0,0.6));
    }
    .project-card-body { padding: 24px; }
    .project-tag {
      font-size: 11px; font-weight: 600; letter-spacing: 0.1em;
      text-transform: uppercase; color: var(--accent);
      margin-bottom: 8px;
    }
    .project-title {
      font-family: var(--font-display);
      font-size: 20px; font-weight: 700;
      margin-bottom: 6px;
    }
    .project-year { font-size: 13px; color: var(--muted); }

    /* marquee */
    .marquee-wrap {
      overflow: hidden; border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      padding: 20px 0; margin: 60px 0 0;
    }
    .marquee-track {
      display: flex; gap: 64px;
      animation: marquee 20s linear infinite;
      width: max-content;
    }
    .marquee-track span {
      font-family: var(--font-display);
      font-size: 15px; font-weight: 600; color: var(--muted);
      white-space: nowrap; letter-spacing: 0.05em; text-transform: uppercase;
    }
    .marquee-track span.dot { color: var(--accent); }
    @keyframes marquee { from{transform:translateX(0)} to{transform:translateX(-50%)} }

    /* ── ABOUT ── */
    #about {
      display: grid; grid-template-columns: 1fr 1fr;
      gap: 80px; align-items: center;
    }
    .about-img-wrap {
      position: relative;
    }
    .about-img-wrap img {
      width: 100%; border-radius: var(--radius);
      object-fit: cover; aspect-ratio: 3/4;
      filter: grayscale(20%);
    }
    .about-badge {
      position: absolute; bottom: 24px; left: 24px;
      background: rgba(10,10,10,0.9);
      border: 1px solid var(--border);
      border-radius: 12px; padding: 16px 20px;
      backdrop-filter: blur(10px);
    }
    .about-badge strong {
      font-family: var(--font-display); font-size: 26px;
      display: block; line-height: 1;
    }
    .about-badge small { font-size: 12px; color: var(--muted); }
    .about-text p { color: var(--muted); margin-bottom: 24px; line-height: 1.8; }
    .skills-list { display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 32px; }
    .skill-chip {
      border: 1px solid var(--border); border-radius: 100px;
      padding: 8px 18px; font-size: 13px; color: var(--text);
      transition: border-color .2s, color .2s;
    }
    .skill-chip:hover { border-color: var(--accent); color: var(--accent); }

    /* ── WHY ME ── */
    #why { background: var(--surface); }
    .why-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 24px; }
    .why-card {
      background: var(--surface2);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 36px 32px;
      transition: border-color .25s, transform .25s;
    }
    .why-card:hover { border-color: rgba(200,255,0,0.3); transform: translateY(-4px); }
    .why-icon { font-size: 32px; margin-bottom: 20px; }
    .why-card h3 {
      font-family: var(--font-display); font-size: 20px; font-weight: 700;
      margin-bottom: 12px;
    }
    .why-card p { color: var(--muted); font-size: 14px; line-height: 1.7; }

    /* ── TESTIMONIALS ── */
    .testimonial-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 48px;
      max-width: 700px; margin: 0 auto;
      text-align: center;
    }
    .testimonial-card blockquote {
      font-size: 18px; line-height: 1.8;
      color: var(--text); font-style: italic;
      margin-bottom: 32px;
    }
    .testimonial-author {
      display: flex; align-items: center; justify-content: center; gap: 14px;
    }
    .testimonial-author img {
      width: 48px; height: 48px; border-radius: 50%; object-fit: cover;
      border: 2px solid var(--border);
    }
    .testimonial-author strong {
      font-family: var(--font-display); font-size: 15px;
      display: block;
    }
    .testimonial-author small { color: var(--muted); font-size: 12px; }

    /* ── FAQ ── */
    #faq { background: var(--surface); }
    .faq-list { max-width: 720px; }
    .faq-item {
      border-bottom: 1px solid var(--border);
      overflow: hidden;
    }
    .faq-question {
      width: 100%; background: none; border: none;
      color: var(--text); font-family: var(--font-display);
      font-size: 17px; font-weight: 600;
      padding: 24px 0; cursor: pointer;
      display: flex; justify-content: space-between; align-items: center;
      text-align: left; transition: color .2s;
    }
    .faq-question:hover { color: var(--accent); }
    .faq-question .chevron {
      font-size: 20px; transition: transform .3s; flex-shrink: 0;
      margin-left: 16px;
    }
    .faq-question.open .chevron { transform: rotate(45deg); }
    .faq-answer {
      max-height: 0; overflow: hidden;
      transition: max-height .35s ease, padding .35s ease;
      color: var(--muted); font-size: 15px; line-height: 1.7;
    }
    .faq-answer.open { max-height: 300px; padding-bottom: 24px; }

    /* ── CONTACT ── */
    #contact {
      display: grid; grid-template-columns: 1fr 1fr;
      gap: 80px; align-items: start;
    }
    .contact-info h2 {
      font-family: var(--font-display);
      font-size: clamp(32px,4vw,54px); font-weight: 800;
      line-height: 1.1; letter-spacing: -0.02em;
      margin-bottom: 20px;
    }
    .contact-info p { color: var(--muted); margin-bottom: 40px; line-height: 1.7; }
    .contact-detail {
      display: flex; align-items: center; gap: 14px;
      margin-bottom: 16px; color: var(--text); font-size: 15px;
    }
    .contact-detail .icon {
      width: 40px; height: 40px;
      border: 1px solid var(--border); border-radius: 10px;
      display: flex; align-items: center; justify-content: center;
      font-size: 17px; flex-shrink: 0;
    }
    .contact-detail a { color: var(--text); text-decoration: none; }
    .contact-detail a:hover { color: var(--accent); }

    /* form */
    .contact-form { display: flex; flex-direction: column; gap: 16px; }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
    .form-group { display: flex; flex-direction: column; gap: 8px; }
    .form-group label { font-size: 13px; color: var(--muted); font-weight: 500; }
    .form-group input,
    .form-group textarea,
    .form-group select {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 14px 18px;
      color: var(--text); font-family: var(--font-body); font-size: 15px;
      outline: none; transition: border-color .2s;
      resize: none;
      -webkit-appearance: none;
    }
    .form-group input:focus,
    .form-group textarea:focus,
    .form-group select:focus { border-color: rgba(255,255,255,0.3); }
    .form-group textarea { min-height: 140px; }
    .btn-submit {
      background: var(--text); color: #000;
      border: none; padding: 16px 32px;
      border-radius: 100px; cursor: pointer;
      font-family: var(--font-display); font-weight: 700; font-size: 15px;
      transition: background .2s, transform .15s;
      display: flex; align-items: center; justify-content: center; gap: 8px;
    }
    .btn-submit:hover { background: var(--accent); transform: translateY(-2px); }
    .form-success {
      display: none; background: rgba(200,255,0,0.08);
      border: 1px solid rgba(200,255,0,0.3);
      border-radius: 12px; padding: 20px 24px;
      color: var(--accent); font-size: 15px; text-align: center;
    }

    /* social links */
    .socials { display: flex; gap: 12px; margin-top: 32px; }
    .social-link {
      width: 42px; height: 42px;
      border: 1px solid var(--border); border-radius: 10px;
      display: flex; align-items: center; justify-content: center;
      color: var(--muted); text-decoration: none; font-size: 16px;
      transition: border-color .2s, color .2s;
    }
    .social-link:hover { border-color: var(--accent); color: var(--accent); }

    /* ── FOOTER ── */
    footer {
      padding: 48px;
      border-top: 1px solid var(--border);
      display: flex; align-items: center; justify-content: space-between;
      color: var(--muted); font-size: 13px;
    }
    footer a { color: var(--muted); text-decoration: none; }
    footer a:hover { color: var(--text); }
    .footer-logo {
      font-family: var(--font-display); font-weight: 800;
      font-size: 18px; color: var(--text);
    }

    /* ── SCROLLBAR ── */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: #333; border-radius: 3px; }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      nav { padding: 16px 24px; }
      .nav-links { gap: 20px; }
      .hero { padding: 120px 24px 60px; }
      .stats-bar { flex-direction: column; }
      .stat { border-right: none; border-bottom: 1px solid var(--border); }
      .stat:last-child { border-bottom: none; }
      section { padding: 72px 24px; }
      .portfolio-grid { grid-template-columns: 1fr; }
      #about, #contact { grid-template-columns: 1fr; gap: 40px; }
      .why-grid { grid-template-columns: 1fr; }
      .form-row { grid-template-columns: 1fr; }
      footer { flex-direction: column; gap: 16px; text-align: center; }
    }
    @media (max-width: 600px) {
      .nav-links { display: none; }
      .hero h1 { font-size: 36px; }
    }

    /* fade-in animation */
    .fade-in {
      opacity: 0; transform: translateY(24px);
      transition: opacity .6s ease, transform .6s ease;
    }
    .fade-in.visible { opacity: 1; transform: translateY(0); }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">
    <img src="https://framerusercontent.com/images/D0N10p1QD5DJ5nssvgfyqvSE.jpg" alt="Kunal Singh">
    Kunal Singh
  </a>
  <div class="nav-links">
    <a href="#portfolio">Portfolio</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
    <a href="#contact" class="nav-cta">Get in Touch</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-badge">
    <span></span> Available for freelance work
  </div>
  <h1>Product designer crafting <em>clean &amp; modern</em> designs</h1>
  <p>Creating products that look amazing and convert well. Say no more to designs that only benefit one side.</p>
  <div class="hero-actions">
    <a href="#portfolio" class="btn-primary">View Work</a>
    <a href="#contact" class="btn-outline">Let's Talk</a>
  </div>
  <div class="stats-bar fade-in">
    <div class="stat">
      <div class="stat-num">8+</div>
      <div class="stat-label">Years of Experience</div>
    </div>
    <div class="stat">
      <div class="stat-num">20+</div>
      <div class="stat-label">Happy Clients</div>
    </div>
    <div class="stat">
      <div class="stat-num">40+</div>
      <div class="stat-label">Projects Completed</div>
    </div>
    <div class="stat">
      <div class="stat-num">10k+</div>
      <div class="stat-label">Hours of Designing</div>
    </div>
  </div>
  <div class="hero-orb"></div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track">
    <span>Logo Design</span><span class="dot">✦</span>
    <span>Brand Identity</span><span class="dot">✦</span>
    <span>Packaging Design</span><span class="dot">✦</span>
    <span>Social Media</span><span class="dot">✦</span>
    <span>Product Design</span><span class="dot">✦</span>
    <span>Visual Communication</span><span class="dot">✦</span>
    <span>Logo Design</span><span class="dot">✦</span>
    <span>Brand Identity</span><span class="dot">✦</span>
    <span>Packaging Design</span><span class="dot">✦</span>
    <span>Social Media</span><span class="dot">✦</span>
    <span>Product Design</span><span class="dot">✦</span>
    <span>Visual Communication</span><span class="dot">✦</span>
  </div>
</div>

<!-- PORTFOLIO -->
<section id="portfolio">
  <div class="section-label">Portfolio</div>
  <div class="section-title fade-in">My Latest Projects</div>
  <div class="portfolio-grid">
    <a href="#" class="project-card fade-in">
      <div class="project-card-img" style="background: linear-gradient(135deg,#1a1800,#2a2400);">
        <span style="font-size:60px;z-index:1">🔥</span>
      </div>
      <div class="project-card-body">
        <div class="project-tag">Logo Design</div>
        <div class="project-title">Rise &amp; Grind by Prime</div>
        <div class="project-year">2025</div>
      </div>
    </a>
    <a href="#" class="project-card fade-in">
      <div class="project-card-img" style="background: linear-gradient(135deg,#0a1020,#111830);">
        <span style="font-size:60px;z-index:1">🖋️</span>
      </div>
      <div class="project-card-body">
        <div class="project-tag">Brand Identity</div>
        <div class="project-title">NAME BRANDING</div>
        <div class="project-year">2023</div>
      </div>
    </a>
    <a href="#" class="project-card fade-in">
      <div class="project-card-img" style="background: linear-gradient(135deg,#0d1a0a,#142010);">
        <span style="font-size:60px;z-index:1">📦</span>
      </div>
      <div class="project-card-body">
        <div class="project-tag">Packaging Design</div>
        <div class="project-title">Packaging Design</div>
        <div class="project-year">2024</div>
      </div>
    </a>
    <a href="#" class="project-card fade-in">
      <div class="project-card-img" style="background: linear-gradient(135deg,#1a0a1a,#201030);">
        <span style="font-size:60px;z-index:1">📱</span>
      </div>
      <div class="project-card-body">
        <div class="project-tag">Social Media</div>
        <div class="project-title">Social Media Posts</div>
        <div class="project-year">2025</div>
      </div>
    </a>
  </div>
</section>

<!-- ABOUT -->
<section id="about" style="padding: 100px 48px;">
  <div class="about-img-wrap fade-in">
    <img src="https://framerusercontent.com/images/D0N10p1QD5DJ5nssvgfyqvSE.jpg" alt="Kunal Singh">
    <div class="about-badge">
      <strong>8+</strong>
      <small>Years designing</small>
    </div>
  </div>
  <div class="about-text fade-in">
    <div class="section-label">About</div>
    <div class="section-title">I am Kunal Singh, a graphic designer.</div>
    <p>With a background in design, I now apply my expertise to <strong style="color:var(--text)">graphic design</strong>, blending creativity, aesthetics, and visual communication.</p>
    <p>My goal is to create modern, impactful designs that bring ideas and brands to life — designs that both look amazing and convert well.</p>
    <div class="skills-list">
      <div class="skill-chip">Logo Design</div>
      <div class="skill-chip">Product Design</div>
      <div class="skill-chip">Brand Identity</div>
      <div class="skill-chip">Packaging</div>
      <div class="skill-chip">Social Media</div>
      <div class="skill-chip">Typography</div>
    </div>
    <a href="#contact" class="btn-primary">Work with me →</a>
  </div>
</section>

<!-- WHY ME -->
<section id="why">
  <div class="section-label">Why Me?</div>
  <div class="section-title fade-in">I'll help your project shine</div>
  <div class="why-grid">
    <div class="why-card fade-in">
      <div class="why-icon">⚡</div>
      <h3>Efficient Workflow</h3>
      <p>Streamlined design process for rapid delivery, meeting tight deadlines without compromising quality or detail.</p>
    </div>
    <div class="why-card fade-in">
      <div class="why-icon">🤝</div>
      <h3>Collaborative Process</h3>
      <p>I work closely with you, integrating your feedback to create designs that exceed your expectations.</p>
    </div>
    <div class="why-card fade-in">
      <div class="why-icon">🎯</div>
      <h3>Attention to Detail</h3>
      <p>Meticulous attention to every element, ensuring a polished and cohesive final product that impresses.</p>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section id="testimonials" style="background:var(--bg)">
  <div class="section-label">Testimonials</div>
  <div class="section-title fade-in">See what others say about me</div>
  <div class="testimonial-card fade-in">
    <blockquote>
      "Working with Kunal was a great experience. He transformed a simple idea into a bold and powerful logo that perfectly captures the 'Rise &amp; Grind' mindset. His attention to detail and creative approach made the final design both impactful and memorable."
    </blockquote>
    <div class="testimonial-author">
      <img src="https://framerusercontent.com/images/GwGCB7lHUU9D0v6GmCckcxy7o.jpg" alt="Client">
      <div>
        <strong>Prime Brand</strong>
        <small>Rise &amp; Grind Client</small>
      </div>
    </div>
  </div>
</section>

<!-- FAQ -->
<section id="faq">
  <div class="section-label">FAQ</div>
  <div class="section-title fade-in">Frequently Asked Questions</div>
  <div class="faq-list">
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        How do you ensure designs meet user needs and business goals?
        <span class="chevron">+</span>
      </button>
      <div class="faq-answer">
        I start every project with a deep discovery phase — understanding your audience, brand personality, and conversion goals. Every design decision is intentional and tied back to those objectives.
      </div>
    </div>
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        Do you offer freelance or contract design services?
        <span class="chevron">+</span>
      </button>
      <div class="faq-answer">
        Yes! I work with clients on a freelance basis for both short-term projects and long-term contracts. Get in touch to discuss your needs and we'll find the right arrangement.
      </div>
    </div>
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        Can you walk me through a specific project in your portfolio?
        <span class="chevron">+</span>
      </button>
      <div class="faq-answer">
        Absolutely. Feel free to book a call or send me a message and I'll walk you through the process, challenges, and outcomes of any project you're interested in.
      </div>
    </div>
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        What tools and software do you use for your design work?
        <span class="chevron">+</span>
      </button>
      <div class="faq-answer">
        I primarily use Adobe Illustrator, Photoshop, Figma, and InDesign — depending on the project type. For motion and social content, I also use Adobe After Effects.
      </div>
    </div>
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        What is your typical project timeline and pricing?
        <span class="chevron">+</span>
      </button>
      <div class="faq-answer">
        Timelines vary by scope — a logo project typically takes 5–7 days, while a full brand identity can take 2–4 weeks. Reach out via the contact form for a custom quote.
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact" style="background:var(--surface)">
  <div class="contact-info fade-in">
    <div class="section-label">Contact</div>
    <h2>Let's Get in Touch</h2>
    <p>Let's connect and start with your project. I'm always open to discussing new projects, creative ideas, or opportunities.</p>
    <div class="contact-detail">
      <div class="icon">📧</div>
      <a href="mailto:gk0204865@gmail.com">gk0204865@gmail.com</a>
    </div>
    <div class="contact-detail">
      <div class="icon">📱</div>
      <!-- ⬇️ REPLACE with your actual phone number below -->
      <a href="tel:+919999999999">+91 99999 99999</a>
    </div>
    <div class="contact-detail">
      <div class="icon">📍</div>
      <span>India</span>
    </div>
    <div class="socials">
      <!-- Replace hrefs with your actual profile links -->
      <a href="https://twitter.com" target="_blank" class="social-link" title="Twitter">𝕏</a>
      <a href="https://instagram.com" target="_blank" class="social-link" title="Instagram">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg>
      </a>
      <a href="https://linkedin.com" target="_blank" class="social-link" title="LinkedIn">in</a>
      <a href="https://behance.com" target="_blank" class="social-link" title="Behance">Be</a>
    </div>
  </div>

  <div class="fade-in">
    <form class="contact-form" onsubmit="sendEmail(event)">
      <div class="form-row">
        <div class="form-group">
          <label for="fname">First Name</label>
          <input type="text" id="fname" name="fname" placeholder="Rahul" required>
        </div>
        <div class="form-group">
          <label for="lname">Last Name</label>
          <input type="text" id="lname" name="lname" placeholder="Sharma">
        </div>
      </div>
      <div class="form-group">
        <label for="email">Email Address</label>
        <input type="email" id="email" name="email" placeholder="rahul@example.com" required>
      </div>
      <div class="form-group">
        <label for="phone">Phone Number (optional)</label>
        <input type="tel" id="phone" name="phone" placeholder="+91 98765 43210">
      </div>
      <div class="form-group">
        <label for="service">Service Needed</label>
        <select id="service" name="service">
          <option value="">Select a service...</option>
          <option>Logo Design</option>
          <option>Brand Identity</option>
          <option>Packaging Design</option>
          <option>Social Media Design</option>
          <option>Product Design</option>
          <option>Other</option>
        </select>
      </div>
      <div class="form-group">
        <label for="message">Message</label>
        <textarea id="message" name="message" placeholder="Tell me about your project..." required></textarea>
      </div>
      <button type="submit" class="btn-submit">
        Send Message ✦
      </button>
      <div class="form-success" id="formSuccess">
        ✅ Message sent! Kunal will get back to you soon.
      </div>
    </form>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Kunal Singh</div>
  <div>© 2025 Kunal Singh. All rights reserved.</div>
  <div>
    <a href="mailto:gk0204865@gmail.com">gk0204865@gmail.com</a>
  </div>
</footer>

<script>
  /* ── FAQ TOGGLE ── */
  function toggleFaq(btn) {
    const answer = btn.nextElementSibling;
    const isOpen = btn.classList.contains('open');
    document.querySelectorAll('.faq-question.open').forEach(q => {
      q.classList.remove('open');
      q.nextElementSibling.classList.remove('open');
    });
    if (!isOpen) {
      btn.classList.add('open');
      answer.classList.add('open');
    }
  }

  /* ── CONTACT FORM → EMAIL ── */
  function sendEmail(e) {
    e.preventDefault();
    const fname    = document.getElementById('fname').value.trim();
    const lname    = document.getElementById('lname').value.trim();
    const email    = document.getElementById('email').value.trim();
    const phone    = document.getElementById('phone').value.trim();
    const service  = document.getElementById('service').value;
    const message  = document.getElementById('message').value.trim();

    const subject  = encodeURIComponent(`Portfolio Inquiry — ${service || 'General'} | ${fname} ${lname}`);
    const body     = encodeURIComponent(
      `Hi Kunal,\n\nYou have a new inquiry from your portfolio website.\n\n` +
      `Name: ${fname} ${lname}\n` +
      `Email: ${email}\n` +
      `Phone: ${phone || 'Not provided'}\n` +
      `Service: ${service || 'Not specified'}\n\n` +
      `Message:\n${message}\n\n` +
      `---\nSent via kunalsinghrajput.com`
    );

    /* ⬇️ CHANGE THIS EMAIL to your email address */
    const toEmail = 'gk0204865@gmail.com';

    window.location.href = `mailto:${toEmail}?subject=${subject}&body=${body}`;

    // Show success message after short delay
    setTimeout(() => {
      document.getElementById('formSuccess').style.display = 'block';
      e.target.reset();
    }, 600);
  }

  /* ── SCROLL FADE-IN ── */
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
    });
  }, { threshold: 0.1 });
  document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
</script>

</body>
</html>
