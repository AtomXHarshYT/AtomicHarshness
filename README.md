
<style>
  @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600&family=Inter:wght@400;500;600&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body { background: transparent; }

  .readme {
    font-family: 'Inter', sans-serif;
    color: var(--color-text-primary);
    max-width: 860px;
    margin: 0 auto;
    padding: 0 0 40px;
  }

  /* ── Hero ── */
  .hero {
    position: relative;
    text-align: center;
    padding: 48px 24px 36px;
    overflow: hidden;
  }
  .hero-grid {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(var(--color-border-tertiary) 1px, transparent 1px),
      linear-gradient(90deg, var(--color-border-tertiary) 1px, transparent 1px);
    background-size: 40px 40px;
    animation: gridPan 20s linear infinite;
    opacity: 0.4;
  }
  @keyframes gridPan { from { background-position: 0 0; } to { background-position: 40px 40px; } }

  .hero-glow {
    position: absolute;
    top: -60px; left: 50%; transform: translateX(-50%);
    width: 400px; height: 220px;
    background: radial-gradient(ellipse, rgba(0,247,255,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .avatar-ring {
    position: relative;
    display: inline-block;
    margin-bottom: 20px;
  }
  .avatar-svg {
    display: block;
    animation: rotateSlow 12s linear infinite;
  }
  @keyframes rotateSlow { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
  .avatar-inner {
    position: absolute;
    inset: 12px;
    border-radius: 50%;
    background: linear-gradient(135deg, #0a1628, #0f2040);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Fira Code', monospace;
    font-size: 28px;
    font-weight: 600;
    color: #00f7ff;
    letter-spacing: 1px;
    text-shadow: 0 0 20px rgba(0,247,255,0.5);
  }

  .hero-name {
    font-size: 36px;
    font-weight: 600;
    letter-spacing: -0.5px;
    color: var(--color-text-primary);
    margin-bottom: 4px;
    position: relative;
  }
  .hero-wave {
    display: inline-block;
    animation: wave 2s ease-in-out infinite;
    transform-origin: 70% 80%;
  }
  @keyframes wave {
    0%,100% { transform: rotate(0deg); }
    20% { transform: rotate(20deg); }
    40% { transform: rotate(-10deg); }
    60% { transform: rotate(20deg); }
    80% { transform: rotate(-5deg); }
  }

  .typing-container {
    font-family: 'Fira Code', monospace;
    font-size: 14px;
    color: #00f7ff;
    margin: 12px auto;
    height: 22px;
    overflow: hidden;
  }
  .typing-text { display: inline-block; border-right: 2px solid #00f7ff; padding-right: 3px; animation: blink 0.8s step-end infinite; white-space: nowrap; }
  @keyframes blink { 50% { border-color: transparent; } }

  .hero-pills {
    display: flex; flex-wrap: wrap; justify-content: center; gap: 8px;
    margin-top: 16px; position: relative;
  }
  .pill {
    font-size: 12px;
    font-weight: 500;
    padding: 5px 14px;
    border-radius: 20px;
    border: 0.5px solid;
    letter-spacing: 0.3px;
    animation: fadeSlideUp 0.6s ease both;
  }
  .pill-cyan { background: rgba(0,247,255,0.08); border-color: rgba(0,247,255,0.3); color: #00d4db; }
  .pill-purple { background: rgba(122,79,221,0.1); border-color: rgba(122,79,221,0.35); color: #a48be8; }
  .pill-green { background: rgba(39,200,100,0.08); border-color: rgba(39,200,100,0.3); color: #3dcf74; }
  .pill-orange { background: rgba(255,111,0,0.1); border-color: rgba(255,111,0,0.3); color: #ff9240; }
  @keyframes fadeSlideUp { from { opacity:0; transform:translateY(12px); } to { opacity:1; transform:translateY(0); } }
  .pill:nth-child(1){animation-delay:.1s} .pill:nth-child(2){animation-delay:.2s}
  .pill:nth-child(3){animation-delay:.3s} .pill:nth-child(4){animation-delay:.4s}

  /* ── Sections ── */
  .section { padding: 32px 24px 0; }
  .section-label {
    display: flex; align-items: center; gap: 10px;
    font-size: 11px; font-weight: 600; text-transform: uppercase;
    letter-spacing: 1.5px; color: var(--color-text-tertiary);
    margin-bottom: 20px;
  }
  .section-label::before, .section-label::after {
    content: ''; flex: 1; height: 0.5px;
    background: var(--color-border-tertiary);
  }

  /* ── What I do cards ── */
  .do-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 12px; }
  .do-card {
    background: var(--color-background-primary);
    border: 0.5px solid var(--color-border-tertiary);
    border-radius: var(--border-radius-lg);
    padding: 16px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s, transform 0.2s;
    cursor: default;
  }
  .do-card:hover { border-color: var(--color-border-secondary); transform: translateY(-2px); }
  .do-card-accent {
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    border-radius: 12px 12px 0 0;
  }
  .accent-cyan { background: linear-gradient(90deg, #00f7ff, #00a8b5); }
  .accent-purple { background: linear-gradient(90deg, #7a4fdd, #a78ee8); }
  .accent-green { background: linear-gradient(90deg, #27c864, #82e0a0); }
  .do-card-icon { font-size: 22px; margin-bottom: 8px; }
  .do-card-title { font-size: 13px; font-weight: 600; margin-bottom: 4px; color: var(--color-text-primary); }
  .do-card-desc { font-size: 12px; color: var(--color-text-secondary); line-height: 1.6; }

  /* ── Tech badges ── */
  .tech-grid { display: flex; flex-wrap: wrap; gap: 8px; }
  .tech-badge {
    display: flex; align-items: center; gap: 6px;
    padding: 6px 12px;
    border-radius: var(--border-radius-md);
    border: 0.5px solid var(--color-border-tertiary);
    background: var(--color-background-primary);
    font-size: 12px; font-weight: 500;
    color: var(--color-text-primary);
    transition: border-color 0.2s, transform 0.15s;
    cursor: default;
    animation: fadeSlideUp 0.5s ease both;
  }
  .tech-badge:hover { border-color: var(--color-border-primary); transform: translateY(-1px); }
  .tech-dot { width: 7px; height: 7px; border-radius: 50%; flex-shrink: 0; }

  /* ── Building section ── */
  .build-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 10px; }
  .build-item {
    display: flex; align-items: center; gap: 10px;
    background: var(--color-background-secondary);
    border-radius: var(--border-radius-md);
    padding: 12px 14px;
    font-size: 13px;
    font-weight: 500;
    color: var(--color-text-primary);
    border: 0.5px solid var(--color-border-tertiary);
    transition: background 0.2s;
  }
  .build-item:hover { background: var(--color-background-primary); }
  .build-icon {
    width: 28px; height: 28px; border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 14px; flex-shrink: 0;
  }

  /* ── Stats block ── */
  .stats-block {
    background: var(--color-background-secondary);
    border: 0.5px solid var(--color-border-tertiary);
    border-radius: var(--border-radius-lg);
    padding: 20px;
    text-align: center;
  }
  .stats-block img { max-width: 100%; border-radius: var(--border-radius-md); }
  .stats-row { display: flex; flex-wrap: wrap; gap: 12px; justify-content: center; margin-top: 12px; }

  /* ── Connect ── */
  .connect-row { display: flex; flex-wrap: wrap; gap: 10px; }
  .connect-btn {
    display: flex; align-items: center; gap: 8px;
    padding: 10px 18px;
    border-radius: var(--border-radius-md);
    border: 0.5px solid var(--color-border-secondary);
    background: var(--color-background-primary);
    font-size: 13px; font-weight: 500;
    color: var(--color-text-primary);
    text-decoration: none;
    transition: border-color 0.2s, background 0.2s, transform 0.15s;
    cursor: pointer;
  }
  .connect-btn:hover { background: var(--color-background-secondary); border-color: var(--color-border-primary); transform: translateY(-1px); }
  .connect-btn svg { width: 16px; height: 16px; flex-shrink: 0; }

  /* ── Footer ── */
  .footer {
    margin-top: 40px;
    padding: 24px;
    position: relative;
    text-align: center;
    overflow: hidden;
  }
  .footer-wave {
    width: 100%; height: 60px;
    fill: none;
  }
  .footer-wave path { stroke: #00f7ff; stroke-width: 1.5; fill: none; opacity: 0.3; }
  .footer-text { font-size: 11px; color: var(--color-text-tertiary); margin-top: 8px; font-family: 'Fira Code', monospace; }

  /* ── Scroll reveal ── */
  .reveal { opacity: 0; transform: translateY(18px); transition: opacity 0.5s ease, transform 0.5s ease; }
  .reveal.visible { opacity: 1; transform: none; }
</style>

<div class="readme">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-grid"></div>
    <div class="hero-glow"></div>

    <div class="avatar-ring">
      <svg class="avatar-svg" width="100" height="100" viewBox="0 0 100 100">
        <circle cx="50" cy="50" r="44" fill="none" stroke="rgba(0,247,255,0.15)" stroke-width="1"/>
        <circle cx="50" cy="50" r="44" fill="none" stroke="#00f7ff" stroke-width="1.5"
          stroke-dasharray="8 6" stroke-linecap="round"/>
        <circle cx="50" cy="6" r="3" fill="#00f7ff" opacity="0.8"/>
        <circle cx="94" cy="50" r="2" fill="#00f7ff" opacity="0.5"/>
      </svg>
      <div class="avatar-inner">H</div>
    </div>

    <h1 class="hero-name">Hi, I'm Harsh <span class="hero-wave">👋</span></h1>

    <div class="typing-container">
      <span class="typing-text" id="typingText"></span>
    </div>

    <div class="hero-pills">
      <span class="pill pill-cyan">Python · FastAPI · APIs</span>
      <span class="pill pill-purple">AI-Assisted Coder</span>
      <span class="pill pill-green">Backend Developer</span>
      <span class="pill pill-orange">India 📍</span>
    </div>
  </div>

  <!-- WHAT I DO -->
  <div class="section reveal">
    <div class="section-label">What I actually do</div>
    <div class="do-grid">
      <div class="do-card">
        <div class="do-card-accent accent-cyan"></div>
        <div class="do-card-icon">⚙️</div>
        <div class="do-card-title">Backend Logic</div>
        <div class="do-card-desc">APIs, databases, authentication, and workflows — that's my core.</div>
      </div>
      <div class="do-card">
        <div class="do-card-accent accent-purple"></div>
        <div class="do-card-icon">🤖</div>
        <div class="do-card-title">AI as My Coding Partner</div>
        <div class="do-card-desc">Frontend stuff, complex snippets, or learning new things — I use AI tools.</div>
      </div>
      <div class="do-card">
        <div class="do-card-accent accent-green"></div>
        <div class="do-card-icon">🚀</div>
        <div class="do-card-title">Ship Faster</div>
        <div class="do-card-desc">Build things faster without pretending to know everything.</div>
      </div>
    </div>
  </div>

  <!-- TECH -->
  <div class="section reveal">
    <div class="section-label">Tech I work with</div>
    <div class="tech-grid" id="techGrid"></div>
    <p style="margin-top:10px; font-size:11px; color:var(--color-text-tertiary); font-style:italic;">
      HTML/CSS? I can tweak it. For serious frontend, AI helps me — no shame in that.
    </p>
  </div>

  <!-- BUILDING -->
  <div class="section reveal">
    <div class="section-label">What I'm building</div>
    <div class="build-grid">
      <div class="build-item">
        <div class="build-icon" style="background:rgba(0,247,255,0.1); color:#00c8d4;">🏗️</div>
        Backend APIs
      </div>
      <div class="build-item">
        <div class="build-icon" style="background:rgba(122,79,221,0.1); color:#a48be8;">⚙️</div>
        Automation Workflows
      </div>
      <div class="build-item">
        <div class="build-icon" style="background:rgba(39,200,100,0.1); color:#3dcf74;">📊</div>
        Dashboards
      </div>
      <div class="build-item">
        <div class="build-icon" style="background:rgba(255,111,0,0.1); color:#ff9240;">📈</div>
        Trading Signal Logic
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section reveal">
    <div class="section-label">GitHub stats</div>
    <div class="stats-block">
      <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=AtomXHarshYT&theme=tokyonight" alt="Profile details" />
      <div class="stats-row">
        <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=AtomXHarshYT&theme=tokyonight" alt="Stats" style="height:120px;" />
        <img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=AtomXHarshYT&theme=tokyonight&utcOffset=5.5" alt="Productive time" style="height:120px;" />
        <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=AtomXHarshYT&theme=tokyonight" alt="Repos per language" style="height:120px;" />
        <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=AtomXHarshYT&theme=tokyonight" alt="Most commit language" style="height:120px;" />
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section reveal">
    <div class="section-label">Connect</div>
    <div class="connect-row">
      <a class="connect-btn" href="mailto:harshgaming0958@gmail.com">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
        harshgaming0958@gmail.com
      </a>
      <a class="connect-btn" href="https://github.com/AtomXHarshYT">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0 1 12 6.844a9.59 9.59 0 0 1 2.504.337c1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.02 10.02 0 0 0 22 12.017C22 6.484 17.522 2 12 2z"/></svg>
        AtomXHarshYT
      </a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <svg class="footer-wave" viewBox="0 0 860 60" preserveAspectRatio="none">
      <path d="M0,30 C120,55 200,5 320,30 S500,55 640,30 S780,5 860,30" />
      <path d="M0,40 C100,20 220,55 360,35 S520,10 660,40 S780,55 860,30" opacity="0.4"/>
    </svg>
    <p class="footer-text">// built with logic + ai assistance · india 🇮🇳</p>
  </div>

</div>

<script>
const phrases = [
  'Backend Developer',
  'Problem Solver',
  'AI-Assisted Coder',
  'Building Real Things'
];
let pi = 0, ci = 0, deleting = false;
const el = document.getElementById('typingText');
function type() {
  const phrase = phrases[pi];
  if (!deleting) {
    el.textContent = phrase.slice(0, ++ci);
    if (ci === phrase.length) { deleting = true; setTimeout(type, 1800); return; }
  } else {
    el.textContent = phrase.slice(0, --ci);
    if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; setTimeout(type, 400); return; }
  }
  setTimeout(type, deleting ? 55 : 85);
}
type();

const techs = [
  { name: 'Python', dot: '#3776AB' },
  { name: 'FastAPI', dot: '#009688' },
  { name: 'APIs', dot: '#FF6F00' },
  { name: 'Automation', dot: '#9C27B0' },
  { name: 'Firebase', dot: '#FFCA28' },
  { name: 'Supabase', dot: '#3ECF8E' },
  { name: 'HTML / CSS', dot: '#E34F26' },
  { name: 'AI Coding', dot: '#00F7FF' },
];
const grid = document.getElementById('techGrid');
techs.forEach((t, i) => {
  const b = document.createElement('div');
  b.className = 'tech-badge';
  b.style.animationDelay = (i * 0.07) + 's';
  b.innerHTML = `<span class="tech-dot" style="background:${t.dot}"></span>${t.name}`;
  grid.appendChild(b);
});

const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
}, { threshold: 0.1 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
