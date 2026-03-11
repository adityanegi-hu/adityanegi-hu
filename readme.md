<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aditya Negi — Developer Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #050a0f;
    --surface: #0b1520;
    --card: #0f1d2b;
    --border: #1a3044;
    --accent: #00f5c8;
    --accent2: #ff4d6d;
    --accent3: #6c63ff;
    --text: #e8f4f0;
    --muted: #6b8fa8;
    --glow: 0 0 30px rgba(0,245,200,0.2);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,245,200,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,245,200,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  /* Glowing orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.15;
    pointer-events: none;
    z-index: 0;
    animation: float 8s ease-in-out infinite;
  }
  .orb-1 { width: 500px; height: 500px; background: var(--accent3); top: -100px; right: -100px; animation-delay: 0s; }
  .orb-2 { width: 400px; height: 400px; background: var(--accent); bottom: 10%; left: -80px; animation-delay: 3s; }
  .orb-3 { width: 300px; height: 300px; background: var(--accent2); top: 40%; right: 10%; animation-delay: 5s; }

  @keyframes float {
    0%, 100% { transform: translateY(0) scale(1); }
    50% { transform: translateY(-30px) scale(1.05); }
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 20px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 60px 0 50px;
    position: relative;
  }

  .avatar-ring {
    width: 120px; height: 120px;
    margin: 0 auto 24px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent3), var(--accent2));
    padding: 3px;
    animation: spin-border 6s linear infinite;
    box-shadow: 0 0 40px rgba(0,245,200,0.4);
  }
  @keyframes spin-border {
    0% { filter: hue-rotate(0deg); }
    100% { filter: hue-rotate(360deg); }
  }
  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--card);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 44px;
  }

  .badge-row {
    display: flex;
    justify-content: center;
    gap: 8px;
    margin-bottom: 20px;
    flex-wrap: wrap;
  }
  .badge {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 20px;
    border: 1px solid;
    letter-spacing: 0.05em;
  }
  .badge-green { border-color: var(--accent); color: var(--accent); background: rgba(0,245,200,0.07); }
  .badge-pink  { border-color: var(--accent2); color: var(--accent2); background: rgba(255,77,109,0.07); }
  .badge-purple{ border-color: var(--accent3); color: var(--accent3); background: rgba(108,99,255,0.07); }

  .hero h1 {
    font-size: clamp(2.2rem, 6vw, 3.5rem);
    font-weight: 800;
    line-height: 1.1;
    letter-spacing: -0.02em;
    background: linear-gradient(135deg, #fff 30%, var(--accent));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
  }
  .hero .tagline {
    font-family: 'Space Mono', monospace;
    color: var(--accent);
    font-size: 13px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 20px;
  }
  .hero p {
    color: var(--muted);
    font-size: 1rem;
    max-width: 520px;
    margin: 0 auto 32px;
    line-height: 1.7;
  }

  /* ── SOCIAL BUTTONS ── */
  .social-row {
    display: flex;
    justify-content: center;
    gap: 12px;
    flex-wrap: wrap;
    margin-bottom: 16px;
  }
  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 20px;
    border-radius: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    font-weight: 700;
    text-decoration: none;
    border: 1px solid var(--border);
    transition: all 0.25s ease;
    letter-spacing: 0.03em;
    background: var(--card);
    color: var(--text);
  }
  .social-btn:hover {
    transform: translateY(-3px);
    border-color: var(--accent);
    color: var(--accent);
    box-shadow: 0 8px 24px rgba(0,245,200,0.15);
  }
  .social-btn svg { width: 16px; height: 16px; flex-shrink: 0; }

  .email-chip {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    border: 1px dashed var(--border);
    padding: 8px 16px;
    border-radius: 6px;
    margin-top: 8px;
  }

  /* ── SECTION HEADINGS ── */
  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ── ABOUT CARDS ── */
  .about-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 16px;
    margin-bottom: 48px;
  }
  .about-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }
  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 100%;
    background: var(--accent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .about-card:hover {
    border-color: var(--accent);
    transform: translateY(-4px);
    box-shadow: var(--glow);
  }
  .about-card:hover::before { opacity: 1; }
  .about-card .icon { font-size: 24px; margin-bottom: 10px; }
  .about-card h3 { font-size: 13px; font-weight: 700; color: var(--accent); margin-bottom: 6px; letter-spacing: 0.04em; }
  .about-card p { font-size: 13px; color: var(--muted); line-height: 1.6; }

  /* ── TECH STACK ── */
  .tech-section { margin-bottom: 48px; }
  .tech-category { margin-bottom: 24px; }
  .tech-category h3 {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 12px;
  }
  .tech-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }
  .tech-pill {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    font-size: 13px;
    font-weight: 600;
    transition: all 0.25s ease;
    cursor: default;
  }
  .tech-pill:hover {
    transform: scale(1.05) translateY(-2px);
    border-color: var(--accent);
    box-shadow: 0 4px 20px rgba(0,245,200,0.12);
    color: var(--accent);
  }
  .tech-pill .dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    margin-bottom: 48px;
  }
  @media(max-width:480px) { .stats-grid { grid-template-columns: 1fr; } }
  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px 20px;
    text-align: center;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }
  .stat-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent3), var(--accent));
    opacity: 0;
    transition: opacity 0.3s;
  }
  .stat-card:hover { transform: translateY(-4px); box-shadow: var(--glow); }
  .stat-card:hover::after { opacity: 1; }
  .stat-num {
    font-family: 'Space Mono', monospace;
    font-size: 2rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--accent), var(--accent3));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .stat-label { font-size: 12px; color: var(--muted); margin-top: 6px; }

  /* ── CURRENTLY LEARNING ── */
  .learning-bar {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    margin-bottom: 48px;
  }
  .learning-item {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 16px;
  }
  .learning-item:last-child { margin-bottom: 0; }
  .learning-item .name {
    font-size: 13px;
    font-weight: 600;
    min-width: 160px;
    color: var(--text);
  }
  .prog-track {
    flex: 1;
    height: 6px;
    background: var(--border);
    border-radius: 3px;
    overflow: hidden;
  }
  .prog-fill {
    height: 100%;
    border-radius: 3px;
    background: linear-gradient(90deg, var(--accent3), var(--accent));
    animation: grow 1.5s ease-out forwards;
    transform-origin: left;
    transform: scaleX(0);
  }
  @keyframes grow { to { transform: scaleX(1); } }
  .prog-pct {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    min-width: 36px;
    text-align: right;
  }

  /* ── COLLAB ── */
  .collab-box {
    background: linear-gradient(135deg, rgba(108,99,255,0.12), rgba(0,245,200,0.08));
    border: 1px solid var(--accent3);
    border-radius: 16px;
    padding: 32px;
    text-align: center;
    margin-bottom: 48px;
    position: relative;
    overflow: hidden;
  }
  .collab-box::before {
    content: '{ }';
    position: absolute;
    top: -10px; right: 20px;
    font-family: 'Space Mono', monospace;
    font-size: 80px;
    color: var(--accent3);
    opacity: 0.06;
  }
  .collab-box h2 { font-size: 1.4rem; font-weight: 800; margin-bottom: 10px; }
  .collab-box p { color: var(--muted); font-size: 14px; margin-bottom: 20px; }
  .cta-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 28px;
    background: var(--accent);
    color: var(--bg);
    border-radius: 8px;
    font-weight: 700;
    font-size: 14px;
    text-decoration: none;
    transition: all 0.25s;
  }
  .cta-btn:hover { transform: scale(1.05); box-shadow: 0 0 30px rgba(0,245,200,0.5); }

  /* ── FUN FACT ── */
  .fun-fact {
    border: 1px dashed var(--border);
    border-radius: 12px;
    padding: 20px 24px;
    margin-bottom: 48px;
    display: flex;
    align-items: center;
    gap: 16px;
  }
  .fun-fact .emoji { font-size: 32px; }
  .fun-fact p { color: var(--muted); font-size: 14px; line-height: 1.6; }
  .fun-fact strong { color: var(--text); }

  /* ── FOOTER ── */
  footer {
    text-align: center;
    padding: 24px 0 40px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.08em;
  }
  footer span { color: var(--accent); }

  /* ── PRONOUNS ── */
  .pronoun-tag {
    display: inline-block;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent3);
    border: 1px solid var(--accent3);
    padding: 3px 10px;
    border-radius: 4px;
    margin-top: 12px;
    background: rgba(108,99,255,0.07);
  }
</style>
</head>
<body>

<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="container">

  <!-- ── HERO ── -->
  <section class="hero">
    <div class="avatar-ring">
      <div class="avatar-inner">🧑‍💻</div>
    </div>

    <div class="badge-row">
      <span class="badge badge-green">● Open to Collaborate</span>
      <span class="badge badge-pink">Cyber Analyst</span>
      <span class="badge badge-purple">Full-Stack Dev</span>
    </div>

    <h1>Aditya Negi</h1>
    <p class="tagline">// Building the Web · Securing the Future</p>
    <p>Passionate developer crafting innovative digital experiences. Currently exploring the intersection of cybersecurity and full-stack development.</p>
    <div class="pronoun-tag">he / him</div>

    <br/><br/>

    <div class="social-row">
      <a class="social-btn" href="https://www.linkedin.com/in/aditya-negi-38b43830a/" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a class="social-btn" href="https://x.com/Adityan12935364" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
        Twitter / X
      </a>
      <a class="social-btn" href="https://github.com/adityanegi-hu" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
        GitHub
      </a>
    </div>

    <div class="email-chip">
      📧 anegi0956@gmail.com
    </div>
  </section>

  <!-- ── ABOUT ── -->
  <div class="section-label">About Me</div>
  <div class="about-grid">
    <div class="about-card">
      <div class="icon">🌱</div>
      <h3>Currently Learning</h3>
      <p>Cyber Analysis & expanding into new programming languages and security tools.</p>
    </div>
    <div class="about-card">
      <div class="icon">🤝</div>
      <h3>Looking to Collaborate</h3>
      <p>Open-source projects and cutting-edge technology initiatives that push boundaries.</p>
    </div>
    <div class="about-card">
      <div class="icon">💬</div>
      <h3>Ask Me About</h3>
      <p>Web Development, Data Science, Open Source contributions & Cyber Analysis.</p>
    </div>
    <div class="about-card">
      <div class="icon">🎯</div>
      <h3>Goal</h3>
      <p>Bridge the gap between full-stack development and cybersecurity expertise.</p>
    </div>
  </div>

  <!-- ── TECH STACK ── -->
  <div class="section-label">Tech Stack</div>
  <div class="tech-section">
    <div class="tech-category">
      <h3>Languages</h3>
      <div class="tech-pills">
        <span class="tech-pill"><span class="dot" style="background:#3776AB"></span>Python</span>
        <span class="tech-pill"><span class="dot" style="background:#F7DF1E"></span>JavaScript</span>
      </div>
    </div>
    <div class="tech-category">
      <h3>Frameworks</h3>
      <div class="tech-pills">
        <span class="tech-pill"><span class="dot" style="background:#61DAFB"></span>React</span>
        <span class="tech-pill"><span class="dot" style="background:#339933"></span>Node.js</span>
      </div>
    </div>
    <div class="tech-category">
      <h3>Tools & Databases</h3>
      <div class="tech-pills">
        <span class="tech-pill"><span class="dot" style="background:#F05032"></span>Git</span>
        <span class="tech-pill"><span class="dot" style="background:#2496ED"></span>Docker</span>
        <span class="tech-pill"><span class="dot" style="background:#4479A1"></span>MySQL</span>
        <span class="tech-pill"><span class="dot" style="background:#47A248"></span>MongoDB</span>
      </div>
    </div>
  </div>

  <!-- ── LEARNING PROGRESS ── -->
  <div class="section-label">Learning Progress</div>
  <div class="learning-bar">
    <div class="learning-item">
      <span class="name">🔐 Cyber Analysis</span>
      <div class="prog-track"><div class="prog-fill" style="width:60%"></div></div>
      <span class="prog-pct">60%</span>
    </div>
    <div class="learning-item">
      <span class="name">⚛️ React / Node.js</span>
      <div class="prog-track"><div class="prog-fill" style="width:80%;animation-delay:.2s"></div></div>
      <span class="prog-pct">80%</span>
    </div>
    <div class="learning-item">
      <span class="name">🐍 Python</span>
      <div class="prog-track"><div class="prog-fill" style="width:75%;animation-delay:.4s"></div></div>
      <span class="prog-pct">75%</span>
    </div>
    <div class="learning-item">
      <span class="name">🗄️ Databases</span>
      <div class="prog-track"><div class="prog-fill" style="width:70%;animation-delay:.6s"></div></div>
      <span class="prog-pct">70%</span>
    </div>
  </div>

  <!-- ── STATS ── -->
  <div class="section-label">GitHub Stats</div>
  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-num">⭐</div>
      <div class="stat-label">Active on GitHub</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">🌍</div>
      <div class="stat-label">Open Source Contributor</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">🔒</div>
      <div class="stat-label">Security Enthusiast</div>
    </div>
  </div>

  <!-- ── COLLABORATE ── -->
  <div class="collab-box">
    <h2>Let's Build Something Together</h2>
    <p>I'm open to open-source projects, hackathons, and exciting tech collaborations. If you have an idea — let's talk.</p>
    <a class="cta-btn" href="mailto:anegi0956@gmail.com">
      ✉️ Get in Touch
    </a>
  </div>

  <!-- ── FUN FACT ── -->
  <div class="section-label">Fun Fact</div>
  <div class="fun-fact">
    <span class="emoji">⚡</span>
    <p><strong>I'm faster than a PLANET?! 😱</strong> Well, digitally at least — the speed at which ideas go from brain to code is practically orbital velocity.</p>
  </div>

  <!-- ── FOOTER ── -->
  <footer>
    Made with <span>♥</span> by Aditya Negi · <span>anegi0956@gmail.com</span>
  </footer>

</div>

</body>
</html>
