<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Subhajit Sahu — Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@300;400;600&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080c10;
    --bg2: #0d1117;
    --bg3: #111820;
    --border: #1e2d3d;
    --accent: #00d4ff;
    --accent2: #7c3aed;
    --accent3: #10b981;
    --text: #c9d1d9;
    --text-dim: #6e7681;
    --text-bright: #f0f6fc;
    --glow: rgba(0, 212, 255, 0.15);
    --glow2: rgba(124, 58, 237, 0.12);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
    position: relative;
  }

  /* Animated background grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  /* Radial glow effects */
  body::after {
    content: '';
    position: fixed;
    top: -200px; left: -200px;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(124,58,237,0.08) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
    animation: driftGlow 12s ease-in-out infinite alternate;
  }

  @keyframes driftGlow {
    from { transform: translate(0, 0); }
    to   { transform: translate(80px, 60px); }
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ---- HERO ---- */
  .hero {
    border: 1px solid var(--border);
    background: linear-gradient(135deg, #0d1117 0%, #111820 50%, #0a0f16 100%);
    border-radius: 16px;
    padding: 48px 40px 40px;
    margin-bottom: 28px;
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent), var(--accent2), transparent);
    animation: scanline 4s linear infinite;
  }

  @keyframes scanline {
    0%   { opacity: 0.4; }
    50%  { opacity: 1; }
    100% { opacity: 0.4; }
  }

  .hero-corner {
    position: absolute;
    top: 16px; right: 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--text-dim);
    letter-spacing: 2px;
    opacity: 0.6;
  }

  .name-block {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 10px;
  }

  .status-dot {
    width: 10px; height: 10px;
    border-radius: 50%;
    background: var(--accent3);
    box-shadow: 0 0 8px var(--accent3), 0 0 20px rgba(16,185,129,0.4);
    animation: pulse 2s ease-in-out infinite;
    flex-shrink: 0;
  }

  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 8px var(--accent3), 0 0 20px rgba(16,185,129,0.4); }
    50%       { box-shadow: 0 0 14px var(--accent3), 0 0 35px rgba(16,185,129,0.6); }
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(28px, 5vw, 44px);
    font-weight: 800;
    color: var(--text-bright);
    letter-spacing: -1px;
    line-height: 1;
  }

  h1 span {
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .tagline {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--accent);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 28px;
    opacity: 0.8;
  }

  .about-list {
    list-style: none;
    display: grid;
    gap: 10px;
  }

  .about-list li {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    font-size: 14.5px;
    color: var(--text);
    line-height: 1.5;
  }

  .about-list li .icon {
    font-size: 16px;
    flex-shrink: 0;
    margin-top: 1px;
  }

  /* ---- SECTION HEADING ---- */
  .section-heading {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 20px;
    margin-top: 36px;
  }

  .section-heading::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  .section-heading h2 {
    font-family: 'Syne', sans-serif;
    font-size: 16px;
    font-weight: 700;
    color: var(--text-bright);
    letter-spacing: 2px;
    text-transform: uppercase;
    white-space: nowrap;
  }

  .section-heading .icon {
    font-size: 18px;
  }

  /* ---- SOCIALS ---- */
  .socials-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .social-pill {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    border-radius: 8px;
    border: 1px solid var(--border);
    background: var(--bg2);
    text-decoration: none;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    font-weight: 600;
    color: var(--text);
    letter-spacing: 0.5px;
    transition: all 0.25s ease;
    position: relative;
    overflow: hidden;
  }

  .social-pill:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(0,212,255,0.05);
    box-shadow: 0 0 16px rgba(0,212,255,0.1), inset 0 0 16px rgba(0,212,255,0.03);
    transform: translateY(-2px);
  }

  /* ---- TECH STACK ---- */
  .tech-section {
    border: 1px solid var(--border);
    border-radius: 16px;
    background: var(--bg2);
    padding: 28px;
    position: relative;
    overflow: hidden;
  }

  .tech-section::before {
    content: '';
    position: absolute;
    bottom: 0; right: 0;
    width: 300px; height: 300px;
    background: radial-gradient(circle, rgba(0,212,255,0.04) 0%, transparent 70%);
    pointer-events: none;
  }

  .tech-category {
    margin-bottom: 24px;
  }

  .tech-category:last-child { margin-bottom: 0; }

  .tech-cat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--text-dim);
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .tech-cat-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 12px;
    border-radius: 6px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11.5px;
    font-weight: 600;
    color: #fff;
    border: 1px solid transparent;
    transition: all 0.2s ease;
    cursor: default;
    letter-spacing: 0.3px;
  }

  .badge:hover {
    transform: translateY(-2px) scale(1.04);
    filter: brightness(1.15);
    box-shadow: 0 4px 16px rgba(0,0,0,0.4);
  }

  /* Badge colors by category */
  .badge.lang   { background: #0d1b2e; border-color: #1e3a5f; color: #7dd3fc; }
  .badge.fe     { background: #0d1a22; border-color: #1a3344; color: #38bdf8; }
  .badge.be     { background: #0d1f14; border-color: #1a3d24; color: #4ade80; }
  .badge.db     { background: #1a1207; border-color: #3d2d0e; color: #fbbf24; }
  .badge.devops { background: #150d22; border-color: #2e1d44; color: #c084fc; }
  .badge.tools  { background: #1a0f10; border-color: #3d1d1e; color: #f87171; }
  .badge.design { background: #1a0f18; border-color: #3d1d37; color: #f0abfc; }

  /* ---- GITHUB STATS ---- */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  @media(max-width: 600px) {
    .stats-grid { grid-template-columns: 1fr; }
  }

  .stats-card {
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    background: var(--bg2);
    transition: border-color 0.3s ease;
  }

  .stats-card:hover { border-color: var(--accent); }

  .stats-card.full { grid-column: 1 / -1; }

  .stats-card img {
    width: 100%;
    display: block;
    border-radius: 12px;
  }

  /* ---- TROPHIES ---- */
  .trophies-card {
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    background: var(--bg2);
    transition: border-color 0.3s ease;
  }

  .trophies-card:hover { border-color: var(--accent2); }

  .trophies-card img {
    width: 100%;
    display: block;
  }

  /* ---- VISITOR COUNTER ---- */
  .footer-bar {
    margin-top: 36px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    padding-top: 24px;
    border-top: 1px solid var(--border);
  }

  .visitor-badge img { border-radius: 4px; }

  .footer-note {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--text-dim);
    letter-spacing: 1px;
  }

  /* ---- HACKATHON BADGE ---- */
  .hackathon-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 6px 14px;
    border-radius: 20px;
    background: linear-gradient(135deg, rgba(124,58,237,0.2), rgba(0,212,255,0.1));
    border: 1px solid rgba(124,58,237,0.4);
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #c4b5fd;
    letter-spacing: 1px;
    margin-top: 16px;
  }

  .hackathon-badge .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: #a78bfa;
    box-shadow: 0 0 6px #a78bfa;
  }

  /* ---- FADE-IN ANIMATIONS ---- */
  .fade-in {
    opacity: 0;
    transform: translateY(16px);
    animation: fadeUp 0.6s ease forwards;
  }

  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }

  .fade-in:nth-child(1)  { animation-delay: 0.05s; }
  .fade-in:nth-child(2)  { animation-delay: 0.12s; }
  .fade-in:nth-child(3)  { animation-delay: 0.19s; }
  .fade-in:nth-child(4)  { animation-delay: 0.26s; }
  .fade-in:nth-child(5)  { animation-delay: 0.33s; }

  /* ---- COPY README BUTTON ---- */
  .copy-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 20px;
    border-radius: 8px;
    background: linear-gradient(135deg, var(--accent2), var(--accent));
    border: none;
    color: #fff;
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    font-weight: 700;
    cursor: pointer;
    letter-spacing: 1px;
    transition: all 0.25s ease;
    box-shadow: 0 4px 20px rgba(0,212,255,0.2);
  }

  .copy-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 28px rgba(0,212,255,0.35);
  }

  .copy-btn:active { transform: translateY(0); }

  pre#readme-src {
    display: none;
  }
</style>
</head>
<body>
<div class="container">

  <!-- HERO CARD -->
  <div class="hero fade-in">
    <div class="hero-corner">README.md</div>
    <div class="name-block">
      <div class="status-dot"></div>
      <h1>Subhajit <span>Sahu</span></h1>
    </div>
    <p class="tagline">Full Stack Engineer · AI Builder · OSS Contributor</p>

    <ul class="about-list">
      <li><span class="icon">💻</span> Full Stack Developer passionate about building scalable, production-ready web applications</li>
      <li><span class="icon">🚀</span> <strong>Smart India Hackathon Finalist</strong> — developed AI-powered solutions under national-level competition</li>
      <li><span class="icon">⚛️</span> Proficient in React, Node.js, Express, MongoDB, and modern JavaScript ecosystem</li>
      <li><span class="icon">🧠</span> Strong DSA foundation in C++ — consistent problem solver on competitive platforms</li>
      <li><span class="icon">🌐</span> Experienced designing RESTful APIs and deploying full-stack systems to cloud platforms</li>
      <li><span class="icon">🎯</span> Obsessed with clean, efficient, maintainable code and SOLID principles</li>
      <li><span class="icon">📚</span> Perpetual learner — currently exploring DevOps, system design & distributed systems</li>
      <li><span class="icon">🤝</span> Open to internships, collaborations & software engineering opportunities</li>
    </ul>

    <div class="hackathon-badge">
      <div class="dot"></div>
      🏆 SIH Finalist &nbsp;·&nbsp; AI Solutions &nbsp;·&nbsp; National Recognition
    </div>
  </div>

  <!-- SOCIALS -->
  <div class="fade-in">
    <div class="section-heading">
      <span class="icon">🌐</span>
      <h2>Connect</h2>
    </div>
    <div class="socials-grid">
      <a href="https://www.instagram.com/_subhajit.10" target="_blank" class="social-pill">
        📸 Instagram
      </a>
      <a href="https://www.linkedin.com/in/subhajitsahu/" target="_blank" class="social-pill">
        💼 LinkedIn
      </a>
      <a href="https://stackoverflow.com/users/22867333" target="_blank" class="social-pill">
        📚 Stack Overflow
      </a>
      <a href="https://mastodon.social/@SubhajitSahu" target="_blank" class="social-pill">
        🐘 Mastodon
      </a>
      <a href="mailto:subhajitsahu133@gmail.com" class="social-pill">
        ✉️ subhajitsahu133@gmail.com
      </a>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="fade-in">
    <div class="section-heading">
      <span class="icon">💻</span>
      <h2>Tech Stack</h2>
    </div>
    <div class="tech-section">

      <div class="tech-category">
        <div class="tech-cat-label">Languages</div>
        <div class="badges">
          <span class="badge lang">C</span>
          <span class="badge lang">C++</span>
          <span class="badge lang">Java</span>
          <span class="badge lang">JavaScript</span>
          <span class="badge lang">HTML5</span>
          <span class="badge lang">CSS3</span>
          <span class="badge lang">LaTeX</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-cat-label">Frontend</div>
        <div class="badges">
          <span class="badge fe">React</span>
          <span class="badge fe">React Native</span>
          <span class="badge fe">Next.js</span>
          <span class="badge fe">Angular</span>
          <span class="badge fe">Redux</span>
          <span class="badge fe">TailwindCSS</span>
          <span class="badge fe">Bootstrap</span>
          <span class="badge fe">SASS</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-cat-label">Backend &amp; APIs</div>
        <div class="badges">
          <span class="badge be">Node.js</span>
          <span class="badge be">Express.js</span>
          <span class="badge be">JWT</span>
          <span class="badge be">REST APIs</span>
          <span class="badge be">Apache</span>
          <span class="badge be">Nginx</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-cat-label">Databases &amp; Cloud</div>
        <div class="badges">
          <span class="badge db">MongoDB</span>
          <span class="badge db">MySQL</span>
          <span class="badge db">Firebase</span>
          <span class="badge db">Appwrite</span>
          <span class="badge db">Oracle</span>
          <span class="badge db">AWS</span>
          <span class="badge db">Vercel</span>
          <span class="badge db">Render</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-cat-label">DevOps &amp; Testing</div>
        <div class="badges">
          <span class="badge devops">Docker</span>
          <span class="badge devops">Kubernetes</span>
          <span class="badge devops">Git</span>
          <span class="badge devops">GitHub</span>
          <span class="badge devops">GitLab</span>
          <span class="badge devops">Jest</span>
          <span class="badge devops">Postman</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-cat-label">Design &amp; Analytics</div>
        <div class="badges">
          <span class="badge design">Figma</span>
          <span class="badge design">Canva</span>
          <span class="badge design">Blender</span>
          <span class="badge design">Adobe</span>
          <span class="badge design">Power BI</span>
        </div>
      </div>

    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="fade-in">
    <div class="section-heading">
      <span class="icon">📊</span>
      <h2>GitHub Stats</h2>
    </div>
    <div class="stats-grid">
      <div class="stats-card">
        <img src="https://github-readme-stats.vercel.app/api?username=Subhajit-sahu&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true&bg_color=0d1117&title_color=00d4ff&text_color=c9d1d9&icon_color=7c3aed&border_radius=12" alt="GitHub Stats" loading="lazy"/>
      </div>
      <div class="stats-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Subhajit-sahu&theme=tokyonight&hide_border=true&layout=compact&bg_color=0d1117&title_color=00d4ff&text_color=c9d1d9&border_radius=12" alt="Top Languages" loading="lazy"/>
      </div>
      <div class="stats-card full">
        <img src="https://nirzak-streak-stats.vercel.app/?user=Subhajit-sahu&theme=tokyonight&hide_border=true&background=0d1117&ring=00d4ff&fire=7c3aed&currStreakLabel=00d4ff&border_radius=12" alt="GitHub Streak" loading="lazy"/>
      </div>
    </div>
  </div>

  <!-- TROPHIES -->
  <div class="fade-in">
    <div class="section-heading">
      <span class="icon">🏆</span>
      <h2>GitHub Trophies</h2>
    </div>
    <div class="trophies-card">
      <img src="https://github-profile-trophy.vercel.app/?username=Subhajit-sahu&theme=tokyonight&no-frame=true&no-bg=true&margin-w=4&column=7" alt="GitHub Trophies" loading="lazy"/>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer-bar fade-in">
    <a href="https://visitcount.itsvg.in" target="_blank" class="visitor-badge">
      <img src="https://visitcount.itsvg.in/api?id=Subhajit-sahu&icon=6&color=9&label=Profile%20Views" alt="Profile Views"/>
    </a>
    <span class="footer-note">// crafted with ♥ &amp; coffee</span>
  </div>

</div>

<!-- Hidden raw README for copy -->
<pre id="readme-src">
# 💫 About Me

&lt;div align="center"&gt;

![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=22&pause=1000&color=00D4FF&center=true&width=500&lines=Full+Stack+Developer;SIH+Hackathon+Finalist;React+%7C+Node+%7C+MongoDB;Always+learning+%F0%9F%9A%80)

&lt;/div&gt;

🚀 **Smart India Hackathon Finalist** — AI-powered solutions builder  
💻 Full Stack Developer passionate about scalable, real-world web apps  
⚛️ React · Node.js · Express · MongoDB · modern JavaScript  
🧠 Strong DSA foundation in C++ — competitive problem solver  
🌐 REST API design &amp; cloud deployment (AWS · Vercel · Render)  
🎯 Clean, efficient, maintainable code with SOLID principles  
📚 Currently exploring DevOps, system design &amp; distributed systems  
🤝 Open to internships, collaborations &amp; SWE opportunities  

---

## 🌐 Socials

[![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&amp;logoColor=white)](https://www.instagram.com/_subhajit.10)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&amp;logoColor=white)](https://www.linkedin.com/in/subhajitsahu/)
[![Stack Overflow](https://img.shields.io/badge/-Stackoverflow-FE7A16?logo=stack-overflow&amp;logoColor=white)](https://stackoverflow.com/users/22867333)
[![Email](https://img.shields.io/badge/Email-D14836?logo=gmail&amp;logoColor=white)](mailto:subhajitsahu133@gmail.com)

---

## 💻 Tech Stack

**Languages**  
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&amp;logo=c&amp;logoColor=white)
![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&amp;logo=c%2B%2B&amp;logoColor=white)
![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&amp;logo=openjdk&amp;logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&amp;logo=javascript&amp;logoColor=%23F7DF1E)

**Frontend**  
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&amp;logo=react&amp;logoColor=%2361DAFB)
![Next JS](https://img.shields.io/badge/Next-black?style=for-the-badge&amp;logo=next.js&amp;logoColor=white)
![Angular](https://img.shields.io/badge/angular-%23DD0031.svg?style=for-the-badge&amp;logo=angular&amp;logoColor=white)
![Redux](https://img.shields.io/badge/redux-%23593d88.svg?style=for-the-badge&amp;logo=redux&amp;logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&amp;logo=tailwind-css&amp;logoColor=white)

**Backend**  
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&amp;logo=node.js&amp;logoColor=white)
![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&amp;logo=express&amp;logoColor=%2361DAFB)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&amp;logo=JSON%20web%20tokens)

**Databases &amp; Cloud**  
![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&amp;logo=mongodb&amp;logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&amp;logo=mysql&amp;logoColor=white)
![Firebase](https://img.shields.io/badge/firebase-a08021?style=for-the-badge&amp;logo=firebase&amp;logoColor=ffcd34)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&amp;logo=amazon-aws&amp;logoColor=white)

**DevOps**  
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&amp;logo=docker&amp;logoColor=white)
![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&amp;logo=kubernetes&amp;logoColor=white)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&amp;logo=git&amp;logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&amp;logo=github&amp;logoColor=white)

---

## 📊 GitHub Stats

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=Subhajit-sahu&amp;theme=tokyonight&amp;hide_border=true&amp;include_all_commits=true&amp;count_private=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=Subhajit-sahu&amp;theme=tokyonight&amp;hide_border=true&amp;layout=compact)

![GitHub Streak](https://nirzak-streak-stats.vercel.app/?user=Subhajit-sahu&amp;theme=tokyonight&amp;hide_border=true)

## 🏆 Trophies

![Trophies](https://github-profile-trophy.vercel.app/?username=Subhajit-sahu&amp;theme=tokyonight&amp;no-frame=true&amp;margin-w=4)

---

[![Profile Views](https://visitcount.itsvg.in/api?id=Subhajit-sahu&amp;icon=6&amp;color=9)](https://visitcount.itsvg.in)
</pre>

<script>
  // Smooth entrance for grid rows
  const cards = document.querySelectorAll('.stats-card, .trophies-card, .tech-section');
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if(e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  cards.forEach(c => {
    c.style.opacity = '0';
    c.style.transform = 'translateY(20px)';
    c.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    obs.observe(c);
  });

  // Badge hover sound effect (visual only)
  document.querySelectorAll('.badge').forEach(b => {
    b.addEventListener('mouseenter', () => {
      b.style.transition = 'all 0.15s cubic-bezier(0.175, 0.885, 0.32, 1.275)';
    });
  });
</script>
</body>
</html>
