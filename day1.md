Designed a context‑rich prompt that asked the AI to build a personality profile.

Included details about my work, goals, mindset, and communication style.

Asked the AI to analyze my strengths, weaknesses, curiosity, and learning style.

Structured the output into clear sections: working style, strengths/weaknesses, type of AI user, career paths, etc.

Added creative elements like a  AI title and a cinematic character description.

Generated a hyper‑realistic cinematic AI portrait to visually represent the profile.

Made the profile modern, cinematic, internet‑native, and LinkedIn‑shareable.
<img width="842" height="1264" alt="ai_challenge" src="https://github.com/user-attachments/assets/c3d7723a-654f-4e3a-a372-058b47654cec" />
[ai_personality_profile_personal.html](https://github.com/user-attachments/files/28476715/ai_personality_profile_personal.html)<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Syne:wght@400;700;800&family=JetBrains+Mono:wght@300;400;500&display=swap');

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #05070f;
    color: #e8eaf0;
    font-family: 'Space Grotesk', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  .wrapper {
    max-width: 760px;
    margin: 0 auto;
    padding: 0;
    position: relative;
  }

  .scanlines {
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,255,180,0.012) 2px,
      rgba(0,255,180,0.012) 4px
    );
    pointer-events: none;
    z-index: 999;
  }

  /* HERO SECTION */
  .hero {
    background: linear-gradient(165deg, #0a0f1e 0%, #060b15 40%, #030609 100%);
    padding: 40px 36px 32px;
    position: relative;
    overflow: hidden;
    border-bottom: 1px solid rgba(0,220,150,0.12);
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 320px; height: 320px;
    background: radial-gradient(circle, rgba(0,180,120,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero::after {
    content: '';
    position: absolute;
    bottom: -40px; left: 30%;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(80,120,255,0.06) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.25em;
    color: #00dc96;
    text-transform: uppercase;
    margin-bottom: 10px;
    opacity: 0.85;
  }

  .hero-title {
    font-family: 'Syne', sans-serif;
    font-size: 48px;
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -0.02em;
    background: linear-gradient(135deg, #ffffff 0%, #a8ffdf 50%, #6ec6ff 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
  }

  .hero-subtitle {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: #00dc96;
    letter-spacing: 0.1em;
    margin-bottom: 20px;
  }

  .hero-desc {
    font-size: 14px;
    line-height: 1.75;
    color: #8a9ab5;
    max-width: 420px;
    margin-bottom: 20px;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.12em;
    padding: 5px 12px;
    border-radius: 2px;
    text-transform: uppercase;
  }

  .badge-outline {
    border: 1px solid rgba(0,220,150,0.35);
    color: #00dc96;
    background: rgba(0,220,150,0.05);
  }

  .badge-glow {
    border: 1px solid rgba(110,198,255,0.35);
    color: #6ec6ff;
    background: rgba(110,198,255,0.05);
  }

  .hero-inner {
    display: flex;
    gap: 28px;
    align-items: flex-start;
    flex-wrap: wrap;
  }

  .hero-left { flex: 1; min-width: 260px; }

  .portrait-frame {
    width: 150px;
    height: 180px;
    flex-shrink: 0;
    position: relative;
  }

  .portrait-photo {
    width: 150px;
    height: 180px;
    object-fit: cover;
    object-position: center top;
    border: 1px solid rgba(0,220,150,0.3);
    border-radius: 4px;
    display: block;
    filter: contrast(1.05) brightness(0.95);
  }

  .corner-tl, .corner-br {
    position: absolute;
    width: 16px; height: 16px;
    border-color: #00dc96;
    border-style: solid;
    z-index: 2;
  }
  .corner-tl { top: -1px; left: -1px; border-width: 2px 0 0 2px; }
  .corner-br { bottom: -1px; right: -1px; border-width: 0 2px 2px 0; }

  .portrait-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to bottom, transparent 60%, rgba(0,220,150,0.06) 100%);
    border-radius: 4px;
    pointer-events: none;
  }

  /* QUOTE BLOCK */
  .quote-block {
    background: rgba(0,220,150,0.03);
    border-left: 2px solid #00dc96;
    padding: 14px 18px;
    margin: 0 36px;
    position: relative;
  }

  .quote-text {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-style: italic;
    color: #c5d5e8;
    line-height: 1.6;
    margin-bottom: 6px;
  }

  .quote-sub {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #4a6080;
  }

  /* GRID SECTIONS */
  .grid-section {
    padding: 28px 36px;
    background: #05070f;
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }

  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 14px;
  }

  .card {
    background: #080d18;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 6px;
    padding: 18px;
    position: relative;
    overflow: hidden;
  }

  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,220,150,0.25), transparent);
  }

  .card-accent { border-color: rgba(0,220,150,0.12); }
  .card-accent-blue { border-color: rgba(110,198,255,0.12); }

  .card-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #00dc96;
    letter-spacing: 0.15em;
    margin-bottom: 10px;
    opacity: 0.6;
  }

  .card-title {
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: #c5d5e8;
    margin-bottom: 12px;
  }

  .dot-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 7px;
  }

  .dot-list li {
    font-size: 12.5px;
    color: #7a8fa5;
    padding-left: 14px;
    position: relative;
    line-height: 1.4;
  }

  .dot-list li::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: #00dc96;
    font-size: 9px;
    top: 2px;
  }

  .dot-list.red li::before { color: #ff6b6b; }
  .dot-list.blue li::before { color: #6ec6ff; }

  .wide-card {
    background: #080d18;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 6px;
    padding: 20px 22px;
    position: relative;
    overflow: hidden;
  }

  .wide-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,220,150,0.2), transparent);
  }

  .wide-card-body {
    font-size: 13px;
    color: #7a8fa5;
    line-height: 1.75;
  }

  .section-divider {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 18px;
  }

  .section-divider-line {
    flex: 1;
    height: 1px;
    background: rgba(255,255,255,0.06);
  }

  .section-divider-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #3d5270;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    white-space: nowrap;
  }

  /* STATS */
  .stats-row {
    display: flex;
    gap: 20px;
    background: #080d18;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 6px;
    padding: 18px 22px;
  }

  .stat-cell { flex: 1; }

  .stat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #3d5270;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 4px;
  }

  .stat-val {
    font-family: 'Syne', sans-serif;
    font-size: 22px;
    font-weight: 800;
    color: #00dc96;
    margin-bottom: 6px;
  }

  .stat-bar-wrap {
    height: 3px;
    background: rgba(255,255,255,0.06);
    border-radius: 2px;
    overflow: hidden;
  }

  .stat-bar {
    height: 100%;
    background: linear-gradient(90deg, #00dc96, #6ec6ff);
    border-radius: 2px;
  }

  /* FUEL */
  .fuel-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .fuel-chip {
    display: flex;
    align-items: center;
    gap: 8px;
    background: #080d18;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 3px;
    padding: 7px 12px;
    font-size: 12px;
    color: #6a7e95;
    font-family: 'JetBrains Mono', monospace;
  }

  .fuel-icon {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: #00dc96;
    flex-shrink: 0;
  }

  .fuel-icon.blue { background: #6ec6ff; }
  .fuel-icon.amber { background: #ffc264; }

  /* MODE BAR */
  .mode-bar {
    background: #080d18;
    border-top: 1px solid rgba(255,255,255,0.06);
    border-bottom: 1px solid rgba(255,255,255,0.06);
    padding: 14px 36px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .mode-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #3d5270;
    letter-spacing: 0.18em;
    text-transform: uppercase;
  }

  .mode-dots { display: flex; gap: 20px; }

  .mode-dot {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #00dc96;
    position: relative;
    padding-left: 14px;
  }

  .mode-dot::before {
    content: '';
    position: absolute;
    left: 0; top: 50%;
    transform: translateY(-50%);
    width: 6px; height: 6px;
    border-radius: 50%;
    background: #00dc96;
    box-shadow: 0 0 6px #00dc96;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  /* TITLE SECTION */
  .title-section {
    background: linear-gradient(135deg, #06091a, #080d20);
    border-top: 1px solid rgba(0,220,150,0.08);
    border-bottom: 1px solid rgba(0,220,150,0.08);
    padding: 28px 36px;
    text-align: center;
  }

  .ai-crown {
    font-size: 22px;
    color: #00dc96;
    opacity: 0.5;
    margin-bottom: 10px;
    letter-spacing: 0.3em;
  }

  .ai-title-big {
    font-family: 'Syne', sans-serif;
    font-size: 38px;
    font-weight: 800;
    letter-spacing: 0.02em;
    background: linear-gradient(135deg, #ffffff, #a8ffdf, #6ec6ff);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 10px;
  }

  .ai-title-sub {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #3d5270;
    letter-spacing: 0.12em;
  }

  /* FOOTER */
  .footer-quote {
    padding: 28px 36px;
    background: #030508;
    text-align: center;
  }

  .footer-quote-text {
    font-family: 'Syne', sans-serif;
    font-style: italic;
    font-size: 13px;
    color: #2a3a52;
    line-height: 1.8;
  }
</style>
</head>
<body>
<div class="scanlines"></div>
<div class="wrapper">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-tag">AI Personality Profile</div>
    <div class="hero-inner">
      <div class="hero-left">
        <div class="hero-title">THE QUIET<br>ARCHITECT</div>
        <div class="hero-subtitle">Builder. Researcher. Problem Solver. Visionary.</div>
        <div class="hero-desc">
          You don't just use AI — you think with it, design with it, and turn deep questions into meaningful impact. Driven by curiosity, rigor, and the desire to create things that matter.
        </div>
        <div class="badges">
          <span class="badge badge-outline">AI Native</span>
          <span class="badge badge-outline">Researcher</span>
          <span class="badge badge-glow">Strategist</span>
          <span class="badge badge-glow">Builder</span>
        </div>
      </div>
      <div class="portrait-frame">
        <img class="portrait-photo" src="data:image/jpeg;base64,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" alt="Profile Photo" />
        <div class="portrait-overlay"></div>
        <div class="corner-tl"></div>
        <div class="corner-br"></div>
      </div>
    </div>
  </div>

  <!-- QUOTE -->
  <div style="padding: 20px 36px; background: #05070f;">
    <div class="quote-block">
      <div class="quote-text">"I don't follow hype. I dissect it, rebuild it, and ship something better."</div>
      <div class="quote-sub">// You ask sharper questions than most. That's rare.</div>
    </div>
  </div>

  <!-- WORKING STYLE + STRENGTHS + WEAKNESSES + TYPE -->
  <div class="grid-section">
    <div class="grid-2">

      <div class="card card-accent">
        <div class="card-num">01 —</div>
        <div class="card-title">AI Working Style</div>
        <ul class="dot-list">
          <li>Research-First, Build-Second</li>
          <li>Prompt engineering with intent</li>
          <li>Multi-tool orchestrator</li>
          <li>Pattern recognizer &amp; connector</li>
          <li>Data-validated decisions</li>
          <li>Long-form analytical thinker</li>
        </ul>
      </div>

      <div class="card card-accent">
        <div class="card-num">02 —</div>
        <div class="card-title">Strengths</div>
        <ul class="dot-list">
          <li>Deep academic curiosity</li>
          <li>Precise, structured communication</li>
          <li>Cross-domain synthesis</li>
          <li>Calm under complexity</li>
          <li>Empathy-driven problem framing</li>
          <li>Visual &amp; creative thinker</li>
        </ul>
      </div>

      <div class="card">
        <div class="card-num">03 —</div>
        <div class="card-title">Weaknesses</div>
        <ul class="dot-list red">
          <li>Over-researches before acting</li>
          <li>Underestimates own capability</li>
          <li>Waits for "perfect" conditions</li>
          <li>May undersell herself publicly</li>
          <li>Risk-averse to visible failure</li>
        </ul>
      </div>

      <div class="card card-accent-blue">
        <div class="card-num">04 —</div>
        <div class="card-title">Type of AI User</div>
        <div style="font-size: 16px; font-weight: 600; color: #6ec6ff; font-family: 'Syne', sans-serif; margin-bottom: 10px;">The AI Power User</div>
        <div class="wide-card-body" style="font-size: 12.5px;">
          You combine technical skill, creativity, and research to build, automate, and scale real-world solutions.
        </div>
      </div>

    </div>
  </div>

  <!-- CAREER PATHS -->
  <div class="grid-section">
    <div class="section-divider">
      <div class="section-divider-line"></div>
      <div class="section-divider-label">05 — Best Career Paths</div>
      <div class="section-divider-line"></div>
    </div>
    <div class="grid-3">
      <div class="card card-accent">
        <div style="font-size: 11px; color: #00dc96; font-family: 'JetBrains Mono', monospace; margin-bottom: 6px; letter-spacing: 0.08em;">CORE FIT</div>
        <ul class="dot-list" style="gap: 8px;">
          <li>AI Engineer / ML Engineer</li>
          <li>Applied AI Researcher</li>
          <li>AI Product Builder</li>
        </ul>
      </div>
      <div class="card">
        <div style="font-size: 11px; color: #6ec6ff; font-family: 'JetBrains Mono', monospace; margin-bottom: 6px; letter-spacing: 0.08em;">HIGH GROWTH</div>
        <ul class="dot-list blue">
          <li>Data Scientist / Analyst</li>
          <li>AI Ethicist / Policy</li>
          <li>EdTech AI Builder</li>
        </ul>
      </div>
      <div class="card">
        <div style="font-size: 11px; color: #ffc264; font-family: 'JetBrains Mono', monospace; margin-bottom: 6px; letter-spacing: 0.08em;">FOUNDER MODE</div>
        <ul class="dot-list" style="gap: 8px;">
          <li style="color: #7a8fa5;">Startup Founder (AI-Native)</li>
          <li style="color: #7a8fa5;">AI Consultant / Strategist</li>
          <li style="color: #7a8fa5;">Research Lab Lead</li>
        </ul>
      </div>
    </div>
  </div>

  <!-- LEARNING + WHAT MAKES YOU DIFFERENT -->
  <div class="grid-section">
    <div class="grid-2">
      <div class="card card-accent">
        <div class="card-num">06 —</div>
        <div class="card-title">Learning &amp; Decision Style</div>
        <ul class="dot-list">
          <li>Learn by Doing</li>
          <li>Research Before Building</li>
          <li>Test, Validate, Iterate</li>
          <li>Data &gt; Opinions</li>
          <li>Long-Term Vision</li>
          <li>Growth Mindset</li>
        </ul>
      </div>

      <div class="card card-accent-blue">
        <div class="card-num">07 —</div>
        <div class="card-title">What Makes You Different</div>
        <div class="wide-card-body" style="font-size: 13px;">
          You treat AI like a co-pilot, not a crutch. You're not here for shortcuts — you're here to build, solve, and create impact. You bridge creativity + logic like most people can't.
        </div>
      </div>
    </div>
  </div>

  <!-- TO BECOME ELITE -->
  <div class="grid-section">
    <div class="section-divider">
      <div class="section-divider-line"></div>
      <div class="section-divider-label">08 — To Become Elite with AI</div>
      <div class="section-divider-line"></div>
    </div>
    <div class="wide-card">
      <div class="grid-2" style="gap: 10px 24px;">
        <div>
          <ul class="dot-list">
            <li>Build in Public</li>
            <li>Sharpen Niche Expertise</li>
            <li>Improve Consistency</li>
          </ul>
        </div>
        <div>
          <ul class="dot-list blue">
            <li>Delegate &amp; Automate More</li>
            <li>Master Advanced AI Systems</li>
            <li>Keep Shipping</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- AI TITLE -->
  <div class="title-section">
    <div class="ai-crown">◈</div>
    <div style="font-family: 'JetBrains Mono', monospace; font-size: 10px; color: #3d5270; letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 8px;">AI Title for You</div>
    <div class="ai-title-big">THE AI ARCHITECT</div>
    <div class="ai-title-sub">Designing intelligent systems. Building the future. One prompt at a time.</div>
  </div>

  <!-- AI CHARACTER DESCRIPTION -->
  <div class="grid-section">
    <div class="section-divider">
      <div class="section-divider-line"></div>
      <div class="section-divider-label">AI Character Description</div>
      <div class="section-divider-line"></div>
    </div>
    <div class="wide-card" style="border-color: rgba(0,220,150,0.12);">
      <div style="font-family: 'JetBrains Mono', monospace; font-size: 10px; color: #00dc96; letter-spacing: 0.15em; margin-bottom: 14px; opacity: 0.7;">// CINEMATIC LOG</div>
      <div class="wide-card-body" style="font-size: 14px; color: #9aaec4; line-height: 1.85;">
        A Gen-Z builder with a hacker mindset and a researcher's soul. She thrives in the intersection of AI, code, data, and creativity. On a mission to solve big problems, build powerful products, and leave a mark on the future.
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div style="padding: 0 36px 28px; background: #05070f;">
    <div class="stats-row">
      <div class="stat-cell">
        <div class="stat-label">Focus</div>
        <div class="stat-val">95%</div>
        <div class="stat-bar-wrap"><div class="stat-bar" style="width: 95%"></div></div>
      </div>
      <div class="stat-cell">
        <div class="stat-label">Energy</div>
        <div class="stat-val">90%</div>
        <div class="stat-bar-wrap"><div class="stat-bar" style="width: 90%"></div></div>
      </div>
      <div class="stat-cell">
        <div class="stat-label">Impact</div>
        <div class="stat-val">92%</div>
        <div class="stat-bar-wrap"><div class="stat-bar" style="width: 92%"></div></div>
      </div>
    </div>
  </div>

  <!-- FUEL -->
  <div class="grid-section" style="padding-top: 0;">
    <div class="section-divider" style="margin-top: 8px;">
      <div class="section-divider-line"></div>
      <div class="section-divider-label">Fuel</div>
      <div class="section-divider-line"></div>
    </div>
    <div class="fuel-grid">
      <div class="fuel-chip"><div class="fuel-icon"></div>Curiosity</div>
      <div class="fuel-chip"><div class="fuel-icon blue"></div>Purpose</div>
      <div class="fuel-chip"><div class="fuel-icon amber"></div>Code</div>
      <div class="fuel-chip"><div class="fuel-icon amber"></div>Coffee</div>
      <div class="fuel-chip"><div class="fuel-icon"></div>Late Nights</div>
      <div class="fuel-chip"><div class="fuel-icon blue"></div>Big Picture Thinking</div>
    </div>
  </div>

  <!-- MODE BAR -->
  <div class="mode-bar">
    <span class="mode-label">Current Mode</span>
    <div class="mode-dots">
      <span class="mode-dot">Building</span>
      <span class="mode-dot">Learning</span>
      <span class="mode-dot">Shipping</span>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer-quote">
    <div class="footer-quote-text">
      "The best way to predict the future is to build it."<br>
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 11px; color: #2a3a52; font-style: normal;">— You, but in AI mode.</span>
    </div>
  </div>

</div>
</body>
</html>



