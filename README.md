<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Sweekar Shetty — Developer Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #ffffff;
    --bg-secondary: #f5f5f3;
    --bg-info: #e6f1fb;
    --text-primary: #1a1a18;
    --text-secondary: #5f5e5a;
    --text-tertiary: #888780;
    --text-info: #185fa5;
    --border: rgba(0,0,0,0.1);
    --border-strong: rgba(0,0,0,0.18);
    --border-info: rgba(24,95,165,0.3);
    --radius-md: 8px;
    --radius-lg: 12px;
    --radius-xl: 16px;
  }

  @media (prefers-color-scheme: dark) {
    :root {
      --bg: #1c1c1a;
      --bg-secondary: #252523;
      --bg-info: #0c2e4a;
      --text-primary: #f0ede8;
      --text-secondary: #b4b2a9;
      --text-tertiary: #6e6d69;
      --text-info: #85b7eb;
      --border: rgba(255,255,255,0.09);
      --border-strong: rgba(255,255,255,0.16);
      --border-info: rgba(133,183,235,0.3);
    }
  }

  body {
    font-family: 'Syne', sans-serif;
    background: var(--bg);
    color: var(--text-primary);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    padding: 3rem 1.5rem;
  }

  .profile {
    width: 100%;
    max-width: 680px;
  }

  /* Header */
  .header {
    display: flex;
    align-items: flex-start;
    gap: 1.5rem;
    margin-bottom: 2.5rem;
  }

  .avatar {
    width: 72px;
    height: 72px;
    border-radius: 50%;
    background: var(--bg-secondary);
    border: 0.5px solid var(--border-strong);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    font-weight: 700;
    color: var(--text-secondary);
    flex-shrink: 0;
    letter-spacing: -1px;
  }

  .header-text h1 {
    font-size: 22px;
    font-weight: 500;
    color: var(--text-primary);
    line-height: 1.2;
    margin-bottom: 6px;
  }

  .header-text p {
    font-size: 14px;
    color: var(--text-secondary);
    line-height: 1.65;
    max-width: 460px;
  }

  .badge-row {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 12px;
  }

  .badge {
    font-size: 11px;
    font-weight: 500;
    padding: 3px 10px;
    border-radius: 20px;
    border: 0.5px solid var(--border-strong);
    color: var(--text-secondary);
    background: var(--bg-secondary);
    font-family: 'DM Mono', monospace;
    letter-spacing: 0.02em;
  }

  .badge.active {
    background: var(--bg-info);
    color: var(--text-info);
    border-color: var(--border-info);
  }

  /* Divider */
  .divider {
    height: 0.5px;
    background: var(--border);
    margin: 1.75rem 0;
  }

  /* Section label */
  .section-label {
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--text-tertiary);
    margin-bottom: 1rem;
    font-family: 'DM Mono', monospace;
  }

  /* Status grid */
  .status-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    margin-bottom: 0;
  }

  @media (max-width: 520px) {
    .status-grid { grid-template-columns: 1fr; }
  }

  .status-card {
    background: var(--bg-secondary);
    border-radius: var(--radius-md);
    padding: 0.875rem 1rem;
  }

  .status-card .label {
    font-size: 11px;
    color: var(--text-tertiary);
    margin-bottom: 5px;
    font-family: 'DM Mono', monospace;
    letter-spacing: 0.05em;
  }

  .status-card .value {
    font-size: 13px;
    font-weight: 500;
    color: var(--text-primary);
    line-height: 1.4;
  }

  .status-card .value a {
    color: var(--text-info);
    text-decoration: none;
  }

  .status-card .value a:hover {
    text-decoration: underline;
  }

  /* Tech chips */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tech-chip {
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 5px 11px;
    background: var(--bg);
    border: 0.5px solid var(--border);
    border-radius: var(--radius-md);
    font-size: 12px;
    color: var(--text-secondary);
    font-weight: 500;
    transition: border-color 0.15s, background 0.15s;
  }

  .tech-chip:hover {
    border-color: var(--border-strong);
    background: var(--bg-secondary);
  }

  .tech-chip img {
    width: 16px;
    height: 16px;
    object-fit: contain;
  }

  /* Links */
  .links-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .link-btn {
    display: flex;
    align-items: center;
    gap: 7px;
    padding: 7px 14px;
    border-radius: var(--radius-md);
    border: 0.5px solid var(--border-strong);
    background: transparent;
    font-size: 13px;
    font-weight: 500;
    color: var(--text-secondary);
    cursor: pointer;
    text-decoration: none;
    font-family: 'Syne', sans-serif;
    transition: background 0.15s, color 0.15s;
  }

  .link-btn:hover {
    background: var(--bg-secondary);
    color: var(--text-primary);
  }

  .link-btn svg {
    width: 14px;
    height: 14px;
    flex-shrink: 0;
    opacity: 0.65;
  }

  /* Stats */
  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }

  @media (max-width: 480px) {
    .stats-row { grid-template-columns: 1fr; }
  }

  .stat-card {
    background: var(--bg-secondary);
    border-radius: var(--radius-md);
    padding: 0.875rem;
    overflow: hidden;
  }

  .stat-card img {
    width: 100%;
    height: auto;
    border-radius: 4px;
    display: block;
  }

  /* Footer */
  .footer {
    margin-top: 2.5rem;
    font-size: 12px;
    color: var(--text-tertiary);
    font-family: 'DM Mono', monospace;
    text-align: center;
  }
</style>
</head>
<body>
<div class="profile">

  <div class="header">
    <div class="avatar">SS</div>
    <div class="header-text">
      <h1>Sweekar Shetty</h1>
      <p>Building skills in pixel art & game development. Sculpting the intersection of creative design and full-stack engineering.</p>
      <div class="badge-row">
        <span class="badge active">Open to work</span>
        <span class="badge">Mangaluru, IN</span>
        <span class="badge">Game Dev</span>
        <span class="badge">Pixel Art</span>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <div class="section-label">Currently</div>
  <div class="status-grid">
    <div class="status-card">
      <div class="label">Building</div>
      <div class="value"><a href="https://github.com/Sweekk/HireReady-AI.git" target="_blank">Hire-Ready AI</a></div>
    </div>
    <div class="status-card">
      <div class="label">Learning</div>
      <div class="value">Unity · MERN · Flutter</div>
    </div>
    <div class="status-card">
      <div class="label">Contact</div>
      <div class="value"><a href="mailto:sweekarshetty06@gmail.com">sweekarshetty06@gmail.com</a></div>
    </div>
  </div>

  <div class="divider"></div>

  <div class="section-label">Tech stack</div>
  <div class="tech-grid">
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" alt="C++"/>C++</div>
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/csharp/csharp-original.svg" alt="C#"/>C#</div>
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="TypeScript"/>TypeScript</div>
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="React"/>React</div>
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="Node.js"/>Node.js</div>
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original-wordmark.svg" alt="Express"/>Express</div>
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="MongoDB"/>MongoDB</div>
    <div class="tech-chip"><img src="https://www.vectorlogo.zone/logos/flutterio/flutterio-icon.svg" alt="Flutter"/>Flutter</div>
    <div class="tech-chip"><img src="https://www.vectorlogo.zone/logos/unity3d/unity3d-icon.svg" alt="Unity"/>Unity</div>
    <div class="tech-chip"><img src="https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg" alt="Tailwind"/>Tailwind</div>
    <div class="tech-chip"><img src="https://www.vectorlogo.zone/logos/firebase/firebase-icon.svg" alt="Firebase"/>Firebase</div>
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="Docker"/>Docker</div>
    <div class="tech-chip"><img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="Figma"/>Figma</div>
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="HTML5"/>HTML5</div>
    <div class="tech-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="CSS3"/>CSS3</div>
  </div>

  <div class="divider"></div>

  <div class="section-label">Connect</div>
  <div class="links-row">
    <a href="https://github.com/Sweekk" target="_blank" class="link-btn">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.477 2 12c0 4.418 2.865 8.166 6.839 9.489.5.092.682-.217.682-.482 0-.237-.009-.868-.013-1.703-2.782.604-3.369-1.34-3.369-1.34-.454-1.155-1.11-1.463-1.11-1.463-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.831.092-.646.35-1.086.636-1.336-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.029-2.683-.103-.253-.446-1.27.098-2.647 0 0 .84-.269 2.75 1.025A9.578 9.578 0 0112 6.836c.85.004 1.705.115 2.504.337 1.909-1.294 2.747-1.025 2.747-1.025.546 1.377.203 2.394.1 2.647.64.699 1.028 1.592 1.028 2.683 0 3.842-2.339 4.687-4.566 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.741 0 .267.18.578.688.48C19.138 20.163 22 16.418 22 12c0-5.523-4.477-10-10-10z"/></svg>
      GitHub
    </a>
    <a href="https://www.linkedin.com/in/sweekar-shetty-1a4255335/" target="_blank" class="link-btn">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
      LinkedIn
    </a>
    <a href="https://twitter.com/sweek06_" target="_blank" class="link-btn">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.742l7.722-8.817-8.152-10.683h7.052l4.26 5.632L18.243 2.25zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
      Twitter
    </a>
    <a href="https://www.hackerrank.com/sweekarshetty06" target="_blank" class="link-btn">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 0c1.285 0 9.75 4.886 10.392 6 .645 1.115.645 10.885 0 12S13.287 24 12 24s-9.75-4.886-10.392-6c-.645-1.115-.645-10.885 0-12C2.25 4.886 10.715 0 12 0zm2.295 6.799c-.141 0-.258.115-.258.258v3.875H9.963V7.057c0-.141-.115-.258-.258-.258h-1.3c-.141 0-.258.115-.258.258v9.886c0 .141.115.258.258.258h1.3c.141 0 .258-.115.258-.258v-3.875h4.074v3.875c0 .141.115.258.258.258h1.3c.141 0 .258-.115.258-.258V7.057c0-.141-.115-.258-.258-.258h-1.3z"/></svg>
      HackerRank
    </a>
    <a href="https://discord.gg/724484428834799627" target="_blank" class="link-btn">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.317 4.37a19.791 19.791 0 00-4.885-1.515.074.074 0 00-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 00-5.487 0 12.64 12.64 0 00-.617-1.25.077.077 0 00-.079-.037A19.736 19.736 0 003.677 4.37a.07.07 0 00-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 00.031.057 19.9 19.9 0 005.993 3.03.078.078 0 00.084-.028c.462-.63.874-1.295 1.226-1.994a.076.076 0 00-.041-.106 13.107 13.107 0 01-1.872-.892.077.077 0 01-.008-.128 10.2 10.2 0 00.372-.292.074.074 0 01.077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 01.078.01c.12.098.246.198.373.292a.077.077 0 01-.006.127 12.299 12.299 0 01-1.873.892.077.077 0 00-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 00.084.028 19.839 19.839 0 006.002-3.03.077.077 0 00.032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 00-.031-.03z"/></svg>
      Discord
    </a>
  </div>

  <div class="divider"></div>

  <div class="section-label">GitHub stats</div>
  <div class="stats-row">
    <div class="stat-card">
      <img src="https://github-readme-stats.vercel.app/api/top-langs?username=sweekk&show_icons=true&locale=en&layout=compact&hide_border=true&bg_color=00000000&title_color=888780&text_color=5f5e5a" alt="Top languages"/>
    </div>
    <div class="stat-card">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=sweekk&hide_border=true&background=00000000&currStreakLabel=888780&sideLabels=888780&dates=888780&fire=E24B4A&ring=378ADD&currStreakNum=1a1a18&sideNums=1a1a18" alt="GitHub streak"/>
    </div>
  </div>

  <div class="footer">sweekarshetty06@gmail.com · github.com/Sweekk</div>

</div>
</body>
</html>
