
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Space+Grotesk:wght@400;500;700&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .profile-root {
    font-family: 'Space Grotesk', sans-serif;
    background: #050816;
    color: #e2e8f0;
    min-height: 100vh;
    overflow: hidden;
    position: relative;
  }

  .stars {
    position: absolute; inset: 0; pointer-events: none;
    background-image:
      radial-gradient(1px 1px at 10% 15%, rgba(0,245,255,0.6) 0%, transparent 100%),
      radial-gradient(1px 1px at 25% 60%, rgba(255,255,255,0.4) 0%, transparent 100%),
      radial-gradient(1px 1px at 40% 25%, rgba(139,92,246,0.5) 0%, transparent 100%),
      radial-gradient(1px 1px at 55% 80%, rgba(0,245,255,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 70% 35%, rgba(255,255,255,0.5) 0%, transparent 100%),
      radial-gradient(1px 1px at 85% 55%, rgba(139,92,246,0.4) 0%, transparent 100%),
      radial-gradient(1px 1px at 15% 90%, rgba(255,255,255,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 92% 10%, rgba(0,245,255,0.5) 0%, transparent 100%),
      radial-gradient(1px 1px at 60% 50%, rgba(255,255,255,0.2) 0%, transparent 100%),
      radial-gradient(1px 1px at 33% 42%, rgba(139,92,246,0.3) 0%, transparent 100%);
    animation: starPulse 4s ease-in-out infinite alternate;
  }

  @keyframes starPulse {
    from { opacity: 0.6; }
    to { opacity: 1; }
  }

  .hero {
    position: relative;
    padding: 3rem 2rem 2rem;
    text-align: center;
    border-bottom: 1px solid rgba(0,245,255,0.12);
  }

  .hero-grid-bg {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(0,245,255,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,245,255,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  .hero-glow {
    position: absolute; top: -60px; left: 50%; transform: translateX(-50%);
    width: 500px; height: 300px;
    background: radial-gradient(ellipse, rgba(0,245,255,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .status-badge {
    display: inline-flex; align-items: center; gap: 6px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; color: #00f5ff;
    border: 1px solid rgba(0,245,255,0.3);
    background: rgba(0,245,255,0.06);
    padding: 4px 12px; border-radius: 20px;
    margin-bottom: 1.5rem;
    animation: fadeInDown 0.5s ease forwards;
  }

  .status-dot {
    width: 6px; height: 6px; border-radius: 50%;
    background: #00f5ff;
    animation: blink 1.2s ease-in-out infinite;
  }

  @keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0.2;} }

  .hero-name {
    font-size: clamp(2rem, 5vw, 3.2rem);
    font-weight: 700;
    letter-spacing: -0.02em;
    line-height: 1.1;
    background: linear-gradient(135deg, #00f5ff 0%, #a78bfa 50%, #00f5ff 100%);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: shimmer 3s linear infinite, fadeInUp 0.6s ease 0.2s both;
  }

  @keyframes shimmer { to { background-position: 200% center; } }

  .hero-role {
    margin-top: 0.75rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px; color: #8b5cf6;
    animation: fadeInUp 0.6s ease 0.4s both;
  }

  .hero-tagline {
    margin-top: 0.5rem;
    font-size: 14px; color: #64748b;
    animation: fadeInUp 0.6s ease 0.5s both;
  }

  .hero-actions {
    display: flex; gap: 12px; justify-content: center; flex-wrap: wrap;
    margin-top: 1.5rem;
    animation: fadeInUp 0.6s ease 0.6s both;
  }

  .btn-primary {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 8px 20px; border-radius: 8px;
    font-size: 13px; font-weight: 500; font-family: inherit;
    background: rgba(0,245,255,0.1);
    color: #00f5ff; border: 1px solid rgba(0,245,255,0.4);
    cursor: pointer; text-decoration: none;
    transition: all 0.2s ease;
  }

  .btn-primary:hover {
    background: rgba(0,245,255,0.18);
    border-color: #00f5ff;
    transform: translateY(-1px);
  }

  .btn-secondary {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 8px 20px; border-radius: 8px;
    font-size: 13px; font-weight: 500; font-family: inherit;
    background: rgba(139,92,246,0.1);
    color: #a78bfa; border: 1px solid rgba(139,92,246,0.4);
    cursor: pointer; text-decoration: none;
    transition: all 0.2s ease;
  }

  .btn-secondary:hover {
    background: rgba(139,92,246,0.18);
    border-color: #8b5cf6;
    transform: translateY(-1px);
  }

  .section {
    padding: 2rem;
    border-bottom: 1px solid rgba(255,255,255,0.05);
  }

  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px; letter-spacing: 0.12em;
    color: #00f5ff; opacity: 0.7;
    text-transform: uppercase; margin-bottom: 1.25rem;
    display: flex; align-items: center; gap: 8px;
  }

  .section-label::after {
    content: ''; flex: 1; height: 1px;
    background: linear-gradient(90deg, rgba(0,245,255,0.3), transparent);
  }

  .profile-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 12px;
  }

  .info-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 10px; padding: 1rem;
    transition: border-color 0.2s;
  }

  .info-card:hover { border-color: rgba(0,245,255,0.2); }

  .info-card-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px; color: #475569; text-transform: uppercase;
    letter-spacing: 0.1em; margin-bottom: 4px;
  }

  .info-card-value {
    font-size: 13px; font-weight: 500; color: #e2e8f0;
  }

  .info-card-value.cyan { color: #00f5ff; }
  .info-card-value.purple { color: #a78bfa; }

  .mission-box {
    background: rgba(0,245,255,0.04);
    border: 1px solid rgba(0,245,255,0.15);
    border-radius: 10px; padding: 1rem;
    margin-top: 12px;
    font-size: 13px; color: #94a3b8; font-style: italic;
    display: flex; align-items: center; gap: 10px;
  }

  .mission-icon { font-size: 18px; }

  .tech-grid {
    display: grid; grid-template-columns: repeat(auto-fill, minmax(76px, 1fr));
    gap: 8px;
  }

  .tech-chip {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 8px; padding: 8px 6px;
    text-align: center; font-size: 11px;
    font-family: 'JetBrains Mono', monospace;
    color: #94a3b8;
    transition: all 0.2s ease;
    cursor: default;
  }

  .tech-chip:hover {
    background: rgba(0,245,255,0.06);
    border-color: rgba(0,245,255,0.3);
    color: #00f5ff;
    transform: translateY(-2px);
  }

  .tech-chip .chip-icon { font-size: 20px; display: block; margin-bottom: 4px; }

  .projects-grid {
    display: grid; grid-template-columns: 1fr; gap: 12px;
  }

  .project-card {
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 12px; padding: 1.25rem;
    transition: all 0.25s ease;
    position: relative; overflow: hidden;
  }

  .project-card::before {
    content: ''; position: absolute;
    top: 0; left: 0; right: 0; height: 2px;
    opacity: 0; transition: opacity 0.2s;
  }

  .project-card.cyan-accent::before { background: linear-gradient(90deg, #00f5ff, transparent); }
  .project-card.purple-accent::before { background: linear-gradient(90deg, #8b5cf6, transparent); }
  .project-card.green-accent::before { background: linear-gradient(90deg, #10b981, transparent); }

  .project-card:hover::before { opacity: 1; }
  .project-card:hover { border-color: rgba(255,255,255,0.14); transform: translateX(4px); }

  .project-header {
    display: flex; justify-content: space-between;
    align-items: flex-start; margin-bottom: 10px;
  }

  .project-title-row { display: flex; align-items: center; gap: 10px; }
  .project-emoji { font-size: 22px; }

  .project-name {
    font-weight: 600; font-size: 14px; color: #e2e8f0;
  }

  .project-type {
    font-size: 10px; color: #64748b;
    font-family: 'JetBrains Mono', monospace;
    text-transform: uppercase; letter-spacing: 0.08em;
  }

  .project-status {
    display: inline-flex; align-items: center; gap: 5px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px; padding: 3px 10px; border-radius: 20px;
    background: rgba(16,185,129,0.1); color: #10b981;
    border: 1px solid rgba(16,185,129,0.25);
  }

  .project-status-dot { width: 5px; height: 5px; border-radius: 50%; background: #10b981; animation: blink 1.5s infinite; }

  .project-features {
    display: flex; flex-wrap: wrap; gap: 6px; margin-top: 10px;
  }

  .feature-tag {
    font-size: 11px; padding: 3px 10px; border-radius: 6px;
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    color: #64748b; font-family: 'JetBrains Mono', monospace;
  }

  .stats-row {
    display: grid; grid-template-columns: 1fr 1fr; gap: 10px;
  }

  .stat-card {
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 10px; padding: 1rem;
    text-align: center;
  }

  .stat-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 28px; font-weight: 700;
    background: linear-gradient(135deg, #00f5ff, #8b5cf6);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .stat-label { font-size: 11px; color: #475569; margin-top: 4px; }

  .connect-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 10px;
  }

  .connect-card {
    display: flex; align-items: center; gap: 10px;
    padding: 12px 14px; border-radius: 10px;
    border: 1px solid rgba(255,255,255,0.07);
    background: rgba(255,255,255,0.02);
    text-decoration: none; color: #94a3b8;
    transition: all 0.2s ease; cursor: pointer;
  }

  .connect-card:hover {
    border-color: rgba(0,245,255,0.25);
    background: rgba(0,245,255,0.05);
    color: #00f5ff;
    transform: translateY(-2px);
  }

  .connect-icon { font-size: 20px; }
  .connect-label { font-size: 12px; font-weight: 500; }
  .connect-sub { font-size: 10px; color: #475569; }

  .footer-bar {
    padding: 1.5rem 2rem;
    text-align: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; color: #1e3a4a;
    border-top: 1px solid rgba(0,245,255,0.06);
    position: relative;
  }

  .footer-text {
    color: #334155;
    display: flex; justify-content: center; align-items: center; gap: 8px;
  }

  .footer-glow {
    color: #00f5ff; opacity: 0.5;
    animation: blink 2s infinite;
  }

  @keyframes fadeInDown {
    from { opacity: 0; transform: translateY(-10px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .appear { opacity: 0; transform: translateY(20px); transition: all 0.5s ease; }
  .appear.visible { opacity: 1; transform: translateY(0); }

  .typing-cursor {
    display: inline-block; width: 2px; height: 1em;
    background: #00f5ff; vertical-align: middle;
    animation: blink 0.7s step-end infinite;
    margin-left: 2px;
  }

  .lang-bar-container { margin-top: 10px; }

  .lang-row {
    display: flex; align-items: center; justify-content: space-between;
    margin-bottom: 6px;
  }

  .lang-name { font-size: 12px; color: #94a3b8; }
  .lang-pct { font-family: 'JetBrains Mono', monospace; font-size: 11px; color: #475569; }

  .lang-track {
    height: 4px; background: rgba(255,255,255,0.06);
    border-radius: 4px; overflow: hidden; margin-bottom: 10px;
  }

  .lang-fill {
    height: 100%; border-radius: 4px;
    transition: width 1.2s ease;
    width: 0;
  }

  .lang-fill.cyan { background: #00f5ff; }
  .lang-fill.purple { background: #8b5cf6; }
  .lang-fill.blue { background: #3b82f6; }
  .lang-fill.green { background: #10b981; }
  .lang-fill.orange { background: #f97316; }

  .terminal-block {
    background: rgba(0,0,0,0.4);
    border: 1px solid rgba(0,245,255,0.12);
    border-radius: 10px; padding: 1rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px; margin-top: 12px;
  }

  .terminal-line { margin: 2px 0; }
  .t-prompt { color: #00f5ff; }
  .t-cmd { color: #e2e8f0; }
  .t-ok { color: #10b981; }
  .t-dim { color: #334155; }
</style>

<div class="profile-root" id="root">
  <div class="stars"></div>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-grid-bg"></div>
    <div class="hero-glow"></div>

    <div class="status-badge">
      <div class="status-dot"></div>
      <span>SYSTEM ONLINE — DEVELOPER MODE</span>
    </div>

    <h1 class="hero-name">Yugam Kothari</h1>

    <div class="hero-role" id="typing-role">Full Stack Developer</div>
    <div class="hero-tagline">React Native · UI/UX · Real World Systems</div>

    <div class="hero-actions">
      <a class="btn-primary" href="mailto:yugamkothari886@gmail.com">
        <i class="ti ti-mail" aria-hidden="true"></i> Email Me
      </a>
      <a class="btn-secondary" href="https://linkedin.com/in/yugam-kothari-b18309332">
        <i class="ti ti-brand-linkedin" aria-hidden="true"></i> LinkedIn
      </a>
    </div>
  </div>

  <!-- PROFILE -->
  <div class="section appear" id="s1">
    <div class="section-label">Core Profile</div>
    <div class="profile-grid">
      <div class="info-card">
        <div class="info-card-label">Role</div>
        <div class="info-card-value cyan">Full Stack Dev</div>
      </div>
      <div class="info-card">
        <div class="info-card-label">Style</div>
        <div class="info-card-value purple">Cyber UI Architect</div>
      </div>
      <div class="info-card">
        <div class="info-card-label">Location</div>
        <div class="info-card-value">India 🇮🇳</div>
      </div>
      <div class="info-card">
        <div class="info-card-label">Status</div>
        <div class="info-card-value" style="color:#10b981">Open to Work</div>
      </div>
    </div>
    <div class="mission-box">
      <span class="mission-icon">🚀</span>
      <span>"Let's Build Something Together" — turning ideas into real, working systems</span>
    </div>
  </div>

  <!-- TECH ARSENAL -->
  <div class="section appear" id="s2">
    <div class="section-label">Tech Arsenal</div>
    <div class="tech-grid">
      <div class="tech-chip"><span class="chip-icon">⚛️</span>React</div>
      <div class="tech-chip"><span class="chip-icon">▲</span>Next.js</div>
      <div class="tech-chip"><span class="chip-icon">📱</span>RN</div>
      <div class="tech-chip"><span class="chip-icon">🟢</span>Node</div>
      <div class="tech-chip"><span class="chip-icon">🔷</span>TypeScript</div>
      <div class="tech-chip"><span class="chip-icon">🔥</span>Firebase</div>
      <div class="tech-chip"><span class="chip-icon">⚡</span>Supabase</div>
      <div class="tech-chip"><span class="chip-icon">🐘</span>Postgres</div>
      <div class="tech-chip"><span class="chip-icon">🗄️</span>MySQL</div>
      <div class="tech-chip"><span class="chip-icon">☕</span>Java</div>
      <div class="tech-chip"><span class="chip-icon">🤖</span>Kotlin</div>
      <div class="tech-chip"><span class="chip-icon">🎨</span>Tailwind</div>
      <div class="tech-chip"><span class="chip-icon">🖼️</span>Figma</div>
      <div class="tech-chip"><span class="chip-icon">🐙</span>GitHub</div>
    </div>

    <div class="lang-bar-container" style="margin-top:1.5rem;">
      <div class="section-label" style="margin-bottom:1rem;">Top Languages</div>
      <div class="lang-row"><span class="lang-name">JavaScript / TypeScript</span><span class="lang-pct">42%</span></div>
      <div class="lang-track"><div class="lang-fill cyan" data-w="42"></div></div>

      <div class="lang-row"><span class="lang-name">Kotlin / Java</span><span class="lang-pct">28%</span></div>
      <div class="lang-track"><div class="lang-fill purple" data-w="28"></div></div>

      <div class="lang-row"><span class="lang-name">CSS / Tailwind</span><span class="lang-pct">18%</span></div>
      <div class="lang-track"><div class="lang-fill blue" data-w="18"></div></div>

      <div class="lang-row"><span class="lang-name">SQL</span><span class="lang-pct">12%</span></div>
      <div class="lang-track"><div class="lang-fill green" data-w="12"></div></div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section appear" id="s3">
    <div class="section-label">System Projects</div>
    <div class="projects-grid">

      <div class="project-card cyan-accent">
        <div class="project-header">
          <div class="project-title-row">
            <span class="project-emoji">🛕</span>
            <div>
              <div class="project-name">Jinaarya Vihar Seva</div>
              <div class="project-type">Safety + Tracking System</div>
            </div>
          </div>
          <div class="project-status"><div class="project-status-dot"></div>Active</div>
        </div>
        <div class="project-features">
          <span class="feature-tag">Live GPS Tracking</span>
          <span class="feature-tag">Emergency SOS</span>
          <span class="feature-tag">Admin Panel</span>
          <span class="feature-tag">Route Deviation Alerts</span>
        </div>
      </div>

      <div class="project-card purple-accent">
        <div class="project-header">
          <div class="project-title-row">
            <span class="project-emoji">🛍</span>
            <div>
              <div class="project-name">Kiddorin System</div>
              <div class="project-type">Stock Management System</div>
            </div>
          </div>
          <div class="project-status"><div class="project-status-dot"></div>Active</div>
        </div>
        <div class="project-features">
          <span class="feature-tag">Inventory Engine</span>
          <span class="feature-tag">Billing System</span>
          <span class="feature-tag">Product Control</span>
        </div>
      </div>

      <div class="project-card green-accent">
        <div class="project-header">
          <div class="project-title-row">
            <span class="project-emoji">🌐</span>
            <div>
              <div class="project-name">Web Engine</div>
              <div class="project-type">Full Stack Web Development</div>
            </div>
          </div>
          <div class="project-status"><div class="project-status-dot"></div>Active</div>
        </div>
        <div class="project-features">
          <span class="feature-tag">Business Websites</span>
          <span class="feature-tag">Portfolio Systems</span>
          <span class="feature-tag">Responsive UI/UX</span>
        </div>
      </div>

    </div>
  </div>

  <!-- SYSTEM TERMINAL -->
  <div class="section appear" id="s4">
    <div class="section-label">System Status</div>
    <div class="terminal-block">
      <div class="terminal-line"><span class="t-prompt">$</span> <span class="t-cmd">boot yugamm15.system</span></div>
      <div class="terminal-line t-dim">———————————————————————</div>
      <div class="terminal-line"><span class="t-ok">✔</span> Identity Loaded</div>
      <div class="terminal-line"><span class="t-ok">✔</span> Developer Profile Active</div>
      <div class="terminal-line"><span class="t-ok">✔</span> Portfolio Online</div>
      <div class="terminal-line"><span class="t-ok">✔</span> Creativity Engine Running</div>
      <div class="terminal-line t-dim" style="margin-top:6px;">MODE: BUILD · LEARN · EVOLVE</div>
    </div>

    <div class="stats-row" style="margin-top:12px;">
      <div class="stat-card">
        <div class="stat-number" id="cnt-projects">0</div>
        <div class="stat-label">Projects Shipped</div>
      </div>
      <div class="stat-card">
        <div class="stat-number" id="cnt-tech">0</div>
        <div class="stat-label">Technologies Mastered</div>
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section appear" id="s5">
    <div class="section-label">Connection Portal</div>
    <div class="connect-grid">
      <a class="connect-card" href="mailto:yugamkothari886@gmail.com">
        <span class="connect-icon">📧</span>
        <div>
          <div class="connect-label">Email</div>
          <div class="connect-sub">yugamkothari886@gmail.com</div>
        </div>
      </a>
      <a class="connect-card" href="https://linkedin.com/in/yugam-kothari-b18309332">
        <span class="connect-icon">💼</span>
        <div>
          <div class="connect-label">LinkedIn</div>
          <div class="connect-sub">yugam-kothari</div>
        </div>
      </a>
      <a class="connect-card" href="https://github.com/yugamm15">
        <span class="connect-icon">🐙</span>
        <div>
          <div class="connect-label">GitHub</div>
          <div class="connect-sub">@yugamm15</div>
        </div>
      </a>
      <div class="connect-card" style="cursor:default;">
        <span class="connect-icon">🇮🇳</span>
        <div>
          <div class="connect-label">Based in India</div>
          <div class="connect-sub">Open to remote work</div>
        </div>
      </div>
    </div>
  </div>

  <div class="footer-bar">
    <div class="footer-text">
      <span class="footer-glow">█</span>
      <span>yugamm15 · made with precision · 2025</span>
      <span class="footer-glow">█</span>
    </div>
  </div>
</div>

<script>
  const roles = ['Full Stack Developer', 'React Native Architect', 'UI/UX System Designer', 'Building Real World Systems'];
  let ri = 0, ci = 0, deleting = false;
  const el = document.getElementById('typing-role');

  function type() {
    const cur = roles[ri];
    if (!deleting && ci <= cur.length) {
      el.textContent = cur.slice(0, ci++);
      setTimeout(type, 65);
    } else if (!deleting && ci > cur.length) {
      deleting = true;
      setTimeout(type, 1800);
    } else if (deleting && ci >= 0) {
      el.textContent = cur.slice(0, ci--);
      setTimeout(type, 35);
    } else {
      deleting = false;
      ri = (ri + 1) % roles.length;
      setTimeout(type, 200);
    }
  }
  setTimeout(type, 800);

  const obs = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        if (e.target.id === 's2') animateBars();
        if (e.target.id === 's4') animateCounters();
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.appear').forEach(el => obs.observe(el));

  function animateBars() {
    document.querySelectorAll('.lang-fill').forEach(bar => {
      setTimeout(() => { bar.style.width = bar.dataset.w + '%'; }, 200);
    });
  }

  function animateCounters() {
    animateCount('cnt-projects', 3, 800);
    animateCount('cnt-tech', 14, 900);
  }

  function animateCount(id, target, dur) {
    const el = document.getElementById(id);
    const step = target / (dur / 30);
    let val = 0;
    const t = setInterval(() => {
      val = Math.min(val + step, target);
      el.textContent = Math.round(val);
      if (val >= target) clearInterval(t);
    }, 30);
  }
</script>
