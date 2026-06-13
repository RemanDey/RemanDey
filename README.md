
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;600&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .profile-root {
    font-family: 'Space Grotesk', sans-serif;
    background: #050a14;
    color: #e2e8f0;
    min-height: 100vh;
    padding: 2rem 1.5rem;
    position: relative;
    overflow: hidden;
  }

  .bg-grid {
    position: absolute; inset: 0;
    background-image: linear-gradient(rgba(0,247,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,247,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  .bg-orb {
    position: absolute; border-radius: 50%; filter: blur(80px); pointer-events: none;
  }
  .orb1 { width: 400px; height: 400px; background: rgba(0,247,255,0.06); top: -100px; right: -100px; }
  .orb2 { width: 300px; height: 300px; background: rgba(120,80,255,0.07); bottom: 100px; left: -80px; }
  .orb3 { width: 200px; height: 200px; background: rgba(255,107,107,0.05); top: 50%; left: 40%; }

  .glass {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.09);
    border-radius: 16px;
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
  }

  .glass-accent {
    background: rgba(0,247,255,0.05);
    border: 1px solid rgba(0,247,255,0.15);
    border-radius: 16px;
    backdrop-filter: blur(12px);
  }

  .hero { text-align: center; padding: 2.5rem 1.5rem 2rem; position: relative; }

  .avatar-ring {
    width: 90px; height: 90px; border-radius: 50%;
    background: linear-gradient(135deg, #00f7ff22, #7c3aed22);
    border: 1.5px solid rgba(0,247,255,0.35);
    display: flex; align-items: center; justify-content: center;
    margin: 0 auto 1.25rem;
    position: relative;
    font-family: 'JetBrains Mono', monospace;
    font-size: 28px; font-weight: 600;
    color: #00f7ff;
  }
  .avatar-ring::before {
    content: '';
    position: absolute; inset: -4px; border-radius: 50%;
    background: conic-gradient(from 0deg, #00f7ff44, transparent 60%, #7c3aed44, transparent 100%);
    animation: spin 6s linear infinite;
    z-index: -1;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .name {
    font-size: 2rem; font-weight: 700; letter-spacing: -0.5px;
    background: linear-gradient(90deg, #00f7ff, #a78bfa, #f472b6);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    margin-bottom: 0.35rem;
  }

  .role {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem; color: #00f7ff; letter-spacing: 2px;
    text-transform: uppercase; opacity: 0.85;
    margin-bottom: 1.25rem;
  }

  .tagline {
    font-size: 0.92rem; color: rgba(226,232,240,0.6);
    font-style: italic; margin-bottom: 1.5rem;
  }

  .badges {
    display: flex; flex-wrap: wrap; gap: 8px; justify-content: center;
  }

  .badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.68rem; letter-spacing: 0.5px;
    padding: 5px 12px; border-radius: 999px;
    border: 1px solid rgba(0,247,255,0.2);
    background: rgba(0,247,255,0.06);
    color: #00f7ff;
    white-space: nowrap;
  }
  .badge.purple { border-color: rgba(167,139,250,0.3); background: rgba(167,139,250,0.07); color: #a78bfa; }
  .badge.pink { border-color: rgba(244,114,182,0.3); background: rgba(244,114,182,0.07); color: #f472b6; }
  .badge.orange { border-color: rgba(251,146,60,0.3); background: rgba(251,146,60,0.07); color: #fb923c; }

  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem; letter-spacing: 3px; text-transform: uppercase;
    color: #00f7ff; opacity: 0.6; margin-bottom: 1rem;
  }

  .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 12px; }
  .grid-3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 10px; margin-bottom: 12px; }

  .stat-card {
    padding: 1rem 1.25rem; text-align: center;
  }
  .stat-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.6rem; font-weight: 700;
    background: linear-gradient(135deg, #00f7ff, #a78bfa);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    line-height: 1;
  }
  .stat-lbl { font-size: 0.72rem; color: rgba(226,232,240,0.5); margin-top: 4px; letter-spacing: 0.5px; }

  .project-card { padding: 1rem 1.25rem; margin-bottom: 10px; position: relative; overflow: hidden; }
  .project-card::before {
    content: ''; position: absolute; top: 0; left: 0; width: 3px; height: 100%;
    background: linear-gradient(180deg, #00f7ff, #7c3aed);
    border-radius: 3px 0 0 3px;
  }
  .project-title { font-size: 0.92rem; font-weight: 600; color: #e2e8f0; margin-bottom: 4px; }
  .project-desc { font-size: 0.78rem; color: rgba(226,232,240,0.55); line-height: 1.5; margin-bottom: 8px; }
  .project-tags { display: flex; flex-wrap: wrap; gap: 5px; }
  .ptag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.62rem; padding: 2px 8px; border-radius: 4px;
    background: rgba(0,247,255,0.08); border: 1px solid rgba(0,247,255,0.15);
    color: rgba(0,247,255,0.8);
  }

  .skill-grid { display: flex; flex-wrap: wrap; gap: 7px; }
  .skill-pill {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.67rem; padding: 5px 11px;
    border-radius: 8px;
    border: 1px solid rgba(255,255,255,0.1);
    background: rgba(255,255,255,0.04);
    color: rgba(226,232,240,0.75);
    transition: all 0.2s;
  }
  .skill-pill:hover { border-color: rgba(0,247,255,0.35); color: #00f7ff; background: rgba(0,247,255,0.06); }

  .link-bar { display: flex; gap: 10px; flex-wrap: wrap; }
  .link-btn {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem; padding: 8px 16px;
    border-radius: 10px; text-decoration: none;
    display: flex; align-items: center; gap: 6px;
    transition: all 0.2s; cursor: pointer;
    border: none; font-family: inherit;
  }
  .link-btn.primary {
    background: rgba(0,247,255,0.12); border: 1px solid rgba(0,247,255,0.3);
    color: #00f7ff;
  }
  .link-btn.primary:hover { background: rgba(0,247,255,0.2); }
  .link-btn.secondary {
    background: rgba(167,139,250,0.1); border: 1px solid rgba(167,139,250,0.25);
    color: #a78bfa;
  }
  .link-btn.secondary:hover { background: rgba(167,139,250,0.18); }
  .link-btn.ghost {
    background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.1);
    color: rgba(226,232,240,0.7);
  }
  .link-btn.ghost:hover { border-color: rgba(255,255,255,0.2); color: #e2e8f0; }

  .seek-item { display: flex; align-items: flex-start; gap: 10px; padding: 10px 0; border-bottom: 1px solid rgba(255,255,255,0.05); }
  .seek-item:last-child { border-bottom: none; }
  .seek-dot {
    width: 8px; height: 8px; border-radius: 50%; margin-top: 5px; flex-shrink: 0;
    background: #00f7ff; box-shadow: 0 0 6px #00f7ff88;
  }
  .seek-dot.purple { background: #a78bfa; box-shadow: 0 0 6px #a78bfa88; }
  .seek-dot.pink { background: #f472b6; box-shadow: 0 0 6px #f472b688; }
  .seek-dot.orange { background: #fb923c; box-shadow: 0 0 6px #fb923c88; }
  .seek-text { font-size: 0.82rem; color: rgba(226,232,240,0.75); line-height: 1.5; }
  .seek-text strong { color: #e2e8f0; font-weight: 500; }

  .section { padding: 1.25rem; margin-bottom: 12px; }

  .divider {
    height: 1px; background: linear-gradient(90deg, transparent, rgba(0,247,255,0.2), transparent);
    margin: 0.5rem 0 1.25rem;
  }

  .mono { font-family: 'JetBrains Mono', monospace; }

  .footer-bar {
    text-align: center; padding: 1.25rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem; color: rgba(226,232,240,0.3); letter-spacing: 1px;
  }

  .pulse-ring {
    display: inline-block; width: 8px; height: 8px; border-radius: 50%;
    background: #00f7ff; box-shadow: 0 0 6px #00f7ff;
    animation: pulse 2s infinite;
  }
  @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.3; } }
</style>

<div class="profile-root">
  <div class="bg-grid"></div>
  <div class="bg-orb orb1"></div>
  <div class="bg-orb orb2"></div>
  <div class="bg-orb orb3"></div>

  <!-- Hero -->
  <div class="glass hero" style="margin-bottom:12px; position:relative; z-index:1;">
    <div class="avatar-ring">RD</div>
    <div class="name">Reman Dey</div>
    <div class="role">Engineering Physics · IIT Mandi</div>
    <div class="tagline">"I don't just study the universe — I build things inspired by it."</div>
    <div class="badges">
      <span class="badge">Laser Physics</span>
      <span class="badge purple">Robotics</span>
      <span class="badge pink">AI & NLP</span>
      <span class="badge orange">Embedded Systems</span>
      <span class="badge purple">Optics</span>
    </div>
  </div>

  <!-- Stats -->
  <div class="grid-3" style="position:relative;z-index:1;">
    <div class="glass stat-card">
      <div class="stat-num">7+</div>
      <div class="stat-lbl">Projects Built</div>
    </div>
    <div class="glass stat-card">
      <div class="stat-num">5</div>
      <div class="stat-lbl">Languages</div>
    </div>
    <div class="glass stat-card">
      <div class="stat-num">∞</div>
      <div class="stat-lbl">Curiosity</div>
    </div>
  </div>

  <!-- Tech Stack -->
  <div class="glass section" style="position:relative;z-index:1;margin-bottom:12px;">
    <div class="section-label">// Tech Arsenal</div>
    <div class="divider"></div>
    <p style="font-size:0.72rem;color:rgba(226,232,240,0.4);margin-bottom:10px;font-family:'JetBrains Mono',monospace;">Languages</p>
    <div class="skill-grid" style="margin-bottom:14px;">
      <span class="skill-pill">Python</span>
      <span class="skill-pill">C++</span>
      <span class="skill-pill">C</span>
      <span class="skill-pill">JavaScript</span>
      <span class="skill-pill">HTML5</span>
      <span class="skill-pill">CSS3</span>
    </div>
    <p style="font-size:0.72rem;color:rgba(226,232,240,0.4);margin-bottom:10px;font-family:'JetBrains Mono',monospace;">Hardware & Embedded</p>
    <div class="skill-grid" style="margin-bottom:14px;">
      <span class="skill-pill">Arduino</span>
      <span class="skill-pill">Raspberry Pi</span>
      <span class="skill-pill">Robotics</span>
      <span class="skill-pill">Electronics</span>
    </div>
    <p style="font-size:0.72rem;color:rgba(226,232,240,0.4);margin-bottom:10px;font-family:'JetBrains Mono',monospace;">AI & Software</p>
    <div class="skill-grid">
      <span class="skill-pill">AI / ML</span>
      <span class="skill-pill">NLP</span>
      <span class="skill-pill">Telegram Bot API</span>
      <span class="skill-pill">Gemini API</span>
      <span class="skill-pill">Git</span>
      <span class="skill-pill">GitHub</span>
    </div>
  </div>

  <!-- Projects -->
  <div style="position:relative;z-index:1;margin-bottom:12px;">
    <div class="glass" style="padding:1.25rem 1.25rem 0.5rem;">
      <div class="section-label">// Featured Projects</div>
      <div class="divider"></div>
    </div>
    <div style="height:8px;"></div>

    <div class="glass project-card">
      <div class="project-title">🤝 FriendForge</div>
      <div class="project-desc">A private web app to track and cherish your connections — relationship management, personal style.</div>
      <div class="project-tags"><span class="ptag">HTML</span><span class="ptag">CSS</span><span class="ptag">JS</span></div>
    </div>

    <div class="glass project-card">
      <div class="project-title">🤖 Dodo & Luna</div>
      <div class="project-desc">Python-powered Telegram bots with smart conversational AI using NLP pipelines.</div>
      <div class="project-tags"><span class="ptag">Python</span><span class="ptag">NLP</span><span class="ptag">Telegram API</span></div>
    </div>

    <div class="glass project-card">
      <div class="project-title">💬 DodoTalks</div>
      <div class="project-desc">Sleek AI chat app powered by Google Gemini with a charming dodo mascot interface.</div>
      <div class="project-tags"><span class="ptag">Web</span><span class="ptag">Gemini API</span></div>
    </div>

    <div class="glass project-card">
      <div class="project-title">⚡ Tesla Turbine</div>
      <div class="project-desc">Bladeless turbine leveraging viscosity and boundary layer effects — pure physics in motion.</div>
      <div class="project-tags"><span class="ptag">Physics</span><span class="ptag">Mechanical Eng.</span></div>
    </div>

    <div class="glass project-card">
      <div class="project-title">🔦 Laser Transceiver</div>
      <div class="project-desc">Laser-based transmitter and receiver system bridging optics and electronics.</div>
      <div class="project-tags"><span class="ptag">Electronics</span><span class="ptag">Optics</span></div>
    </div>
  </div>

  <!-- Seeking -->
  <div class="glass-accent section" style="position:relative;z-index:1;margin-bottom:12px;">
    <div class="section-label">// Open To</div>
    <div class="divider" style="background:linear-gradient(90deg,transparent,rgba(0,247,255,0.15),transparent);"></div>
    <div class="seek-item">
      <div class="seek-dot"></div>
      <div class="seek-text"><strong>Advanced Physics Research</strong> — experimental design, lab instrumentation</div>
    </div>
    <div class="seek-item">
      <div class="seek-dot purple"></div>
      <div class="seek-text"><strong>Robotics & Intelligent Automation</strong> — embedded + cognitive systems</div>
    </div>
    <div class="seek-item">
      <div class="seek-dot pink"></div>
      <div class="seek-text"><strong>Software & AI Development</strong> — NLP, bots, real-world AI applications</div>
    </div>
    <div class="seek-item">
      <div class="seek-dot orange"></div>
      <div class="seek-text"><strong>Hardware Prototyping</strong> — from PCB to physics-inspired machines</div>
    </div>
  </div>

  <!-- Links -->
  <div class="glass section" style="position:relative;z-index:1;margin-bottom:12px;">
    <div class="section-label">// Connect</div>
    <div class="divider"></div>
    <div class="link-bar">
      <button class="link-btn primary" onclick="openLink('https://remandey.github.io/my-portfolio')">
        <i class="ti ti-world" aria-hidden="true"></i> Portfolio
      </button>
      <button class="link-btn secondary" onclick="openLink('https://linkedin.com/in/remandey')">
        <i class="ti ti-brand-linkedin" aria-hidden="true"></i> LinkedIn
      </button>
      <button class="link-btn ghost" onclick="openLink('https://github.com/RemanDey')">
        <i class="ti ti-brand-github" aria-hidden="true"></i> GitHub
      </button>
      <button class="link-btn ghost" onclick="openLink('mailto:reman.airport@gmail.com')">
        <i class="ti ti-mail" aria-hidden="true"></i> Email
      </button>
    </div>
  </div>

  <!-- Footer -->
  <div class="footer-bar" style="position:relative;z-index:1;">
    <span class="pulse-ring" style="margin-right:8px;"></span>
    "The universe is my playground. I just happen to build in it."
  </div>
</div>
