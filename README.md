<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cyb3rNha | SOC Analyst & Network Instructor</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #020c0e;
    --panel: #050f12;
    --border: #0ff2;
    --neon: #00ffe7;
    --neon2: #ff003c;
    --neon3: #ffe600;
    --text: #c8f0eb;
    --dim: #4a8a82;
    --glow: 0 0 12px #00ffe7aa, 0 0 32px #00ffe740;
    --glow-red: 0 0 12px #ff003caa;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Rajdhani', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid bg */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,255,231,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,231,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
    animation: gridShift 20s linear infinite;
  }

  @keyframes gridShift {
    0% { background-position: 0 0, 0 0; }
    100% { background-position: 40px 40px, 40px 40px; }
  }

  body::after {
    content: '';
    position: fixed;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(ellipse at 30% 20%, rgba(0,255,231,0.06) 0%, transparent 50%),
                radial-gradient(ellipse at 80% 80%, rgba(255,0,60,0.04) 0%, transparent 50%);
    pointer-events: none;
    z-index: 0;
    animation: pulseGlow 8s ease-in-out infinite alternate;
  }

  @keyframes pulseGlow {
    0% { opacity: 0.5; transform: scale(1); }
    100% { opacity: 1; transform: scale(1.05); }
  }

  /* Scanlines */
  .scanlines {
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.08) 2px,
      rgba(0,0,0,0.08) 4px
    );
    pointer-events: none;
    z-index: 1;
  }

  .container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 40px 20px 80px;
    position: relative;
    z-index: 2;
  }

  /* ── TOP BAR ── */
  .topbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 12px 20px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 48px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    color: var(--dim);
  }
  .topbar .blink { animation: blink 1.2s step-end infinite; color: var(--neon); }
  @keyframes blink { 50% { opacity: 0; } }
  .status-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--neon); display: inline-block; box-shadow: var(--glow); margin-right: 6px; animation: pulseGlow 1.5s ease-in-out infinite alternate; }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 220px 1fr;
    gap: 48px;
    align-items: start;
    margin-bottom: 64px;
  }

  .avatar-wrap {
    position: relative;
    width: 200px;
    height: 200px;
  }

  .avatar-ring {
    position: absolute;
    inset: -10px;
    border-radius: 50%;
    border: 2px solid transparent;
    background: conic-gradient(from 0deg, var(--neon), var(--neon2), var(--neon3), var(--neon)) border-box;
    -webkit-mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
    -webkit-mask-composite: destination-out;
    mask-composite: exclude;
    animation: spinRing 4s linear infinite;
  }
  @keyframes spinRing { to { transform: rotate(360deg); } }

  .avatar-ring2 {
    position: absolute;
    inset: -20px;
    border-radius: 50%;
    border: 1px solid rgba(0,255,231,0.15);
    animation: spinRing 8s linear infinite reverse;
  }

  .avatar-img {
    width: 200px;
    height: 200px;
    border-radius: 50%;
    object-fit: cover;
    filter: grayscale(20%) contrast(1.1);
    border: 3px solid var(--bg);
  }

  /* fallback avatar placeholder */
  .avatar-placeholder {
    width: 200px;
    height: 200px;
    border-radius: 50%;
    background: linear-gradient(135deg, #0a2a2e, #051a1f);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Orbitron', monospace;
    font-size: 56px;
    color: var(--neon);
    text-shadow: var(--glow);
    border: 3px solid rgba(0,255,231,0.2);
    letter-spacing: 2px;
  }

  .soc-badge {
    position: absolute;
    bottom: 8px;
    right: 8px;
    background: var(--neon2);
    color: #fff;
    font-family: 'Orbitron', monospace;
    font-size: 9px;
    font-weight: 700;
    padding: 4px 8px;
    border-radius: 4px;
    letter-spacing: 2px;
    box-shadow: var(--glow-red);
  }

  .hero-info { padding-top: 10px; }

  .hero-tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--neon);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 8px;
    opacity: 0.8;
  }

  .hero-name {
    font-family: 'Orbitron', monospace;
    font-size: clamp(32px, 5vw, 56px);
    font-weight: 900;
    color: #fff;
    letter-spacing: 2px;
    line-height: 1;
    margin-bottom: 4px;
    text-shadow: 0 0 30px rgba(0,255,231,0.3);
  }
  .hero-name span { color: var(--neon); text-shadow: var(--glow); }

  .hero-handle {
    font-family: 'Share Tech Mono', monospace;
    font-size: 14px;
    color: var(--dim);
    margin-bottom: 20px;
  }
  .hero-handle span { color: var(--neon); }

  .hero-desc {
    font-size: 17px;
    font-weight: 300;
    color: var(--text);
    line-height: 1.7;
    max-width: 560px;
    margin-bottom: 24px;
    border-left: 2px solid var(--neon);
    padding-left: 16px;
  }

  .hero-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 28px;
  }

  .tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    padding: 5px 12px;
    border: 1px solid;
    border-radius: 3px;
    letter-spacing: 1px;
    text-transform: uppercase;
    transition: all 0.3s;
  }
  .tag:hover { transform: translateY(-2px); }
  .tag-neon { border-color: var(--neon); color: var(--neon); }
  .tag-neon:hover { background: rgba(0,255,231,0.1); box-shadow: var(--glow); }
  .tag-red { border-color: var(--neon2); color: var(--neon2); }
  .tag-red:hover { background: rgba(255,0,60,0.1); box-shadow: var(--glow-red); }
  .tag-yellow { border-color: var(--neon3); color: var(--neon3); }
  .tag-yellow:hover { background: rgba(255,230,0,0.1); }

  /* stats */
  .stats-row {
    display: flex;
    gap: 24px;
    flex-wrap: wrap;
  }
  .stat {
    text-align: center;
    padding: 10px 20px;
    border: 1px solid var(--border);
    background: rgba(0,255,231,0.02);
    border-radius: 4px;
    min-width: 80px;
    transition: all 0.3s;
  }
  .stat:hover { border-color: var(--neon); background: rgba(0,255,231,0.06); }
  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 22px;
    font-weight: 700;
    color: var(--neon);
    display: block;
    text-shadow: var(--glow);
  }
  .stat-lbl { font-size: 11px; color: var(--dim); letter-spacing: 1px; text-transform: uppercase; }

  /* ── SECTION CARD ── */
  .section {
    margin-bottom: 48px;
    animation: fadeUp 0.6s ease both;
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }
  .section:nth-child(5) { animation-delay: 0.4s; }
  .section:nth-child(6) { animation-delay: 0.5s; }

  .section-head {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 20px;
    padding-bottom: 10px;
    border-bottom: 1px solid var(--border);
  }

  .section-head-icon {
    width: 32px;
    height: 32px;
    background: rgba(0,255,231,0.08);
    border: 1px solid var(--neon);
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    box-shadow: 0 0 8px rgba(0,255,231,0.2);
  }

  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: 14px;
    font-weight: 700;
    color: #fff;
    letter-spacing: 3px;
    text-transform: uppercase;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, rgba(0,255,231,0.3), transparent);
  }

  /* ── SKILL GRID ── */
  .skill-group { margin-bottom: 28px; }

  .skill-group-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--dim);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .skill-group-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .skill-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .pill {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 14px;
    background: rgba(5,15,18,0.8);
    border: 1px solid rgba(0,255,231,0.12);
    border-radius: 6px;
    font-family: 'Rajdhani', sans-serif;
    font-size: 14px;
    font-weight: 600;
    color: var(--text);
    transition: all 0.3s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .pill::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,255,231,0.05), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .pill:hover {
    border-color: var(--neon);
    color: #fff;
    transform: translateY(-2px);
    box-shadow: 0 4px 20px rgba(0,255,231,0.15);
  }

  .pill:hover::before { opacity: 1; }

  .pill-icon {
    width: 22px;
    height: 22px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 15px;
  }

  .pill.red:hover { border-color: var(--neon2); box-shadow: 0 4px 20px rgba(255,0,60,0.15); }
  .pill.yellow:hover { border-color: var(--neon3); box-shadow: 0 4px 20px rgba(255,230,0,0.15); }

  /* ── TERMINAL ── */
  .terminal {
    background: #000;
    border: 1px solid rgba(0,255,231,0.25);
    border-radius: 8px;
    overflow: hidden;
    font-family: 'Share Tech Mono', monospace;
    box-shadow: 0 0 40px rgba(0,255,231,0.08);
  }

  .terminal-bar {
    background: #0a1a1e;
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    border-bottom: 1px solid rgba(0,255,231,0.15);
  }

  .terminal-dot {
    width: 12px; height: 12px;
    border-radius: 50%;
  }
  .td-r { background: #ff5f57; }
  .td-y { background: #febc2e; }
  .td-g { background: #28c840; }

  .terminal-title {
    flex: 1;
    text-align: center;
    font-size: 11px;
    color: var(--dim);
    letter-spacing: 2px;
  }

  .terminal-body {
    padding: 20px;
    font-size: 13px;
    line-height: 2;
    min-height: 200px;
  }

  .t-line { display: flex; align-items: baseline; gap: 8px; }
  .t-prompt { color: var(--neon); }
  .t-cmd { color: #fff; }
  .t-out { color: #6a9f98; padding-left: 16px; display: block; }
  .t-key { color: var(--neon3); }
  .t-val { color: var(--text); }
  .t-comment { color: var(--dim); }
  .t-cursor { display: inline-block; width: 8px; height: 14px; background: var(--neon); animation: blink 1s step-end infinite; vertical-align: middle; box-shadow: var(--glow); }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 16px;
  }

  .project-card {
    background: rgba(5,15,18,0.9);
    border: 1px solid rgba(0,255,231,0.12);
    border-radius: 8px;
    padding: 20px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
    cursor: pointer;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(to right, transparent, var(--neon), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .project-card:hover {
    border-color: rgba(0,255,231,0.35);
    transform: translateY(-4px);
    box-shadow: 0 8px 32px rgba(0,255,231,0.12);
  }

  .project-card:hover::before { opacity: 1; }

  .project-icon {
    font-size: 28px;
    margin-bottom: 12px;
  }

  .project-name {
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    font-weight: 700;
    color: var(--neon);
    letter-spacing: 1px;
    margin-bottom: 8px;
  }

  .project-desc {
    font-size: 13px;
    color: var(--dim);
    line-height: 1.6;
    margin-bottom: 14px;
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .ptag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    padding: 3px 8px;
    border: 1px solid rgba(0,255,231,0.2);
    border-radius: 3px;
    color: var(--dim);
    letter-spacing: 1px;
  }

  /* ── CONTACT ── */
  .contact-row {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }

  .contact-btn {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 12px 22px;
    border: 1px solid rgba(0,255,231,0.25);
    border-radius: 6px;
    background: rgba(0,255,231,0.03);
    color: var(--text);
    font-family: 'Rajdhani', sans-serif;
    font-size: 15px;
    font-weight: 600;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.3s;
    letter-spacing: 1px;
  }

  .contact-btn:hover {
    border-color: var(--neon);
    color: var(--neon);
    background: rgba(0,255,231,0.06);
    box-shadow: var(--glow);
    transform: translateY(-2px);
  }

  .contact-btn.primary {
    border-color: var(--neon);
    color: var(--neon);
    background: rgba(0,255,231,0.06);
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding-top: 48px;
    border-top: 1px solid var(--border);
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--dim);
    letter-spacing: 2px;
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 640px) {
    .hero { grid-template-columns: 1fr; justify-items: center; text-align: center; }
    .hero-desc { border-left: none; padding-left: 0; border-top: 2px solid var(--neon); padding-top: 12px; }
    .hero-tags { justify-content: center; }
    .stats-row { justify-content: center; }
  }

  /* typing effect */
  @keyframes typing {
    from { width: 0; }
    to { width: 100%; }
  }

  .type-effect {
    overflow: hidden;
    white-space: nowrap;
    animation: typing 2s steps(30) 0.5s both;
    display: inline-block;
  }
</style>
</head>
<body>
<div class="scanlines"></div>

<div class="container">

  <!-- Top bar -->
  <div class="topbar">
    <span><span class="status-dot"></span>SYSTEM ONLINE</span>
    <span class="blink">// SOC_ANALYST.profile</span>
    <span id="clock" style="font-size:11px;"></span>
  </div>

  <!-- HERO -->
  <div class="hero section">
    <div class="avatar-wrap">
      <div class="avatar-ring2"></div>
      <div class="avatar-ring"></div>
      <div class="avatar-placeholder">K</div>
      <div class="soc-badge">SOC</div>
    </div>

    <div class="hero-info">
      <div class="hero-tag">// Security Operations Center</div>
      <div class="hero-name">Cyb3r<span>Nha</span></div>
      <div class="hero-handle">@<span>Cyb3rNha</span> · NHA SMOKE</div>
      <p class="hero-desc">
        Cyber Security Analyst & Network Instructor — passionate about threat detection, penetration testing, and defending real-world systems.
        Building at the intersection of offensive knowledge and defensive practice.
      </p>
      <div class="hero-tags">
        <span class="tag tag-neon">SOC Analyst</span>
        <span class="tag tag-red">Penetration Tester</span>
        <span class="tag tag-yellow">Network Instructor</span>
        <span class="tag tag-neon">Full-Stack Dev</span>
      </div>
      <div class="stats-row">
        <div class="stat">
          <span class="stat-num" id="c1">0</span>
          <span class="stat-lbl">Repos</span>
        </div>
        <div class="stat">
          <span class="stat-num" id="c2">0</span>
          <span class="stat-lbl">Followers</span>
        </div>
        <div class="stat">
          <span class="stat-num" id="c3">0</span>
          <span class="stat-lbl">Stars</span>
        </div>
        <div class="stat">
          <span class="stat-num" id="c4">0</span>
          <span class="stat-lbl">Commits</span>
        </div>
      </div>
    </div>
  </div>

  <!-- TERMINAL -->
  <div class="section">
    <div class="terminal">
      <div class="terminal-bar">
        <div class="terminal-dot td-r"></div>
        <div class="terminal-dot td-y"></div>
        <div class="terminal-dot td-g"></div>
        <div class="terminal-title">bash — cyb3rnha@kali ~ —zsh</div>
      </div>
      <div class="terminal-body">
        <div class="t-line"><span class="t-prompt">cyb3rnha@kali:~$</span> <span class="t-cmd">cat whoami.json</span></div>
        <span class="t-out">{</span>
        <span class="t-out">&nbsp;&nbsp;<span class="t-key">"name"</span>: <span class="t-val">"Kanha (NHA SMOKE)"</span>,</span>
        <span class="t-out">&nbsp;&nbsp;<span class="t-key">"role"</span>: <span class="t-val">"SOC Analyst / Network Instructor"</span>,</span>
        <span class="t-out">&nbsp;&nbsp;<span class="t-key">"location"</span>: <span class="t-val">"Cambodia 🇰🇭"</span>,</span>
        <span class="t-out">&nbsp;&nbsp;<span class="t-key">"focus"</span>: <span class="t-val">"Threat hunting, pentesting, full-stack security"</span>,</span>
        <span class="t-out">&nbsp;&nbsp;<span class="t-key">"languages"</span>: <span class="t-val">["Khmer", "English"]</span></span>
        <span class="t-out">}</span>
        <div class="t-line" style="margin-top:8px"><span class="t-prompt">cyb3rnha@kali:~$</span> <span class="t-cmd">nmap -sV localhost <span class="t-comment"># self scan 😄</span></span></div>
        <span class="t-out">PORT&nbsp;&nbsp;&nbsp;&nbsp; STATE  SERVICE&nbsp;&nbsp;&nbsp; VERSION</span>
        <span class="t-out">80/tcp&nbsp;&nbsp; open&nbsp;&nbsp; http&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Laravel/PHP 8.x</span>
        <span class="t-out">443/tcp&nbsp; open&nbsp;&nbsp; https&nbsp;&nbsp;&nbsp;&nbsp; API Gateway</span>
        <span class="t-out">22/tcp&nbsp;&nbsp; open&nbsp;&nbsp; ssh&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Kali Linux</span>
        <div class="t-line" style="margin-top:8px"><span class="t-prompt">cyb3rnha@kali:~$</span> <span class="t-cursor"></span></div>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-head">
      <div class="section-head-icon">⚡</div>
      <div class="section-title">Skills & Technologies</div>
      <div class="section-line"></div>
    </div>

    <div class="skill-group">
      <div class="skill-group-label">🌐 Frontend</div>
      <div class="skill-pills">
        <div class="pill"><div class="pill-icon">🔶</div>HTML5</div>
        <div class="pill"><div class="pill-icon">🔷</div>CSS3</div>
        <div class="pill"><div class="pill-icon">💛</div>JavaScript</div>
        <div class="pill"><div class="pill-icon">🔵</div>TypeScript</div>
        <div class="pill"><div class="pill-icon">⚛️</div>React</div>
        <div class="pill"><div class="pill-icon">💚</div>Vue.js</div>
        <div class="pill"><div class="pill-icon">🅱</div>Bootstrap</div>
        <div class="pill"><div class="pill-icon">🌊</div>Tailwind</div>
        <div class="pill"><div class="pill-icon">💲</div>jQuery</div>
      </div>
    </div>

    <div class="skill-group">
      <div class="skill-group-label">⚙️ Backend</div>
      <div class="skill-pills">
        <div class="pill yellow"><div class="pill-icon">🐘</div>PHP</div>
        <div class="pill yellow"><div class="pill-icon">🔴</div>Laravel</div>
        <div class="pill yellow"><div class="pill-icon">🟩</div>Node.js</div>
        <div class="pill yellow"><div class="pill-icon">⚡</div>Express.js</div>
        <div class="pill yellow"><div class="pill-icon">🌿</div>MongoDB</div>
        <div class="pill yellow"><div class="pill-icon">🐬</div>MySQL</div>
        <div class="pill yellow"><div class="pill-icon">🔌</div>REST API</div>
      </div>
    </div>

    <div class="skill-group">
      <div class="skill-group-label">🔐 Cybersecurity / Networking</div>
      <div class="skill-pills">
        <div class="pill red"><div class="pill-icon">🐉</div>Kali Linux</div>
        <div class="pill red"><div class="pill-icon">🐧</div>Ubuntu</div>
        <div class="pill red"><div class="pill-icon">🔍</div>Nmap</div>
        <div class="pill red"><div class="pill-icon">🕷</div>Metasploit</div>
        <div class="pill red"><div class="pill-icon">🔎</div>Wireshark</div>
        <div class="pill red"><div class="pill-icon">🌐</div>Burp Suite</div>
        <div class="pill red"><div class="pill-icon">🛡</div>SOC/SIEM</div>
        <div class="pill red"><div class="pill-icon">🔗</div>VPN/Firewall</div>
      </div>
    </div>

    <div class="skill-group">
      <div class="skill-group-label">💻 Programming</div>
      <div class="skill-pills">
        <div class="pill"><div class="pill-icon">⚙️</div>C++</div>
        <div class="pill"><div class="pill-icon">☕</div>Java</div>
        <div class="pill"><div class="pill-icon">🐍</div>Python</div>
        <div class="pill"><div class="pill-icon">🔧</div>Bash/Shell</div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-head">
      <div class="section-head-icon">📁</div>
      <div class="section-title">Featured Projects</div>
      <div class="section-line"></div>
    </div>

    <div class="projects-grid">
      <div class="project-card">
        <div class="project-icon">🔤</div>
        <div class="project-name">KhmerOCR</div>
        <div class="project-desc">Fast Khmer optical character recognition engine for document scanning and text extraction.</div>
        <div class="project-tags">
          <span class="ptag">Python</span>
          <span class="ptag">OCR</span>
          <span class="ptag">ML</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon">🛡️</div>
        <div class="project-name">SOC Dashboard</div>
        <div class="project-desc">Real-time security operations dashboard for log monitoring, alerting and incident tracking.</div>
        <div class="project-tags">
          <span class="ptag">Laravel</span>
          <span class="ptag">Vue.js</span>
          <span class="ptag">SIEM</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon">🌐</div>
        <div class="project-name">NetScan API</div>
        <div class="project-desc">RESTful API wrapping common network recon tools (nmap, whois, traceroute) for security audits.</div>
        <div class="project-tags">
          <span class="ptag">PHP</span>
          <span class="ptag">API</span>
          <span class="ptag">Networking</span>
        </div>
      </div>
    </div>
  </div>

  <!-- CONTACT -->
  <div class="section">
    <div class="section-head">
      <div class="section-head-icon">📡</div>
      <div class="section-title">Connect</div>
      <div class="section-line"></div>
    </div>
    <div class="contact-row">
      <a href="https://github.com/Cyb3rNha" class="contact-btn primary" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
        GitHub
      </a>
      <a href="https://www.youtube.com/@ReanCyberKh" class="contact-btn" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M23.498 6.186a3.016 3.016 0 00-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 00.502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 002.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 002.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg>
        YouTube
      </a>
      <a href="#" class="contact-btn">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
        Facebook
      </a>
      <a href="mailto:cyb3rnha@gmail.com" class="contact-btn">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        Email
      </a>
    </div>
  </div>

  <div class="footer">
    <p style="margin-bottom:8px">© 2026 · CYBERNH A · NHA SMOKE · SOC ANALYST · CAMBODIA 🇰🇭</p>
    <p style="color: rgba(0,255,231,0.3);">// hack the planet &nbsp;|&nbsp; defend the world</p>
  </div>

</div>

<script>
  // Clock
  function updateClock() {
    const now = new Date();
    document.getElementById('clock').textContent =
      now.toLocaleTimeString('en-US', { hour12: false }) + ' UTC+7';
  }
  updateClock();
  setInterval(updateClock, 1000);

  // Counter animation
  function animateCount(id, target, duration = 1200) {
    const el = document.getElementById(id);
    let start = 0;
    const step = target / (duration / 16);
    const timer = setInterval(() => {
      start = Math.min(start + step, target);
      el.textContent = Math.round(start);
      if (start >= target) clearInterval(timer);
    }, 16);
  }

  setTimeout(() => {
    animateCount('c1', 2);
    animateCount('c2', 1);
    animateCount('c3', 8);
    animateCount('c4', 47);
  }, 400);

  // Pill hover sparkle (subtle)
  document.querySelectorAll('.pill').forEach(pill => {
    pill.addEventListener('mouseenter', () => {
      pill.style.letterSpacing = '0.5px';
    });
    pill.addEventListener('mouseleave', () => {
      pill.style.letterSpacing = '';
    });
  });
</script>
</body>
</html>
