
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>SmartBiz — Turn Ideas Into Empires</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #ffffff;
      --surface: #f7f8fa;
      --border: #e5e7eb;
      --text: #1f2328;
      --muted: #57606a;
      --accent: #3b82d4;
      --purple: #7c5cd8;
      --dark: #0d1117;
      --dark2: #161b22;
      --gold: #f5a623;
      --green: #2da44e;
      --card-bg: #ffffff;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: -apple-system, "Segoe UI", system-ui, sans-serif;
      background: var(--bg);
      color: var(--text);
      font-size: 15px;
      line-height: 1.65;
      overflow-x: hidden;
    }

    /* ── SCROLLBAR ── */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: var(--surface); }
    ::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 3px; }

    /* ══════════════════════════════
       NAV
    ══════════════════════════════ */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 999;
      background: rgba(13,17,23,0.96);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid #21262d;
      height: 64px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 6%;
    }
    .nav-logo {
      display: flex;
      align-items: center;
      gap: 10px;
      text-decoration: none;
    }
    .nav-logo-icon {
      width: 36px; height: 36px;
      background: linear-gradient(135deg, var(--accent), var(--purple));
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.1rem; font-weight: 900; color: #fff;
    }
    .nav-logo-text { font-size: 1.15rem; font-weight: 800; color: #fff; letter-spacing: -0.01em; }
    .nav-logo-text span { color: var(--accent); }

    .nav-links { display: flex; align-items: center; gap: 32px; list-style: none; }
    .nav-links a { color: #8b949e; font-size: 0.88rem; text-decoration: none; font-weight: 500; letter-spacing: 0.01em; transition: color 0.15s; }
    .nav-links a:hover { color: #fff; }
    .nav-cta {
      background: var(--accent);
      color: #fff !important;
      padding: 8px 20px;
      border-radius: 6px;
      font-weight: 600 !important;
      font-size: 0.86rem !important;
    }
    .nav-cta:hover { background: #2d6bc4 !important; color: #fff !important; }

    /* ══════════════════════════════
       HERO
    ══════════════════════════════ */
    .hero {
      background: var(--dark);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 100px 6% 80px;
      position: relative;
      overflow: hidden;
    }
    .hero-bg-grid {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(59,130,212,0.06) 1px, transparent 1px),
        linear-gradient(90deg, rgba(59,130,212,0.06) 1px, transparent 1px);
      background-size: 60px 60px;
    }
    .hero-glow {
      position: absolute;
      width: 600px; height: 600px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(59,130,212,0.18) 0%, transparent 70%);
      top: 50%; left: 50%;
      transform: translate(-50%, -60%);
      pointer-events: none;
    }
    .hero-glow2 {
      position: absolute;
      width: 400px; height: 400px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(124,92,216,0.14) 0%, transparent 70%);
      bottom: 0; right: 10%;
      pointer-events: none;
    }
    .hero-content { position: relative; z-index: 2; max-width: 780px; }
    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: rgba(59,130,212,0.12);
      border: 1px solid rgba(59,130,212,0.3);
      color: #79b8ff;
      font-size: 0.78rem;
      font-weight: 600;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      padding: 6px 16px;
      border-radius: 20px;
      margin-bottom: 24px;
    }
    .hero-badge-dot { width: 6px; height: 6px; background: var(--accent); border-radius: 50%; }
    .hero h1 {
      font-size: clamp(2.2rem, 5.5vw, 4rem);
      font-weight: 900;
      color: #fff;
      line-height: 1.1;
      margin-bottom: 22px;
      letter-spacing: -0.02em;
    }
    .hero h1 .grad {
      background: linear-gradient(135deg, var(--accent) 0%, var(--purple) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .hero-sub {
      color: #8b949e;
      font-size: 1.1rem;
      max-width: 560px;
      margin: 0 auto 38px;
      line-height: 1.7;
    }
    .hero-btns { display: flex; gap: 14px; justify-content: center; flex-wrap: wrap; }
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 13px 28px;
      border-radius: 8px;
      font-size: 0.92rem;
      font-weight: 700;
      cursor: pointer;
      border: none;
      text-decoration: none;
      transition: all 0.15s;
      letter-spacing: 0.01em;
    }
    .btn-primary { background: var(--accent); color: #fff; }
    .btn-primary:hover { background: #2d6bc4; transform: translateY(-1px); }
    .btn-ghost { background: transparent; color: #c9d1d9; border: 1.5px solid #30363d; }
    .btn-ghost:hover { border-color: var(--accent); color: #fff; transform: translateY(-1px); }

    .hero-metrics {
      display: flex;
      justify-content: center;
      gap: 48px;
      flex-wrap: wrap;
      margin-top: 64px;
      padding-top: 36px;
      border-top: 1px solid #21262d;
    }
    .hero-metric { text-align: center; }
    .hero-metric-num { font-size: 1.8rem; font-weight: 900; color: #fff; }
    .hero-metric-num span { color: var(--accent); }
    .hero-metric-lbl { font-size: 0.8rem; color: #8b949e; text-transform: uppercase; letter-spacing: 0.08em; margin-top: 2px; }

    /* ══════════════════════════════
       MARQUEE TRUST BAR
    ══════════════════════════════ */
    .trust-bar {
      background: var(--dark2);
      border-top: 1px solid #21262d;
      border-bottom: 1px solid #21262d;
      padding: 16px 0;
      overflow: hidden;
      white-space: nowrap;
    }
    .marquee-track {
      display: inline-block;
      animation: marquee 22s linear infinite;
    }
    .marquee-item {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      margin: 0 40px;
      color: #484f58;
      font-size: 0.88rem;
      font-weight: 700;
      letter-spacing: 0.06em;
      text-transform: uppercase;
    }
    .marquee-dot { width: 4px; height: 4px; background: #484f58; border-radius: 50%; }
    @keyframes marquee {
      0% { transform: translateX(0); }
      100% { transform: translateX(-50%); }
    }

    /* ══════════════════════════════
       SECTIONS
    ══════════════════════════════ */
    section { padding: 90px 6%; }
    .section-chip {
      display: inline-block;
      background: rgba(59,130,212,0.1);
      color: var(--accent);
      font-size: 0.72rem;
      font-weight: 700;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      padding: 5px 14px;
      border-radius: 20px;
      margin-bottom: 12px;
    }
    .section-title {
      font-size: clamp(1.7rem, 3.5vw, 2.4rem);
      font-weight: 900;
      line-height: 1.2;
      letter-spacing: -0.02em;
      margin-bottom: 12px;
    }
    .section-sub {
      color: var(--muted);
      max-width: 520px;
      margin-bottom: 52px;
      font-size: 0.97rem;
    }
    .center { text-align: center; }
    .center .section-sub { margin-left: auto; margin-right: auto; }

    /* ══════════════════════════════
       IDEAS / SERVICES
    ══════════════════════════════ */
    .ideas-section { background: var(--surface); }
    .ideas-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(290px, 1fr));
      gap: 24px;
    }
    .idea-card {
      background: var(--card-bg);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 28px 26px 30px;
      position: relative;
      overflow: hidden;
      cursor: default;
      transition: border-color 0.2s, transform 0.2s;
    }
    .idea-card:hover { border-color: var(--accent); transform: translateY(-3px); }
    .idea-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 3px;
      border-radius: 14px 14px 0 0;
    }
    .idea-card.c1::before { background: linear-gradient(90deg, var(--accent), var(--purple)); }
    .idea-card.c2::before { background: linear-gradient(90deg, var(--green), var(--accent)); }
    .idea-card.c3::before { background: linear-gradient(90deg, var(--gold), #e85d04); }
    .idea-card.c4::before { background: linear-gradient(90deg, var(--purple), #e056b4); }
    .idea-card.c5::before { background: linear-gradient(90deg, #00bcd4, var(--green)); }
    .idea-card.c6::before { background: linear-gradient(90deg, #e85d04, var(--gold)); }
    .idea-icon {
      width: 48px; height: 48px;
      border-radius: 12px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.4rem;
      margin-bottom: 18px;
    }
    .idea-icon.i1 { background: rgba(59,130,212,0.12); }
    .idea-icon.i2 { background: rgba(45,164,78,0.12); }
    .idea-icon.i3 { background: rgba(245,166,35,0.12); }
    .idea-icon.i4 { background: rgba(124,92,216,0.12); }
    .idea-icon.i5 { background: rgba(0,188,212,0.12); }
    .idea-icon.i6 { background: rgba(232,93,4,0.12); }
    .idea-title { font-size: 1.05rem; font-weight: 800; margin-bottom: 8px; }
    .idea-desc { color: var(--muted); font-size: 0.88rem; line-height: 1.6; margin-bottom: 16px; }
    .idea-profit {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: rgba(45,164,78,0.1);
      color: var(--green);
      font-size: 0.78rem;
      font-weight: 700;
      padding: 4px 10px;
      border-radius: 20px;
    }

    /* ══════════════════════════════
       HOW IT WORKS
    ══════════════════════════════ */
    .steps-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
      gap: 0;
      position: relative;
    }
    .steps-grid::before {
      content: '';
      position: absolute;
      top: 36px; left: 18%;
      right: 18%;
      height: 2px;
      background: linear-gradient(90deg, var(--accent), var(--purple));
      opacity: 0.3;
    }
    .step-item { text-align: center; padding: 0 24px 24px; position: relative; }
    .step-circle {
      width: 72px; height: 72px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--accent), var(--purple));
      display: flex; align-items: center; justify-content: center;
      font-size: 1.5rem;
      margin: 0 auto 20px;
      border: 4px solid var(--bg);
      box-shadow: 0 0 0 2px var(--accent);
      position: relative;
      z-index: 1;
    }
    .step-num {
      position: absolute;
      top: -4px; right: -4px;
      width: 22px; height: 22px;
      background: var(--dark);
      color: var(--accent);
      border-radius: 50%;
      font-size: 0.65rem;
      font-weight: 900;
      display: flex; align-items: center; justify-content: center;
      border: 1.5px solid var(--accent);
    }
    .step-title { font-size: 1rem; font-weight: 800; margin-bottom: 8px; }
    .step-text { color: var(--muted); font-size: 0.87rem; }

    /* ══════════════════════════════
       STATS
    ══════════════════════════════ */
    .stats-section {
      background: var(--dark);
      color: #fff;
    }
    .stats-section .section-title { color: #fff; }
    .stats-section .section-sub { color: #8b949e; }
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 24px;
    }
    .stat-card {
      background: var(--dark2);
      border: 1px solid #21262d;
      border-radius: 14px;
      padding: 30px 24px;
      text-align: center;
    }
    .stat-num { font-size: 2.4rem; font-weight: 900; color: var(--accent); margin-bottom: 6px; }
    .stat-lbl { color: #8b949e; font-size: 0.85rem; letter-spacing: 0.04em; }
    .stat-icon { font-size: 1.8rem; margin-bottom: 12px; }

    /* ══════════════════════════════
       TESTIMONIALS
    ══════════════════════════════ */
    .testimonials-section { background: var(--surface); }
    .testi-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 22px;
    }
    .testi-card {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 26px 26px 28px;
    }
    .testi-stars { color: var(--gold); font-size: 0.9rem; letter-spacing: 2px; margin-bottom: 14px; }
    .testi-text { color: var(--text); font-size: 0.93rem; line-height: 1.7; margin-bottom: 20px; font-style: italic; }
    .testi-author { display: flex; align-items: center; gap: 12px; }
    .testi-avatar {
      width: 40px; height: 40px;
      border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-size: 1rem; font-weight: 700; color: #fff;
    }
    .testi-name { font-size: 0.9rem; font-weight: 700; }
    .testi-role { font-size: 0.78rem; color: var(--muted); }

    /* ══════════════════════════════
       PRICING
    ══════════════════════════════ */
    .pricing-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 24px;
      max-width: 960px;
      margin: 0 auto;
    }
    .price-card {
      background: var(--card-bg);
      border: 1.5px solid var(--border);
      border-radius: 16px;
      padding: 32px 28px 36px;
      text-align: center;
      position: relative;
    }
    .price-card.featured {
      border-color: var(--accent);
      background: #f0f7ff;
    }
    .price-badge {
      position: absolute;
      top: -12px;
      left: 50%;
      transform: translateX(-50%);
      background: var(--accent);
      color: #fff;
      font-size: 0.72rem;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      padding: 4px 16px;
      border-radius: 20px;
    }
    .price-plan { font-size: 0.78rem; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: var(--muted); margin-bottom: 10px; }
    .price-amount { font-size: 3rem; font-weight: 900; color: var(--text); line-height: 1; margin-bottom: 4px; }
    .price-amount sup { font-size: 1.2rem; vertical-align: super; font-weight: 700; }
    .price-period { color: var(--muted); font-size: 0.85rem; margin-bottom: 24px; }
    .price-features { list-style: none; text-align: left; margin-bottom: 28px; display: flex; flex-direction: column; gap: 10px; }
    .price-features li { font-size: 0.88rem; color: var(--text); display: flex; align-items: center; gap: 8px; }
    .price-features li .check { color: var(--green); font-weight: 700; }
    .price-features li .cross { color: #d1d5db; }
    .btn-plan {
      width: 100%;
      padding: 12px;
      border-radius: 8px;
      font-size: 0.92rem;
      font-weight: 700;
      cursor: pointer;
      border: none;
      transition: all 0.15s;
    }
    .btn-plan.primary { background: var(--accent); color: #fff; }
    .btn-plan.primary:hover { background: #2d6bc4; }
    .btn-plan.outline { background: transparent; color: var(--accent); border: 1.5px solid var(--accent); }
    .btn-plan.outline:hover { background: var(--accent); color: #fff; }

    /* ══════════════════════════════
       FAQ
    ══════════════════════════════ */
    .faq-section { background: var(--surface); }
    .faq-list { max-width: 720px; margin: 0 auto; display: flex; flex-direction: column; gap: 12px; }
    .faq-item {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 10px;
      overflow: hidden;
    }
    .faq-q {
      width: 100%;
      background: none;
      border: none;
      padding: 18px 22px;
      font-size: 0.95rem;
      font-weight: 700;
      color: var(--text);
      cursor: pointer;
      text-align: left;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
    }
    .faq-q:hover { color: var(--accent); }
    .faq-icon { font-size: 1.1rem; color: var(--accent); flex-shrink: 0; transition: transform 0.2s; }
    .faq-item.open .faq-icon { transform: rotate(45deg); }
    .faq-a {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.3s ease, padding 0.3s ease;
      font-size: 0.9rem;
      color: var(--muted);
      padding: 0 22px;
      line-height: 1.7;
    }
    .faq-item.open .faq-a { max-height: 200px; padding: 0 22px 18px; }

    /* ══════════════════════════════
       CTA BANNER
    ══════════════════════════════ */
    .cta-section {
      background: linear-gradient(135deg, #0d1117 0%, #1a1f2e 50%, #0d1117 100%);
      text-align: center;
      padding: 90px 6%;
      position: relative;
      overflow: hidden;
    }
    .cta-section::before {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse 80% 60% at 50% 100%, rgba(59,130,212,0.12) 0%, transparent 70%);
    }
    .cta-content { position: relative; z-index: 1; }
    .cta-section h2 { font-size: clamp(1.8rem, 4vw, 3rem); font-weight: 900; color: #fff; margin-bottom: 14px; letter-spacing: -0.02em; }
    .cta-section p { color: #8b949e; font-size: 1.05rem; margin-bottom: 36px; }
    .cta-input-row { display: flex; gap: 10px; justify-content: center; flex-wrap: wrap; }
    .cta-input {
      padding: 13px 20px;
      border-radius: 8px;
      border: 1.5px solid #30363d;
      background: #161b22;
      color: #fff;
      font-size: 0.92rem;
      width: 300px;
      outline: none;
    }
    .cta-input:focus { border-color: var(--accent); }
    .cta-input::placeholder { color: #484f58; }

    /* ══════════════════════════════
       FOOTER
    ══════════════════════════════ */
    footer {
      background: var(--dark);
      border-top: 1px solid #21262d;
      padding: 56px 6% 28px;
    }
    .footer-top {
      display: grid;
      grid-template-columns: 1.5fr 1fr 1fr 1fr;
      gap: 40px;
      margin-bottom: 40px;
    }
    @media (max-width: 720px) {
      .footer-top { grid-template-columns: 1fr 1fr; }
      .nav-links { display: none; }
      .steps-grid::before { display: none; }
    }
    @media (max-width: 480px) {
      .footer-top { grid-template-columns: 1fr; }
    }
    .footer-brand-logo {
      display: flex; align-items: center; gap: 10px; margin-bottom: 14px;
    }
    .footer-brand-logo .logo-box {
      width: 32px; height: 32px;
      background: linear-gradient(135deg, var(--accent), var(--purple));
      border-radius: 7px;
      display: flex; align-items: center; justify-content: center;
      font-size: 0.95rem; font-weight: 900; color: #fff;
    }
    .footer-brand-logo .logo-name { font-size: 1rem; font-weight: 800; color: #fff; }
    .footer-brand-logo .logo-name span { color: var(--accent); }
    .footer-brand-desc { color: #57606a; font-size: 0.87rem; line-height: 1.6; max-width: 240px; }
    .footer-col-title { color: #8b949e; font-size: 0.75rem; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 14px; }
    .footer-col-links { display: flex; flex-direction: column; gap: 9px; list-style: none; }
    .footer-col-links a { color: #57606a; font-size: 0.87rem; text-decoration: none; transition: color 0.15s; }
    .footer-col-links a:hover { color: #fff; }
    .footer-bottom {
      border-top: 1px solid #21262d;
      padding-top: 22px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: gap;
      gap: 12px;
    }
    .footer-copy { color: #484f58; font-size: 0.82rem; }
    .footer-made { font-size: 0.75rem; color: #484f58; text-align: center; }

    /* ══════════════════════════════
       COUNTER ANIMATION
    ══════════════════════════════ */
    .count-up { display: inline-block; }

    /* ══════════════════════════════
       MODAL
    ══════════════════════════════ */
    .modal-overlay {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.7);
      z-index: 1000;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }
    .modal-overlay.open { display: flex; }
    .modal-box {
      background: #fff;
      border-radius: 16px;
      max-width: 480px;
      width: 100%;
      overflow: hidden;
    }
    .modal-head {
      background: var(--dark);
      padding: 28px;
      position: relative;
    }
    .modal-close-btn {
      position: absolute; top: 14px; right: 16px;
      background: none; border: none; color: #8b949e;
      font-size: 1.3rem; cursor: pointer; line-height: 1;
    }
    .modal-head-icon { font-size: 2.8rem; margin-bottom: 10px; }
    .modal-head-title { color: #fff; font-size: 1.25rem; font-weight: 800; }
    .modal-head-sub { color: #8b949e; font-size: 0.88rem; margin-top: 4px; }
    .modal-body-pad { padding: 24px 28px 28px; }
    .modal-detail-row { display: flex; justify-content: space-between; align-items: center; padding: 10px 0; border-bottom: 1px solid var(--border); }
    .modal-detail-row:last-child { border: none; }
    .modal-detail-lbl { font-size: 0.83rem; color: var(--muted); }
    .modal-detail-val { font-size: 0.9rem; font-weight: 700; color: var(--text); }
    .modal-desc-title { font-size: 0.75rem; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: var(--accent); margin-bottom: 8px; }
    .modal-desc-text { font-size: 0.9rem; color: var(--muted); line-height: 1.65; }
  </style>
</head>
<body>
<script>
  window.wxOConfiguration = {
    orchestrationID: "923deb9b5fdc4b26b9fc7ea936236e84_9ed64adf-22b8-493f-97d0-c882b6eb03ca",
    hostURL: "https://au-syd.watson-orchestrate.cloud.ibm.com",
    rootElementID: "root",
    deploymentPlatform: "ibmcloud",
    crn: "crn:v1:bluemix:public:watsonx-orchestrate:au-syd:a/923deb9b5fdc4b26b9fc7ea936236e84:9ed64adf-22b8-493f-97d0-c882b6eb03ca::",
    chatOptions: {
        agentId: "1cda7e11-cd38-4da4-bb99-02abc71c1617", 
    }
  };
  setTimeout(function () {
    const script = document.createElement('script');
    script.src = `${window.wxOConfiguration.hostURL}/wxochat/wxoLoader.js?embed=true`;
    script.addEventListener('load', function () {
        wxoLoader.init();
    });
    document.head.appendChild(script);
  }, 0);                     
</script>

<nav>
  <a class="nav-logo" href="#">
    <div class="nav-logo-icon">SB</div>
    <span class="nav-logo-text">Smart<span>Biz</span></span>
  </a>
  <ul class="nav-links">
    <li><a href="#ideas">Ideas</a></li>
    <li><a href="#how">How It Works</a></li>
    <li><a href="#stats">Results</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#faq">FAQ</a></li>
    <li><a href="#start" class="nav-cta">Get Started</a></li>
  </ul>
</nav>


<header class="hero" id="home">
  <div class="hero-bg-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>
  <div class="hero-content">
    <div class="hero-badge">
      <span class="hero-badge-dot"></span>
      Trusted by 50,000+ Entrepreneurs Worldwide
    </div>
    <h1>Turn Your <span class="grad">Smart Business Idea</span><br />Into a Thriving Empire</h1>
    <p class="hero-sub">Discover high-potential business ideas, get a step-by-step roadmap, access expert mentorship, and launch with confidence — all in one platform.</p>
    <div class="hero-btns">
      <a href="#ideas" class="btn btn-primary">Explore Ideas →</a>
      <a href="#how" class="btn btn-ghost">How It Works</a>
    </div>
    <div class="hero-metrics">
      <div class="hero-metric">
        <div class="hero-metric-num"><span class="count-up" data-target="50">0</span>K<span>+</span></div>
        <div class="hero-metric-lbl">Entrepreneurs</div>
      </div>
      <div class="hero-metric">
        <div class="hero-metric-num"><span class="count-up" data-target="120">0</span><span>+</span></div>
        <div class="hero-metric-lbl">Business Ideas</div>
      </div>
      <div class="hero-metric">
        <div class="hero-metric-num"><span class="count-up" data-target="98">0</span><span>%</span></div>
        <div class="hero-metric-lbl">Success Rate</div>
      </div>
      <div class="hero-metric">
        <div class="hero-metric-num">$<span class="count-up" data-target="2">0</span>B<span>+</span></div>
        <div class="hero-metric-lbl">Revenue Generated</div>
      </div>
    </div>
  </div>
</header>


<div class="trust-bar">
  <div class="marquee-track" id="marqueeTrack"></div>
</div>


<section id="ideas" class="ideas-section">
  <div class="center">
    <div class="section-chip">Business Ideas</div>
    <div class="section-title">6 Hottest Business Ideas of 2025</div>
    <p class="section-sub">Each idea is validated with market data, profitability analysis, and a clear launch roadmap. Click to learn more.</p>
  </div>
  <div class="ideas-grid" id="ideasGrid"></div>
</section>


<section id="how">
  <div class="center">
    <div class="section-chip">Process</div>
    <div class="section-title">From Idea to Income in 4 Steps</div>
    <p class="section-sub">Our proven framework takes you from concept to launch without the guesswork.</p>
  </div>
  <div class="steps-grid" id="stepsGrid"></div>
</section>


<section id="stats" class="stats-section">
  <div class="center">
    <div class="section-chip" style="background:rgba(59,130,212,0.2);color:#79b8ff">Results</div>
    <div class="section-title">Numbers That Speak for Themselves</div>
    <p class="section-sub" style="color:#8b949e;margin:0 auto 52px">Our platform has helped thousands of entrepreneurs build sustainable, profitable businesses.</p>
  </div>
  <div class="stats-grid" id="statsGrid"></div>
</section>


<section id="testimonials" class="testimonials-section">
  <div class="center">
    <div class="section-chip">Testimonials</div>
    <div class="section-title">Success Stories from Our Community</div>
    <p class="section-sub">Real entrepreneurs, real results — hear what our members have to say.</p>
  </div>
  <div class="testi-grid" id="testiGrid"></div>
</section>


<section id="pricing">
  <div class="center">
    <div class="section-chip">Pricing</div>
    <div class="section-title">Simple, Transparent Pricing</div>
    <p class="section-sub">No hidden fees. Choose the plan that fits your ambition.</p>
  </div>
  <div class="pricing-grid" id="pricingGrid"></div>
</section>


<section id="faq" class="faq-section">
  <div class="center">
    <div class="section-chip">FAQ</div>
    <div class="section-title">Frequently Asked Questions</div>
    <p class="section-sub">Everything you need to know before you launch your next big idea.</p>
  </div>
  <div class="faq-list" id="faqList"></div>
</section>


<section id="start" class="cta-section">
  <div class="cta-content">
    <h2>Ready to Launch Your Business?</h2>
    <p>Join 50,000+ smart entrepreneurs. Get your free business idea report today — no credit card required.</p>
    <div class="cta-input-row">
      <input class="cta-input" type="email" />
      <a href="#" class="btn btn-primary">Get Free Report →</a>
    </div>
  </div>
</section>


<footer>
  <div class="footer-top">
    <div>
      <div class="footer-brand-logo">
        <div class="logo-box">SB</div>
        <div class="logo-name">Smart<span>Biz</span></div>
      </div>
      <p class="footer-brand-desc">Empowering entrepreneurs worldwide with validated business ideas, expert mentorship, and proven frameworks since 2020.</p>
    </div>
    <div>
      <div class="footer-col-title">Platform</div>
      <ul class="footer-col-links">
        <li><a href="#">Business Ideas</a></li>
        <li><a href="#">Market Research</a></li>
        <li><a href="#">Launch Roadmap</a></li>
        <li><a href="#">Mentorship</a></li>
        <li><a href="#">Community</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-col-title">Company</div>
      <ul class="footer-col-links">
        <li><a href="#">About Us</a></li>
        <li><a href="#">Careers</a></li>
        <li><a href="#">Blog</a></li>
        <li><a href="#">Press</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-col-title">Legal</div>
      <ul class="footer-col-links">
        <li><a href="#">Privacy Policy</a></li>
        <li><a href="#">Terms of Service</a></li>
        <li><a href="#">Cookie Policy</a></li>
        <li><a href="#">Refund Policy</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <div class="footer-copy">© 2025 SmartBiz. All rights reserved.</div>
    <div class="footer-made">Made with IBM Bob</div>
  </div>
</footer>


<div class="modal-overlay" id="modalOverlay">
  <div class="modal-box">
    <div class="modal-head">
      <button class="modal-close-btn" id="modalClose">✕</button>
      <div class="modal-head-icon" id="mIcon"></div>
      <div class="modal-head-title" id="mTitle"></div>
      <div class="modal-head-sub" id="mSub"></div>
    </div>
    <div class="modal-body-pad">
      <div class="modal-detail-row"><span class="modal-detail-lbl">Startup Cost</span><span class="modal-detail-val" id="mCost"></span></div>
      <div class="modal-detail-row"><span class="modal-detail-lbl">Monthly Revenue Potential</span><span class="modal-detail-val" id="mRevenue"></span></div>
      <div class="modal-detail-row"><span class="modal-detail-lbl">Time to First Revenue</span><span class="modal-detail-val" id="mTime"></span></div>
      <div class="modal-detail-row"><span class="modal-detail-lbl">Difficulty Level</span><span class="modal-detail-val" id="mDiff"></span></div>
      <br />
      <div class="modal-desc-title">About This Idea</div>
      <div class="modal-desc-text" id="mDesc"></div>
    </div>
  </div>
</div>


</body>
</html>
