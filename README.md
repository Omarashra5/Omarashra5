
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Syne:wght@700;800&family=Fira+Code:wght@400;500&display=swap');

  * { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --cyan: #00F7FF;
    --purple: #8B5CF6;
    --dark: #050A13;
    --card: rgba(255,255,255,0.03);
    --border: rgba(0,247,255,0.15);
    --text: #E2E8F0;
    --muted: #64748B;
  }

  body { background: transparent; }

  .profile-root {
    background: linear-gradient(135deg, #050A13 0%, #0A1628 50%, #05111F 100%);
    border-radius: 20px;
    overflow: hidden;
    position: relative;
    font-family: 'Space Grotesk', sans-serif;
    color: var(--text);
    padding-bottom: 40px;
  }

  /* Animated grid background */
  .grid-bg {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background-image:
      linear-gradient(rgba(0,247,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,247,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  /* Hero section */
  .hero {
    position: relative;
    z-index: 1;
    padding: 50px 40px 40px;
    display: flex;
    align-items: center;
    gap: 36px;
  }

  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
  }

  .avatar-ring {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    background: conic-gradient(from 0deg, #00F7FF, #8B5CF6, #EC4899, #00F7FF);
    padding: 3px;
    animation: spin 4s linear infinite;
  }

  @keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: #050A13;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 36px;
    font-weight: 800;
    color: var(--cyan);
    letter-spacing: -2px;
  }

  .status-dot {
    position: absolute;
    bottom: 6px; right: 6px;
    width: 18px; height: 18px;
    background: #22C55E;
    border-radius: 50%;
    border: 3px solid #050A13;
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(34,197,94,0.4); }
    50% { box-shadow: 0 0 0 8px rgba(34,197,94,0); }
  }

  .hero-info { flex: 1; }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: 42px;
    font-weight: 800;
    color: #fff;
    line-height: 1;
    letter-spacing: -1px;
    margin-bottom: 6px;
  }

  .hero-name span {
    background: linear-gradient(90deg, #00F7FF, #8B5CF6);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-title {
    font-size: 14px;
    color: var(--cyan);
    font-family: 'Fira Code', monospace;
    margin-bottom: 16px;
    opacity: 0.9;
  }

  .hero-title::before { content: '> '; opacity: 0.5; }

  .badges {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .badge {
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.5px;
    text-transform: uppercase;
  }

  .badge-cyan { background: rgba(0,247,255,0.1); color: var(--cyan); border: 1px solid rgba(0,247,255,0.3); }
  .badge-purple { background: rgba(139,92,246,0.1); color: #A78BFA; border: 1px solid rgba(139,92,246,0.3); }
  .badge-green { background: rgba(34,197,94,0.1); color: #4ADE80; border: 1px solid rgba(34,197,94,0.3); }

  /* Sections */
  .section {
    position: relative;
    z-index: 1;
    padding: 0 40px;
    margin-bottom: 32px;
  }

  .section-title {
    font-family: 'Fira Code', monospace;
    font-size: 11px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, rgba(0,247,255,0.2), transparent);
  }

  /* Stats grid */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px 16px;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: transform 0.2s, border-color 0.2s;
    cursor: default;
  }

  .stat-card:hover {
    transform: translateY(-3px);
    border-color: rgba(0,247,255,0.4);
  }

  .stat-card::before {
    content: '';
    position: absolute;
    top: -40px; left: -40px;
    width: 100px; height: 100px;
    border-radius: 50%;
    opacity: 0.05;
  }

  .stat-card:nth-child(1)::before { background: #00F7FF; }
  .stat-card:nth-child(2)::before { background: #8B5CF6; }
  .stat-card:nth-child(3)::before { background: #EC4899; }
  .stat-card:nth-child(4)::before { background: #22C55E; }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 28px;
    font-weight: 800;
    margin-bottom: 4px;
  }

  .stat-card:nth-child(1) .stat-num { color: #00F7FF; }
  .stat-card:nth-child(2) .stat-num { color: #A78BFA; }
  .stat-card:nth-child(3) .stat-num { color: #F472B6; }
  .stat-card:nth-child(4) .stat-num { color: #4ADE80; }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    font-weight: 500;
  }

  /* Skills */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
  }

  .skill-row {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 16px;
  }

  .skill-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 10px;
  }

  .skill-name { font-size: 13px; font-weight: 600; color: var(--text); }
  .skill-pct { font-family: 'Fira Code', monospace; font-size: 12px; color: var(--cyan); }

  .skill-bar {
    height: 3px;
    background: rgba(255,255,255,0.06);
    border-radius: 99px;
    overflow: hidden;
  }

  .skill-fill {
    height: 100%;
    border-radius: 99px;
    position: relative;
    animation: fillBar 1.5s ease-out forwards;
  }

  @keyframes fillBar {
    from { width: 0%; }
  }

  /* Projects */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    cursor: pointer;
    transition: transform 0.2s, border-color 0.2s, background 0.2s;
    position: relative;
    overflow: hidden;
  }

  .project-card:hover {
    transform: translateY(-4px);
    border-color: rgba(139,92,246,0.5);
    background: rgba(139,92,246,0.05);
  }

  .project-tag {
    font-size: 10px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--cyan);
    margin-bottom: 8px;
    font-family: 'Fira Code', monospace;
  }

  .project-name {
    font-size: 15px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 6px;
  }

  .project-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.5;
  }

  .project-tech {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
    margin-top: 12px;
  }

  .tech-chip {
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 4px;
    background: rgba(0,247,255,0.08);
    color: rgba(0,247,255,0.8);
    font-family: 'Fira Code', monospace;
  }

  /* Connect */
  .connect-grid {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .connect-btn {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 10px 18px;
    border-radius: 8px;
    border: 1px solid;
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
    text-decoration: none;
  }

  .connect-btn:hover { transform: translateY(-2px); filter: brightness(1.2); }

  .btn-portfolio { border-color: rgba(0,247,255,0.4); color: var(--cyan); background: rgba(0,247,255,0.05); }
  .btn-email { border-color: rgba(234,67,53,0.4); color: #F87171; background: rgba(234,67,53,0.05); }
  .btn-wa { border-color: rgba(37,211,102,0.4); color: #4ADE80; background: rgba(37,211,102,0.05); }
  .btn-ig { border-color: rgba(228,64,95,0.4); color: #F472B6; background: rgba(228,64,95,0.05); }

  /* Footer */
  .footer-bar {
    position: relative;
    z-index: 1;
    margin: 0 40px 0;
    padding-top: 24px;
    border-top: 1px solid rgba(0,247,255,0.08);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .footer-quote {
    font-family: 'Fira Code', monospace;
    font-size: 12px;
    color: rgba(0,247,255,0.4);
  }

  .footer-logo {
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    font-weight: 800;
    letter-spacing: 2px;
    color: rgba(255,255,255,0.15);
  }

  /* Corner accent */
  .corner-accent {
    position: absolute;
    top: 0; right: 0;
    width: 200px; height: 200px;
    background: radial-gradient(circle at top right, rgba(139,92,246,0.15), transparent 60%);
    pointer-events: none;
    z-index: 0;
  }

  .corner-accent-2 {
    position: absolute;
    bottom: 0; left: 0;
    width: 300px; height: 200px;
    background: radial-gradient(circle at bottom left, rgba(0,247,255,0.08), transparent 60%);
    pointer-events: none;
    z-index: 0;
  }
</style>

<h2 class="sr-only">Omar Ashraf — Elite Full-Stack Developer GitHub Profile Card</h2>

<div class="profile-root">
  <div class="grid-bg"></div>
  <div class="corner-accent"></div>
  <div class="corner-accent-2"></div>

  <!-- Hero -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar-ring">
        <div class="avatar-inner">OA</div>
      </div>
      <div class="status-dot" title="Available for work"></div>
    </div>
    <div class="hero-info">
      <div class="hero-name">OMAR <span>ASHRAF</span></div>
      <div class="hero-title">Elite Full-Stack Developer · Egypt 🇪🇬</div>
      <div class="badges">
        <span class="badge badge-cyan">React</span>
        <span class="badge badge-cyan">Node.js</span>
        <span class="badge badge-purple">Laravel</span>
        <span class="badge badge-purple">PHP</span>
        <span class="badge badge-green">Open to Work</span>
      </div>
    </div>
  </div>

  <!-- Stats -->
  <div class="section">
    <div class="section-title">// github stats</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-num">47</div>
        <div class="stat-label">Repositories</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">312</div>
        <div class="stat-label">Contributions</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">28</div>
        <div class="stat-label">Stars Earned</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">14</div>
        <div class="stat-label">Followers</div>
      </div>
    </div>
  </div>

  <!-- Skills -->
  <div class="section">
    <div class="section-title">// tech mastery</div>
    <div class="skills-grid">
      <div class="skill-row">
        <div class="skill-top"><span class="skill-name">React / Next.js</span><span class="skill-pct">92%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:92%;background:linear-gradient(90deg,#00F7FF,#06B6D4)"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-top"><span class="skill-name">Node.js / Express</span><span class="skill-pct">88%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:88%;background:linear-gradient(90deg,#8B5CF6,#A78BFA)"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-top"><span class="skill-name">Laravel / PHP</span><span class="skill-pct">85%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:85%;background:linear-gradient(90deg,#EC4899,#F472B6)"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-top"><span class="skill-name">MySQL / APIs</span><span class="skill-pct">90%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:90%;background:linear-gradient(90deg,#22C55E,#4ADE80)"></div></div>
      </div>
    </div>
  </div>

  <!-- Featured Projects -->
  <div class="section">
    <div class="section-title">// featured builds</div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-tag">⚡ E-Commerce</div>
        <div class="project-name">ShopFlow Platform</div>
        <div class="project-desc">Full-stack e-commerce with cart, auth, payments & admin dashboard</div>
        <div class="project-tech">
          <span class="tech-chip">React</span>
          <span class="tech-chip">Node.js</span>
          <span class="tech-chip">MySQL</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-tag">🔐 Auth System</div>
        <div class="project-name">SecureAuth API</div>
        <div class="project-desc">JWT-based authentication with role management and refresh tokens</div>
        <div class="project-tech">
          <span class="tech-chip">Laravel</span>
          <span class="tech-chip">REST API</span>
          <span class="tech-chip">PHP</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-tag">📊 Dashboard</div>
        <div class="project-name">Admin Pro Suite</div>
        <div class="project-desc">Real-time analytics dashboard with charts, filters, and exports</div>
        <div class="project-tech">
          <span class="tech-chip">React</span>
          <span class="tech-chip">Tailwind</span>
          <span class="tech-chip">Express</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-tag">🌍 Production</div>
        <div class="project-name">Portfolio v2</div>
        <div class="project-desc">Personal portfolio deployed on Vercel — fast, responsive, animated</div>
        <div class="project-tech">
          <span class="tech-chip">Next.js</span>
          <span class="tech-chip">Vercel</span>
          <span class="tech-chip">Tailwind</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Connect -->
  <div class="section">
    <div class="section-title">// connect</div>
    <div class="connect-grid">
      <a class="connect-btn btn-portfolio" href="https://profileomar.vercel.app/" target="_blank">
        <i class="ti ti-globe" aria-hidden="true"></i> Portfolio
      </a>
      <a class="connect-btn btn-email" href="mailto:omarcreat33@gmail.com">
        <i class="ti ti-mail" aria-hidden="true"></i> Gmail
      </a>
      <a class="connect-btn btn-wa" href="https://wa.me/201012329975" target="_blank">
        <i class="ti ti-brand-whatsapp" aria-hidden="true"></i> WhatsApp
      </a>
      <a class="connect-btn btn-ig" href="https://www.instagram.com/tss_vvk/" target="_blank">
        <i class="ti ti-brand-instagram" aria-hidden="true"></i> Instagram
      </a>
    </div>
  </div>

  <!-- Footer -->
  <div class="footer-bar">
    <span class="footer-quote">// build · break · learn · repeat 🚀</span>
    <span class="footer-logo">OMAR ASHRAF</span>
  </div>
</div>
