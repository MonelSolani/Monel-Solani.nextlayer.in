<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Monel Solani — Mechanical Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Bebas+Neue&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0a;
    --surface: #111111;
    --surface2: #1a1a1a;
    --accent: #ff5c00;
    --accent2: #ffb800;
    --text: #f0ede8;
    --muted: #888;
    --border: #222;
    --grid: rgba(255,92,0,0.04);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
    cursor: crosshair;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(var(--grid) 1px, transparent 1px),
      linear-gradient(90deg, var(--grid) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 24px 48px;
    backdrop-filter: blur(12px);
    background: rgba(10,10,10,0.7);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px;
    letter-spacing: 3px;
    color: var(--accent);
  }
  .nav-links {
    display: flex;
    gap: 36px;
    list-style: none;
  }
  .nav-links a {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--accent); }

  /* HERO */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 0 48px;
    overflow: hidden;
    z-index: 1;
  }
  .hero-bg-text {
    position: absolute;
    right: -20px;
    top: 50%;
    transform: translateY(-50%);
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(120px, 18vw, 280px);
    color: rgba(255,92,0,0.04);
    line-height: 1;
    user-select: none;
    white-space: nowrap;
    letter-spacing: -5px;
  }
  .hero-content {
    max-width: 700px;
    animation: fadeUp 1s ease both;
  }
  .hero-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .hero-label::before {
    content: '';
    width: 40px;
    height: 1px;
    background: var(--accent);
  }
  h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(72px, 10vw, 140px);
    line-height: 0.9;
    letter-spacing: -2px;
    margin-bottom: 32px;
  }
  h1 span { color: var(--accent); }
  .hero-desc {
    font-size: 17px;
    color: #aaa;
    line-height: 1.7;
    max-width: 520px;
    margin-bottom: 48px;
  }
  .hero-stats {
    display: flex;
    gap: 48px;
    margin-bottom: 48px;
  }
  .stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 48px;
    color: var(--accent);
    line-height: 1;
  }
  .stat-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-top: 4px;
  }
  .hero-cta {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }
  .btn {
    display: inline-block;
    padding: 14px 32px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    text-decoration: none;
    transition: all 0.25s;
    cursor: pointer;
    border: none;
  }
  .btn-primary {
    background: var(--accent);
    color: #000;
  }
  .btn-primary:hover {
    background: var(--accent2);
    transform: translate(-2px, -2px);
    box-shadow: 4px 4px 0 #fff;
  }
  .btn-outline {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border);
  }
  .btn-outline:hover {
    border-color: var(--accent);
    color: var(--accent);
    transform: translate(-2px, -2px);
    box-shadow: 4px 4px 0 var(--accent);
  }
  .scroll-indicator {
    position: absolute;
    bottom: 40px;
    left: 48px;
    display: flex;
    align-items: center;
    gap: 12px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    animation: bounce 2s ease infinite;
  }
  .scroll-line {
    width: 1px;
    height: 60px;
    background: linear-gradient(var(--accent), transparent);
  }

  /* SECTIONS */
  section {
    position: relative;
    z-index: 1;
    padding: 120px 48px;
  }
  .section-header {
    display: flex;
    align-items: baseline;
    gap: 24px;
    margin-bottom: 72px;
  }
  .section-num {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 2px;
  }
  h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(48px, 6vw, 80px);
    letter-spacing: -1px;
    line-height: 1;
  }
  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
    max-width: 200px;
    margin-left: auto;
  }

  /* SKILLS */
  #skills {
    background: var(--surface);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 2px;
  }
  .skill-item {
    background: var(--bg);
    padding: 24px;
    border: 1px solid var(--border);
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
  }
  .skill-item::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0;
    width: 100%; height: 2px;
    background: var(--accent);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }
  .skill-item:hover::before { transform: scaleX(1); }
  .skill-item:hover { background: var(--surface2); }
  .skill-icon {
    font-size: 20px;
    margin-bottom: 8px;
  }
  .skill-name {
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    letter-spacing: 1px;
    color: var(--text);
  }
  .skill-tag {
    margin-top: 8px;
    font-size: 10px;
    letter-spacing: 1px;
    color: var(--muted);
    text-transform: uppercase;
  }

  /* EXPERIENCE */
  .exp-list {
    display: flex;
    flex-direction: column;
    gap: 0;
  }
  .exp-item {
    display: grid;
    grid-template-columns: 200px 1fr;
    gap: 48px;
    padding: 48px 0;
    border-bottom: 1px solid var(--border);
    position: relative;
  }
  .exp-item:first-child { border-top: 1px solid var(--border); }
  .exp-date {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 1px;
    color: var(--muted);
    padding-top: 4px;
  }
  .exp-role {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px;
    letter-spacing: 1px;
    margin-bottom: 4px;
  }
  .exp-company {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 2px;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 16px;
  }
  .exp-desc {
    font-size: 14px;
    color: #999;
    line-height: 1.8;
  }
  .exp-desc li {
    margin-bottom: 8px;
    padding-left: 16px;
    position: relative;
    list-style: none;
  }
  .exp-desc li::before {
    content: '→';
    position: absolute;
    left: 0;
    color: var(--accent);
    font-size: 12px;
  }

  /* PROJECTS */
  #projects { background: var(--surface); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }

  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
    gap: 2px;
  }
  .project-card {
    background: var(--bg);
    border: 1px solid var(--border);
    padding: 36px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
    cursor: default;
  }
  .project-card::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(255,92,0,0.06), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .project-card:hover { transform: translate(-3px, -3px); box-shadow: 5px 5px 0 var(--accent); }
  .project-card:hover::after { opacity: 1; }
  .project-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 72px;
    color: rgba(255,92,0,0.1);
    line-height: 1;
    position: absolute;
    top: 16px; right: 24px;
  }
  .project-tag {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
    display: inline-block;
    border: 1px solid rgba(255,92,0,0.3);
    padding: 4px 10px;
  }
  .project-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 26px;
    letter-spacing: 1px;
    margin-bottom: 16px;
    line-height: 1.1;
  }
  .project-desc {
    font-size: 13px;
    color: #888;
    line-height: 1.7;
  }

  /* CONTACT */
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
  }
  .contact-left {
    padding: 60px;
    background: var(--surface);
    border: 1px solid var(--border);
  }
  .contact-right {
    padding: 60px;
    background: var(--accent);
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .contact-heading {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 56px;
    line-height: 1;
    color: #000;
    margin-bottom: 32px;
  }
  .contact-item {
    display: flex;
    flex-direction: column;
    margin-bottom: 32px;
  }
  .contact-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 6px;
  }
  .contact-value {
    font-size: 16px;
    color: var(--text);
  }
  .contact-value a {
    color: var(--text);
    text-decoration: none;
  }
  .contact-value a:hover { color: var(--accent); }

  /* EDUCATION STRIP */
  .edu-strip {
    display: flex;
    gap: 2px;
    margin-top: 2px;
  }
  .edu-card {
    flex: 1;
    background: var(--surface2);
    border: 1px solid var(--border);
    padding: 32px;
    transition: all 0.2s;
  }
  .edu-card:hover { border-color: var(--accent); }
  .edu-deg {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px;
    letter-spacing: 1px;
    margin-bottom: 8px;
    color: var(--accent);
  }
  .edu-school {
    font-size: 14px;
    color: var(--text);
    margin-bottom: 4px;
  }
  .edu-grade {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  /* MARQUEE */
  .marquee-strip {
    overflow: hidden;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 18px 0;
    background: var(--accent);
  }
  .marquee-inner {
    display: flex;
    gap: 60px;
    white-space: nowrap;
    animation: marquee 20s linear infinite;
  }
  .marquee-text {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 20px;
    letter-spacing: 4px;
    color: #000;
    flex-shrink: 0;
  }
  .marquee-dot { color: rgba(0,0,0,0.4); }

  /* FOOTER */
  footer {
    position: relative;
    z-index: 1;
    padding: 32px 48px;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .footer-copy {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(40px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50%       { transform: translateY(10px); }
  }
  @keyframes marquee {
    from { transform: translateX(0); }
    to   { transform: translateX(-50%); }
  }

  /* SCROLL ANIMATIONS */
  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: none;
  }

  @media (max-width: 768px) {
    nav { padding: 20px 24px; }
    .nav-links { gap: 20px; }
    section { padding: 80px 24px; }
    .hero { padding: 0 24px; }
    .exp-item { grid-template-columns: 1fr; gap: 16px; }
    .contact-grid { grid-template-columns: 1fr; }
    .edu-strip { flex-direction: column; }
    footer { flex-direction: column; gap: 16px; }
    .hero-stats { gap: 28px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">MS</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="about">
  <div class="hero-bg-text">ENGINEER</div>
  <div class="hero-content">
    <div class="hero-label">Mechanical Engineer · Mumbai, India</div>
    <h1>MONEL<br><span>SOLANI</span></h1>
    <p class="hero-desc">Robotics designer, systems thinker, and hands-on builder. Over 1000+ hours on SolidWorks, leading teams, and engineering robots that compete on the world stage.</p>
    <div class="hero-stats">
      <div>
        <div class="stat-num">30+</div>
        <div class="stat-label">Projects Built</div>
      </div>
      <div>
        <div class="stat-num">1K+</div>
        <div class="stat-label">SolidWorks Hours</div>
      </div>
      <div>
        <div class="stat-num">8.82</div>
        <div class="stat-label">CGPA</div>
      </div>
    </div>
    <div class="hero-cta">
      <a href="#projects" class="btn btn-primary">View Projects</a>
      <a href="#contact" class="btn btn-outline">Get In Touch</a>
    </div>
  </div>
  <div class="scroll-indicator">
    <div class="scroll-line"></div>
    Scroll
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-strip">
  <div class="marquee-inner">
    <span class="marquee-text">SOLIDWORKS CSWA &amp; CSWP CERTIFIED <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">ROBOTICS DESIGN <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">FRC · FTC · FGC COMPETITIONS <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">3D PRINTING &amp; PROTOTYPING <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">ANSYS SIMULATION <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">PNEUMATIC SYSTEMS <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">SOLIDWORKS CSWA &amp; CSWP CERTIFIED <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">ROBOTICS DESIGN <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">FRC · FTC · FGC COMPETITIONS <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">3D PRINTING &amp; PROTOTYPING <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">ANSYS SIMULATION <span class="marquee-dot">✦</span></span>
    <span class="marquee-text">PNEUMATIC SYSTEMS <span class="marquee-dot">✦</span></span>
  </div>
</div>

<!-- SKILLS -->
<section id="skills">
  <div class="section-header">
    <span class="section-num">01</span>
    <h2>SKILLS</h2>
    <div class="section-line"></div>
  </div>
  <div class="skills-grid reveal">
    <div class="skill-item"><div class="skill-icon">⚙️</div><div class="skill-name">SolidWorks</div><div class="skill-tag">CSWA &amp; CSWP Certified</div></div>
    <div class="skill-item"><div class="skill-icon">✏️</div><div class="skill-name">AutoCAD</div><div class="skill-tag">2D / 3D Drafting</div></div>
    <div class="skill-item"><div class="skill-icon">🔷</div><div class="skill-name">CATIA</div><div class="skill-tag">Parametric Design</div></div>
    <div class="skill-item"><div class="skill-icon">🔶</div><div class="skill-name">Fusion 360</div><div class="skill-tag">CAD / CAM</div></div>
    <div class="skill-item"><div class="skill-icon">🖨️</div><div class="skill-name">FDM 3D Printing</div><div class="skill-tag">Prototyping</div></div>
    <div class="skill-item"><div class="skill-icon">🔬</div><div class="skill-name">ANSYS</div><div class="skill-tag">FEA Simulation</div></div>
    <div class="skill-item"><div class="skill-icon">💨</div><div class="skill-name">Pneumatic Systems</div><div class="skill-tag">Design &amp; Integration</div></div>
    <div class="skill-item"><div class="skill-icon">🤖</div><div class="skill-name">Arduino</div><div class="skill-tag">Embedded Basics</div></div>
    <div class="skill-item"><div class="skill-icon">📐</div><div class="skill-name">3D Modelling</div><div class="skill-tag">Complex Structures</div></div>
    <div class="skill-item"><div class="skill-icon">📊</div><div class="skill-name">MATLAB</div><div class="skill-tag">Simulation Basics</div></div>
    <div class="skill-item"><div class="skill-icon">💻</div><div class="skill-name">C Programming</div><div class="skill-tag">Fundamentals</div></div>
    <div class="skill-item"><div class="skill-icon">📋</div><div class="skill-name">MS Office</div><div class="skill-tag">Excel · PowerPoint</div></div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-header">
    <span class="section-num">02</span>
    <h2>EXPERIENCE</h2>
    <div class="section-line"></div>
  </div>
  <div class="exp-list">
    <div class="exp-item reveal">
      <div>
        <div class="exp-date">Jun 2022 – Aug 2023</div>
      </div>
      <div>
        <div class="exp-role">Mechanical Intern / Mentor</div>
        <div class="exp-company">The Innovation Story · Dadar, Mumbai</div>
        <ul class="exp-desc">
          <li>Designed mechanical systems for FIRST Robotics Competition 2023, FIRST Tech Challenge 2023, and FIRST Global Challenge 2022.</li>
          <li>Mentored students through competitive robotics programs across FRC, FTC, and FGC seasons.</li>
          <li>Designed and manufactured full prototypes for each year's challenge themes.</li>
        </ul>
      </div>
    </div>
    <div class="exp-item reveal">
      <div>
        <div class="exp-date">Jan 2021 – Aug 2022</div>
      </div>
      <div>
        <div class="exp-role">Lead — Mechanical Team</div>
        <div class="exp-company">Team KJSCE Robocon</div>
        <ul class="exp-desc">
          <li>Led a 9-member mechanical team designing and prototyping robot mechanisms.</li>
          <li>Designed a 3-wheel Holonomic Drivetrain and varied picking mechanisms (pneumatic &amp; electric).</li>
          <li>Worked with 3D printers, laser cutters, CNCs, and conventional machine tools.</li>
        </ul>
      </div>
    </div>
    <div class="exp-item reveal">
      <div>
        <div class="exp-date">Mar – Jul 2022</div>
      </div>
      <div>
        <div class="exp-role">Internship — Railway Crack Detection</div>
        <div class="exp-company">KJSCE · Research Project</div>
        <ul class="exp-desc">
          <li>Designed and manufactured a prototype bot to traverse railway tracks and detect cracks.</li>
          <li>Integrated ultrasonic sensors and an ML-trained camera (detecting cracks &gt;2cm).</li>
          <li>Engineered a compact traversal solution for the unique track geometry.</li>
        </ul>
      </div>
    </div>
    <div class="exp-item reveal">
      <div>
        <div class="exp-date">Oct – Nov 2021</div>
      </div>
      <div>
        <div class="exp-role">Internship — Industrial EOT Crane</div>
        <div class="exp-company">Minerva Engineering Tools Co. · Mumbai</div>
        <ul class="exp-desc">
          <li>Designed an Industrial Overhead Underslung Crane to lift 1-ton die-casting molds.</li>
          <li>Covered design of Runway, End Carriage, Bridge, loading mechanics, and drive systems.</li>
        </ul>
      </div>
    </div>
    <div class="exp-item reveal">
      <div>
        <div class="exp-date">Jul – Aug 2021</div>
      </div>
      <div>
        <div class="exp-role">Internship — CNC &amp; Packaging</div>
        <div class="exp-company">ELMACH Packing Pvt. Ltd. · Mumbai</div>
        <ul class="exp-desc">
          <li>Learned operation of CNC Milling and Turning machines.</li>
          <li>Studied the assembly process of Blister and Carton packaging machines.</li>
        </ul>
      </div>
    </div>
    <div class="exp-item reveal">
      <div>
        <div class="exp-date">Jun 2021</div>
      </div>
      <div>
        <div class="exp-role">Internship — Hip Joint FEA</div>
        <div class="exp-company">KJSCE · Research</div>
        <ul class="exp-desc">
          <li>Performed FEA on femur bone vs. femur implant using ANSYS Workbench 2021.</li>
          <li>Converted results into a research paper format.</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-header">
    <span class="section-num">03</span>
    <h2>PROJECTS</h2>
    <div class="section-line"></div>
  </div>
  <div class="projects-grid">

    <div class="project-card reveal">
      <div class="project-num">01</div>
      <div class="project-tag">Robotics · FTC 2023</div>
      <div class="project-title">FTC Mobile Robot with Turret &amp; Lift</div>
      <p class="project-desc">Autonomous robot for FIRST Tech Challenge 2023 featuring a Mecanum drivetrain with odometry pods, a custom turret system using a stack of 3 bearings instead of bulky COTS parts, and a slider-and-string lifting mechanism reaching 889mm.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">02</div>
      <div class="project-tag">Robotics · FRC 2023</div>
      <div class="project-title">FRC Swerve Drive Competition Robot</div>
      <p class="project-desc">Most complex build — swerve drive with Falcon 500 motors (6300 RPM, 4.69Nm stall torque), variable planetary gearboxes, autonomous localization, and an active compliant-wheel intake for cone and cube game pieces.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">03</div>
      <div class="project-tag">Mechanism Design</div>
      <div class="project-title">Cycloidal Drive Gearbox (10:1)</div>
      <p class="project-desc">Compact 3D-printed cycloidal gearbox with 10:1 reduction. Designed without bearings or rollers (30×50×50mm form factor), using a hex-profile shaft. Built to benchmark cycloidal vs. planetary drive characteristics.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">04</div>
      <div class="project-tag">Robotics · Robocon 2022</div>
      <div class="project-title">Robocon 2022 R1 &amp; R2 Holonomic Robots</div>
      <p class="project-desc">R1: 3-wheel holonomic drive with flywheel shooting mechanism for breaking lagoris at variable pitch. R2: Holonomic drive with stacking mechanism, linear guide belt system for efficient ball and lagori disk retrieval.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">05</div>
      <div class="project-tag">Robotics · Robocon 2021</div>
      <div class="project-title">Robocon 2021 Arrow Picking &amp; Throwing Bots</div>
      <p class="project-desc">Two-robot system for picking arrows using pneumatic/electric grippers and a spring-and-pneumatic-piston throwing mechanism with adjustable angle via lead screw. Included custom gripper designs and potentiometer feedback.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">06</div>
      <div class="project-tag">Research · KJSCE</div>
      <div class="project-title">Railway Track Crack Detection Bot</div>
      <p class="project-desc">First prototype for autonomous railway inspection. Uses ultrasonic sensors and an ML-trained camera to detect cracks &gt;2cm. Custom compact traversal mechanism to grip and navigate actual rail geometry.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">07</div>
      <div class="project-tag">Assistive Tech</div>
      <div class="project-title">Mind-Controlled Assistive Wheelchair</div>
      <p class="project-desc">Designed a BLDC hub-motor wheelchair platform intended as a base for EEG-based mind-control navigation. Included ANSYS structural analysis and integration of caster and drive wheel systems.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">08</div>
      <div class="project-tag">Mechanical Design</div>
      <div class="project-title">Self-Balancing 2-Wheeler (Mechanical Gyroscope)</div>
      <p class="project-desc">Two-wheeled vehicle stabilized using spinning disc gyroscopes generating a counter-reacting couple to resist tipping. A purely mechanical approach to dynamic balancing.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">09</div>
      <div class="project-tag">Aerospace</div>
      <div class="project-title">BLDC Quadcopter Drone</div>
      <p class="project-desc">Built a quadcopter using the KK 2.1.5 flight controller and 2212 1000kv BLDC motors. Focus on understanding quadcopter flight dynamics and mechanical frame design from scratch.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">10</div>
      <div class="project-tag">Research · KJSCE</div>
      <div class="project-title">Hip Joint FEA on ANSYS</div>
      <p class="project-desc">Comparative finite element analysis of natural femur bone vs. titanium implant under physiological loading conditions using ANSYS Workbench 2021. Results published as a research paper.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">11</div>
      <div class="project-tag">Industrial Design</div>
      <div class="project-title">Industrial EOT Overhead Crane (1 Ton)</div>
      <p class="project-desc">Full design of an Overhead Underslung Crane for Minerva Engineering Tools. Covers runway, end carriage, bridge, drive mechanisms, and structural analysis per applicable load standards.</p>
    </div>

    <div class="project-card reveal">
      <div class="project-num">12</div>
      <div class="project-tag">Custom Hardware</div>
      <div class="project-title">Self-Locking Gripper &amp; 3D Slew Bearing</div>
      <p class="project-desc">Self-locking spring-actuated gripper with passive engagement and pull-trigger release. Also designed a custom 3D-printed slew bearing using angled cylindrical rollers for combined axial and radial load handling.</p>
    </div>

  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="section-header">
    <span class="section-num">04</span>
    <h2>EDUCATION</h2>
    <div class="section-line"></div>
  </div>
  <div class="edu-strip reveal">
    <div class="edu-card">
      <div class="edu-deg">BTech — Mechanical Engineering</div>
      <div class="edu-school">KJ Somaiya College of Engineering · 2019 – 2023</div>
      <div class="edu-grade">CGPA: 8.82 / 10.0</div>
    </div>
    <div class="edu-card">
      <div class="edu-deg">HSC — Science &amp; Commerce</div>
      <div class="edu-school">KJ Somaiya Junior College · 2019</div>
      <div class="edu-grade">76.77%</div>
    </div>
    <div class="edu-card">
      <div class="edu-deg">SSC — Secondary School</div>
      <div class="edu-school">North Mumbai Welfare Society High School · 2017</div>
      <div class="edu-grade">86.60%</div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact" style="padding-top: 0;">
  <div class="section-header" style="margin-bottom: 32px; padding-top: 0;">
    <span class="section-num">05</span>
    <h2>CONTACT</h2>
    <div class="section-line"></div>
  </div>
  <div class="contact-grid reveal">
    <div class="contact-left">
      <p style="font-size:15px; color:#888; line-height:1.8; margin-bottom:40px;">Available for full-time roles, internships, and collaborative robotics / mechanical design projects. Based in Mumbai — open to opportunities globally.</p>
      <div class="contact-item">
        <span class="contact-label">Email</span>
        <span class="contact-value"><a href="mailto:monelsolani@gmail.com">monelsolani@gmail.com</a></span>
      </div>
      <div class="contact-item">
        <span class="contact-label">Academic Email</span>
        <span class="contact-value"><a href="mailto:monel.s@somaiya.edu">monel.s@somaiya.edu</a></span>
      </div>
      <div class="contact-item">
        <span class="contact-label">Phone</span>
        <span class="contact-value"><a href="tel:+919702703038">+91 9702703038</a></span>
      </div>
      <div class="contact-item">
        <span class="contact-label">Location</span>
        <span class="contact-value">Ghatkopar, Mumbai, India</span>
      </div>
    </div>
    <div class="contact-right">
      <div class="contact-heading">LET'S BUILD SOMETHING.</div>
      <p style="font-size:15px; color:rgba(0,0,0,0.7); line-height:1.7;">Robotics competitions. Industrial design. Precision mechanisms. If it moves, I can help design it.</p>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-copy">© 2024 Monel Solani · Mechanical Engineer · Mumbai</div>
  <div class="footer-copy">SOLIDWORKS CSWA &amp; CSWP CERTIFIED</div>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 60);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(el => observer.observe(el));

  // Active nav link
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(sec => {
      if (window.scrollY >= sec.offsetTop - 200) current = sec.id;
    });
    navLinks.forEach(link => {
      link.style.color = link.getAttribute('href') === '#' + current ? 'var(--accent)' : '';
    });
  });
</script>
</body>
</html>
