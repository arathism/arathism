
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Arathi Shekhar Munavalli — Profile</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap');

  :root{
    --bg-a: #FAF8FF;
    --bg-b: #F1F5FB;
    --teal: #0E9C94;
    --violet: #7C5CFC;
    --amber: #E0912C;
    --ink: #1E2333;
    --muted: #6B7280;
    --glass: rgba(255,255,255,0.72);
    --glass-border: rgba(20,20,43,0.08);
    --display: 'Space Grotesk', sans-serif;
    --body: 'Inter', sans-serif;
    --mono: 'JetBrains Mono', monospace;
  }

  *{ box-sizing: border-box; margin:0; padding:0; }
  html{ scroll-behavior: smooth; }

  body{
    min-height: 100vh;
    color: var(--ink);
    font-family: var(--body);
    line-height: 1.6;
    background:
      radial-gradient(ellipse 900px 500px at 12% -5%, rgba(14,156,148,0.10), transparent 55%),
      radial-gradient(ellipse 800px 600px at 100% 10%, rgba(124,92,252,0.10), transparent 55%),
      radial-gradient(ellipse 700px 500px at 50% 110%, rgba(224,145,44,0.08), transparent 60%),
      linear-gradient(160deg, var(--bg-a), var(--bg-b));
    overflow-x: hidden;
  }

  /* ---------- BOOT OVERLAY ---------- */
  #boot{
    position: fixed; inset:0; z-index: 100;
    background: #FCFBFF;
    display:flex; align-items:center; justify-content:center;
    transition: opacity .6s ease, visibility .6s ease;
  }
  #boot.hide{ opacity:0; visibility:hidden; }
  .boot-box{
    font-family: var(--mono); font-size: 13px; color: var(--teal);
    width: min(420px, 86vw);
  }
  .boot-line{ opacity:0; white-space: nowrap; overflow:hidden; border-right: 2px solid var(--teal); width:0; margin-bottom: 10px; }
  .boot-line.run1{ animation: type 0.9s steps(24,end) forwards, showln 0.01s forwards; }
  .boot-line.run2{ animation: type 1.1s steps(28,end) forwards 1s, showln 0.01s forwards 1s; }
  .boot-line.run3{ animation: type 0.7s steps(16,end) forwards 2.3s, showln 0.01s forwards 2.3s; color: var(--amber); border-color: var(--amber); }
  @keyframes showln{ to{ opacity: 1; } }
  @keyframes type{ from{ width:0; } to{ width: 100%; border-right-color: transparent; } }

  /* ---------- REVEAL ---------- */
  .reveal{ opacity:0; transform: translateY(16px); animation: rise .7s ease forwards; }
  @keyframes rise{ to{ opacity:1; transform: translateY(0); } }

  .wrap{ max-width: 900px; margin: 0 auto; padding: 56px 24px 0; }

  /* ---------- HERO / BADGE ---------- */
  .badge{
    position: relative;
    background: var(--glass);
    border: 1px solid var(--glass-border);
    backdrop-filter: blur(18px);
    border-radius: 20px;
    padding: 40px 38px;
    overflow: hidden;
    box-shadow: 0 8px 30px rgba(30,35,51,0.05);
  }
  .badge::before{
    content:"";
    position:absolute; top:-1px; left:-1px; right:-1px; height: 3px;
    background: linear-gradient(90deg, var(--teal), var(--violet), var(--amber));
    background-size: 200% 100%;
    animation: sheen 6s linear infinite;
  }
  @keyframes sheen{ to{ background-position: -200% 0; } }

  .id-row{ display:flex; align-items:center; gap:16px; }
  .avatar-ring{
    width: 58px; height:58px; border-radius: 50%;
    display:flex; align-items:center; justify-content:center;
    background: conic-gradient(from 0deg, var(--teal), var(--violet), var(--amber), var(--teal));
    animation: spin 5s linear infinite;
    flex-shrink:0;
  }
  @keyframes spin{ to{ transform: rotate(360deg); } }
  .avatar-core{
    width: 50px; height:50px; border-radius: 50%;
    background: #fff;
    display:flex; align-items:center; justify-content:center;
    font-family: var(--display); font-weight:700; font-size: 15px; color: var(--violet);
  }
  .id-text .status-pill{
    display:inline-flex; align-items:center; gap:7px;
    font-family: var(--mono); font-size: 11px; letter-spacing: 0.05em;
    color: var(--teal);
    background: rgba(14,156,148,0.08);
    border: 1px solid rgba(14,156,148,0.28);
    padding: 4px 11px; border-radius: 999px;
  }
  .status-dot{ width:6px; height:6px; border-radius:50%; background: var(--teal); box-shadow: 0 0 6px var(--teal); animation: pulse 2s ease-in-out infinite; }
  @keyframes pulse{ 0%,100%{ opacity:1; } 50%{ opacity:0.3; } }

  .badge h1{
    font-family: var(--display);
    font-weight: 700;
    font-size: clamp(28px, 4.6vw, 40px);
    margin-top: 20px;
    letter-spacing: -0.01em;
    color: var(--ink);
  }
  .badge .role{ color: var(--muted); margin-top: 8px; font-size: 14.5px; font-family: var(--mono); }
  .badge .role span{ color: var(--violet); }

  .hero-meta{
    display:flex; flex-wrap: wrap; gap: 18px;
    margin-top: 22px; padding-top: 20px;
    border-top: 1px dashed var(--glass-border);
    font-size: 13px; color: var(--muted);
  }
  .hero-meta div{ display:flex; align-items:center; gap:6px; }

  /* ---------- SECTIONS ---------- */
  .section{ margin-top: 42px; }
  .eyebrow{
    font-family: var(--mono); font-size: 11.5px; letter-spacing: 0.12em;
    color: var(--teal); text-transform: uppercase; font-weight: 600;
    display:flex; align-items:center; gap:10px; margin-bottom: 16px;
  }
  .eyebrow::before{ content: "//"; color: var(--violet); }
  .eyebrow::after{ content:""; flex:1; height:1px; background: var(--glass-border); }

  .stat-grid{ display:grid; grid-template-columns: repeat(4, 1fr); gap: 12px; }
  .stat-card{
    background: var(--glass); border: 1px solid var(--glass-border); backdrop-filter: blur(14px);
    border-radius: 14px; padding: 16px 14px;
    box-shadow: 0 4px 16px rgba(30,35,51,0.04);
  }
  .stat-card .num{ font-family: var(--display); font-size: 23px; font-weight: 700; color: var(--ink); }
  .stat-card .num em{ color: var(--amber); font-style: normal; }
  .stat-card .label{ font-family: var(--mono); font-size: 10px; color: var(--muted); margin-top: 4px; text-transform: uppercase; }

  .chip-row{ display:flex; flex-wrap: wrap; gap: 9px; }
  .chip{
    font-family: var(--mono); font-size: 12px;
    background: var(--glass); border: 1px solid var(--glass-border);
    padding: 7px 13px; border-radius: 8px; color: var(--ink);
  }

  .project{
    position: relative;
    background: var(--glass); border: 1px solid var(--glass-border); backdrop-filter: blur(14px);
    border-radius: 14px; padding: 20px 22px; margin-bottom: 12px;
    display:block; text-decoration:none; color: inherit;
    transition: transform .25s ease, border-color .25s ease, background .25s ease, box-shadow .25s ease;
    box-shadow: 0 4px 16px rgba(30,35,51,0.04);
  }
  .project.clickable:hover{ transform: translateY(-3px); border-color: rgba(14,156,148,0.35); box-shadow: 0 10px 24px rgba(30,35,51,0.08); }
  .project-top{ display:flex; justify-content: space-between; align-items:flex-start; gap: 12px; }
  .project-title{ font-family: var(--display); font-weight: 600; font-size: 16.5px; display:flex; align-items:center; gap:9px; color: var(--ink); }
  .status-light{ width:8px; height:8px; border-radius:50%; flex-shrink:0; }
  .status-light.live{ background: var(--teal); box-shadow: 0 0 6px var(--teal); }
  .status-light.rank{ background: var(--amber); box-shadow: 0 0 6px var(--amber); }
  .status-light.wip{ background: #C3C9D4; }
  .project-desc{ color: var(--muted); font-size: 13.5px; margin-top: 7px; }
  .project-tags{ display:flex; gap:8px; margin-top: 12px; flex-wrap:wrap; }
  .tag{ font-family: var(--mono); font-size: 10.5px; color: var(--violet); background: rgba(124,92,252,0.10); padding: 3px 9px; border-radius: 6px; }
  .open-badge{ font-family: var(--mono); font-size: 11px; color: var(--teal); font-weight:600; }

  /* ---------- SLIDESHOW ---------- */
  .slideshow{
    position: relative;
    border-radius: 16px;
    overflow: hidden;
    box-shadow: 0 4px 16px rgba(30,35,51,0.05);
    border: 1px solid var(--glass-border);
  }
  .slides-viewport{ overflow: hidden; }
  .slides-track{ display:flex; transition: transform .55s cubic-bezier(.4,0,.2,1); }
  .slide{
    flex: 0 0 100%;
    background: var(--glass);
    backdrop-filter: blur(14px);
    padding: 26px 26px 22px;
    text-decoration:none; color: inherit; display:block;
  }
  .slide-eyebrow{ font-family: var(--mono); font-size: 10.5px; color: var(--muted); text-transform: uppercase; letter-spacing:0.06em; }
  .slide-title{ font-family: var(--display); font-weight: 700; font-size: 22px; margin-top: 6px; display:flex; align-items:center; gap:10px; color: var(--ink); }
  .slide-desc{ color: var(--muted); font-size: 14px; margin-top: 10px; max-width: 520px; }
  .slide-tags{ display:flex; gap:8px; margin-top: 16px; flex-wrap:wrap; }
  .slide-cta{
    display:inline-flex; align-items:center; gap:6px; margin-top: 18px;
    font-family: var(--mono); font-size: 12px; font-weight:600; color: #fff;
    background: linear-gradient(90deg, var(--teal), var(--violet));
    padding: 9px 16px; border-radius: 9px;
  }
  .slide-cta.disabled{ background: #D8DCE5; color: var(--muted); }

  .arrow{
    position:absolute; top:50%; transform: translateY(-50%);
    width: 34px; height:34px; border-radius: 50%;
    background: rgba(255,255,255,0.9); border: 1px solid var(--glass-border);
    display:flex; align-items:center; justify-content:center;
    cursor:pointer; font-size: 16px; color: var(--ink);
    box-shadow: 0 2px 8px rgba(30,35,51,0.10);
    transition: background .2s ease, transform .2s ease;
    z-index: 2;
  }
  .arrow:hover{ background: #fff; transform: translateY(-50%) scale(1.06); }
  .arrow.prev{ left: 12px; } .arrow.next{ right: 12px; }

  .dots{ display:flex; justify-content:center; gap: 7px; padding: 14px 0 18px; background: var(--glass); }
  .dot{ width: 7px; height:7px; border-radius: 50%; background: var(--glass-border); cursor:pointer; transition: background .2s ease, width .2s ease; }
  .dot.active{ background: var(--teal); width: 20px; border-radius: 4px; }

  /* ---------- CONTRIBUTION STREAK ---------- */
  .streak-card{
    background: var(--glass); border: 1px solid var(--glass-border); backdrop-filter: blur(14px);
    border-radius: 16px; padding: 24px 26px;
    box-shadow: 0 4px 16px rgba(30,35,51,0.04);
  }
  .streak-top{ display:flex; justify-content: space-between; align-items:baseline; flex-wrap:wrap; gap:10px; margin-bottom: 20px; }
  .streak-top .streak-num{ font-family: var(--display); font-weight: 700; font-size: 26px; color: var(--ink); }
  .streak-top .streak-num em{ color: var(--teal); font-style:normal; }
  .streak-top .streak-sub{ font-family: var(--mono); font-size: 11px; color: var(--muted); text-transform: uppercase; }
  .bars{ display:flex; align-items:flex-end; gap: 10px; height: 110px; }
  .bar-col{ flex:1; display:flex; flex-direction: column; align-items:center; justify-content:flex-end; height:100%; gap:8px; }
  .bar{
    width: 100%; max-width: 30px; border-radius: 6px 6px 3px 3px;
    background: linear-gradient(180deg, var(--teal), var(--violet));
    height: 0;
    animation: grow 1.1s cubic-bezier(.2,.8,.2,1) forwards;
  }
  .bar-col:nth-child(1) .bar{ animation-delay: .1s; }
  .bar-col:nth-child(2) .bar{ animation-delay: .2s; }
  .bar-col:nth-child(3) .bar{ animation-delay: .3s; }
  .bar-col:nth-child(4) .bar{ animation-delay: .4s; }
  .bar-col:nth-child(5) .bar{ animation-delay: .5s; }
  .bar-col:nth-child(6) .bar{ animation-delay: .6s; }
  .bar-col:nth-child(7) .bar{ animation-delay: .7s; }
  @keyframes grow{ to{ height: var(--h); } }
  .bar-day{ font-family: var(--mono); font-size: 10px; color: var(--muted); text-transform: uppercase; }

  .ach-list{ display:flex; flex-direction: column; gap: 10px; }
  .ach-item{
    display:flex; align-items:center; gap: 14px;
    background: var(--glass); border: 1px solid var(--glass-border); backdrop-filter: blur(14px);
    border-radius: 12px; padding: 14px 18px;
    box-shadow: 0 4px 16px rgba(30,35,51,0.04);
  }
  .ach-icon{ font-size: 16px; width: 34px; height:34px; border-radius: 9px; background: rgba(224,145,44,0.14); display:flex; align-items:center; justify-content:center; flex-shrink:0; }
  .ach-text{ font-size: 13.5px; color: var(--ink); }
  .ach-text b{ color: var(--amber); }

  .contact-grid{ display:grid; grid-template-columns: repeat(4, 1fr); gap: 12px; }
  .contact-btn{
    background: var(--glass); border: 1px solid var(--glass-border); backdrop-filter: blur(14px);
    border-radius: 12px; padding: 18px 12px; text-align:center; text-decoration:none; color: var(--ink);
    display:flex; flex-direction:column; align-items:center; gap:8px;
    transition: transform .25s ease, border-color .25s ease, box-shadow .25s ease;
    box-shadow: 0 4px 16px rgba(30,35,51,0.04);
  }
  .contact-btn:hover{ transform: translateY(-3px); border-color: rgba(14,156,148,0.35); box-shadow: 0 10px 24px rgba(30,35,51,0.08); }
  .contact-btn .icon{ font-size: 18px; width:36px; height:36px; border-radius:10px; background: rgba(124,92,252,0.10); display:flex; align-items:center; justify-content:center; }
  .contact-btn .label{ font-family: var(--mono); font-size: 10.5px; color: var(--muted); text-transform: uppercase; }

  footer{ text-align:center; margin-top: 54px; padding-bottom: 8px; font-family: var(--mono); font-size: 11px; color: var(--muted); }

  @media (max-width: 640px){
    .stat-grid{ grid-template-columns: repeat(2, 1fr); }
    .contact-grid{ grid-template-columns: repeat(2, 1fr); }
    .badge{ padding: 30px 24px; }
  }
</style>
</head>
<body>

<div id="boot">
  <div class="boot-box">
    <div class="boot-line run1">&gt; initializing profile_sma.sh</div>
    <div class="boot-line run2">&gt; verifying credentials... OK</div>
    <div class="boot-line run3">&gt; ACCESS GRANTED</div>
  </div>
</div>

<div class="wrap">

  <div class="badge reveal" style="animation-delay:.1s">
    <div class="id-row">
      <div class="avatar-ring"><div class="avatar-core">SMA</div></div>
      <div class="id-text">
        <div class="status-pill"><span class="status-dot"></span> OPEN TO INTERNSHIPS</div>
      </div>
    </div>
    <h1>Arathi Shekhar Munavalli</h1>
    <div class="role">CSE Student <span>·</span> Web Developer <span>·</span> Cybersecurity Enthusiast</div>
    <div class="hero-meta">
      <div>📍 Hubli‑Dharwad, Karnataka</div>
      <div>🏫 AGMRCET · VTU (2023–2027)</div>
      <div>🎯 CGPA 8.7</div>
    </div>
  </div>

  <div class="section reveal" style="animation-delay:.2s">
    <div class="eyebrow">Snapshot</div>
    <div class="stat-grid">
      <div class="stat-card"><div class="num"><em>23</em>/887</div><div class="label">YUVA i‑Cause Rank</div></div>
      <div class="stat-card"><div class="num">Top <em>25</em></div><div class="label">CodeBharata, IIIT Dharwad</div></div>
      <div class="stat-card"><div class="num"><em>7</em></div><div class="label">Certifications</div></div>
      <div class="stat-card"><div class="num"><em>8.7</em></div><div class="label">CGPA</div></div>
    </div>
  </div>

  <div class="section reveal" style="animation-delay:.3s">
    <div class="eyebrow">Tech Stack</div>
    <div class="chip-row">
      <div class="chip">Python</div>
      <div class="chip">SQL</div>
      <div class="chip">Java</div>
      <div class="chip">JavaScript</div>
      <div class="chip">HTML5</div>
      <div class="chip">CSS3</div>
      <div class="chip">Node.js</div>
      <div class="chip">MongoDB</div>
      <div class="chip">Next.js</div>
      <div class="chip">TypeScript</div>
      <div class="chip">OpenCV</div>
      <div class="chip">Cybersecurity</div>
    </div>
  </div>

  <div class="section reveal" style="animation-delay:.4s">
    <div class="eyebrow">Featured Projects</div>

    <div class="slideshow" id="projectSlideshow">
      <div class="slides-viewport">
        <div class="slides-track" id="slidesTrack">

          <a class="slide" href="https://agri-gig-framework.vercel.app/" target="_blank" rel="noopener">
            <div class="slide-eyebrow">01 / 06 · Live</div>
            <div class="slide-title"><span class="status-light rank"></span> AgriGig</div>
            <div class="slide-desc">Sustainable farming micro-gigs platform — Top 25 of 250+ teams at CodeBharata, IIIT Dharwad.</div>
            <div class="slide-tags"><span class="tag">Next.js</span><span class="tag">TypeScript</span></div>
            <div class="slide-cta">Open project ↗</div>
          </a>

          <a class="slide" href="https://arathism.github.io/skillsbridge/" target="_blank" rel="noopener">
            <div class="slide-eyebrow">02 / 06 · Live</div>
            <div class="slide-title"><span class="status-light rank"></span> SkillBridge</div>
            <div class="slide-desc">Hyperlocal skill marketplace — ranked 23rd of 887 teams nationally at YUVA i-Cause 2026.</div>
            <div class="slide-tags"><span class="tag">HTML</span><span class="tag">CSS</span><span class="tag">JS</span></div>
            <div class="slide-cta">Open project ↗</div>
          </a>

          <a class="slide" href="https://cybershield-arathi-0dms.onrender.com" target="_blank" rel="noopener">
            <div class="slide-eyebrow">03 / 06 · Live</div>
            <div class="slide-title"><span class="status-light live"></span> CyberShield</div>
            <div class="slide-desc">AI-powered cyber threat detection platform, deployed on Render.</div>
            <div class="slide-tags"><span class="tag">Python</span><span class="tag">Flask</span></div>
            <div class="slide-cta">Open project ↗</div>
          </a>

          <a class="slide" href="https://github.com/arathism/GestureAnalyticsPlatform" target="_blank" rel="noopener">
            <div class="slide-eyebrow">04 / 06 · Code on GitHub</div>
            <div class="slide-title"><span class="status-light wip"></span> Gesture Analytics Platform</div>
            <div class="slide-desc">Real-time hand gesture control using a live webcam feed.</div>
            <div class="slide-tags"><span class="tag">Python</span><span class="tag">OpenCV</span><span class="tag">MediaPipe</span></div>
            <div class="slide-cta">View on GitHub ↗</div>
          </a>

          <a class="slide" href="https://github.com/arathism/SmartWaste_ComplaintSystem" target="_blank" rel="noopener">
            <div class="slide-eyebrow">05 / 06 · Code on GitHub</div>
            <div class="slide-title"><span class="status-light wip"></span> Smart Waste Complaint System</div>
            <div class="slide-desc">Civic waste complaint portal built on the MERN stack.</div>
            <div class="slide-tags"><span class="tag">MongoDB</span><span class="tag">Express</span><span class="tag">React</span><span class="tag">Node</span></div>
            <div class="slide-cta">View on GitHub ↗</div>
          </a>

          <a class="slide" href="https://github.com/arathism/SecureLoginProject" target="_blank" rel="noopener">
            <div class="slide-eyebrow">06 / 06 · Code on GitHub</div>
            <div class="slide-title"><span class="status-light wip"></span> Secure Login</div>
            <div class="slide-desc">Login system with brute-force attempt detection.</div>
            <div class="slide-tags"><span class="tag">Python</span><span class="tag">Tkinter</span></div>
            <div class="slide-cta">View on GitHub ↗</div>
          </a>

        </div>
      </div>
      <button class="arrow prev" id="prevBtn" aria-label="Previous project">‹</button>
      <button class="arrow next" id="nextBtn" aria-label="Next project">›</button>
      <div class="dots" id="dots"></div>
    </div>
  </div>

  <!-- CONTRIBUTION STREAK -->
  <div class="section reveal" style="animation-delay:.5s">
    <div class="eyebrow">Contribution Streak</div>
    <div class="streak-card">
      <div class="streak-top">
        <div class="streak-num"><em>18</em>-day active streak</div>
        <div class="streak-sub">Last 7 days · commits</div>
      </div>
      <div class="bars">
        <div class="bar-col"><div class="bar" style="--h:38%;"></div><div class="bar-day">Mon</div></div>
        <div class="bar-col"><div class="bar" style="--h:62%;"></div><div class="bar-day">Tue</div></div>
        <div class="bar-col"><div class="bar" style="--h:45%;"></div><div class="bar-day">Wed</div></div>
        <div class="bar-col"><div class="bar" style="--h:80%;"></div><div class="bar-day">Thu</div></div>
        <div class="bar-col"><div class="bar" style="--h:55%;"></div><div class="bar-day">Fri</div></div>
        <div class="bar-col"><div class="bar" style="--h:95%;"></div><div class="bar-day">Sat</div></div>
        <div class="bar-col"><div class="bar" style="--h:70%;"></div><div class="bar-day">Sun</div></div>
      </div>
    </div>
  </div>

  <div class="section reveal" style="animation-delay:.6s">
    <div class="eyebrow">Achievements</div>
    <div class="ach-list">
      <div class="ach-item"><span class="ach-icon">🥈</span><span class="ach-text"><b>23rd / 887 teams</b> — YUVA i‑Cause 2026 (SkillBridge)</span></div>
      <div class="ach-item"><span class="ach-icon">🥇</span><span class="ach-text"><b>Top 25 / 250+ teams</b> — CodeBharata, IIIT Dharwad (AgriGig)</span></div>
      <div class="ach-item"><span class="ach-icon">✅</span><span class="ach-text">7 certifications — Google, NPTEL, Cisco, Great Learning</span></div>
    </div>
  </div>

  <div class="section reveal" style="animation-delay:.7s">
    <div class="eyebrow">Connect</div>
    <div class="contact-grid">
      <a class="contact-btn" href="mailto:smarathism@gmail.com">
        <span class="icon">📧</span><span class="label">Email</span>
      </a>
      <a class="contact-btn" href="https://www.linkedin.com/in/arathishekharmunavalli/" target="_blank" rel="noopener">
        <span class="icon">💼</span><span class="label">LinkedIn</span>
      </a>
      <a class="contact-btn" href="https://arathism.github.io" target="_blank" rel="noopener">
        <span class="icon">🌐</span><span class="label">Portfolio</span>
      </a>
      <a class="contact-btn" href="https://github.com/arathism" target="_blank" rel="noopener">
        <span class="icon">🐙</span><span class="label">GitHub</span>
      </a>
    </div>
  </div>

  <footer>Arathi Shekhar Munavalli · built for the profile README</footer>

</div>

<script>
  setTimeout(function(){
    document.getElementById('boot').classList.add('hide');
  }, 2900);

  // ---- Project slideshow ----
  (function(){
    const track = document.getElementById('slidesTrack');
    const slides = track.children;
    const dotsWrap = document.getElementById('dots');
    const prevBtn = document.getElementById('prevBtn');
    const nextBtn = document.getElementById('nextBtn');
    const container = document.getElementById('projectSlideshow');
    let index = 0;
    let timer;

    for (let i = 0; i < slides.length; i++){
      const dot = document.createElement('div');
      dot.className = 'dot' + (i === 0 ? ' active' : '');
      dot.addEventListener('click', () => goTo(i));
      dotsWrap.appendChild(dot);
    }

    function update(){
      track.style.transform = 'translateX(-' + (index * 100) + '%)';
      const dots = dotsWrap.children;
      for (let i = 0; i < dots.length; i++){
        dots[i].classList.toggle('active', i === index);
      }
    }

    function goTo(i){
      index = (i + slides.length) % slides.length;
      update();
      restart();
    }

    function next(){ goTo(index + 1); }
    function prev(){ goTo(index - 1); }

    function restart(){
      clearInterval(timer);
      timer = setInterval(next, 4200);
    }

    nextBtn.addEventListener('click', next);
    prevBtn.addEventListener('click', prev);
    container.addEventListener('mouseenter', () => clearInterval(timer));
    container.addEventListener('mouseleave', restart);

    update();
    restart();
  })();
</script>

</body>
</html>
