<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rohit Kumar — Builder @ IIT (BHU)</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #04070f;
    --surface: #0b1020;
    --border: #161f38;
    --accent: #00e5ff;
    --accent2: #7c3aed;
    --accent3: #f59e0b;
    --green: #10b981;
    --text: #e2e8f0;
    --muted: #4e627a;
    --card: #0a1020;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,.025) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,.025) 1px, transparent 1px);
    background-size: 44px 44px;
    pointer-events: none; z-index: 0;
  }

  .orb { position: fixed; border-radius: 50%; filter: blur(130px); pointer-events: none; z-index: 0; animation: drift 16s ease-in-out infinite alternate; }
  .orb1 { width: 560px; height: 560px; background: rgba(0,229,255,.06); top: -180px; left: -120px; }
  .orb2 { width: 420px; height: 420px; background: rgba(124,58,237,.09); bottom: -120px; right: -80px; animation-delay: -8s; }
  .orb3 { width: 280px; height: 280px; background: rgba(245,158,11,.05); top: 45%; left: 55%; animation-delay: -4s; }
  @keyframes drift { from { transform: translate(0,0) scale(1); } to { transform: translate(50px,35px) scale(1.1); } }

  .wrapper { position: relative; z-index: 1; max-width: 880px; margin: 0 auto; padding: 64px 24px 88px; }

  /* HERO */
  .hero { display: flex; flex-direction: column; align-items: flex-start; gap: 14px; margin-bottom: 52px; opacity: 0; animation: fadeUp .7s ease .05s forwards; }

  .hero-badges { display: flex; gap: 10px; flex-wrap: wrap; }
  .badge {
    display: inline-flex; align-items: center; gap: 7px;
    font-family: 'Space Mono', monospace; font-size: 10px; letter-spacing: .12em; text-transform: uppercase;
    padding: 5px 13px; border-radius: 100px; border: 1px solid;
  }
  .badge-live { color: var(--green); border-color: rgba(16,185,129,.3); background: rgba(16,185,129,.05); }
  .badge-live::before { content: ''; width: 6px; height: 6px; border-radius: 50%; background: var(--green); animation: pg 1.6s ease-in-out infinite; }
  @keyframes pg { 0%,100% { box-shadow: 0 0 0 0 rgba(16,185,129,.5); } 50% { box-shadow: 0 0 0 7px rgba(16,185,129,0); } }
  .badge-iit { color: var(--accent); border-color: rgba(0,229,255,.2); background: rgba(0,229,255,.04); }
  .badge-founder { color: var(--accent3); border-color: rgba(245,158,11,.25); background: rgba(245,158,11,.05); }

  .hero h1 { font-size: clamp(2.6rem, 7vw, 4.4rem); font-weight: 800; line-height: 1.02; letter-spacing: -.025em; }
  .hero h1 .grad {
    background: linear-gradient(135deg, var(--accent) 20%, var(--accent2) 80%);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  }
  .hero-sub { font-size: 1.05rem; color: var(--muted); max-width: 560px; line-height: 1.75; }
  .hero-sub strong { color: var(--text); }

  .hero-cta { display: flex; gap: 10px; margin-top: 6px; flex-wrap: wrap; }
  .btn {
    display: inline-flex; align-items: center; gap: 8px; padding: 10px 22px; border-radius: 8px;
    font-family: 'Space Mono', monospace; font-size: 12px; font-weight: 700; letter-spacing: .06em;
    text-decoration: none; transition: transform .22s, box-shadow .22s, border-color .22s, color .22s;
    cursor: pointer; border: none;
  }
  .btn svg { width: 14px; height: 14px; fill: currentColor; flex-shrink: 0; }
  .btn-primary { background: var(--accent); color: #000; box-shadow: 0 0 22px rgba(0,229,255,.22); }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 0 40px rgba(0,229,255,.45); }
  .btn-founder { background: var(--accent3); color: #000; box-shadow: 0 0 22px rgba(245,158,11,.2); }
  .btn-founder:hover { transform: translateY(-2px); box-shadow: 0 0 40px rgba(245,158,11,.4); }
  .btn-ghost { background: transparent; color: var(--text); border: 1px solid var(--border); }
  .btn-ghost:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

  /* SECTION LABEL */
  .section-label {
    font-family: 'Space Mono', monospace; font-size: 10px; letter-spacing: .2em; text-transform: uppercase;
    color: var(--muted); margin-bottom: 20px; display: flex; align-items: center; gap: 12px;
  }
  .section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }

  /* TERMINAL */
  .terminal { background: #050d1a; border: 1px solid var(--border); border-radius: 14px; overflow: hidden; margin-bottom: 52px; opacity: 0; animation: fadeUp .7s ease .15s forwards; }
  .terminal-bar { display: flex; align-items: center; gap: 8px; padding: 11px 16px; background: #090f1e; border-bottom: 1px solid var(--border); }
  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-red { background: #ff5f57; } .dot-yel { background: #ffbd2e; } .dot-grn { background: #28c840; }
  .terminal-title { font-family: 'Space Mono', monospace; font-size: 11px; color: var(--muted); margin-left: 6px; }
  .terminal-body { padding: 20px 22px; font-family: 'Space Mono', monospace; font-size: 13px; line-height: 1.9; }
  .t-prompt { color: var(--accent2); } .t-cmd { color: var(--accent); } .t-key { color: #f59e0b; }
  .t-val { color: #a5f3fc; } .t-str { color: #86efac; }
  .cursor { display: inline-block; width: 8px; height: 14px; background: var(--accent); margin-left: 2px; vertical-align: middle; animation: blink .85s step-end infinite; }
  @keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: 0; } }

  /* STATUS GRID */
  .status-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 52px; opacity: 0; animation: fadeUp .7s ease .25s forwards; }
  @media(max-width: 520px) { .status-grid { grid-template-columns: 1fr; } }
  .status-card { display: flex; align-items: flex-start; gap: 14px; padding: 18px 20px; background: var(--card); border: 1px solid var(--border); border-radius: 12px; transition: border-color .2s, transform .2s; }
  .status-card:hover { border-color: rgba(0,229,255,.22); transform: translateY(-2px); }
  .status-icon { font-size: 1.4rem; flex-shrink: 0; margin-top: 2px; }
  .status-title { font-family: 'Space Mono', monospace; font-size: 10px; letter-spacing: .1em; text-transform: uppercase; color: var(--muted); margin-bottom: 5px; }
  .status-value { font-size: .9rem; font-weight: 600; color: var(--text); }
  .status-value a { color: var(--accent); text-decoration: none; }
  .status-value a:hover { text-decoration: underline; }

  /* VENTURES */
  .ventures-section { margin-bottom: 52px; opacity: 0; animation: fadeUp .7s ease .35s forwards; }
  .ventures-grid { display: flex; flex-direction: column; gap: 14px; }
  .venture-card {
    display: grid; grid-template-columns: auto 1fr auto; align-items: center; gap: 20px;
    padding: 22px 24px; background: var(--card); border: 1px solid var(--border); border-radius: 14px;
    text-decoration: none; color: inherit; transition: border-color .25s, transform .25s, box-shadow .25s;
    position: relative; overflow: hidden;
  }
  .venture-card::after { content: ''; position: absolute; inset: 0; background: linear-gradient(135deg, transparent 55%, rgba(0,229,255,.025)); pointer-events: none; }
  .venture-card:hover { border-color: rgba(0,229,255,.3); transform: translateY(-3px); box-shadow: 0 16px 48px rgba(0,0,0,.45), 0 0 30px rgba(0,229,255,.06); }
  .venture-card.amber:hover { border-color: rgba(245,158,11,.35); box-shadow: 0 16px 48px rgba(0,0,0,.45), 0 0 30px rgba(245,158,11,.07); }
  .venture-card.violet:hover { border-color: rgba(124,58,237,.4); box-shadow: 0 16px 48px rgba(0,0,0,.45), 0 0 30px rgba(124,58,237,.08); }

  .venture-icon { width: 52px; height: 52px; border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 1.6rem; flex-shrink: 0; border: 1px solid; }
  .vi-cyan   { background: rgba(0,229,255,.07);  border-color: rgba(0,229,255,.2); }
  .vi-amber  { background: rgba(245,158,11,.07); border-color: rgba(245,158,11,.2); }
  .vi-violet { background: rgba(124,58,237,.08); border-color: rgba(124,58,237,.25); }

  .venture-body { min-width: 0; }
  .venture-name { font-size: 1.05rem; font-weight: 700; margin-bottom: 5px; }
  .venture-desc { font-size: .875rem; color: var(--muted); line-height: 1.65; }

  .venture-meta { display: flex; flex-direction: column; align-items: flex-end; gap: 6px; flex-shrink: 0; }
  .vpill {
    font-family: 'Space Mono', monospace; font-size: 9px; font-weight: 700; letter-spacing: .1em;
    text-transform: uppercase; padding: 4px 10px; border-radius: 100px; white-space: nowrap; border: 1px solid;
  }
  .vp-live     { color: var(--green);   border-color: rgba(16,185,129,.3);  background: rgba(16,185,129,.06); }
  .vp-founder  { color: var(--accent3); border-color: rgba(245,158,11,.3);  background: rgba(245,158,11,.05); }
  .vp-cofound  { color: var(--accent2); border-color: rgba(124,58,237,.3);  background: rgba(124,58,237,.06); }
  .vp-built    { color: var(--accent);  border-color: rgba(0,229,255,.25);  background: rgba(0,229,255,.05); }
  .venture-url { font-family: 'Space Mono', monospace; font-size: 10px; color: var(--muted); white-space: nowrap; }

  @media(max-width: 620px) { .venture-card { grid-template-columns: auto 1fr; } .venture-meta { display: none; } }

  /* SKILLS */
  .skills-section { margin-bottom: 52px; opacity: 0; animation: fadeUp .7s ease .45s forwards; }
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(84px, 1fr)); gap: 10px; }
  .skill-chip {
    display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 8px;
    padding: 14px 8px; background: var(--card); border: 1px solid var(--border); border-radius: 10px;
    font-family: 'Space Mono', monospace; font-size: 9px; font-weight: 700; letter-spacing: .07em;
    color: var(--muted); text-align: center; transition: all .22s; cursor: default;
  }
  .skill-chip:hover { border-color: var(--accent); color: var(--accent); background: rgba(0,229,255,.04); transform: translateY(-3px) scale(1.05); box-shadow: 0 8px 24px rgba(0,0,0,.4); }
  .skill-chip img { width: 26px; height: 26px; object-fit: contain; filter: grayscale(40%) brightness(.8); transition: filter .22s; }
  .skill-chip:hover img { filter: grayscale(0%) brightness(1.05); }

  /* CONNECT */
  .connect-section { margin-bottom: 52px; opacity: 0; animation: fadeUp .7s ease .55s forwards; }
  .connect-grid { display: flex; gap: 10px; flex-wrap: wrap; }
  .social-btn {
    display: inline-flex; align-items: center; gap: 10px; padding: 11px 20px;
    background: var(--card); border: 1px solid var(--border); border-radius: 10px;
    color: var(--text); text-decoration: none; font-family: 'Space Mono', monospace; font-size: 11px; font-weight: 700;
    transition: all .2s;
  }
  .social-btn:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-3px); box-shadow: 0 8px 24px rgba(0,229,255,.1); }
  .social-btn svg { width: 17px; height: 17px; fill: currentColor; }

  /* STATS */
  .stats-section { opacity: 0; animation: fadeUp .7s ease .65s forwards; }
  .stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  @media(max-width: 560px) { .stats-grid { grid-template-columns: 1fr; } }
  .stat-card { background: var(--card); border: 1px solid var(--border); border-radius: 12px; overflow: hidden; transition: border-color .25s, transform .25s; }
  .stat-card:hover { border-color: rgba(0,229,255,.25); transform: translateY(-3px); }
  .stat-card img { width: 100%; display: block; }

  @keyframes fadeUp { from { opacity: 0; transform: translateY(22px); } to { opacity: 1; transform: translateY(0); } }

  /* FOOTER */
  .footer {
    margin-top: 64px; padding-top: 24px; border-top: 1px solid var(--border);
    font-family: 'Space Mono', monospace; font-size: 11px; color: var(--muted);
    display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 8px;
    opacity: 0; animation: fadeUp .7s ease .85s forwards;
  }
  .footer a { color: var(--accent); text-decoration: none; }
  .footer a:hover { text-decoration: underline; }
</style>
</head>
<body>

<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="wrapper">

  <!-- HERO -->
  <header class="hero">
    <div class="hero-badges">
      <span class="badge badge-live">Building live</span>
      <span class="badge badge-iit">IIT (BHU) · 3rd Year</span>
      <span class="badge badge-founder">Founder &amp; Co-founder</span>
    </div>
    <h1>Hi, I'm <span class="grad">Rohit Kumar</span> 👋</h1>
    <p class="hero-sub">
      <strong>3rd year Chemical @ IIT (BHU) Varanasi</strong> — shipping real products and building companies. Currently founding <strong>TripFlow</strong>, shipped <strong>Whispr</strong>, and co-founding <strong>ConnectIIT</strong>. Passionate about full-stack engineering and diving deeper into AI/ML.
    </p>
    <div class="hero-cta">
      <a href="https://tripflow.live" target="_blank" class="btn btn-founder">🚀 tripflow.live</a>
      <a href="https://github.com/r120dhiman/" target="_blank" class="btn btn-primary">
        <svg viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.44 9.8 8.2 11.38.6.1.82-.26.82-.58v-2.17c-3.34.73-4.04-1.4-4.04-1.4-.55-1.38-1.33-1.75-1.33-1.75-1.09-.74.08-.73.08-.73 1.2.08 1.84 1.24 1.84 1.24 1.07 1.83 2.8 1.3 3.49 1 .1-.78.42-1.3.76-1.6-2.67-.3-5.47-1.33-5.47-5.93 0-1.31.47-2.38 1.24-3.22-.14-.3-.54-1.52.1-3.18 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 3-.4c1.02 0 2.04.13 3 .4 2.28-1.55 3.28-1.23 3.28-1.23.65 1.66.24 2.88.12 3.18.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.63-5.48 5.92.43.37.82 1.1.82 2.22v3.29c0 .32.22.7.83.58C20.57 21.8 24 17.3 24 12 24 5.37 18.63 0 12 0z"/></svg>
        GitHub
      </a>
      <a href="mailto:r120dhiman+github@gmail.com" class="btn btn-ghost">✉ Contact</a>
    </div>
  </header>

  <!-- TERMINAL -->
  <div class="terminal">
    <div class="terminal-bar">
      <span class="dot dot-red"></span><span class="dot dot-yel"></span><span class="dot dot-grn"></span>
      <span class="terminal-title">rohit.config.json</span>
    </div>
    <div class="terminal-body">
      <div><span class="t-prompt">~</span> <span class="t-cmd">cat</span> rohit.config.json</div>
      <div>{</div>
      <div>&nbsp;&nbsp;<span class="t-key">"name"</span>:        <span class="t-val">"Rohit Kumar"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"college"</span>:     <span class="t-val">"IIT (BHU) Varanasi · Chemical"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"year"</span>:        <span class="t-val">"3rd Year"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"founding"</span>:    <span class="t-str">"TripFlow  →  tripflow.live"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"built"</span>:       <span class="t-str">"Whispr    →  whispr.in (anon chat)"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"cofounding"</span>:  <span class="t-str">"ConnectIIT — exclusive IITian network"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"exploring"</span>:   <span class="t-val">"AI/ML, system design, scaling"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"stack"</span>:       [<span class="t-val">"Next.js", "React", "Node.js", "Go"</span>]</div>
      <div>} <span class="cursor"></span></div>
    </div>
  </div>

  <!-- STATUS -->
  <div class="status-grid">
    <div class="status-card">
      <div class="status-icon">🚀</div>
      <div>
        <div class="status-title">Currently Co-Founding</div>
        <div class="status-value"><a href="https://tripflow.live" target="_blank">TripFlow.live</a> — travel platform</div>
      </div>
    </div>
    <div class="status-card">
      <div class="status-icon">🤫</div>
      <div>
        <div class="status-title">Already Shipped</div>
        <div class="status-value"><a href="https://whispr.in" target="_blank">Whispr.in</a> — anonymous chat</div>
      </div>
    </div>
    <div class="status-card">
      <div class="status-icon">🔗</div>
      <div>
        <div class="status-title">Co-founding</div>
        <div class="status-value">ConnectIIT — IITian-only network</div>
      </div>
    </div>
    <div class="status-card">
      <div class="status-icon">📫</div>
      <div>
        <div class="status-title">Reach Me</div>
        <div class="status-value"><a href="mailto:r120dhiman+github@gmail.com">r120dhiman@gmail.com</a></div>
      </div>
    </div>
  </div>

  <!-- VENTURES -->
  <section class="ventures-section">
    <div class="section-label">Ventures &amp; Projects</div>
    <div class="ventures-grid">

      <a href="https://tripflow.live" target="_blank" class="venture-card">
        <div class="venture-icon vi-cyan">✈️</div>
        <div class="venture-body">
          <div class="venture-name">TripFlow</div>
          <div class="venture-desc">My own company — a travel platform to plan trips, discover routes, and connect with fellow travellers. Live, growing, and actively being built.</div>
        </div>
        <div class="venture-meta">
          <span class="vpill vp-live">● Live</span>
          <span class="vpill vp-founder">Founder</span>
          <span class="venture-url">tripflow.live</span>
        </div>
      </a>

      <a href="https://whispr.in" target="_blank" class="venture-card amber">
        <div class="venture-icon vi-amber">🤫</div>
        <div class="venture-body">
          <div class="venture-name">Whispr</div>
          <div class="venture-desc">Anonymous real-time chatting platform built from the ground up. No identity, no trace — just raw conversations. Live at whispr.in.</div>
        </div>
        <div class="venture-meta">
          <span class="vpill vp-live">● Live</span>
          <span class="vpill vp-built">Built it</span>
          <span class="venture-url">whispr.in</span>
        </div>
      </a>

      <a href="#" class="venture-card violet">
        <div class="venture-icon vi-violet">🎓</div>
        <div class="venture-body">
          <div class="venture-name">ConnectIIT</div>
          <div class="venture-desc">An exclusive network built for IITians — students and alumni from IITs across India collaborating, connecting, and growing together.</div>
        </div>
        <div class="venture-meta">
          <span class="vpill vp-cofound">Co-founder</span>
          <span class="venture-url">connectiit.tech</span>
        </div>
      </a>

    </div>
  </section>

  <!-- SKILLS -->
  <section class="skills-section">
    <div class="section-label">Tech Stack</div>
    <div class="skills-grid">
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="">React</div>
      <div class="skill-chip"><img src="https://cdn.worldvectorlogo.com/logos/nextjs-2.svg" alt="">Next.js</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="">Node.js</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original-wordmark.svg" alt="">Express</div>
      <div class="skill-chip"><img src="https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg" alt="">Tailwind</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="">JS</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="">TypeScript</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/go/go-original.svg" alt="">Go</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="">Python</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" alt="">C++</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="">MongoDB</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="">MySQL</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original.svg" alt="">Postgres</div>
      <div class="skill-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="">Docker</div>
      <div class="skill-chip"><img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="">Git</div>
      <div class="skill-chip"><img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="">Figma</div>
    </div>
  </section>

  <!-- CONNECT -->
  <section class="connect-section">
    <div class="section-label">Connect With Me</div>
    <div class="connect-grid">
      <a href="https://linkedin.com/in/rohit-kumar2005" target="_blank" class="social-btn">
        <svg viewBox="0 0 24 24"><path d="M20.447 20.452H17v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a1.98 1.98 0 0 1-1.98-1.98c0-1.093.887-1.98 1.98-1.98s1.98.887 1.98 1.98a1.98 1.98 0 0 1-1.98 1.98zm1.707 13.019H3.63V9h3.414v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="https://instagram.com/rohit.kumar.2005" target="_blank" class="social-btn">
        <svg viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/></svg>
        Instagram
      </a>
      <a href="https://www.leetcode.com/rohitdhiman94660" target="_blank" class="social-btn">
        <svg viewBox="0 0 24 24"><path d="M13.483 0a1.374 1.374 0 0 0-.961.438L7.116 6.226l-3.854 4.126a5.266 5.266 0 0 0-1.209 2.104 5.35 5.35 0 0 0-.125.513 5.527 5.527 0 0 0 .062 2.362 5.83 5.83 0 0 0 .349 1.017 5.938 5.938 0 0 0 1.271 1.818l4.277 4.193.039.038c2.248 2.165 5.852 2.133 8.063-.074l2.396-2.392c.54-.54.54-1.414.003-1.955a1.378 1.378 0 0 0-1.951-.003l-2.396 2.392a3.021 3.021 0 0 1-4.205.038l-.02-.019-4.276-4.193c-.652-.64-.972-1.469-.948-2.263a2.68 2.68 0 0 1 .066-.523 2.545 2.545 0 0 1 .619-1.164L9.13 8.114c1.058-1.134 3.204-1.27 4.43-.278l3.501 2.831c.593.48 1.461.387 1.94-.207a1.384 1.384 0 0 0-.207-1.943l-3.5-2.831c-.8-.647-1.766-1.045-2.774-1.202l2.015-2.158A1.384 1.384 0 0 0 13.483 0zm-2.866 12.815a1.38 1.38 0 0 0-1.38 1.382 1.38 1.38 0 0 0 1.38 1.382H20.79a1.38 1.38 0 0 0 1.38-1.382 1.38 1.38 0 0 0-1.38-1.382z"/></svg>
        LeetCode
      </a>
      <a href="https://github.com/r120dhiman/" target="_blank" class="social-btn">
        <svg viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.44 9.8 8.2 11.38.6.1.82-.26.82-.58v-2.17c-3.34.73-4.04-1.4-4.04-1.4-.55-1.38-1.33-1.75-1.33-1.75-1.09-.74.08-.73.08-.73 1.2.08 1.84 1.24 1.84 1.24 1.07 1.83 2.8 1.3 3.49 1 .1-.78.42-1.3.76-1.6-2.67-.3-5.47-1.33-5.47-5.93 0-1.31.47-2.38 1.24-3.22-.14-.3-.54-1.52.1-3.18 0 0 1.01-.32 3.3 1.23a11.5 11.5 0 0 1 3-.4c1.02 0 2.04.13 3 .4 2.28-1.55 3.28-1.23 3.28-1.23.65 1.66.24 2.88.12 3.18.77.84 1.23 1.91 1.23 3.22 0 4.61-2.8 5.63-5.48 5.92.43.37.82 1.1.82 2.22v3.29c0 .32.22.7.83.58C20.57 21.8 24 17.3 24 12 24 5.37 18.63 0 12 0z"/></svg>
        GitHub
      </a>
    </div>
  </section>

  <!-- STATS -->
  <section class="stats-section">
    <div class="section-label">GitHub Stats</div>
    <div class="stats-grid">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=r120dhiman&show_icons=true&theme=transparent&title_color=00e5ff&text_color=94a3b8&icon_color=7c3aed&border_color=161f38&bg_color=0a1020" alt="GitHub Stats" loading="lazy" />
      </div>
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs?username=r120dhiman&show_icons=true&theme=transparent&title_color=00e5ff&text_color=94a3b8&border_color=161f38&bg_color=0a1020&layout=compact" alt="Top Languages" loading="lazy" />
      </div>
      <div class="stat-card" style="grid-column: 1 / -1;">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=r120dhiman&theme=transparent&ring=00e5ff&fire=f59e0b&currStreakLabel=00e5ff&sideLabels=94a3b8&dates=4e627a&border=161f38&background=0a1020" alt="GitHub Streak" loading="lazy" />
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <span>Rohit Kumar · IIT (BHU) Varanasi · 3rd Year CSE</span>
    <span>
      <a href="https://tripflow.live" target="_blank">tripflow.live</a> &nbsp;·&nbsp;
      <a href="https://whispr.in" target="_blank">whispr.in</a> &nbsp;·&nbsp;
      <a href="mailto:r120dhiman+github@gmail.com">email me</a>
    </span>
  </footer>

</div>
</body>
</html>
