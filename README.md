<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CGT & Negative Gearing Reform Tool — Australian Federal Budget 2026–27</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #0B1F3A;
    --navy-mid: #132A4E;
    --navy-light: #1E3D6B;
    --gold: #C9973A;
    --gold-light: #E8B85A;
    --gold-pale: #FDF3E0;
    --red: #C0392B;
    --red-pale: #FDF0EE;
    --green: #1A6B45;
    --green-pale: #EAF5EF;
    --blue: #1A5FA8;
    --blue-pale: #EBF3FC;
    --amber: #A35C00;
    --amber-pale: #FFF8ED;
    --text: #0B1F3A;
    --text-mid: #3D5270;
    --text-light: #7B90A8;
    --border: #DDE4EF;
    --border-strong: #B8C6DB;
    --surface: #F7F9FC;
    --surface-mid: #EEF2F8;
    --white: #FFFFFF;
    --radius: 10px;
    --radius-lg: 16px;
    --shadow: 0 2px 12px rgba(11,31,58,0.08);
    --shadow-lg: 0 8px 32px rgba(11,31,58,0.12);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--surface);
    color: var(--text);
    font-size: 15px;
    line-height: 1.65;
    min-height: 100vh;
  }

  /* ── HEADER ── */
  .site-header {
    background: var(--navy);
    color: white;
    padding: 0;
    position: sticky;
    top: 0;
    z-index: 100;
    border-bottom: 2px solid var(--gold);
  }
  .header-inner {
    max-width: 1140px;
    margin: 0 auto;
    padding: 0 2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 64px;
    gap: 1rem;
  }
  .header-brand {
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .header-crest {
    width: 36px;
    height: 36px;
    background: var(--gold);
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'DM Serif Display', serif;
    font-size: 18px;
    color: var(--navy);
    font-weight: 700;
    flex-shrink: 0;
  }
  .header-title {
    font-family: 'DM Serif Display', serif;
    font-size: 17px;
    color: white;
    letter-spacing: -0.01em;
    line-height: 1.2;
  }
  .header-title span { color: var(--gold-light); }
  .header-badge {
    background: rgba(201,151,58,0.18);
    border: 1px solid rgba(201,151,58,0.4);
    color: var(--gold-light);
    font-size: 11px;
    font-weight: 500;
    padding: 3px 10px;
    border-radius: 100px;
    white-space: nowrap;
  }

  /* ── HERO ── */
  .hero {
    background: var(--navy-mid);
    border-bottom: 1px solid rgba(255,255,255,0.07);
    padding: 2.5rem 2rem;
  }
  .hero-inner {
    max-width: 1140px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 2rem;
    align-items: center;
  }
  .hero h1 {
    font-family: 'DM Serif Display', serif;
    font-size: 30px;
    color: white;
    letter-spacing: -0.02em;
    line-height: 1.2;
    margin-bottom: 0.5rem;
  }
  .hero h1 em { color: var(--gold-light); font-style: normal; }
  .hero p {
    color: rgba(255,255,255,0.6);
    font-size: 14px;
    max-width: 520px;
  }
  .hero-stats {
    display: flex;
    gap: 1.5rem;
    flex-shrink: 0;
  }
  .hero-stat {
    text-align: center;
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.1);
    border-radius: var(--radius);
    padding: 1rem 1.25rem;
    min-width: 110px;
  }
  .hero-stat-val {
    font-family: 'DM Serif Display', serif;
    font-size: 22px;
    color: var(--gold-light);
    display: block;
    line-height: 1;
    margin-bottom: 4px;
  }
  .hero-stat-label {
    font-size: 11px;
    color: rgba(255,255,255,0.5);
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }

  /* ── LAYOUT ── */
  .app-body {
    max-width: 1140px;
    margin: 0 auto;
    padding: 2rem;
    display: grid;
    grid-template-columns: 220px 1fr;
    gap: 2rem;
    align-items: start;
  }

  /* ── SIDEBAR NAV ── */
  .sidebar {
    position: sticky;
    top: 84px;
  }
  .nav-label {
    font-size: 10px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--text-light);
    margin-bottom: 8px;
    padding: 0 4px;
  }
  .nav-item {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px 14px;
    border-radius: var(--radius);
    cursor: pointer;
    font-size: 13.5px;
    color: var(--text-mid);
    font-weight: 400;
    border: none;
    background: transparent;
    width: 100%;
    text-align: left;
    transition: all 0.15s;
    margin-bottom: 2px;
  }
  .nav-item:hover { background: var(--surface-mid); color: var(--text); }
  .nav-item.active {
    background: var(--navy);
    color: white;
    font-weight: 500;
  }
  .nav-item .nav-icon {
    width: 28px;
    height: 28px;
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    flex-shrink: 0;
    background: rgba(255,255,255,0.1);
  }
  .nav-item:not(.active) .nav-icon { background: var(--surface-mid); }
  .nav-divider { height: 1px; background: var(--border); margin: 12px 0; }
  .nav-disclaimer {
    font-size: 11px;
    color: var(--text-light);
    line-height: 1.6;
    padding: 12px;
    background: var(--amber-pale);
    border-radius: var(--radius);
    border-left: 3px solid var(--gold);
    margin-top: 1rem;
  }
  .nav-disclaimer strong { color: var(--amber); display: block; margin-bottom: 2px; }

  /* ── MAIN CONTENT ── */
  .main { min-width: 0; }
  .panel { display: none; animation: fadeIn 0.2s ease; }
  .panel.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: translateY(0); } }

  /* ── SECTION HEADERS ── */
  .section-header {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 1.5rem;
  }
  .section-icon {
    width: 44px;
    height: 44px;
    background: var(--navy);
    border-radius: var(--radius);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    flex-shrink: 0;
    color: var(--gold-light);
  }
  .section-header h2 {
    font-family: 'DM Serif Display', serif;
    font-size: 22px;
    color: var(--text);
    letter-spacing: -0.02em;
    line-height: 1.2;
    margin-bottom: 3px;
  }
  .section-header p { font-size: 13.5px; color: var(--text-mid); line-height: 1.5; }

  /* ── CARDS ── */
  .card {
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    padding: 1.5rem;
    margin-bottom: 1.25rem;
    box-shadow: var(--shadow);
  }
  .card-title {
    font-family: 'DM Serif Display', serif;
    font-size: 17px;
    color: var(--text);
    letter-spacing: -0.01em;
    margin-bottom: 0.5rem;
  }
  .card-body { font-size: 13.5px; color: var(--text-mid); line-height: 1.7; }

  .callout {
    border-radius: var(--radius);
    padding: 1rem 1.25rem;
    font-size: 13px;
    line-height: 1.65;
    margin-bottom: 1rem;
    border-left: 4px solid;
  }
  .callout-info { background: var(--blue-pale); border-color: var(--blue); color: #0E3A68; }
  .callout-warn { background: var(--amber-pale); border-color: var(--gold); color: var(--amber); }
  .callout-danger { background: var(--red-pale); border-color: var(--red); color: #8B1A10; }
  .callout-success { background: var(--green-pale); border-color: var(--green); color: #0F4229; }
  .callout strong { font-weight: 600; display: block; margin-bottom: 2px; }

  /* ── REGIME GRID ── */
  .regime-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1rem;
    margin-bottom: 1.5rem;
  }
  .regime-card {
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    padding: 1.25rem;
    box-shadow: var(--shadow);
    position: relative;
    overflow: hidden;
  }
  .regime-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 4px;
  }
  .regime-card.era-precgt::before { background: #7B90A8; }
  .regime-card.era-nominal::before { background: #C0392B; }
  .regime-card.era-index::before { background: #1A5FA8; }
  .regime-card.era-discount::before { background: #1A6B45; }
  .regime-card.era-new::before { background: var(--gold); }
  .regime-card.era-company::before { background: #3D5270; }

  .regime-era-label {
    font-size: 10px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--text-light);
    margin-bottom: 6px;
  }
  .regime-card-title {
    font-family: 'DM Serif Display', serif;
    font-size: 16px;
    color: var(--text);
    margin-bottom: 8px;
  }
  .regime-desc { font-size: 12.5px; color: var(--text-mid); line-height: 1.65; }
  .regime-badge {
    display: inline-block;
    margin-top: 10px;
    font-size: 11px;
    font-weight: 500;
    padding: 3px 10px;
    border-radius: 100px;
    border: 1px solid;
  }
  .badge-exempt { background: #EAF5EF; color: var(--green); border-color: rgba(26,107,69,0.3); }
  .badge-full { background: var(--red-pale); color: var(--red); border-color: rgba(192,57,43,0.3); }
  .badge-idx { background: var(--blue-pale); color: var(--blue); border-color: rgba(26,95,168,0.3); }
  .badge-disc { background: var(--green-pale); color: var(--green); border-color: rgba(26,107,69,0.3); }
  .badge-new { background: #FEF9EE; color: var(--amber); border-color: rgba(201,151,58,0.4); }
  .badge-neutral { background: var(--surface-mid); color: var(--text-mid); border-color: var(--border); }
  .badge-change { background: var(--red-pale); color: var(--red); border-color: rgba(192,57,43,0.3); }

  /* ── TIMELINE ── */
  .timeline { margin-bottom: 1.5rem; }
  .timeline-item {
    display: flex;
    gap: 1rem;
    padding-bottom: 1.25rem;
    position: relative;
  }
  .timeline-item:not(:last-child)::after {
    content: '';
    position: absolute;
    left: 11px;
    top: 24px;
    bottom: 0;
    width: 2px;
    background: var(--border);
  }
  .timeline-dot {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    flex-shrink: 0;
    border: 3px solid var(--white);
    box-shadow: 0 0 0 2px currentColor;
    margin-top: 1px;
    z-index: 1;
  }
  .dot-blue { color: var(--blue); background: var(--blue); }
  .dot-amber { color: var(--gold); background: var(--gold); }
  .dot-red { color: var(--red); background: var(--red); }
  .dot-green { color: var(--green); background: var(--green); }
  .timeline-content {}
  .timeline-date { font-size: 12px; font-weight: 600; color: var(--text-light); margin-bottom: 2px; text-transform: uppercase; letter-spacing: 0.05em; }
  .timeline-title { font-size: 14px; font-weight: 600; color: var(--text); margin-bottom: 4px; }
  .timeline-body { font-size: 13px; color: var(--text-mid); line-height: 1.65; }

  /* ── CALCULATOR ── */
  .calc-card {
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    padding: 1.75rem;
    margin-bottom: 1.25rem;
    box-shadow: var(--shadow);
  }
  .calc-section-title {
    font-size: 12px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--text-light);
    margin-bottom: 1rem;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
  }
  .form-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
    margin-bottom: 1rem;
  }
  .form-grid-3 { grid-template-columns: 1fr 1fr 1fr; }
  .form-group { display: flex; flex-direction: column; gap: 6px; }
  .form-group label {
    font-size: 12px;
    font-weight: 500;
    color: var(--text-mid);
    letter-spacing: 0.01em;
  }
  .form-group input,
  .form-group select {
    padding: 9px 12px;
    font-size: 14px;
    font-family: 'DM Sans', sans-serif;
    border: 1px solid var(--border-strong);
    border-radius: var(--radius);
    background: var(--surface);
    color: var(--text);
    transition: border-color 0.15s, box-shadow 0.15s;
    outline: none;
    width: 100%;
  }
  .form-group input:focus,
  .form-group select:focus {
    border-color: var(--navy);
    box-shadow: 0 0 0 3px rgba(11,31,58,0.08);
    background: var(--white);
  }
  .form-hint { font-size: 11px; color: var(--text-light); line-height: 1.5; margin-top: 2px; }

  .calc-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 11px 24px;
    background: var(--navy);
    color: white;
    border: none;
    border-radius: var(--radius);
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    transition: background 0.15s, transform 0.1s;
    margin-top: 0.5rem;
  }
  .calc-btn:hover { background: var(--navy-light); }
  .calc-btn:active { transform: scale(0.98); }

  /* ── RESULTS ── */
  .results-section { margin-top: 1.5rem; }
  .results-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 1.25rem;
  }
  .metric-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1rem 1.1rem;
  }
  .metric-label { font-size: 11px; color: var(--text-light); margin-bottom: 6px; font-weight: 500; text-transform: uppercase; letter-spacing: 0.05em; line-height: 1.4; }
  .metric-value { font-family: 'DM Serif Display', serif; font-size: 24px; color: var(--text); letter-spacing: -0.02em; line-height: 1; }
  .metric-sub { font-size: 11.5px; color: var(--text-light); margin-top: 4px; }
  .metric-worse { color: var(--red); }
  .metric-better { color: var(--green); }
  .metric-neutral { color: var(--text); }

  .workings-box {
    background: var(--navy);
    border-radius: var(--radius-lg);
    padding: 1.5rem;
    color: rgba(255,255,255,0.85);
    font-family: 'DM Mono', monospace;
    font-size: 12.5px;
    line-height: 2;
  }
  .workings-box .wk-section {
    color: var(--gold-light);
    font-weight: 500;
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin-top: 1rem;
    margin-bottom: 2px;
    padding-top: 1rem;
    border-top: 1px solid rgba(255,255,255,0.1);
  }
  .workings-box .wk-section:first-child { margin-top: 0; padding-top: 0; border-top: none; }
  .workings-box .wk-line { display: flex; justify-content: space-between; gap: 2rem; }
  .workings-box .wk-key { color: rgba(255,255,255,0.6); }
  .workings-box .wk-val { color: white; font-weight: 500; white-space: nowrap; }
  .workings-box .wk-total {
    border-top: 1px solid rgba(255,255,255,0.2);
    padding-top: 4px;
    margin-top: 4px;
    color: var(--gold-light);
    font-weight: 500;
  }

  /* ── COMPARE TABLE ── */
  .compare-wrapper { overflow-x: auto; margin-bottom: 1.5rem; border-radius: var(--radius-lg); border: 1px solid var(--border); box-shadow: var(--shadow); }
  .compare-table { width: 100%; border-collapse: collapse; font-size: 13px; }
  .compare-table thead tr { background: var(--navy); }
  .compare-table th {
    padding: 12px 14px;
    text-align: left;
    font-size: 11px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.07em;
    color: rgba(255,255,255,0.7);
    white-space: nowrap;
  }
  .compare-table th:first-child { color: rgba(255,255,255,0.5); }
  .compare-table th.col-old { color: var(--gold-light); }
  .compare-table th.col-new { color: #F4A9A3; }
  .compare-table td {
    padding: 12px 14px;
    border-bottom: 1px solid var(--border);
    vertical-align: top;
    color: var(--text);
    font-size: 13px;
    line-height: 1.6;
  }
  .compare-table tr:last-child td { border-bottom: none; }
  .compare-table tr:nth-child(even) td { background: var(--surface); }
  .compare-table td:first-child { font-weight: 500; color: var(--text); font-size: 13px; }
  .compare-table td.col-old { background: #FFFBF2 !important; }
  .compare-table tr:nth-child(even) td.col-old { background: #FFF8E8 !important; }
  .compare-table td.col-new { background: #FFF8F8 !important; }
  .compare-table tr:nth-child(even) td.col-new { background: #FFEEED !important; }
  .tbl-badge {
    display: inline-block;
    padding: 2px 9px;
    border-radius: 100px;
    font-size: 11px;
    font-weight: 500;
    margin-bottom: 4px;
    border: 1px solid;
  }
  .tbl-ok { background: var(--green-pale); color: var(--green); border-color: rgba(26,107,69,0.25); }
  .tbl-bad { background: var(--red-pale); color: var(--red); border-color: rgba(192,57,43,0.25); }
  .tbl-neutral { background: var(--surface-mid); color: var(--text-mid); border-color: var(--border-strong); }
  .tbl-warn { background: var(--amber-pale); color: var(--amber); border-color: rgba(163,92,0,0.25); }

  .sub-heading {
    font-family: 'DM Serif Display', serif;
    font-size: 20px;
    color: var(--text);
    letter-spacing: -0.02em;
    margin-bottom: 1rem;
    margin-top: 1.5rem;
    padding-bottom: 8px;
    border-bottom: 2px solid var(--border);
  }
  .sub-heading:first-of-type { margin-top: 0; }

  /* ── SCENARIO NOTE ── */
  .scenario-note {
    border-radius: var(--radius);
    padding: 12px 16px;
    font-size: 13px;
    line-height: 1.6;
    margin-top: 1rem;
    border-left: 4px solid;
    display: none;
  }
  .scenario-note.show { display: block; }
  .sn-warn { background: var(--amber-pale); border-color: var(--gold); color: var(--amber); }
  .sn-danger { background: var(--red-pale); border-color: var(--red); color: #7A120B; }
  .sn-info { background: var(--blue-pale); border-color: var(--blue); color: #0E3A68; }
  .sn-success { background: var(--green-pale); border-color: var(--green); color: #0F4229; }

  /* ── FOOTNOTE ── */
  .footnote {
    font-size: 11px;
    color: var(--text-light);
    line-height: 1.65;
    margin-top: 1.25rem;
    padding-top: 1rem;
    border-top: 1px solid var(--border);
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 800px) {
    .app-body { grid-template-columns: 1fr; padding: 1rem; }
    .sidebar { position: static; }
    .nav-item { display: inline-flex; width: auto; }
    .hero-inner { grid-template-columns: 1fr; }
    .hero-stats { display: none; }
    .results-grid { grid-template-columns: 1fr 1fr; }
    .form-grid { grid-template-columns: 1fr; }
    .form-grid-3 { grid-template-columns: 1fr; }
  }

  .divider { height: 1px; background: var(--border); margin: 1.5rem 0; }

  select option { font-family: 'DM Sans', sans-serif; }
</style>
</head>
<body>

<!-- HEADER -->
<header class="site-header">
  <div class="header-inner">
    <div class="header-brand">
      <div class="header-crest">A</div>
      <div class="header-title">
        Australian Tax Reform Analyser<br>
        <span>CGT & Negative Gearing — Budget 2026–27</span>
      </div>
    </div>
    <div class="header-badge">Budget night: 12 May 2026</div>
  </div>
</header>

<!-- HERO -->
<div class="hero">
  <div class="hero-inner">
    <div>
      <h1>Capital Gains Tax &amp; Negative Gearing<br><em>Investor Impact Tool</em></h1>
      <p>Based on Treasurer Chalmers' 2026–27 Federal Budget announcements. For use by investors, advisers, and tax professionals. All calculations are estimates only and do not constitute tax advice.</p>
    </div>
    <div class="hero-stats">
      <div class="hero-stat">
        <span class="hero-stat-val">$3.6B</span>
        <span class="hero-stat-label">CGT + NG revenue</span>
      </div>
      <div class="hero-stat">
        <span class="hero-stat-val">1 Jul '27</span>
        <span class="hero-stat-label">New rules commence</span>
      </div>
      <div class="hero-stat">
        <span class="hero-stat-val">900K+</span>
        <span class="hero-stat-label">Trusts affected</span>
      </div>
    </div>
  </div>
</div>

<!-- APP BODY -->
<div class="app-body">

  <!-- SIDEBAR -->
  <aside class="sidebar">
    <div class="nav-label">Navigation</div>
    <button class="nav-item active" onclick="showPanel('history')">
      <span class="nav-icon">📜</span> Legislative History
    </button>
    <button class="nav-item" onclick="showPanel('cgt')">
      <span class="nav-icon">📈</span> CGT Calculator
    </button>
    <button class="nav-item" onclick="showPanel('ng')">
      <span class="nav-icon">🏠</span> Negative Gearing
    </button>
    <button class="nav-item" onclick="showPanel('compare')">
      <span class="nav-icon">⚖️</span> Side-by-Side Compare
    </button>
    <div class="nav-divider"></div>
    <div class="nav-disclaimer">
      <strong>Professional disclaimer</strong>
      All figures are illustrative estimates based on Budget announcements of 12 May 2026. Legislation not yet enacted. Seek advice from a registered tax agent.
    </div>
  </aside>

  <!-- MAIN -->
  <main class="main">

    <!-- PANEL: LEGISLATIVE HISTORY -->
    <div id="panel-history" class="panel active">
      <div class="section-header">
        <div class="section-icon">📜</div>
        <div>
          <h2>Legislative History — CGT &amp; Negative Gearing</h2>
          <p>Every regime since introduction, with the 2026–27 Budget changes in context.</p>
        </div>
      </div>

      <div class="callout callout-info">
        <strong>Why history matters</strong>
        The new CGT indexation regime is essentially a return to the 1992–1999 approach abandoned by John Howard. Understanding the mechanics of that era is essential to modelling the new rules correctly.
      </div>

      <div class="sub-heading">Capital Gains Tax — full regime history</div>
      <div class="regime-grid">
        <div class="regime-card era-precgt">
          <div class="regime-era-label">Pre — 20 Sep 1985</div>
          <div class="regime-card-title">No CGT</div>
          <div class="regime-desc">Capital gains from assets acquired before 20 September 1985 were fully exempt from income tax. These are commonly referred to as "pre-CGT assets". There was no discount, no indexation — simply exempt. Introduced by the Hawke government's 1985 Budget, CGT only applied to assets acquired from that date forward.</div>
          <span class="regime-badge badge-exempt">Fully exempt</span>
        </div>
        <div class="regime-card era-nominal">
          <div class="regime-era-label">20 Sep 1985 — 10 Aug 1992</div>
          <div class="regime-card-title">Nominal gain — full inclusion</div>
          <div class="regime-desc">CGT introduced under s.160 ITAA 1936 (now Pt 3-1 ITAA 1997). The full nominal capital gain (proceeds minus original cost base) was included in assessable income and taxed at the individual's marginal rate. No inflation relief. Companies and individuals treated symmetrically — no discount for either.</div>
          <span class="regime-badge badge-full">100% of gain — marginal rate</span>
        </div>
        <div class="regime-card era-index">
          <div class="regime-era-label">11 Aug 1992 — 20 Sep 1999</div>
          <div class="regime-card-title">Indexation regime (Keating)</div>
          <div class="regime-desc">Cost base indexed quarterly to CPI (base: September quarter 1985). Only real (inflation-adjusted) gains were taxable. Assets held less than 12 months: no indexation, full nominal gain assessed. Assets held 12+ months: cost base indexed; only the real gain assessable. Superannuation funds taxed at 2/3 of gain (effective ~15% on indexed gain for complying funds). Companies still received no discount.</div>
          <span class="regime-badge badge-idx">CPI-indexed cost base</span>
        </div>
        <div class="regime-card era-discount">
          <div class="regime-era-label">21 Sep 1999 — 30 Jun 2027</div>
          <div class="regime-card-title">50% discount (Ralph Review)</div>
          <div class="regime-desc">Howard government adopted the Ralph Review recommendation, replacing indexation with a flat 50% discount for individuals and trusts on assets held 12+ months. Superannuation funds: 33⅓% discount. Companies: no discount. Indexation frozen at 30 September 1999 CPI. Taxpayers with pre-1999 assets could elect indexation or the 50% discount — in practice nearly all elected the discount. This regime has operated for over 25 years.</div>
          <span class="regime-badge badge-disc">50% discount (individuals &amp; trusts)</span>
        </div>
        <div class="regime-card era-new" style="border: 2px solid var(--gold);">
          <div class="regime-era-label" style="color:var(--amber);">★ From 1 July 2027 — New Budget announcement</div>
          <div class="regime-card-title">CPI indexation + 30% minimum tax</div>
          <div class="regime-desc">50% CGT discount abolished for gains accruing from 1 July 2027. Replaced with CPI cost base indexation (akin to 1992–1999) plus a new 30% minimum tax on net capital gains after indexation. Applies to individuals, trusts, and partnerships. Pre-CGT assets (acquired before Sep 1985) brought into system for gains arising after 1 July 2027. Investors in new residential property may elect the old 50% discount instead. Income support recipients exempt from minimum tax. Superannuation fund CGT discount (33⅓%) confirmed unchanged.</div>
          <span class="regime-badge badge-new">CPI indexation + 30% minimum tax</span>
        </div>
        <div class="regime-card era-company">
          <div class="regime-era-label">All periods — Companies</div>
          <div class="regime-card-title">No CGT discount — all eras</div>
          <div class="regime-desc">Companies have never received a CGT discount in any regime. Capital gains are taxed at the applicable corporate rate (30% general rate; 25% for base rate entities with aggregated turnover &lt; $50M). No change under the 2026–27 Budget.</div>
          <span class="regime-badge badge-neutral">No change — 30%/25% rate</span>
        </div>
      </div>

      <div class="divider"></div>
      <div class="sub-heading">Negative Gearing — legislative history</div>

      <div class="card">
        <div class="timeline">
          <div class="timeline-item">
            <div class="timeline-dot dot-blue"></div>
            <div class="timeline-content">
              <div class="timeline-date">Pre-1985 – longstanding common law</div>
              <div class="timeline-title">Full deductibility — general income tax principles</div>
              <div class="timeline-body">Under s.51(1) ITAA 1936 (now s.8-1 ITAA 1997), all losses and outgoings necessarily incurred in gaining assessable income were deductible. Rental losses — including interest — were deductible against any income. Negative gearing had no specific statutory authority; it was a natural consequence of general deductibility principles applied to leveraged property investment. This had operated without restriction for decades prior to 1985.</div>
            </div>
          </div>
          <div class="timeline-item">
            <div class="timeline-dot dot-amber"></div>
            <div class="timeline-content">
              <div class="timeline-date">July 1985 — September 1987</div>
              <div class="timeline-title">Keating quarantining — brief and reversed</div>
              <div class="timeline-body">Treasurer Paul Keating quarantined rental losses in July 1985 (alongside the introduction of CGT), such that net rental losses could only be deducted against rental income — not other income. The policy had an immediate and severe contractionary effect on the rental market, particularly in Brisbane and Perth, where rents rose sharply and vacancy rates tightened. The measure was repealed in September 1987 by Keating himself, with full deductibility restored. This 1985–1987 episode is directly relevant to assessing the likely economic impact of the 2026 Budget changes.</div>
            </div>
          </div>
          <div class="timeline-item">
            <div class="timeline-dot dot-green"></div>
            <div class="timeline-content">
              <div class="timeline-date">September 1987 — 11 May 2026</div>
              <div class="timeline-title">Full negative gearing — unrestricted for all residential property</div>
              <div class="timeline-body">Net rental losses fully deductible against all income — salary, wages, business income, and other passive income. This applied to established and new residential dwellings alike. Approximately 2.5 million Australians claimed rental deductions in the 2022–23 income year. Around 83% of investor loans in 2025 were for established properties rather than new builds — the primary policy justification cited by Treasury for restricting negative gearing to new supply.</div>
            </div>
          </div>
          <div class="timeline-item">
            <div class="timeline-dot dot-red"></div>
            <div class="timeline-content">
              <div class="timeline-date">12 May 2026 (Budget night) — in force from 1 July 2027</div>
              <div class="timeline-title">New restrictions — established residential property only</div>
              <div class="timeline-body">For established residential properties contracted after 7:30pm AEST 12 May 2026: net rental losses ring-fenced to residential rental income only from 1 July 2027. Unused losses carry forward indefinitely and may be offset against future rental income or gains from the same or other residential rental properties — but cannot offset wages, salary, or business income. New builds: fully negatively gearable. Grandfathered: properties contracted before Budget night. Excluded: SMSFs, widely held trusts (incl. MITs), commercial property, shares, build-to-rent, private investors in government housing programs.</div>
            </div>
          </div>
        </div>
        <div class="callout callout-warn" style="margin-top:0">
          <strong>Key grandfathering dates</strong>
          CGT: gains accrued to 1 July 2027 remain taxed under the old 50% discount. The asset's market value at 30 June 2027 becomes the new cost base for gains accruing after that date.<br>
          Negative gearing: properties contracted (exchange of contracts) before 7:30pm AEST 12 May 2026 are grandfathered under existing rules indefinitely until the property is sold.
        </div>
      </div>
    </div>

    <!-- PANEL: CGT CALCULATOR -->
    <div id="panel-cgt" class="panel">
      <div class="section-header">
        <div class="section-icon">📈</div>
        <div>
          <h2>CGT Calculator — Before vs After 1 July 2027</h2>
          <p>Compare your capital gains tax liability under the old 50% discount regime and the new CPI indexation + 30% minimum tax. Australian resident individual taxpayer assumed.</p>
        </div>
      </div>

      <div class="calc-card">
        <div class="calc-section-title">Asset details</div>
        <div class="form-grid">
          <div class="form-group">
            <label>Asset type</label>
            <select id="cgt-assetType" onchange="calcCGT()">
              <option value="property_established">Residential property — established</option>
              <option value="property_new">Residential property — new build</option>
              <option value="shares">Shares / units / other capital assets</option>
              <option value="precgt">Pre-CGT asset (acquired before 20 Sep 1985)</option>
            </select>
          </div>
          <div class="form-group">
            <label>Acquisition timing</label>
            <select id="cgt-acqDate" onchange="calcCGT()">
              <option value="before_budget">Before 12 May 2026 (Budget night)</option>
              <option value="after_budget">After 12 May 2026 (Budget night)</option>
            </select>
          </div>
        </div>
        <div class="form-grid form-grid-3">
          <div class="form-group">
            <label>Cost base ($)</label>
            <input type="number" id="cgt-costBase" value="500000" min="0" oninput="calcCGT()">
            <span class="form-hint">Original cost incl. stamp duty, legal fees, and capital improvements</span>
          </div>
          <div class="form-group">
            <label>Sale proceeds ($)</label>
            <input type="number" id="cgt-proceeds" value="900000" min="0" oninput="calcCGT()">
            <span class="form-hint">Net proceeds after agent commission and selling costs</span>
          </div>
          <div class="form-group">
            <label>Holding period</label>
            <select id="cgt-holdPeriod" onchange="calcCGT()">
              <option value="less12">Less than 12 months</option>
              <option value="more12" selected>12 months or more</option>
            </select>
          </div>
        </div>

        <div class="calc-section-title" style="margin-top:1rem">Tax &amp; indexation assumptions</div>
        <div class="form-grid">
          <div class="form-group">
            <label>Marginal income tax rate (incl. Medicare levy)</label>
            <select id="cgt-margRate" onchange="calcCGT()">
              <option value="0.19">19% — $18,201–$45,000 (2026–27 rate post Budget)</option>
              <option value="0.325">32.5% — $45,001–$135,000</option>
              <option value="0.37" selected>37% — $135,001–$190,000</option>
              <option value="0.45">45% + 2% Medicare levy — above $190,000</option>
            </select>
          </div>
          <div class="form-group">
            <label>CPI indexation factor</label>
            <input type="number" id="cgt-cpiIdx" value="1.35" step="0.01" min="1" oninput="calcCGT()">
            <span class="form-hint">Factor to apply to cost base (e.g. 1.35 = 35% CPI increase since acquisition). ATO will publish official quarterly factors. Between 1985–1999 indexation was applied quarterly using CPI.</span>
          </div>
        </div>
        <div class="form-grid">
          <div class="form-group">
            <label>Intended sale date</label>
            <select id="cgt-saleDate" onchange="calcCGT()">
              <option value="before2027">Before 1 July 2027 — old 50% discount applies to entire gain</option>
              <option value="after2027" selected>After 1 July 2027 — new rules apply to post-2027 gain portion</option>
            </select>
          </div>
          <div class="form-group">
            <label>Entity type</label>
            <select id="cgt-entity" onchange="calcCGT()">
              <option value="individual">Individual</option>
              <option value="super">Superannuation fund (complying) — 33⅓% discount</option>
              <option value="company">Company — no CGT discount, all eras</option>
            </select>
          </div>
        </div>
        <button class="calc-btn" onclick="calcCGT()">⟳ Calculate CGT impact</button>
      </div>

      <div id="cgt-results" style="display:none">
        <div class="results-grid">
          <div class="metric-card">
            <div class="metric-label">Nominal capital gain</div>
            <div class="metric-value" id="cgt-r-nominal">—</div>
            <div class="metric-sub">Proceeds minus cost base</div>
          </div>
          <div class="metric-card">
            <div class="metric-label">CGT — old regime</div>
            <div class="metric-value metric-neutral" id="cgt-r-old">—</div>
            <div class="metric-sub" id="cgt-r-old-sub">Pre-1 July 2027</div>
          </div>
          <div class="metric-card">
            <div class="metric-label">CGT — new regime</div>
            <div class="metric-value" id="cgt-r-new">—</div>
            <div class="metric-sub" id="cgt-r-new-sub">Post-1 July 2027</div>
          </div>
          <div class="metric-card">
            <div class="metric-label">Additional tax (new vs old)</div>
            <div class="metric-value" id="cgt-r-diff">—</div>
            <div class="metric-sub" id="cgt-r-diff-sub">Impact of Budget changes</div>
          </div>
        </div>

        <div id="cgt-note" class="scenario-note"></div>

        <div style="margin-top:1.25rem">
          <div style="font-size:12px;font-weight:600;text-transform:uppercase;letter-spacing:0.08em;color:var(--text-light);margin-bottom:0.75rem;">Tax working — old vs new regime</div>
          <div class="workings-box" id="cgt-workings"></div>
        </div>

        <p class="footnote">Calculations are illustrative and based on Budget announcements of 12 May 2026. The ATO has not yet published CPI indexation factors for the new regime. The 30% minimum tax operates as a floor — where the taxpayer's marginal rate applied to the indexed gain exceeds 30%, the marginal rate prevails. Transitional treatment: for assets held through 1 July 2027, the asset's market value at 30 June 2027 acts as the new cost base; gains accrued to that date are taxed under existing 50% discount rules. This tool applies simplified calculations and does not account for prior-year capital losses, net investment income tax, or state-based taxes. Not a substitute for professional advice.</p>
      </div>
    </div>

    <!-- PANEL: NEGATIVE GEARING -->
    <div id="panel-ng" class="panel">
      <div class="section-header">
        <div class="section-icon">🏠</div>
        <div>
          <h2>Negative Gearing — Cash Flow Impact</h2>
          <p>Determine whether your property is affected and model the after-tax cash flow change from 1 July 2027.</p>
        </div>
      </div>

      <div class="callout callout-warn">
        <strong>Critical dividing line — 7:30pm AEST 12 May 2026</strong>
        The grandfathering rule applies at the time of exchange of contracts, not settlement. Properties under binding contract before that precise time are grandfathered under current rules indefinitely until sold. Settlement date is irrelevant.
      </div>

      <div class="calc-card">
        <div class="calc-section-title">Property &amp; investor details</div>
        <div class="form-grid">
          <div class="form-group">
            <label>Property / asset type</label>
            <select id="ng-propType" onchange="calcNG()">
              <option value="established">Established residential property</option>
              <option value="newbuild">New residential dwelling (new build)</option>
              <option value="commercial">Commercial property</option>
              <option value="shares">Shares / managed funds / other assets</option>
              <option value="btr">Build-to-rent development</option>
            </select>
          </div>
          <div class="form-group">
            <label>Contract date (exchange)</label>
            <select id="ng-contractDate" onchange="calcNG()">
              <option value="before">Before 7:30pm AEST 12 May 2026 (grandfathered)</option>
              <option value="after">After 7:30pm AEST 12 May 2026 (new rules apply)</option>
            </select>
          </div>
        </div>
        <div class="form-grid form-grid-3">
          <div class="form-group">
            <label>Gross annual rental income ($)</label>
            <input type="number" id="ng-rental" value="32000" min="0" oninput="calcNG()">
          </div>
          <div class="form-group">
            <label>Annual interest expense ($)</label>
            <input type="number" id="ng-interest" value="45000" min="0" oninput="calcNG()">
            <span class="form-hint">Loan interest on borrowings used to acquire the property</span>
          </div>
          <div class="form-group">
            <label>Other deductible expenses ($)</label>
            <input type="number" id="ng-other" value="8000" min="0" oninput="calcNG()">
            <span class="form-hint">Rates, insurance, agent fees, repairs, depreciation (Div 43 &amp; Div 40)</span>
          </div>
        </div>
        <div class="form-grid">
          <div class="form-group">
            <label>Marginal tax rate (incl. Medicare levy)</label>
            <select id="ng-margRate" onchange="calcNG()">
              <option value="0.19">19%</option>
              <option value="0.325">32.5%</option>
              <option value="0.37" selected>37%</option>
              <option value="0.45">45%</option>
            </select>
          </div>
          <div class="form-group">
            <label>Other residential rental properties (net income / loss) ($)</label>
            <input type="number" id="ng-otherrental" value="0" oninput="calcNG()">
            <span class="form-hint">Relevant because under new rules, losses offset against total rental income across all rental properties</span>
          </div>
        </div>
        <button class="calc-btn" onclick="calcNG()">⟳ Calculate negative gearing impact</button>
      </div>

      <div id="ng-results" style="display:none">
        <div id="ng-eligibility" class="callout" style="margin-bottom:1rem"></div>

        <div class="results-grid">
          <div class="metric-card">
            <div class="metric-label">Net rental result</div>
            <div class="metric-value" id="ng-r-netloss">—</div>
            <div class="metric-sub" id="ng-r-netloss-sub">—</div>
          </div>
          <div class="metric-card">
            <div class="metric-label">Tax saving — old rules</div>
            <div class="metric-value" id="ng-r-old">—</div>
            <div class="metric-sub">Loss × marginal rate</div>
          </div>
          <div class="metric-card">
            <div class="metric-label">Tax saving — new rules</div>
            <div class="metric-value" id="ng-r-new">—</div>
            <div class="metric-sub" id="ng-r-new-sub">—</div>
          </div>
          <div class="metric-card">
            <div class="metric-label">Annual impact</div>
            <div class="metric-value" id="ng-r-impact">—</div>
            <div class="metric-sub">Cash flow change per year</div>
          </div>
        </div>

        <div style="margin-top:1.25rem">
          <div style="font-size:12px;font-weight:600;text-transform:uppercase;letter-spacing:0.08em;color:var(--text-light);margin-bottom:0.75rem;">Working</div>
          <div class="workings-box" id="ng-workings"></div>
        </div>

        <p class="footnote">Negative gearing restrictions apply to established residential properties with exchange of contracts after 7:30pm AEST 12 May 2026, effective from 1 July 2027. Carry-forward losses accumulate indefinitely and may offset future residential rental income or gains from residential rental properties — but cannot shelter wages, salary, or business income. Positively and neutrally geared properties are unaffected. Commercial property, shares, managed funds, SMSFs, widely held trusts (including most MITs), build-to-rent, and government housing program investors are excluded from the restrictions. Seek advice from a registered tax agent for individual circumstances.</p>
      </div>
    </div>

    <!-- PANEL: COMPARE -->
    <div id="panel-compare" class="panel">
      <div class="section-header">
        <div class="section-icon">⚖️</div>
        <div>
          <h2>Side-by-Side Reference — Old vs New Rules</h2>
          <p>Comprehensive rule-by-rule comparison for advisers and investors. Based on Budget announcements only — legislation not yet enacted.</p>
        </div>
      </div>

      <div class="sub-heading">Capital Gains Tax</div>
      <div class="compare-wrapper">
        <table class="compare-table">
          <thead>
            <tr>
              <th style="width:26%">Issue</th>
              <th class="col-old" style="width:37%">Old rules — to 30 June 2027</th>
              <th class="col-new" style="width:37%">New rules — from 1 July 2027</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>CGT discount — individuals &amp; trusts<br><small style="color:var(--text-light);font-weight:400">Assets held ≥ 12 months</small></td>
              <td class="col-old"><span class="tbl-badge tbl-ok">50% discount</span><br>Assessable gain = 50% of nominal gain. Remainder permanently excluded from assessable income. No inflation adjustment.</td>
              <td class="col-new"><span class="tbl-badge tbl-bad">50% discount abolished</span><br>Replaced with CPI cost base indexation. Only the real (above-inflation) gain is assessable. 30% minimum tax applied to the indexed gain.</td>
            </tr>
            <tr>
              <td>Companies</td>
              <td class="col-old"><span class="tbl-badge tbl-neutral">No discount</span><br>Full nominal gain taxed at corporate rate (30% or 25% SBE). This has applied in all eras.</td>
              <td class="col-new"><span class="tbl-badge tbl-ok">No change</span><br>Companies are unaffected by the new regime. Full gain taxed at corporate rate as before.</td>
            </tr>
            <tr>
              <td>Superannuation funds<br><small style="color:var(--text-light);font-weight:400">Incl. SMSFs — accumulation phase</small></td>
              <td class="col-old"><span class="tbl-badge tbl-ok">33⅓% discount</span><br>Effective CGT rate ~10% on gain for complying fund in accumulation phase. Pension phase: fully exempt.</td>
              <td class="col-new"><span class="tbl-badge tbl-ok">No change — confirmed</span><br>Government has confirmed the 33⅓% superannuation discount is not changing. SMSFs and complying funds retain current treatment.</td>
            </tr>
            <tr>
              <td>30% minimum tax floor</td>
              <td class="col-old"><span class="tbl-badge tbl-neutral">No minimum tax</span><br>Low-income earners could pay 0% on the discounted gain if within the tax-free threshold. No floor.</td>
              <td class="col-new"><span class="tbl-badge tbl-bad">30% minimum — new</span><br>After indexation applied, minimum 30% tax on net capital gain. If marginal rate produces a higher effective rate on the indexed gain, marginal rate prevails. Income support recipients exempt.</td>
            </tr>
            <tr>
              <td>Pre-CGT assets<br><small style="color:var(--text-light);font-weight:400">Acquired before 20 Sep 1985</small></td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Fully exempt</span><br>All capital gains on pre-CGT assets are exempt regardless of quantum. This has been the position since CGT was introduced in 1985.</td>
              <td class="col-new"><span class="tbl-badge tbl-bad">Partially brought into CGT</span><br>Gains accrued to 1 July 2027 remain exempt. Gains accruing from 1 July 2027 onwards subject to new regime. Market value at 1 July 2027 becomes the new cost base for these assets.</td>
            </tr>
            <tr>
              <td>New residential property<br><small style="color:var(--text-light);font-weight:400">Acquired post Budget night</small></td>
              <td class="col-old"><span class="tbl-badge tbl-ok">50% discount</span><br>Standard 50% discount applies to eligible new builds held 12+ months.</td>
              <td class="col-new"><span class="tbl-badge tbl-ok">Investor's choice on disposal</span><br>May elect either the 50% CGT discount (old rules) or CPI indexation + 30% minimum tax (new rules) at time of disposal. Designed to incentivise investment in new housing supply.</td>
            </tr>
            <tr>
              <td>Main residence exemption</td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Full exemption</span><br>Principal place of residence fully exempt from CGT (with partial exceptions for rental use, large land, etc.).</td>
              <td class="col-new"><span class="tbl-badge tbl-ok">No change — fully retained</span><br>Main residence exemption is unchanged. No impact on owner-occupiers.</td>
            </tr>
            <tr>
              <td>Transitional arrangement</td>
              <td class="col-old">N/A</td>
              <td class="col-new"><span class="tbl-badge tbl-warn">Transitional split</span><br>For assets held at 1 July 2027 and sold after: the 50% discount applies to gains accrued to that date (based on market value at 30 June 2027). New rules (indexation + min tax) apply only to gains accruing post-1 July 2027. Requires valuation at 30 June 2027.</td>
            </tr>
            <tr>
              <td>Rollover relief</td>
              <td class="col-old">Standard CGT rollovers apply (scrip-for-scrip, marriage breakdown, deceased estates, etc.)</td>
              <td class="col-new"><span class="tbl-badge tbl-ok">Expanded rollover — 3 years</span><br>Additional rollover relief available from 1 July 2027 to 30 June 2030 to facilitate restructuring out of discretionary trusts and other entities.</td>
            </tr>
          </tbody>
        </table>
      </div>

      <div class="sub-heading">Negative Gearing</div>
      <div class="compare-wrapper">
        <table class="compare-table">
          <thead>
            <tr>
              <th style="width:26%">Asset / scenario</th>
              <th class="col-old" style="width:37%">Old rules — existing owners / pre-Budget night</th>
              <th class="col-new" style="width:37%">New rules — established property contracted post Budget night</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Established residential — new purchase<br><small style="color:var(--text-light);font-weight:400">Contracted after 7:30pm AEST 12 May 2026</small></td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Full deductibility</span><br>Net rental losses fully deductible against all income including salary and wages under s.8-1 ITAA 1997.</td>
              <td class="col-new"><span class="tbl-badge tbl-bad">Ring-fenced from 1 Jul 2027</span><br>Rental losses deductible only against total rental income (across all residential properties). Unused losses carry forward indefinitely. Cannot offset wages, salary, or business income.</td>
            </tr>
            <tr>
              <td>Existing property holdings<br><small style="color:var(--text-light);font-weight:400">Contracted before 7:30pm AEST 12 May 2026</small></td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Full deductibility — grandfathered</span><br>Existing investors retain full negative gearing indefinitely until the property is disposed of.</td>
              <td class="col-new"><span class="tbl-badge tbl-ok">Grandfathered — no change</span><br>No change to existing investors. Grandfathering applies at the contract date (exchange), not settlement. A property under contract before Budget night is protected even if settled later.</td>
            </tr>
            <tr>
              <td>New residential dwellings<br><small style="color:var(--text-light);font-weight:400">Eligible new builds</small></td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Full deductibility</span></td>
              <td class="col-new"><span class="tbl-badge tbl-ok">Full deductibility retained</span><br>New builds are exempt from ring-fencing restrictions. Fully negatively gearable against all income. An integrity rule ensures the exemption applies only where net new dwellings are added to housing stock.</td>
            </tr>
            <tr>
              <td>Commercial property</td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Full deductibility</span></td>
              <td class="col-new"><span class="tbl-badge tbl-ok">No change — fully deductible</span><br>Commercial property is entirely outside the new restrictions. Losses deductible against all income as before.</td>
            </tr>
            <tr>
              <td>Shares, managed funds, other assets</td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Full deductibility</span></td>
              <td class="col-new"><span class="tbl-badge tbl-ok">No change — fully deductible</span><br>Investment in shares, ETFs, managed funds, and other non-property assets are unaffected. Margin loan interest and other investment losses remain deductible against all income.</td>
            </tr>
            <tr>
              <td>SMSFs &amp; widely held trusts<br><small style="color:var(--text-light);font-weight:400">Incl. MITs, REITs</small></td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Full deductibility</span></td>
              <td class="col-new"><span class="tbl-badge tbl-ok">Excluded — no change</span><br>SMSFs and widely held trusts (including most managed investment trusts) are explicitly excluded from the ring-fencing rules. Existing treatment preserved.</td>
            </tr>
            <tr>
              <td>Build-to-rent developments</td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Full deductibility</span></td>
              <td class="col-new"><span class="tbl-badge tbl-ok">Exempt — full deductibility</span><br>Build-to-rent developments receive a specific exemption. Negative gearing fully available.</td>
            </tr>
            <tr>
              <td>Carry-forward of unused losses</td>
              <td class="col-old"><span class="tbl-badge tbl-ok">Deductible in year incurred</span><br>Losses offset in the income year they are incurred — no carry-forward required.</td>
              <td class="col-new"><span class="tbl-badge tbl-warn">Carry-forward only for affected properties</span><br>Unused losses accumulate and carry forward indefinitely. May offset future residential rental income or rental gains. Cannot offset salary, wages, or business income in any future year.</td>
            </tr>
            <tr>
              <td>Positive / neutral gearing</td>
              <td class="col-old"><span class="tbl-badge tbl-neutral">Rental income assessed normally</span></td>
              <td class="col-new"><span class="tbl-badge tbl-neutral">No impact</span><br>Properties that are neutrally or positively geared are completely unaffected by the new restrictions.</td>
            </tr>
          </tbody>
        </table>
      </div>

      <div class="callout callout-warn">
        <strong>Discretionary trusts — 30% minimum tax (from 1 July 2028)</strong>
        While not CGT or negative gearing per se, this closely interacts with both measures for property investors using family trust structures. From 1 July 2028, a 30% minimum tax applies at the trustee level on the taxable income of discretionary trusts — neutralising income-splitting strategies. Non-refundable credits flow to beneficiaries. Expanded rollover relief (1 July 2027 – 30 June 2030) is available for restructuring out of discretionary trusts. Excluded: fixed and widely held trusts, complying super funds, special disability trusts, deceased estates, charitable trusts, primary production income, income relating to vulnerable minors.
      </div>

      <p class="footnote">This reference guide is based on Budget announcements of 12 May 2026 only. All measures require legislation before they become law. The ATO has not yet released guidance on the CPI indexation methodology for the new CGT regime. Design of the 30% minimum tax on capital gains and its interaction with the existing CGT framework remains subject to further consultation and legislative drafting. This tool does not constitute legal, tax, or financial advice. © Budget 2026–27 — always refer clients to seek individual advice from a registered tax agent or legal practitioner.</p>
    </div>

  </main>
</div>

<script>
function showPanel(id) {
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(b => b.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  const map = { history: 0, cgt: 1, ng: 2, compare: 3 };
  document.querySelectorAll('.nav-item')[map[id]].classList.add('active');
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

function fmt(n) {
  const abs = Math.abs(Math.round(n));
  const str = '$' + abs.toLocaleString('en-AU');
  return n < 0 ? '-' + str : str;
}
function pct(n) { return (Math.round(n * 1000) / 10).toFixed(1) + '%'; }

function wkLine(key, val, cls) {
  return `<div class="wk-line${cls ? ' ' + cls : ''}"><span class="wk-key">${key}</span><span class="wk-val">${val}</span></div>`;
}

function calcCGT() {
  const assetType = document.getElementById('cgt-assetType').value;
  const acqDate = document.getElementById('cgt-acqDate').value;
  const costBase = parseFloat(document.getElementById('cgt-costBase').value) || 0;
  const proceeds = parseFloat(document.getElementById('cgt-proceeds').value) || 0;
  const holdPeriod = document.getElementById('cgt-holdPeriod').value;
  const margRate = parseFloat(document.getElementById('cgt-margRate').value);
  const cpiIdx = parseFloat(document.getElementById('cgt-cpiIdx').value) || 1;
  const saleDate = document.getElementById('cgt-saleDate').value;
  const entity = document.getElementById('cgt-entity').value;

  document.getElementById('cgt-results').style.display = 'block';

  const nominalGain = proceeds - costBase;
  document.getElementById('cgt-r-nominal').textContent = fmt(nominalGain);

  let oldTax = 0, newTax = 0, oldHtml = '', newHtml = '', noteText = '', noteCls = '';

  // Determine discount for entity type
  let discountRate = 0.5;
  if (entity === 'super') discountRate = 1 / 3;
  if (entity === 'company') discountRate = 0;

  // ── OLD RULES ──
  if (entity === 'company') {
    const corpRate = 0.30;
    oldTax = nominalGain > 0 ? nominalGain * corpRate : 0;
    oldHtml = `<div class="wk-section">Old rules — company (no CGT discount, all eras)</div>`;
    oldHtml += wkLine('Nominal gain', fmt(nominalGain));
    oldHtml += wkLine('CGT discount', 'Nil — companies receive no CGT discount');
    oldHtml += wkLine('Assessable gain', fmt(nominalGain));
    oldHtml += wkLine('Corporate tax rate', pct(corpRate));
    oldHtml += wkLine('Tax payable', fmt(oldTax), 'wk-total');
  } else if (assetType === 'precgt' && saleDate === 'before2027') {
    oldTax = 0;
    oldHtml = `<div class="wk-section">Old rules — pre-CGT asset sold before 1 July 2027</div>`;
    oldHtml += wkLine('Treatment', 'Gain fully exempt — pre-CGT asset');
    oldHtml += wkLine('Tax payable', '$0', 'wk-total');
  } else if (holdPeriod === 'less12') {
    oldTax = nominalGain > 0 ? nominalGain * margRate : 0;
    oldHtml = `<div class="wk-section">Old rules — short-term hold (&lt;12 months, no discount)</div>`;
    oldHtml += wkLine('Nominal gain', fmt(nominalGain));
    oldHtml += wkLine('CGT discount', 'Nil — holding period &lt; 12 months');
    oldHtml += wkLine('Assessable gain (100%)', fmt(nominalGain));
    oldHtml += wkLine('Marginal rate', pct(margRate));
    oldHtml += wkLine('Tax payable', fmt(oldTax), 'wk-total');
  } else {
    const discountedGain = nominalGain * (1 - discountRate);
    oldTax = discountedGain > 0 ? discountedGain * margRate : 0;
    const discLabel = entity === 'super' ? '33⅓% (superannuation fund)' : '50% (individual / trust)';
    oldHtml = `<div class="wk-section">Old rules — ${entity === 'super' ? '33⅓%' : '50%'} CGT discount regime</div>`;
    oldHtml += wkLine('Nominal gain', fmt(nominalGain));
    oldHtml += wkLine('CGT discount applied', discLabel);
    oldHtml += wkLine('Assessable gain (after discount)', fmt(discountedGain));
    oldHtml += wkLine('Marginal rate', pct(margRate));
    oldHtml += wkLine('Tax payable', fmt(oldTax));
    oldHtml += wkLine('Effective rate on nominal gain', pct(oldTax / Math.max(1, nominalGain)), 'wk-total');
  }

  // ── NEW RULES ──
  if (entity === 'company') {
    newTax = oldTax;
    newHtml = `<div class="wk-section">New rules — company (unchanged)</div>`;
    newHtml += wkLine('No change', 'Company CGT treatment is unaffected by Budget measures');
    newHtml += wkLine('Tax payable', fmt(newTax), 'wk-total');
    noteText = 'Company taxpayers are not affected by the 2026–27 CGT changes.';
    noteCls = 'sn-info';
  } else if (entity === 'super') {
    newTax = oldTax;
    newHtml = `<div class="wk-section">New rules — superannuation fund (confirmed unchanged)</div>`;
    newHtml += wkLine('Status', 'Government confirmed super fund 33⅓% CGT discount is not changing');
    newHtml += wkLine('Tax payable', fmt(newTax), 'wk-total');
    noteText = 'Superannuation funds (including SMSFs) retain the existing 33⅓% CGT discount. No change.';
    noteCls = 'sn-success';
  } else if (saleDate === 'before2027') {
    newTax = oldTax;
    newHtml = `<div class="wk-section">New rules — sale before 1 July 2027 (old regime applies)</div>`;
    newHtml += wkLine('Status', 'Entire gain taxed under existing 50% discount — new rules not yet in force');
    newHtml += wkLine('Tax payable', fmt(newTax), 'wk-total');
    noteText = 'Selling before 1 July 2027 means the old 50% CGT discount applies to the full gain. The new regime does not apply.';
    noteCls = 'sn-success';
  } else if (assetType === 'property_new' && acqDate === 'after_budget') {
    // New build — investor may elect better of two
    const discountedGain = nominalGain * 0.5;
    const oldStyleTax = discountedGain > 0 ? discountedGain * margRate : 0;
    const indexedCB = costBase * cpiIdx;
    const realGain = Math.max(0, proceeds - indexedCB);
    const minTax = realGain * 0.30;
    const margTax = realGain * margRate;
    const newStyleTax = Math.max(minTax, margTax);
    const betterOld = oldStyleTax <= newStyleTax;
    newTax = Math.min(oldStyleTax, newStyleTax);
    newHtml = `<div class="wk-section">New rules — new build (investor may ELECT better treatment)</div>`;
    newHtml += wkLine('Option A — 50% discount (old rules)', '');
    newHtml += wkLine('  Assessable gain (50%)', fmt(discountedGain));
    newHtml += wkLine('  Tax @ ' + pct(margRate), fmt(oldStyleTax));
    newHtml += wkLine('Option B — CPI indexation + 30% min tax (new rules)', '');
    newHtml += wkLine('  Indexed cost base (×' + cpiIdx + ')', fmt(indexedCB));
    newHtml += wkLine('  Real gain (above inflation)', fmt(realGain));
    newHtml += wkLine('  30% minimum tax', fmt(minTax));
    newHtml += wkLine('  Tax @ marginal ' + pct(margRate), fmt(margTax));
    newHtml += wkLine('  Tax payable (higher of min / marginal)', fmt(newStyleTax));
    newHtml += wkLine('Better outcome — elect ' + (betterOld ? 'Option A (50% discount)' : 'Option B (indexation)'), fmt(newTax), 'wk-total');
    noteText = 'New residential property: you may elect the more favourable treatment at time of disposal. This calculator shows the lower-tax option.';
    noteCls = 'sn-info';
  } else if (assetType === 'precgt') {
    // Pre-CGT: sold after 1 July 2027 — gains to 30 June 2027 exempt, post-2027 gains in new regime
    const indexedCB = costBase * cpiIdx;
    const realGain = Math.max(0, proceeds - indexedCB);
    const minTax = realGain * 0.30;
    const margTax = realGain * margRate;
    newTax = Math.max(minTax, margTax);
    newHtml = `<div class="wk-section">New rules — pre-CGT asset sold after 1 July 2027</div>`;
    newHtml += wkLine('Pre-2027 gain', 'Exempt (50% discount applied to gain accrued to 30 Jun 2027)');
    newHtml += wkLine('Post-1 Jul 2027 gain', 'Assessed under new regime (market value at 30 Jun 2027 = new cost base)');
    newHtml += wkLine('CPI-indexed cost base (×' + cpiIdx + ')', fmt(indexedCB));
    newHtml += wkLine('Real gain above inflation', fmt(realGain));
    newHtml += wkLine('30% minimum tax on real gain', fmt(minTax));
    newHtml += wkLine('Tax @ marginal rate ' + pct(margRate), fmt(margTax));
    newHtml += wkLine('Tax payable (higher of min / marginal)', fmt(newTax), 'wk-total');
    newHtml += wkLine('Note', 'Simplified — full gain shown. Actual split requires MV at 30 Jun 2027.');
    noteText = 'Pre-CGT assets acquired before 20 September 1985 are partially brought into the CGT system. Gains accrued to 1 July 2027 remain exempt; gains accruing after that date are subject to the new indexation + 30% minimum tax regime. A market valuation at 30 June 2027 will be required.';
    noteCls = 'sn-warn';
  } else if (holdPeriod === 'less12') {
    const minTax = nominalGain * 0.30;
    const margTax = nominalGain * margRate;
    newTax = Math.max(minTax, margTax);
    newHtml = `<div class="wk-section">New rules — short-term hold (&lt;12 months, no indexation)</div>`;
    newHtml += wkLine('Indexation', 'Not available — must hold ≥ 12 months');
    newHtml += wkLine('Assessable gain (full nominal)', fmt(nominalGain));
    newHtml += wkLine('30% minimum tax', fmt(minTax));
    newHtml += wkLine('Tax @ marginal rate ' + pct(margRate), fmt(margTax));
    newHtml += wkLine('Tax payable (higher of min / marginal)', fmt(newTax), 'wk-total');
  } else {
    const indexedCB = costBase * cpiIdx;
    const inflationComponent = Math.max(0, indexedCB - costBase);
    const realGain = Math.max(0, proceeds - indexedCB);
    const minTax = realGain * 0.30;
    const margTax = realGain * margRate;
    newTax = Math.max(minTax, margTax);
    newHtml = `<div class="wk-section">New rules — CPI indexation + 30% minimum tax</div>`;
    newHtml += wkLine('Original cost base', fmt(costBase));
    newHtml += wkLine('CPI indexation factor', '×' + cpiIdx);
    newHtml += wkLine('CPI-indexed cost base', fmt(indexedCB));
    newHtml += wkLine('Inflation component (excluded)', fmt(inflationComponent));
    newHtml += wkLine('Proceeds', fmt(proceeds));
    newHtml += wkLine('Real (inflation-adjusted) gain', fmt(realGain));
    newHtml += wkLine('30% minimum tax on real gain', fmt(minTax));
    newHtml += wkLine('Tax @ marginal rate ' + pct(margRate) + ' on real gain', fmt(margTax));
    newHtml += wkLine('Tax payable (higher of min / marginal)', fmt(newTax));
    newHtml += wkLine('Effective rate on nominal gain', pct(newTax / Math.max(1, nominalGain)), 'wk-total');
  }

  const diff = newTax - oldTax;
  document.getElementById('cgt-r-old').textContent = fmt(oldTax);
  document.getElementById('cgt-r-new').textContent = fmt(newTax);
  const diffEl = document.getElementById('cgt-r-diff');
  diffEl.textContent = (diff >= 0 ? '+' : '') + fmt(diff);
  diffEl.className = 'metric-value ' + (diff > 500 ? 'metric-worse' : diff < -500 ? 'metric-better' : 'metric-neutral');
  document.getElementById('cgt-r-diff-sub').textContent = diff > 0 ? 'More tax under new rules' : diff < 0 ? 'Less tax under new rules' : 'No change';

  document.getElementById('cgt-workings').innerHTML = oldHtml + newHtml;

  const noteEl = document.getElementById('cgt-note');
  if (noteText) {
    noteEl.textContent = noteText;
    noteEl.className = 'scenario-note show ' + noteCls;
  } else {
    noteEl.className = 'scenario-note';
  }
}

function calcNG() {
  const propType = document.getElementById('ng-propType').value;
  const contractDate = document.getElementById('ng-contractDate').value;
  const rental = parseFloat(document.getElementById('ng-rental').value) || 0;
  const interest = parseFloat(document.getElementById('ng-interest').value) || 0;
  const other = parseFloat(document.getElementById('ng-other').value) || 0;
  const margRate = parseFloat(document.getElementById('ng-margRate').value);
  const otherRental = parseFloat(document.getElementById('ng-otherrental').value) || 0;

  document.getElementById('ng-results').style.display = 'block';

  const totalExpenses = interest + other;
  const netRental = rental - totalExpenses;
  const isLoss = netRental < 0;
  const lossAmt = Math.abs(Math.min(0, netRental));

  document.getElementById('ng-r-netloss').textContent = fmt(netRental);
  document.getElementById('ng-r-netloss-sub').textContent = isLoss ? 'Negatively geared' : netRental === 0 ? 'Neutrally geared' : 'Positively geared';

  const eligEl = document.getElementById('ng-eligibility');
  let affected = false;
  let eligText = '', eligCls = '';

  if (propType === 'newbuild' || propType === 'commercial' || propType === 'shares' || propType === 'btr') {
    affected = false;
    eligText = '✓ This asset class is NOT affected by the new negative gearing restrictions. Full deductibility of net losses against all income — including salary and wages — is retained under both old and new rules.';
    eligCls = 'callout callout-success';
  } else if (contractDate === 'before') {
    affected = false;
    eligText = '✓ This property is GRANDFATHERED. It was contracted (exchange of contracts) before 7:30pm AEST 12 May 2026. Existing negative gearing rules apply in full until the property is sold or otherwise disposed of. No change to your current tax position.';
    eligCls = 'callout callout-success';
  } else {
    affected = true;
    eligText = '⚠ This property IS AFFECTED. It is an established residential property contracted after Budget night (7:30pm AEST 12 May 2026). From 1 July 2027, net rental losses may only be deducted against residential rental income — not against wages, salary, or business income. Unused losses carry forward indefinitely.';
    eligCls = 'callout callout-danger';
  }
  eligEl.className = eligCls;
  eligEl.textContent = eligText;

  let oldSaving = 0, newSaving = 0, newSubLabel = '', workingsHtml = '';

  workingsHtml += `<div class="wk-section">Rental income &amp; expenses</div>`;
  workingsHtml += wkLine('Gross rental income', fmt(rental));
  workingsHtml += wkLine('Interest expense', fmt(interest));
  workingsHtml += wkLine('Other deductible expenses', fmt(other));
  workingsHtml += wkLine('Net rental result', fmt(netRental), 'wk-total');

  if (isLoss) {
    oldSaving = lossAmt * margRate;
    workingsHtml += `<div class="wk-section">Old rules — full deductibility against all income</div>`;
    workingsHtml += wkLine('Net rental loss', fmt(lossAmt));
    workingsHtml += wkLine('Deductible against', 'Salary, wages, and all other income');
    workingsHtml += wkLine('Tax saving @ ' + pct(margRate), fmt(oldSaving), 'wk-total');

    if (!affected) {
      newSaving = oldSaving;
      newSubLabel = 'Not affected — same as old rules';
      workingsHtml += `<div class="wk-section">New rules — not affected (grandfathered / exempt asset class)</div>`;
      workingsHtml += wkLine('Status', 'Existing deductibility retained in full');
      workingsHtml += wkLine('Tax saving', fmt(newSaving), 'wk-total');
    } else {
      // Under new rules: loss can offset against all residential rental income
      const totalRentalIncome = rental + otherRental;
      const netRentalPool = totalRentalIncome - totalExpenses;
      if (netRentalPool >= 0) {
        // Other rental income absorbs the loss — no carry-forward
        newSaving = 0;
        newSubLabel = 'Loss absorbed by rental income pool — no salary offset';
        workingsHtml += `<div class="wk-section">New rules — ring-fenced (from 1 July 2027)</div>`;
        workingsHtml += wkLine('Loss this property', fmt(lossAmt));
        workingsHtml += wkLine('Other rental income pool', fmt(otherRental));
        workingsHtml += wkLine('Net rental pool result', fmt(netRentalPool));
        workingsHtml += wkLine('Result', 'Loss absorbed — no current-year salary offset, no carry-forward');
        workingsHtml += wkLine('Loss deductible against wages/salary', '$0', 'wk-total');
      } else {
        // Residual loss remains undeductible against salary in current year
        const residualLoss = Math.abs(netRentalPool);
        newSaving = 0;
        newSubLabel = `$${Math.round(residualLoss).toLocaleString('en-AU')} loss carried forward`;
        workingsHtml += `<div class="wk-section">New rules — ring-fenced (from 1 July 2027)</div>`;
        workingsHtml += wkLine('Loss this property', fmt(lossAmt));
        workingsHtml += wkLine('Other residential rental income', fmt(Math.max(0, otherRental)));
        workingsHtml += wkLine('Net rental pool result', fmt(netRentalPool));
        workingsHtml += wkLine('Loss deductible against wages/salary', '$0');
        workingsHtml += wkLine('Loss carried forward to future rental income', fmt(residualLoss), 'wk-total');
      }
    }
  } else {
    oldSaving = 0; newSaving = 0;
    newSubLabel = 'Not applicable — property is positively geared';
    workingsHtml += `<div class="wk-section">Property is positively / neutrally geared</div>`;
    workingsHtml += wkLine('Status', 'Positive rental income — restrictions do not apply');
    workingsHtml += wkLine('Rental income assessable at', pct(margRate) + ' marginal rate');
  }

  const impact = newSaving - oldSaving;
  document.getElementById('ng-r-old').textContent = fmt(oldSaving);
  document.getElementById('ng-r-new').textContent = fmt(newSaving);
  document.getElementById('ng-r-new-sub').textContent = newSubLabel;
  const impEl = document.getElementById('ng-r-impact');
  impEl.textContent = (impact >= 0 ? '+' : '') + fmt(impact) + '/yr';
  impEl.className = 'metric-value ' + (impact < -10 ? 'metric-worse' : impact > 10 ? 'metric-better' : 'metric-neutral');

  document.getElementById('ng-workings').innerHTML = workingsHtml;
}

// Initialise
calcCGT();
calcNG();
</script>
</body>
</html>
