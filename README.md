<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --flutter-blue: #54C5F8;
    --dart-teal: #00B4AB;
    --firebase-amber: #FFCA28;
    --bg-deep: #0D1117;
    --bg-card: #161B22;
    --bg-card2: #1C2128;
    --border-subtle: rgba(255,255,255,0.08);
    --text-primary: #E6EDF3;
    --text-secondary: #8B949E;
    --text-muted: #484F58;
    --accent: #54C5F8;
    --green: #39D353;
    --purple: #A371F7;
  }

  .profile-root {
    font-family: 'Syne', sans-serif;
    background: var(--bg-deep);
    color: var(--text-primary);
    padding: 2rem 1.5rem;
    min-height: 600px;
  }

  .header {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    margin-bottom: 2rem;
    padding-bottom: 1.5rem;
    border-bottom: 0.5px solid var(--border-subtle);
  }

  .avatar {
    width: 72px;
    height: 72px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--flutter-blue), var(--dart-teal));
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 28px;
    font-weight: 800;
    color: #0D1117;
    flex-shrink: 0;
    position: relative;
  }

  .avatar::after {
    content: '';
    position: absolute;
    inset: -3px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--flutter-blue), var(--purple));
    z-index: -1;
  }

  .header-info h1 {
    font-size: 22px;
    font-weight: 800;
    color: var(--text-primary);
    margin-bottom: 3px;
  }

  .header-info .role {
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--flutter-blue);
    letter-spacing: 0.06em;
  }

  .header-info .role span {
    color: var(--text-muted);
  }

  .typing-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--bg-card);
    border: 0.5px solid var(--border-subtle);
    border-radius: 20px;
    padding: 6px 14px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--dart-teal);
    margin-bottom: 1.5rem;
    width: fit-content;
  }

  .typing-badge .dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--dart-teal);
    animation: blink 1.2s infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.2; }
  }

  #typed-text::after {
    content: '|';
    animation: cursor 0.8s step-start infinite;
    color: var(--flutter-blue);
  }

  @keyframes cursor {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    margin-bottom: 1.5rem;
  }

  .stat-card {
    background: var(--bg-card);
    border: 0.5px solid var(--border-subtle);
    border-radius: 10px;
    padding: 14px 12px;
    text-align: center;
    cursor: pointer;
    transition: border-color 0.2s, transform 0.15s;
  }

  .stat-card:hover {
    border-color: rgba(84,197,248,0.4);
    transform: translateY(-2px);
  }

  .stat-card .num {
    font-size: 20px;
    font-weight: 800;
    color: var(--flutter-blue);
  }

  .stat-card .lbl {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--text-muted);
    margin-top: 3px;
    letter-spacing: 0.04em;
  }

  .section-title {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--text-muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }

  .tech-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 8px;
    margin-bottom: 1.5rem;
  }

  .tech-pill {
    background: var(--bg-card);
    border: 0.5px solid var(--border-subtle);
    border-radius: 8px;
    padding: 10px 6px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
    cursor: pointer;
    transition: border-color 0.2s, transform 0.15s;
  }

  .tech-pill:hover {
    transform: translateY(-2px);
    border-color: rgba(84,197,248,0.35);
  }

  .tech-pill .icon {
    font-size: 20px;
    width: 20px;
    height: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .tech-pill .name {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: var(--text-secondary);
    text-align: center;
  }

  .contrib-wrap {
    background: var(--bg-card);
    border: 0.5px solid var(--border-subtle);
    border-radius: 12px;
    padding: 16px;
    margin-bottom: 1.5rem;
  }

  .contrib-title {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 12px;
  }

  .contrib-title .label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--text-muted);
    letter-spacing: 0.06em;
    text-transform: uppercase;
  }

  .contrib-title .total {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--green);
  }

  #contrib-svg { width: 100%; display: block; }

  .socials-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 8px;
  }

  .social-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    background: var(--bg-card);
    border: 0.5px solid var(--border-subtle);
    border-radius: 8px;
    padding: 10px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--text-secondary);
    cursor: pointer;
    text-decoration: none;
    transition: border-color 0.2s, color 0.2s, transform 0.15s;
  }

  .social-btn:hover { transform: translateY(-2px); }
  .social-btn.twitter:hover { border-color: #1D9BF0; color: #1D9BF0; }
  .social-btn.linkedin:hover { border-color: #0A66C2; color: #0A66C2; }
  .social-btn.facebook:hover { border-color: #1877F2; color: #1877F2; }
  .social-btn.instagram:hover { border-color: #E4405F; color: #E4405F; }

  .social-btn svg { width: 14px; height: 14px; fill: currentColor; flex-shrink: 0; }

  .footer-line {
    margin-top: 1.5rem;
    padding-top: 1rem;
    border-top: 0.5px solid var(--border-subtle);
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 6px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--text-muted);
  }

  .footer-line .dot-green { color: var(--green); }

  .lang-wrap {
    background: var(--bg-card);
    border: 0.5px solid var(--border-subtle);
    border-radius: 12px;
    padding: 16px;
    margin-bottom: 1.5rem;
  }

  .lang-bar {
    height: 8px;
    border-radius: 4px;
    overflow: hidden;
    display: flex;
    margin-bottom: 10px;
  }

  .lang-bar-seg { height: 100%; }

  .lang-legend {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }

  .lang-item {
    display: flex;
    align-items: center;
    gap: 5px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--text-secondary);
  }

  .lang-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }
</style>

<div class="profile-root">

  <div class="header">
    <div class="avatar">EE</div>
    <div class="header-info">
      <h1>Elsayed Elhoseny</h1>
      <p class="role"><span>// </span>Mobile Application Flutter Developer</p>
    </div>
  </div>

  <div class="typing-badge">
    <div class="dot"></div>
    <span id="typed-text"></span>
  </div>

  <div class="stats-row">
    <div class="stat-card">
      <div class="num" id="repos">0</div>
      <div class="lbl">Repos</div>
    </div>
    <div class="stat-card">
      <div class="num" id="commits">0</div>
      <div class="lbl">Commits</div>
    </div>
    <div class="stat-card">
      <div class="num" id="stars">0</div>
      <div class="lbl">Stars</div>
    </div>
  </div>

  <p class="section-title">tech stack</p>
  <div class="tech-grid">
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#54C5F8"><path d="M14.314 0L2.3 12 6 15.7 21.684 0h-7.37zm.014 11.072L6.857 18.53l3.7 3.7 7.484-7.484-3.713-3.674zM0 12l6 6-6 6V12z"/></svg>
      </div>
      <span class="name">Flutter</span>
    </div>
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#00B4AB"><path d="M4.105 4.105S9.158 1.58 11.684 0c.105 1.316.79 4.947 2.37 7.58 1.053-2.105 1.684-5.79 1.526-7.58 1.895.79 5.79 3.105 6.315 3.684-1.316.263-5.79 2.37-8.053 5.158-1.052-2.106-3.105-5.158-3.105-5.158s-1.947 3.526-5 5.263c2.105 2.105 3.526 5.526 3.526 9.053-.79.263-1.842.526-2.895.526-3.158 0-5.79-2.632-5.79-5.79-.001-2.895 1.578-5.527 3.527-8.631z"/></svg>
      </div>
      <span class="name">Dart</span>
    </div>
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#FFCA28"><path d="M3.89 15.672L6.255.461A.542.542 0 0 1 7.27.288l2.543 4.771zm16.794 3.692l-2.25-14a.54.54 0 0 0-.919-.295L3.316 19.365l7.856 4.427a1.621 1.621 0 0 0 1.588 0zM14.3 7.147l-1.82-3.482a.542.542 0 0 0-.96 0L3.53 17.984z"/></svg>
      </div>
      <span class="name">Firebase</span>
    </div>
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#A8B9CC"><path d="M22.394 6c-.167-.29-.398-.543-.652-.69L12.926.22c-.509-.294-1.34-.294-1.848 0L2.26 5.31c-.508.293-.923 1.013-.923 1.6v10.18c0 .294.104.62.271.91.167.29.398.543.652.69l8.816 5.09c.508.293 1.34.293 1.848 0l8.816-5.09c.254-.147.485-.4.652-.69.167-.29.27-.616.27-.91V6.91c.003-.294-.1-.62-.268-.91zM12 19.109c-3.92 0-7.109-3.189-7.109-7.109S8.08 4.891 12 4.891a7.133 7.133 0 0 1 6.156 3.552l-3.076 1.781A3.567 3.567 0 0 0 12 8.445c-1.96 0-3.554 1.595-3.554 3.555S10.04 15.555 12 15.555a3.57 3.57 0 0 0 3.08-1.778l3.078 1.78A7.135 7.135 0 0 1 12 19.109z"/></svg>
      </div>
      <span class="name">Android</span>
    </div>
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#F24E1E"><path d="M5.243 0A5.243 5.243 0 1 0 5.24 10.486H10.486V5.24A5.243 5.243 0 0 0 5.243 0zm0 18.757a5.243 5.243 0 1 0 0 10.486 5.243 5.243 0 0 0 0-10.486zm13.514 0a5.243 5.243 0 1 0 0 10.486 5.243 5.243 0 0 0 0-10.486zm0-18.757a5.243 5.243 0 1 0 0 10.486 5.243 5.243 0 0 0 0-10.486z"/></svg>
      </div>
      <span class="name">Figma</span>
    </div>
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#007ACC"><path d="M0 0h24v24H0V0zm22.034 18.276c-.175-1.095-.888-2.015-3.003-2.873-.736-.345-1.554-.585-1.797-1.14-.091-.33-.105-.51-.046-.705.15-.646.915-.84 1.515-.66.39.12.75.42.976.9 1.034-.676 1.034-.676 1.755-1.125-.27-.42-.404-.601-.586-.78-.63-.705-1.469-1.065-2.834-1.034l-.705.089c-.676.165-1.32.525-1.71 1.005-1.14 1.291-.811 3.541.569 4.471 1.365 1.02 3.361 1.244 3.616 2.205.24 1.17-.87 1.545-1.966 1.41-.811-.18-1.26-.586-1.755-1.336l-1.83 1.051c.21.48.45.689.81 1.109 1.74 1.756 6.09 1.666 6.871-1.004.029-.09.24-.705.074-1.65l.046.067zm-8.983-7.245h-2.248c0 1.938-.009 3.864-.009 5.805 0 1.232.063 2.363-.138 2.711-.33.689-1.18.601-1.566.48-.396-.196-.597-.466-.83-.855-.063-.105-.11-.196-.127-.196l-1.825 1.125c.305.63.75 1.172 1.324 1.517.855.51 2.004.675 3.207.405.783-.226 1.458-.691 1.811-1.411.51-.93.402-2.07.397-3.346.012-2.054 0-4.109 0-6.179l.004-.056z"/></svg>
      </div>
      <span class="name">TypeScript</span>
    </div>
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#F05032"><path d="M23.546 10.93L13.067.452c-.604-.603-1.582-.603-2.188 0L8.708 2.627l2.76 2.76c.645-.215 1.379-.07 1.889.441.516.515.658 1.258.438 1.9l2.658 2.66c.645-.223 1.387-.078 1.9.435.721.72.721 1.884 0 2.604-.719.719-1.881.719-2.6 0-.539-.541-.674-1.337-.404-1.996L12.86 8.955v6.525c.176.086.342.203.488.348.713.721.713 1.883 0 2.6-.719.721-1.889.721-2.609 0-.719-.719-.719-1.879 0-2.598.182-.18.387-.316.605-.406V8.835c-.217-.091-.424-.222-.6-.401-.545-.545-.676-1.342-.396-2.009L7.636 3.7.45 10.881c-.6.605-.6 1.584 0 2.189l10.48 10.477c.604.604 1.582.604 2.186 0l10.43-10.43c.605-.603.605-1.582 0-2.187"/></svg>
      </div>
      <span class="name">Git</span>
    </div>
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#181717"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
      </div>
      <span class="name">GitHub</span>
    </div>
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#FF0000"><path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg>
      </div>
      <span class="name">XD / AE</span>
    </div>
    <div class="tech-pill">
      <div class="icon">
        <svg viewBox="0 0 24 24" style="width:20px;height:20px;fill:#007ACC"><path d="M0 0h24v24H0V0zm22.034 18.276c-.175-1.095-.888-2.015-3.003-2.873-.736-.345-1.554-.585-1.797-1.14-.091-.33-.105-.51-.046-.705.15-.646.915-.84 1.515-.66.39.12.75.42.976.9 1.034-.676 1.034-.676 1.755-1.125-.27-.42-.404-.601-.586-.78-.63-.705-1.469-1.065-2.834-1.034l-.705.089c-.676.165-1.32.525-1.71 1.005-1.14 1.291-.811 3.541.569 4.471 1.365 1.02 3.361 1.244 3.616 2.205.24 1.17-.87 1.545-1.966 1.41-.811-.18-1.26-.586-1.755-1.336l-1.83 1.051c.21.48.45.689.81 1.109 1.74 1.756 6.09 1.666 6.871-1.004.029-.09.24-.705.074-1.65l.046.067zm-8.983-7.245h-2.248c0 1.938-.009 3.864-.009 5.805 0 1.232.063 2.363-.138 2.711-.33.689-1.18.601-1.566.48-.396-.196-.597-.466-.83-.855-.063-.105-.11-.196-.127-.196l-1.825 1.125c.305.63.75 1.172 1.324 1.517.855.51 2.004.675 3.207.405.783-.226 1.458-.691 1.811-1.411.51-.93.402-2.07.397-3.346.012-2.054 0-4.109 0-6.179l.004-.056z"/></svg>
      </div>
      <span class="name">VS Code</span>
    </div>
  </div>

  <div class="lang-wrap">
    <div class="contrib-title">
      <span class="label">most used languages</span>
    </div>
    <div class="lang-bar">
      <div class="lang-bar-seg" style="width:62%;background:#54C5F8;"></div>
      <div class="lang-bar-seg" style="width:23%;background:#00B4AB;"></div>
      <div class="lang-bar-seg" style="width:8%;background:#A371F7;"></div>
      <div class="lang-bar-seg" style="width:7%;background:#FFCA28;"></div>
    </div>
    <div class="lang-legend">
      <div class="lang-item"><div class="lang-dot" style="background:#54C5F8;"></div>Dart 62%</div>
      <div class="lang-item"><div class="lang-dot" style="background:#00B4AB;"></div>Flutter 23%</div>
      <div class="lang-item"><div class="lang-dot" style="background:#A371F7;"></div>TypeScript 8%</div>
      <div class="lang-item"><div class="lang-dot" style="background:#FFCA28;"></div>Other 7%</div>
    </div>
  </div>

  <div class="contrib-wrap">
    <div class="contrib-title">
      <span class="label">contribution activity</span>
      <span class="total" id="contrib-total">0 contributions this year</span>
    </div>
    <svg id="contrib-svg" viewBox="0 0 620 100"></svg>
  </div>

  <p class="section-title">connect</p>
  <div class="socials-row">
    <a class="social-btn twitter" href="https://x.com/elsayedel7oseny" target="_blank">
      <svg viewBox="0 0 24 24"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.746l7.73-8.835L1.254 2.25H8.08l4.259 5.63zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
      Twitter
    </a>
    <a class="social-btn linkedin" href="https://www.linkedin.com/in/elsayed-elhoseny-b4244a292/" target="_blank">
      <svg viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
      LinkedIn
    </a>
    <a class="social-btn facebook" href="https://www.facebook.com/profile.php?id=100005059607534" target="_blank">
      <svg viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
      Facebook
    </a>
    <a class="social-btn instagram" href="https://www.instagram.com/elsayedelhoseny_/" target="_blank">
      <svg viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/></svg>
      Instagram
    </a>
  </div>

  <div class="footer-line">
    <span class="dot-green">●</span>
    <span>Available for opportunities · Damietta, EG</span>
  </div>
</div>

<script>
  const phrases = [
    'Building cross-platform apps ✦',
    'Flutter & Dart enthusiast ✦',
    'Firebase power user ✦',
    'Welcome to my profile 🧑‍💻'
  ];
  let pi = 0, ci = 0, deleting = false;
  const el = document.getElementById('typed-text');
  function type() {
    const cur = phrases[pi];
    if (!deleting) {
      el.textContent = cur.slice(0, ci + 1);
      ci++;
      if (ci === cur.length) { deleting = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = cur.slice(0, ci - 1);
      ci--;
      if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; }
    }
    setTimeout(type, deleting ? 40 : 80);
  }
  type();

  function countUp(id, target) {
    const el = document.getElementById(id);
    let v = 0, step = Math.ceil(target / 60);
    const t = setInterval(() => {
      v = Math.min(v + step, target);
      el.textContent = v;
      if (v >= target) clearInterval(t);
    }, 25);
  }
  countUp('repos', 24);
  countUp('commits', 312);
  countUp('stars', 47);

  setTimeout(() => {
    const el = document.getElementById('contrib-total');
    let v = 0;
    const t = setInterval(() => {
      v = Math.min(v + 7, 412);
      el.textContent = v + ' contributions this year';
      if (v >= 412) clearInterval(t);
    }, 20);
  }, 300);

  const svg = document.getElementById('contrib-svg');
  const weeks = 52, rows = 7;
  const cellSize = 10, gap = 3;
  const offX = 4, offY = 10;
  const colors = ['#161B22', '#0E4429', '#006D32', '#26A641', '#39D353'];
  const seed = (w, d) => { let x = Math.sin(w * 13 + d * 7 + 1) * 10000; return x - Math.floor(x); };
  let maxW = 0;
  for (let w = 0; w < weeks; w++) {
    for (let d = 0; d < rows; d++) {
      const r = seed(w, d);
      const lvl = r < 0.45 ? 0 : r < 0.65 ? 1 : r < 0.78 ? 2 : r < 0.9 ? 3 : 4;
      const x = offX + w * (cellSize + gap);
      const y = offY + d * (cellSize + gap);
      const rect = document.createElementNS('http://www.w3.org/2000/svg', 'rect');
      rect.setAttribute('x', x); rect.setAttribute('y', y);
      rect.setAttribute('width', cellSize); rect.setAttribute('height', cellSize);
      rect.setAttribute('rx', '2'); rect.setAttribute('fill', colors[lvl]);
      svg.appendChild(rect);
      maxW = Math.max(maxW, x + cellSize);
    }
  }
  const totalH = offY + rows * (cellSize + gap) + 10;
  svg.setAttribute('viewBox', `0 0 ${maxW + 20} ${totalH}`);
</script>
