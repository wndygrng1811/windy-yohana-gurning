<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1"/>
<title>GitHub Profile — Nazwa</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,400;0,600;0,700;0,800;0,900;1,700&family=JetBrains+Mono:wght@400;600&display=swap');

  :root{
    --pink0:#fff0f5;
    --pink1:#ffd6e7;
    --pink2:#ffb3cc;
    --pink3:#ff8fab;
    --pink4:#e75480;
    --pink5:#c0336a;
    --pink6:#8b1a4a;
    --rose:#fff5f8;
    --card:#ffffff;
    --text:#3d1a26;
    --muted:#c0617e;
    --border:#ffcce0;
    --r:14px;
  }

  *{box-sizing:border-box;margin:0;padding:0}
  body{background:#fdf0f5;font-family:'Nunito',sans-serif;color:var(--text);min-height:100vh}

  /* ── WRAPPER ── */
  .page{max-width:860px;margin:0 auto;padding:0 0 3rem}

  /* ── HEADER WAVE ── */
  .header{
    position:relative;
    background:linear-gradient(135deg,var(--pink3) 0%,var(--pink4) 50%,var(--pink5) 100%);
    padding:3rem 2rem 4rem;
    text-align:center;
    overflow:hidden;
  }
  .header::before{
    content:'';position:absolute;inset:0;
    background:radial-gradient(ellipse at 20% 50%,rgba(255,255,255,.18) 0%,transparent 60%),
               radial-gradient(ellipse at 80% 20%,rgba(255,200,220,.25) 0%,transparent 50%);
  }
  .wave-svg{display:block;width:100%;margin-top:-1px}
  .header-inner{position:relative;z-index:1}

  /* floating blobs */
  .blob{position:absolute;border-radius:50%;opacity:.18;pointer-events:none}
  .blob-1{width:180px;height:180px;background:#fff;top:-40px;left:-40px;animation:float 6s ease-in-out infinite}
  .blob-2{width:120px;height:120px;background:#ffcce0;bottom:-20px;right:60px;animation:float 8s ease-in-out infinite reverse}
  .blob-3{width:80px;height:80px;background:#fff;top:20px;right:180px;animation:float 5s ease-in-out infinite 1s}
  @keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-14px)}}

  /* avatar */
  .avatar{
    width:90px;height:90px;border-radius:50%;
    background:rgba(255,255,255,.25);
    border:3px solid rgba(255,255,255,.7);
    display:flex;align-items:center;justify-content:center;
    font-size:42px;margin:0 auto 1rem;
    animation:pop .5s cubic-bezier(.34,1.56,.64,1);
  }
  @keyframes pop{from{transform:scale(0);opacity:0}to{transform:scale(1);opacity:1}}

  .header h1{
    font-size:2rem;font-weight:900;color:#fff;
    text-shadow:0 2px 8px rgba(139,26,74,.3);
    margin-bottom:.3rem;
  }
  .header .subtitle{font-size:.85rem;color:rgba(255,255,255,.85);letter-spacing:.5px;margin-bottom:1.25rem}

  /* typing badge row */
  .roles{display:flex;flex-wrap:wrap;justify-content:center;gap:7px;margin-bottom:1rem}
  .role{
    background:rgba(255,255,255,.22);
    border:1px solid rgba(255,255,255,.45);
    color:#fff;font-size:.72rem;font-weight:700;
    padding:4px 13px;border-radius:20px;
    backdrop-filter:blur(4px);
    animation:slidein .4s ease both;
  }
  .role:nth-child(1){animation-delay:.1s}
  .role:nth-child(2){animation-delay:.2s}
  .role:nth-child(3){animation-delay:.3s}
  .role:nth-child(4){animation-delay:.4s}
  .role:nth-child(5){animation-delay:.5s}
  @keyframes slidein{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}

  /* status badge */
  .status-badge{
    display:inline-flex;align-items:center;gap:6px;
    background:rgba(255,255,255,.18);border:1px solid rgba(255,255,255,.4);
    color:#fff;font-size:.72rem;font-weight:700;
    padding:5px 14px;border-radius:20px;
  }
  .pulse{width:7px;height:7px;border-radius:50%;background:#afffcc;animation:pulse 2s infinite}
  @keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.4;transform:scale(.8)}}

  /* view counter */
  .view-row{display:flex;justify-content:center;gap:8px;padding:1rem 0 .5rem;flex-wrap:wrap}
  .view-chip{
    background:var(--pink0);border:1px solid var(--border);
    color:var(--pink5);font-size:.72rem;font-weight:700;
    padding:4px 13px;border-radius:20px;
    display:inline-flex;align-items:center;gap:5px;
  }

  /* ── SECTIONS ── */
  .body{padding:0 1.5rem}
  .section{margin-bottom:2rem}

  .sec-label{
    display:flex;align-items:center;gap:8px;
    font-size:.72rem;font-weight:900;color:var(--pink5);
    text-transform:uppercase;letter-spacing:2px;
    padding-bottom:8px;margin-bottom:1rem;
    border-bottom:1.5px dashed var(--border);
  }
  .sec-label::before{
    content:'◆';font-size:.6rem;color:var(--pink3);
  }

  /* ── ABOUT ── */
  .about-grid{display:grid;grid-template-columns:1fr 220px;gap:1.25rem;align-items:start}
  @media(max-width:600px){.about-grid{grid-template-columns:1fr}}

  .code-card{
    background:#1e0a14;border:1.5px solid #3d1a2a;
    border-radius:var(--r);padding:1.1rem 1.25rem;
    font-family:'JetBrains Mono',monospace;font-size:.75rem;
    line-height:1.85;overflow-x:auto;
  }
  .cc{color:#ff8fab}   /* key */
  .cs{color:#ffcce0}   /* string */
  .cn{color:#ffd6e7}   /* normal */
  .cm{color:#5a3040}   /* comment */
  .ck{color:#ffb3cc}   /* keyword */

  /* info card */
  .info-card{
    background:var(--pink0);border:1.5px solid var(--border);
    border-radius:var(--r);padding:1rem;
    font-size:.78rem;line-height:2;
  }
  .info-row{display:flex;gap:6px;align-items:baseline}
  .info-icon{font-size:.85rem;min-width:20px}
  .info-text{color:var(--text)}
  .info-text b{color:var(--pink5)}

  /* ── GIF / ILLUSTRATION ── */
  .illus{
    background:linear-gradient(135deg,var(--pink1),var(--pink0));
    border:1.5px solid var(--border);border-radius:var(--r);
    overflow:hidden;display:flex;align-items:center;justify-content:center;
    aspect-ratio:4/3;position:relative;
  }
  /* pure CSS coding animation */
  .illus-inner{
    width:100%;height:100%;
    display:flex;flex-direction:column;
    align-items:center;justify-content:center;
    gap:.5rem;padding:1rem;
  }
  .code-line{
    height:7px;border-radius:4px;background:var(--pink3);
    opacity:.55;animation:blink-line 2.5s ease-in-out infinite;
  }
  .code-line:nth-child(1){width:70%;animation-delay:0s}
  .code-line:nth-child(2){width:55%;animation-delay:.2s;background:var(--pink4)}
  .code-line:nth-child(3){width:80%;animation-delay:.4s}
  .code-line:nth-child(4){width:40%;animation-delay:.6s;background:var(--pink5)}
  .code-line:nth-child(5){width:65%;animation-delay:.8s}
  .code-line:nth-child(6){width:50%;animation-delay:1s;background:var(--pink4)}
  .code-line:nth-child(7){width:75%;animation-delay:1.2s}
  .code-line:nth-child(8){width:35%;animation-delay:1.4s;background:var(--pink3)}
  @keyframes blink-line{0%,100%{opacity:.25}50%{opacity:.8}}

  .cursor-blink{
    width:10px;height:16px;background:var(--pink4);border-radius:2px;
    animation:cursor .8s step-end infinite;margin-top:4px;
  }
  @keyframes cursor{0%,100%{opacity:1}50%{opacity:0}}

  .illus-label{
    position:absolute;bottom:8px;left:0;right:0;text-align:center;
    font-size:.65rem;font-weight:700;color:var(--pink5);letter-spacing:.5px;
  }

  /* ── TECH STACK ── */
  .chips{display:flex;flex-wrap:wrap;gap:8px}
  .chip{
    display:inline-flex;align-items:center;gap:5px;
    padding:6px 13px;border-radius:20px;
    font-size:.73rem;font-weight:700;border:1.5px solid;
    transition:transform .15s,box-shadow .15s;cursor:default;
  }
  .chip:hover{transform:translateY(-2px)}
  .chip-dot{width:8px;height:8px;border-radius:50%}

  .t-laravel {background:#fff0f0;border-color:#ffb3b3;color:#991b1b}
  .t-laravel .chip-dot{background:#FF2D20}
  .t-php     {background:#f5f0ff;border-color:#c4b5fd;color:#5b21b6}
  .t-php .chip-dot{background:#777BB4}
  .t-mysql   {background:#eff6ff;border-color:#93c5fd;color:#1e3a8a}
  .t-mysql .chip-dot{background:#4479A1}
  .t-tailwind{background:#f0fdf9;border-color:#6ee7cc;color:#065f46}
  .t-tailwind .chip-dot{background:#38B2AC}
  .t-js      {background:#fefce8;border-color:#fde68a;color:#78350f}
  .t-js .chip-dot{background:#F7DF1E}
  .t-html    {background:#fff7ed;border-color:#fdba74;color:#9a3412}
  .t-html .chip-dot{background:#E34F26}
  .t-css     {background:#eff6ff;border-color:#bfdbfe;color:#1e3a8a}
  .t-css .chip-dot{background:#1572B6}
  .t-flutter {background:#f0f9ff;border-color:#7dd3fc;color:#075985}
  .t-flutter .chip-dot{background:#02569B}
  .t-dart    {background:#f0f9ff;border-color:#93c5fd;color:#1e3a8a}
  .t-dart .chip-dot{background:#0175C2}
  .t-git     {background:#fff0f0;border-color:#fca5a5;color:#991b1b}
  .t-git .chip-dot{background:#F05032}
  .t-github  {background:#f5f0ff;border-color:#c4b5fd;color:#3730a3}
  .t-github .chip-dot{background:#181717}
  .t-figma   {background:#fff0f5;border-color:#f9a8d4;color:#9d174d}
  .t-figma .chip-dot{background:#F24E1E}
  .t-firebase{background:#fefce8;border-color:#fde68a;color:#78350f}
  .t-firebase .chip-dot{background:#FFCA28}

  /* ── PROJECTS ── */
  .proj-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
  @media(max-width:560px){.proj-grid{grid-template-columns:1fr}}

  .proj-card{
    background:var(--card);border:1.5px solid var(--border);
    border-radius:var(--r);padding:1.1rem 1rem;
    transition:border-color .2s,transform .2s;
    position:relative;overflow:hidden;
  }
  .proj-card::before{
    content:'';position:absolute;top:0;left:0;right:0;height:3px;
    background:linear-gradient(90deg,var(--pink3),var(--pink4));
    border-radius:var(--r) var(--r) 0 0;
  }
  .proj-card:hover{border-color:var(--pink3);transform:translateY(-3px)}

  .proj-emoji{font-size:1.6rem;margin-bottom:.5rem}
  .proj-name{font-size:.85rem;font-weight:800;color:var(--pink6);margin-bottom:.3rem}
  .proj-desc{font-size:.73rem;color:var(--muted);line-height:1.5;margin-bottom:.75rem}
  .proj-features{list-style:none;font-size:.72rem;color:var(--text);margin-bottom:.75rem}
  .proj-features li{padding:1.5px 0}
  .proj-features li::before{content:'✦ ';color:var(--pink3);font-size:.6rem}
  .tag-row{display:flex;flex-wrap:wrap;gap:4px}
  .tag{
    background:var(--pink0);color:var(--pink5);
    border:1px solid var(--border);
    font-size:.67rem;font-weight:700;
    padding:2px 8px;border-radius:10px;
  }

  /* ── STATS ── */
  .stats-row{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:1rem}
  .stat-card{
    background:var(--card);border:1.5px solid var(--border);
    border-radius:var(--r);padding:1rem;text-align:center;
  }
  .stat-label{font-size:.67rem;color:var(--muted);text-transform:uppercase;letter-spacing:.8px;margin-bottom:6px}
  .stat-val{font-size:1.75rem;font-weight:900;color:var(--pink4);line-height:1}
  .stat-sub{font-size:.67rem;color:var(--muted);margin-top:4px}

  /* ── LANG BAR ── */
  .lang-card{
    background:var(--card);border:1.5px solid var(--border);
    border-radius:var(--r);padding:1.1rem;margin-bottom:1rem;
  }
  .lang-title{font-size:.73rem;color:var(--muted);font-weight:700;margin-bottom:.75rem}
  .bar-track{
    height:10px;border-radius:6px;background:var(--pink0);
    overflow:hidden;display:flex;margin-bottom:.75rem;
  }
  .bar-seg{height:100%;transition:width .6s ease}
  .legend{display:flex;flex-wrap:wrap;gap:10px}
  .leg-item{display:flex;align-items:center;gap:5px;font-size:.72rem;color:var(--text)}
  .leg-dot{width:9px;height:9px;border-radius:50%}

  /* ── STREAK VIZ ── */
  .streak-card{
    background:var(--card);border:1.5px solid var(--border);
    border-radius:var(--r);padding:1.1rem;margin-bottom:1rem;
  }
  .streak-header{
    display:flex;justify-content:space-between;align-items:center;
    margin-bottom:.875rem;
  }
  .streak-title{font-size:.73rem;color:var(--muted);font-weight:700}
  .streak-count{
    font-size:1.1rem;font-weight:900;color:var(--pink4);
    display:flex;align-items:center;gap:4px;
  }

  .contrib-grid{
    display:grid;
    grid-template-columns:repeat(28,1fr);
    gap:3px;
  }
  .c-day{
    aspect-ratio:1;border-radius:2px;
    background:var(--pink0);
  }
  .c-day.l1{background:#ffd6e7}
  .c-day.l2{background:#ffb3cc}
  .c-day.l3{background:#ff8fab}
  .c-day.l4{background:#e75480}

  /* ── ACTIVITY CHART ── */
  .chart-card{
    background:var(--card);border:1.5px solid var(--border);
    border-radius:var(--r);padding:1.1rem;margin-bottom:1rem;
    overflow:hidden;
  }
  .chart-title{font-size:.73rem;color:var(--muted);font-weight:700;margin-bottom:1rem}
  .chart-area{height:80px;display:flex;align-items:flex-end;gap:6px}
  .chart-col{
    flex:1;display:flex;flex-direction:column;
    align-items:center;gap:3px;
  }
  .chart-bar{
    width:100%;border-radius:4px 4px 0 0;
    background:linear-gradient(180deg,var(--pink3),var(--pink2));
    transition:height .5s ease;
    min-height:4px;
  }
  .chart-month{font-size:.6rem;color:var(--muted);font-weight:600}

  /* ── TROPHY ── */
  .trophy-row{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin-bottom:1rem}
  .trophy{
    background:var(--pink0);border:1.5px solid var(--border);
    border-radius:var(--r);padding:.6rem .875rem;
    display:flex;flex-direction:column;align-items:center;gap:3px;
    min-width:80px;
  }
  .trophy-icon{font-size:1.3rem}
  .trophy-label{font-size:.6rem;font-weight:700;color:var(--pink5);text-align:center;line-height:1.2}
  .trophy-val{font-size:.85rem;font-weight:900;color:var(--pink4)}

  /* ── CONTACT ── */
  .contact-row{display:flex;flex-wrap:wrap;gap:10px;justify-content:center}
  .cbtn{
    display:inline-flex;align-items:center;gap:7px;
    padding:9px 20px;border-radius:25px;
    font-size:.78rem;font-weight:800;border:1.5px solid;
    text-decoration:none;cursor:pointer;
    transition:transform .15s,opacity .15s;
    font-family:'Nunito',sans-serif;
  }
  .cbtn:hover{transform:translateY(-2px);opacity:.85}
  .cbtn-email  {background:#fff0f0;border-color:#fca5a5;color:#991b1b}
  .cbtn-li     {background:#eff6ff;border-color:#93c5fd;color:#1e3a8a}
  .cbtn-ig     {background:#fff0f5;border-color:#f9a8d4;color:#9d174d}
  .cbtn-gh     {background:var(--pink0);border-color:var(--border);color:var(--pink6)}

  .cbtn-icon{
    width:20px;height:20px;border-radius:4px;
    display:flex;align-items:center;justify-content:center;
    font-size:.85rem;
  }

  /* ── FOOTER WAVE ── */
  .footer{
    background:linear-gradient(135deg,var(--pink3) 0%,var(--pink4) 60%,var(--pink5) 100%);
    padding:1.5rem 2rem 1.75rem;text-align:center;margin-top:2rem;
    border-radius:0 0 14px 14px;
    position:relative;overflow:hidden;
  }
  .footer::before{
    content:'';position:absolute;inset:0;
    background:radial-gradient(ellipse at 30% 50%,rgba(255,255,255,.15) 0%,transparent 60%);
  }
  .footer-inner{position:relative;z-index:1}
  .hearts{color:rgba(255,255,255,.8);font-size:.85rem;letter-spacing:6px;margin-bottom:.5rem}
  .footer p{font-size:.8rem;color:rgba(255,255,255,.9);font-style:italic;margin-bottom:.3rem}
  .footer .thanks{font-size:.73rem;color:rgba(255,255,255,.7);font-style:normal;font-weight:700}

  /* ── DIVIDER ── */
  hr{border:none;border-top:1.5px dashed var(--border);margin:1.75rem 0}
</style>
</head>
<body>

<div class="page">

  <!-- ══ HEADER ══ -->
  <div class="header">
    <div class="blob blob-1"></div>
    <div class="blob blob-2"></div>
    <div class="blob blob-3"></div>
    <div class="header-inner">
      <div class="avatar">🌸</div>
      <h1>Hi, I'm Nazwa! 🌸</h1>
      <p class="subtitle">Informatics Engineering Student &nbsp;·&nbsp; Web &amp; Mobile Developer</p>
      <div class="roles">
        <span class="role">🌐 Web Developer</span>
        <span class="role">🔥 Laravel Developer</span>
        <span class="role">🛠 Software Engineer</span>
        <span class="role">📱 Mobile App Developer</span>
        <span class="role">🎓 Informatics Student</span>
      </div>
      <br/>
      <div class="status-badge">
        <span class="pulse"></span>
        Open for Internship &amp; Collaboration
      </div>
    </div>
  </div>

  <!-- wave svg -->
  <svg class="wave-svg" viewBox="0 0 1440 40" xmlns="http://www.w3.org/2000/svg" style="background:#e75480;display:block">
    <path d="M0,20 C360,40 1080,0 1440,20 L1440,40 L0,40 Z" fill="#fdf0f5"/>
  </svg>

  <!-- view counter -->
  <div class="view-row">
    <span class="view-chip">👁 1,247 profile views</span>
    <span class="view-chip">⭐ 24 repositories</span>
    <span class="view-chip">🌸 Open to opportunities</span>
  </div>

  <div class="body">

    <!-- ══ ABOUT ══ -->
    <hr/>
    <div class="section">
      <div class="sec-label">About Me</div>
      <div class="about-grid">
        <div>
          <div class="code-card">
            <span class="cm">// github.com/namakamu</span><br/>
            <span class="ck">const</span> <span class="cn">developer</span> <span class="cc">= {</span><br/>
            &nbsp;&nbsp;<span class="cc">name</span><span class="cn">:</span> <span class="cs">"Nazwa"</span><span class="cn">,</span><br/>
            &nbsp;&nbsp;<span class="cc">campus</span><span class="cn">:</span> <span class="cs">"Teknik Informatika S1"</span><span class="cn">,</span><br/>
            &nbsp;&nbsp;<span class="cc">role</span><span class="cn">:</span> <span class="cs">["Web Dev", "Laravel Dev",</span><br/>
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs">"Mobile Dev"]</span><span class="cn">,</span><br/>
            &nbsp;&nbsp;<span class="cc">tech</span><span class="cn">:</span> <span class="cs">["Laravel", "Flutter",</span><br/>
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs">"Tailwind CSS"]</span><span class="cn">,</span><br/>
            &nbsp;&nbsp;<span class="cc">building</span><span class="cn">:</span> <span class="cs">"Reservation &amp; EduPlatforms"</span><span class="cn">,</span><br/>
            &nbsp;&nbsp;<span class="cc">location</span><span class="cn">:</span> <span class="cs">"Indonesia 🇮🇩"</span><span class="cn">,</span><br/>
            &nbsp;&nbsp;<span class="cc">motto</span><span class="cn">:</span> <span class="cs">"Coffee ☕ → Clean Code 🚀"</span><br/>
            <span class="cc">};</span>
          </div>
        </div>
        <div>
          <div class="illus">
            <div class="illus-inner">
              <div class="code-line"></div>
              <div class="code-line"></div>
              <div class="code-line"></div>
              <div class="code-line"></div>
              <div class="code-line"></div>
              <div class="code-line"></div>
              <div class="code-line"></div>
              <div class="code-line"></div>
              <div class="cursor-blink"></div>
            </div>
            <div class="illus-label">✦ coding in progress ✦</div>
          </div>
          <br/>
          <div class="info-card">
            <div class="info-row"><span class="info-icon">🎓</span><span class="info-text">Mahasiswa <b>Teknik Informatika</b> aktif</span></div>
            <div class="info-row"><span class="info-icon">💻</span><span class="info-text">Fokus sistem <b>reservasi &amp; edukasi</b></span></div>
            <div class="info-row"><span class="info-icon">🌱</span><span class="info-text">Terus belajar hal baru setiap hari</span></div>
            <div class="info-row"><span class="info-icon">💼</span><span class="info-text">Open untuk <b>magang &amp; kolaborasi</b></span></div>
            <div class="info-row"><span class="info-icon">📍</span><span class="info-text">Indonesia 🇮🇩</span></div>
          </div>
        </div>
      </div>
    </div>

    <!-- ══ TECH STACK ══ -->
    <hr/>
    <div class="section">
      <div class="sec-label">Tech Stack</div>
      <div class="chips">
        <span class="chip t-laravel"><span class="chip-dot"></span>Laravel</span>
        <span class="chip t-php"><span class="chip-dot"></span>PHP</span>
        <span class="chip t-mysql"><span class="chip-dot"></span>MySQL</span>
        <span class="chip t-tailwind"><span class="chip-dot"></span>Tailwind CSS</span>
        <span class="chip t-js"><span class="chip-dot"></span>JavaScript</span>
        <span class="chip t-html"><span class="chip-dot"></span>HTML5</span>
        <span class="chip t-css"><span class="chip-dot"></span>CSS3</span>
        <span class="chip t-flutter"><span class="chip-dot"></span>Flutter</span>
        <span class="chip t-dart"><span class="chip-dot"></span>Dart</span>
        <span class="chip t-git"><span class="chip-dot"></span>Git</span>
        <span class="chip t-github"><span class="chip-dot"></span>GitHub</span>
        <span class="chip t-figma"><span class="chip-dot"></span>Figma</span>
        <span class="chip t-firebase"><span class="chip-dot"></span>Firebase</span>
      </div>
    </div>

    <!-- ══ PROJECTS ══ -->
    <hr/>
    <div class="section">
      <div class="sec-label">Featured Projects</div>
      <div class="proj-grid">

        <div class="proj-card">
          <div class="proj-emoji">🎤</div>
          <div class="proj-name">Karaoke Reservation System</div>
          <div class="proj-desc">Sistem reservasi ruangan karaoke modern dengan slot waktu interaktif</div>
          <ul class="proj-features">
            <li>Slot waktu ala bioskop</li>
            <li>Upload bukti pembayaran</li>
            <li>Konfirmasi pembayaran admin</li>
            <li>Dashboard admin responsif</li>
            <li>UI Tailwind modern</li>
          </ul>
          <div class="tag-row">
            <span class="tag">Laravel</span>
            <span class="tag">MySQL</span>
            <span class="tag">Tailwind CSS</span>
          </div>
        </div>

        <div class="proj-card">
          <div class="proj-emoji">🏨</div>
          <div class="proj-name">Hotel Reservation System</div>
          <div class="proj-desc">Platform pemesanan hotel dengan manajemen transaksi lengkap</div>
          <ul class="proj-features">
            <li>Pencarian &amp; filter kamar</li>
            <li>Invoice otomatis</li>
            <li>Dashboard admin</li>
            <li>Manajemen pelanggan</li>
            <li>Riwayat transaksi</li>
          </ul>
          <div class="tag-row">
            <span class="tag">PHP</span>
            <span class="tag">MySQL</span>
          </div>
        </div>

        <div class="proj-card">
          <div class="proj-emoji">📚</div>
          <div class="proj-name">EduConnect Platform</div>
          <div class="proj-desc">Platform edukasi digital untuk pembelajaran online yang modern</div>
          <ul class="proj-features">
            <li>Manajemen kelas &amp; materi</li>
            <li>Interaksi siswa &amp; guru</li>
            <li>Dashboard multi-peran</li>
            <li>Sistem pembelajaran online</li>
            <li>UI modern &amp; interaktif</li>
          </ul>
          <div class="tag-row">
            <span class="tag">Laravel</span>
            <span class="tag">Tailwind CSS</span>
            <span class="tag">MySQL</span>
          </div>
        </div>

        <div class="proj-card">
          <div class="proj-emoji">👶</div>
          <div class="proj-name">SiTumbuh — Child Growth App</div>
          <div class="proj-desc">Aplikasi mobile monitoring pertumbuhan anak &amp; deteksi stunting</div>
          <ul class="proj-features">
            <li>Monitoring pertumbuhan real-time</li>
            <li>Deteksi risiko stunting (WHO)</li>
            <li>Grafik pertumbuhan interaktif</li>
            <li>Edukasi kesehatan anak</li>
            <li>Notifikasi jadwal pemantauan</li>
          </ul>
          <div class="tag-row">
            <span class="tag">Flutter</span>
            <span class="tag">Firebase</span>
            <span class="tag">Dart</span>
          </div>
        </div>

      </div>
    </div>

    <!-- ══ GITHUB ANALYTICS ══ -->
    <hr/>
    <div class="section">
      <div class="sec-label">GitHub Analytics</div>

      <!-- stat cards -->
      <div class="stats-row">
        <div class="stat-card">
          <div class="stat-label">Repositories</div>
          <div class="stat-val">24+</div>
          <div class="stat-sub">public repos</div>
        </div>
        <div class="stat-card">
          <div class="stat-label">Commits</div>
          <div class="stat-val">500+</div>
          <div class="stat-sub">this year</div>
        </div>
        <div class="stat-card">
          <div class="stat-label">Current Streak</div>
          <div class="stat-val">21🔥</div>
          <div class="stat-sub">days active</div>
        </div>
      </div>

      <!-- lang bar -->
      <div class="lang-card">
        <div class="lang-title">📊 Top Languages</div>
        <div class="bar-track">
          <div class="bar-seg" style="width:38%;background:#fca5a5"></div>
          <div class="bar-seg" style="width:22%;background:#fde68a"></div>
          <div class="bar-seg" style="width:18%;background:#6ee7b7"></div>
          <div class="bar-seg" style="width:12%;background:#93c5fd"></div>
          <div class="bar-seg" style="width:10%;background:#f9a8d4"></div>
        </div>
        <div class="legend">
          <div class="leg-item"><div class="leg-dot" style="background:#fca5a5"></div>PHP / Laravel — 38%</div>
          <div class="leg-item"><div class="leg-dot" style="background:#fde68a"></div>JavaScript — 22%</div>
          <div class="leg-item"><div class="leg-dot" style="background:#6ee7b7"></div>CSS / Tailwind — 18%</div>
          <div class="leg-item"><div class="leg-dot" style="background:#93c5fd"></div>Dart / Flutter — 12%</div>
          <div class="leg-item"><div class="leg-dot" style="background:#f9a8d4"></div>Other — 10%</div>
        </div>
      </div>

      <!-- contribution grid -->
      <div class="streak-card">
        <div class="streak-header">
          <span class="streak-title">🌸 Contribution Activity — Last 4 Weeks</span>
          <span class="streak-count">21 🔥 day streak</span>
        </div>
        <div class="contrib-grid" id="cgrid"></div>
      </div>

      <!-- activity chart -->
      <div class="chart-card">
        <div class="chart-title">📈 Monthly Commits — 2024</div>
        <div class="chart-area" id="chart"></div>
      </div>

      <!-- trophies -->
      <div class="trophy-row">
        <div class="trophy"><div class="trophy-icon">🏆</div><div class="trophy-label">Multi-language</div><div class="trophy-val">5 langs</div></div>
        <div class="trophy"><div class="trophy-icon">🔥</div><div class="trophy-label">Commit streak</div><div class="trophy-val">21 days</div></div>
        <div class="trophy"><div class="trophy-icon">⭐</div><div class="trophy-label">Stars earned</div><div class="trophy-val">42 ⭐</div></div>
        <div class="trophy"><div class="trophy-icon">📦</div><div class="trophy-label">Repositories</div><div class="trophy-val">24 repos</div></div>
        <div class="trophy"><div class="trophy-icon">👥</div><div class="trophy-label">Followers</div><div class="trophy-val">38 follow</div></div>
        <div class="trophy"><div class="trophy-icon">🚀</div><div class="trophy-label">Pull requests</div><div class="trophy-val">87 PRs</div></div>
      </div>

    </div>

    <!-- ══ CONTACT ══ -->
    <hr/>
    <div class="section" style="text-align:center">
      <div class="sec-label" style="justify-content:center">Let's Connect 💌</div>
      <div class="contact-row">
        <a class="cbtn cbtn-email" href="mailto:email@gmail.com">
          <span class="cbtn-icon">✉️</span> Email
        </a>
        <a class="cbtn cbtn-li" href="https://linkedin.com/in/usernamekamu" target="_blank">
          <span class="cbtn-icon">💼</span> LinkedIn
        </a>
        <a class="cbtn cbtn-ig" href="https://instagram.com/usernamekamu" target="_blank">
          <span class="cbtn-icon">📸</span> Instagram
        </a>
        <a class="cbtn cbtn-gh" href="https://github.com/namakamu" target="_blank">
          <span class="cbtn-icon">🐙</span> GitHub
        </a>
      </div>
    </div>

  </div><!-- /body -->

  <!-- ══ FOOTER ══ -->
  <div class="footer">
    <div class="footer-inner">
      <div class="hearts">♡ &nbsp; ♡ &nbsp; ♡</div>
      <p>"Code with heart, build with purpose — one commit at a time." 🌸</p>
      <p class="thanks">✨ Thanks for visiting! Let's build something beautiful together ✨</p>
    </div>
  </div>

</div><!-- /page -->

<script>
  // ── contribution grid ──
  const grid = document.getElementById('cgrid');
  const levels = [0,0,1,2,3,4,2,1,0,3,4,2,1,0,0,2,3,4,1,0,2,3,1,4,2,0,1,3];
  levels.forEach(l => {
    const d = document.createElement('div');
    d.className = 'c-day' + (l > 0 ? ' l'+l : '');
    grid.appendChild(d);
  });

  // ── activity chart ──
  const months = ['Jan','Feb','Mar','Apr','Mei','Jun','Jul','Ags','Sep','Okt','Nov','Des'];
  const vals   = [18,22,15,30,28,35,40,38,25,42,36,50];
  const max    = Math.max(...vals);
  const chart  = document.getElementById('chart');
  months.forEach((m,i) => {
    const col = document.createElement('div');
    col.className = 'chart-col';
    const pct = Math.round((vals[i]/max)*100);
    col.innerHTML = `
      <div class="chart-bar" style="height:${pct}%"></div>
      <span class="chart-month">${m}</span>
    `;
    chart.appendChild(col);
  });
</script>
</body>
</html>
