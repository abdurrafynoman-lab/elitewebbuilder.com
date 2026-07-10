<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>WebForge Studio — Websites Designed, Built &amp; Published</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#0F2A47;
    --ink-deep:#081A2E;
    --ink-soft:#274A6C;
    --line-blue:#6FB7FF;
    --line-blue-dim:rgba(111,183,255,0.28);
    --paper:#F6F2E7;
    --paper-deep:#ECE4D0;
    --amber:#FF7A3D;
    --amber-deep:#E6591C;
    --text-on-paper:#12283D;
    --muted-on-ink:rgba(238,246,255,0.68);
    --muted-on-paper:rgba(18,40,61,0.64);
    --shadow: 0 24px 50px -22px rgba(8,26,46,0.45);
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--paper);
    color:var(--text-on-paper);
    font-family:'Inter',sans-serif;
    overflow-x:hidden;
    -webkit-font-smoothing:antialiased;
  }
  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition-duration:0.001ms !important; scroll-behavior:auto !important;}
  }
  a{color:inherit;text-decoration:none;}
  img,svg{display:block;}
  .wrap{max-width:1180px;margin:0 auto;padding:0 32px;}
  .mono{font-family:'IBM Plex Mono',monospace;}

  /* ---------- nav ---------- */
  header{position:sticky;top:0;z-index:50;background:rgba(246,242,231,0.88);backdrop-filter:blur(10px);border-bottom:1px solid rgba(18,40,61,0.1);}
  nav{display:flex;align-items:center;justify-content:space-between;padding:16px 32px;max-width:1180px;margin:0 auto;}
  .brand{display:flex;align-items:center;gap:12px;}
  .logo-mark{width:40px;height:40px;border-radius:9px;background:var(--ink);display:flex;align-items:center;justify-content:center;flex-shrink:0;}
  .logo-mark svg{width:22px;height:22px;color:var(--line-blue);}
  .brand-name{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:1.05rem;color:var(--ink);}
  .brand-name span{display:block;font-family:'IBM Plex Mono',monospace;font-size:0.6rem;letter-spacing:0.16em;color:var(--muted-on-paper);text-transform:uppercase;font-weight:500;}
  .nav-links{display:flex;align-items:center;gap:28px;}
  .nav-links a.section-link{font-size:0.88rem;font-weight:500;color:var(--text-on-paper);opacity:0.8;transition:opacity 0.2s ease;}
  .nav-links a.section-link:hover{opacity:1;}
  .nav-cta{background:var(--amber);color:#fff;font-family:'IBM Plex Mono',monospace;font-size:0.76rem;letter-spacing:0.02em;padding:11px 18px;border-radius:9px;display:flex;align-items:center;gap:8px;box-shadow:0 10px 22px -10px rgba(255,122,61,0.65);transition:transform 0.25s ease, box-shadow 0.25s ease;}
  .nav-cta:hover{transform:translateY(-2px);box-shadow:0 14px 26px -8px rgba(255,122,61,0.8);}
  .nav-cta svg{width:14px;height:14px;}

  /* ---------- hero (blueprint) ---------- */
  .hero{position:relative;background:var(--ink);color:var(--paper);padding:90px 0 96px;overflow:hidden;}
  .hero::before{
    content:"";position:absolute;inset:0;
    background-image:
      repeating-linear-gradient(0deg, var(--line-blue-dim) 0, var(--line-blue-dim) 1px, transparent 1px, transparent 44px),
      repeating-linear-gradient(90deg, var(--line-blue-dim) 0, var(--line-blue-dim) 1px, transparent 1px, transparent 44px);
    opacity:0.5;mask-image:radial-gradient(ellipse at 50% 40%, black 40%, transparent 85%);
  }
  .hero .wrap{position:relative;display:grid;grid-template-columns:1.1fr 0.9fr;gap:54px;align-items:center;}

  .eyebrow{font-family:'IBM Plex Mono',monospace;font-size:0.74rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--line-blue);display:flex;align-items:center;gap:10px;margin-bottom:22px;opacity:0;animation:fadeUp 0.7s ease forwards;animation-delay:0.05s;}
  .eyebrow::before{content:"";width:26px;height:1px;background:var(--line-blue);}

  h1{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:clamp(2.3rem,4.3vw,3.5rem);line-height:1.1;letter-spacing:-0.01em;margin-bottom:22px;opacity:0;animation:fadeUp 0.7s ease forwards;animation-delay:0.15s;}
  h1 .accent{color:var(--amber);}

  .hero p.lead{font-size:1.02rem;line-height:1.75;color:var(--muted-on-ink);max-width:48ch;margin-bottom:32px;opacity:0;animation:fadeUp 0.7s ease forwards;animation-delay:0.25s;}

  .hero-actions{display:flex;align-items:center;gap:16px;flex-wrap:wrap;opacity:0;animation:fadeUp 0.7s ease forwards;animation-delay:0.35s;}
  .btn-primary{background:var(--amber);color:#fff;font-weight:600;font-size:0.94rem;padding:15px 26px;border-radius:10px;display:inline-flex;align-items:center;gap:10px;box-shadow:0 16px 30px -14px rgba(255,122,61,0.7);transition:transform 0.25s ease, box-shadow 0.25s ease;}
  .btn-primary:hover{transform:translateY(-3px);box-shadow:0 20px 34px -12px rgba(255,122,61,0.85);}
  .btn-primary svg{width:18px;height:18px;}
  .btn-ghost{border:1px solid rgba(238,246,255,0.3);color:var(--paper);font-size:0.94rem;font-weight:500;padding:14px 24px;border-radius:10px;display:inline-flex;align-items:center;gap:10px;transition:border-color 0.25s ease, background 0.25s ease;}
  .btn-ghost:hover{border-color:var(--line-blue);background:rgba(111,183,255,0.08);}
  .btn-ghost svg{width:17px;height:17px;}

  @keyframes fadeUp{from{opacity:0;transform:translateY(16px);}to{opacity:1;transform:translateY(0);}}

  /* ---------- signature: blueprint site-plan diagram ---------- */
  .plan-wrap{position:relative;}
  .plan{
    position:relative;background:rgba(9,27,48,0.55);border:1px solid rgba(111,183,255,0.35);
    border-radius:14px;padding:26px 26px 22px;box-shadow:var(--shadow);
    opacity:0;animation:fadeIn 0.9s ease forwards;animation-delay:0.35s;
  }
  @keyframes fadeIn{from{opacity:0;}to{opacity:1;}}
  .plan-label{font-family:'IBM Plex Mono',monospace;font-size:0.65rem;letter-spacing:0.14em;color:var(--line-blue);text-transform:uppercase;margin-bottom:14px;display:flex;justify-content:space-between;}
  .plan-frame{border:1.5px dashed rgba(111,183,255,0.55);border-radius:8px;overflow:hidden;}
  .plan-block{border-bottom:1.5px dashed rgba(111,183,255,0.4);padding:12px 14px;position:relative;}
  .plan-block:last-child{border-bottom:none;}
  .plan-block .tag{font-family:'IBM Plex Mono',monospace;font-size:0.62rem;color:var(--line-blue);letter-spacing:0.06em;text-transform:uppercase;opacity:0.85;}
  .plan-block .dim{position:absolute;right:14px;top:12px;font-family:'IBM Plex Mono',monospace;font-size:0.6rem;color:rgba(238,246,255,0.4);}
  .plan-block.header{height:44px;background:rgba(111,183,255,0.06);}
  .plan-block.hero-b{height:96px;background:rgba(255,122,61,0.08);display:flex;flex-direction:column;justify-content:center;gap:6px;}
  .plan-block.hero-b .bar{height:8px;border-radius:3px;background:rgba(238,246,255,0.25);}
  .plan-block.hero-b .bar.w1{width:60%;}
  .plan-block.hero-b .bar.w2{width:40%;}
  .plan-block.grid3{height:76px;display:grid;grid-template-columns:repeat(3,1fr);gap:8px;padding:12px;background:rgba(111,183,255,0.04);}
  .plan-block.grid3 .cell{border:1px dashed rgba(111,183,255,0.4);border-radius:5px;}
  .plan-block.footer{height:34px;background:rgba(111,183,255,0.06);}
  .plan-stamp{
    position:absolute;bottom:-18px;right:-14px;background:var(--amber);color:#fff;
    font-family:'IBM Plex Mono',monospace;font-size:0.62rem;letter-spacing:0.08em;text-transform:uppercase;
    padding:8px 14px;border-radius:6px;transform:rotate(-6deg);box-shadow:0 10px 20px -8px rgba(255,122,61,0.6);
  }

  /* ---------- process ---------- */
  section{padding:96px 0;position:relative;}
  .section-head{max-width:58ch;margin-bottom:52px;}
  .section-head .eyebrow{color:var(--amber-deep);}
  .section-head .eyebrow::before{background:var(--amber-deep);}
  .section-head h2{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:clamp(1.85rem,3.1vw,2.4rem);line-height:1.15;letter-spacing:-0.01em;color:var(--ink);}
  .section-head p{color:var(--muted-on-paper);margin-top:14px;font-size:1rem;line-height:1.7;}

  .process-row{display:grid;grid-template-columns:repeat(3,1fr);gap:26px;}
  .process-card{background:#fff;border:1px solid rgba(18,40,61,0.08);border-radius:16px;padding:32px 26px;position:relative;transition:transform 0.3s ease, box-shadow 0.3s ease;}
  .process-card:hover{transform:translateY(-6px);box-shadow:var(--shadow);}
  .process-num{font-family:'IBM Plex Mono',monospace;font-size:0.78rem;color:var(--amber-deep);border:1px solid rgba(255,122,61,0.4);border-radius:50%;width:36px;height:36px;display:flex;align-items:center;justify-content:center;margin-bottom:18px;}
  .process-card h3{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:1.18rem;margin-bottom:10px;color:var(--ink);}
  .process-card p{font-size:0.9rem;color:var(--muted-on-paper);line-height:1.65;}
  .process-connector{position:absolute;top:36px;right:-26px;width:26px;height:1px;background:repeating-linear-gradient(90deg, rgba(255,122,61,0.5) 0 6px, transparent 6px 10px);}
  .process-card:last-child .process-connector{display:none;}

  /* ---------- pricing ---------- */
  .pricing-section{background:var(--ink);color:var(--paper);}
  .pricing-section .section-head .eyebrow{color:var(--line-blue);}
  .pricing-section .section-head .eyebrow::before{background:var(--line-blue);}
  .pricing-section .section-head h2{color:var(--paper);}
  .pricing-section .section-head p{color:var(--muted-on-ink);}

  .price-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;}
  .price-card{
    background:var(--paper);color:var(--text-on-paper);border-radius:18px;padding:34px 28px;
    position:relative;transition:transform 0.3s ease, box-shadow 0.3s ease;border:2px solid transparent;
  }
  .price-card:hover{transform:translateY(-8px);box-shadow:0 26px 50px -18px rgba(0,0,0,0.5);}
  .price-card.featured{border-color:var(--amber);}
  .price-card .ribbon{position:absolute;top:-13px;left:28px;background:var(--amber);color:#fff;font-family:'IBM Plex Mono',monospace;font-size:0.62rem;letter-spacing:0.08em;text-transform:uppercase;padding:6px 12px;border-radius:6px;}
  .price-card .kind{font-family:'IBM Plex Mono',monospace;font-size:0.68rem;letter-spacing:0.1em;text-transform:uppercase;color:var(--muted-on-paper);margin-bottom:10px;}
  .price-card h3{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:1.35rem;margin-bottom:16px;}
  .price-card .amount{font-family:'IBM Plex Mono',monospace;font-size:2.2rem;font-weight:600;color:var(--ink);margin-bottom:4px;}
  .price-card .amount sup{font-size:0.9rem;font-weight:500;color:var(--muted-on-paper);margin-left:4px;}
  .price-card .amount-note{font-size:0.78rem;color:var(--muted-on-paper);margin-bottom:22px;}
  .price-card ul{list-style:none;margin-bottom:26px;}
  .price-card li{display:flex;gap:10px;align-items:flex-start;font-size:0.87rem;padding:7px 0;color:var(--text-on-paper);}
  .price-card li svg{width:16px;height:16px;color:var(--amber-deep);flex-shrink:0;margin-top:2px;}
  .price-cta{display:inline-flex;align-items:center;gap:8px;font-family:'IBM Plex Mono',monospace;font-size:0.8rem;font-weight:500;color:var(--ink);border:1.5px solid var(--ink);padding:11px 18px;border-radius:8px;transition:background 0.25s ease, color 0.25s ease;}
  .price-cta:hover{background:var(--ink);color:var(--paper);}
  .price-cta svg{width:14px;height:14px;}

  /* ---------- contact ---------- */
  .contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:24px;}
  .phone-card{background:#fff;border:1px solid rgba(18,40,61,0.08);border-radius:18px;padding:32px 28px;display:flex;align-items:center;gap:20px;transition:transform 0.3s ease, box-shadow 0.3s ease;}
  .phone-card:hover{transform:translateY(-5px);box-shadow:var(--shadow);}
  .phone-icon{width:52px;height:52px;border-radius:12px;background:rgba(255,122,61,0.1);display:flex;align-items:center;justify-content:center;flex-shrink:0;}
  .phone-icon svg{width:24px;height:24px;color:var(--amber-deep);}
  .phone-card .label{font-family:'IBM Plex Mono',monospace;font-size:0.68rem;letter-spacing:0.12em;text-transform:uppercase;color:var(--muted-on-paper);margin-bottom:4px;}
  .phone-card .number{font-family:'IBM Plex Mono',monospace;font-size:1.25rem;font-weight:600;color:var(--ink);letter-spacing:0.02em;}
  .phone-actions{margin-left:auto;display:flex;gap:10px;}
  .icon-btn{width:38px;height:38px;border-radius:9px;background:var(--paper-deep);display:flex;align-items:center;justify-content:center;transition:background 0.2s ease;}
  .icon-btn:hover{background:var(--amber);}
  .icon-btn:hover svg{color:#fff;}
  .icon-btn svg{width:17px;height:17px;color:var(--ink);transition:color 0.2s ease;}

  /* ---------- final cta ---------- */
  .final-cta{background:linear-gradient(155deg, var(--amber) 0%, var(--amber-deep) 100%);color:#fff;text-align:center;border-radius:26px;margin:0 32px;padding:66px 32px;position:relative;overflow:hidden;}
  .final-cta::before{content:"";position:absolute;inset:0;background:radial-gradient(circle at 25% 20%, rgba(255,255,255,0.18), transparent 45%);}
  .final-cta h2{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:clamp(1.85rem,3.4vw,2.5rem);margin-bottom:14px;position:relative;}
  .final-cta p{opacity:0.9;max-width:44ch;margin:0 auto 28px;font-size:1rem;line-height:1.7;position:relative;}
  .final-cta .btn-primary{background:var(--ink);box-shadow:0 16px 30px -12px rgba(0,0,0,0.35);position:relative;}
  .final-cta .btn-primary:hover{box-shadow:0 20px 34px -10px rgba(0,0,0,0.45);}

  /* ---------- footer ---------- */
  footer{padding:52px 0 40px;}
  .footer-row{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:20px;border-top:1px solid rgba(18,40,61,0.1);padding-top:30px;}
  .footer-brand{display:flex;align-items:center;gap:12px;}
  .footer-brand span{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:1rem;color:var(--ink);}
  .footer-note{font-family:'IBM Plex Mono',monospace;font-size:0.74rem;color:var(--muted-on-paper);letter-spacing:0.02em;}

  @media (max-width:900px){
    .hero .wrap{grid-template-columns:1fr;text-align:center;}
    .hero p.lead{margin-left:auto;margin-right:auto;}
    .hero-actions{justify-content:center;}
    .eyebrow{justify-content:center;}
    .plan-wrap{order:-1;margin-bottom:10px;max-width:420px;margin-left:auto;margin-right:auto;}
    .process-row{grid-template-columns:1fr;}
    .process-connector{display:none;}
    .price-grid{grid-template-columns:1fr;}
    .contact-grid{grid-template-columns:1fr;}
    .nav-links{display:none;}
    .final-cta{margin:0 16px;}
    nav{padding:14px 20px;}
    .wrap{padding:0 20px;}
  }
</style>
</head>
<body>

<header>
  <nav>
    <div class="brand">
      <div class="logo-mark"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="16" rx="2"/><path d="M3 9h18M8 4v5"/><path d="M11 13h6M11 16h4"/></svg></div>
      <div class="brand-name">WebForge Studio<span>Design · Build · Publish</span></div>
    </div>
    <div class="nav-links">
      <a class="section-link" href="#process">Process</a>
      <a class="section-link" href="#pricing">Pricing</a>
      <a class="section-link" href="#contact">Contact</a>
      <a class="nav-cta" href="tel:+923457708779">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg>
        Call now
      </a>
    </div>
  </nav>
</header>

<section class="hero">
  <div class="wrap">
    <div class="hero-copy">
      <div class="eyebrow">Websites, designed &amp; published for you</div>
      <h1>Your website, <span class="accent">planned, built, and live</span> — no technical headaches for you.</h1>
      <p class="lead">I design and build websites for individuals and businesses, then publish them so they're live on the internet — no plugins to configure, no hosting to figure out. You just tell me what you need.</p>
      <div class="hero-actions">
        <a class="btn-primary" href="tel:+923457708779">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg>
          Call 0345 7708779
        </a>
        <a class="btn-ghost" href="https://wa.me/923457708779?text=Hi%2C%20I%27d%20like%20to%20get%20a%20website%20made." target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12.04 2c-5.5 0-9.96 4.46-9.96 9.96 0 1.76.46 3.45 1.32 4.95L2 22l5.2-1.36a9.9 9.9 0 0 0 4.84 1.24h.01c5.5 0 9.96-4.46 9.96-9.96S17.54 2 12.04 2zm0 18.2h-.01a8.2 8.2 0 0 1-4.2-1.15l-.3-.18-3.12.82.83-3.04-.2-.31a8.2 8.2 0 0 1-1.26-4.38c0-4.54 3.7-8.24 8.26-8.24 2.2 0 4.27.86 5.83 2.42a8.18 8.18 0 0 1 2.42 5.83c0 4.54-3.7 8.23-8.25 8.23z"/></svg>
          WhatsApp
        </a>
      </div>
    </div>

    <div class="plan-wrap">
      <div class="plan">
        <div class="plan-label"><span>site-plan.spec</span><span>v1.0</span></div>
        <div class="plan-frame">
          <div class="plan-block header"><span class="tag">nav / header</span><span class="dim">100% × 64px</span></div>
          <div class="plan-block hero-b"><span class="tag">hero</span><span class="dim">100% × auto</span><div class="bar w1"></div><div class="bar w2"></div></div>
          <div class="plan-block grid3"><div class="cell"></div><div class="cell"></div><div class="cell"></div></div>
          <div class="plan-block footer"><span class="tag">footer</span></div>
        </div>
        <div class="plan-stamp">published ✓</div>
      </div>
    </div>
  </div>
</section>

<section id="process">
  <div class="wrap">
    <div class="section-head">
      <div class="eyebrow">How it works</div>
      <h2>From a phone call to a live website</h2>
      <p>You don't need to know anything about websites. Three steps, and I handle every part in between.</p>
    </div>
    <div class="process-row">
      <div class="process-card">
        <div class="process-connector"></div>
        <div class="process-num">01</div>
        <h3>Tell me what you need</h3>
        <p>Call or message with what the website is for — yourself, your business, or your store — and what you'd like on it.</p>
      </div>
      <div class="process-card">
        <div class="process-connector"></div>
        <div class="process-num">02</div>
        <h3>I design &amp; build it</h3>
        <p>Your pages are designed and built to match what you asked for, with a look and layout that fits your work.</p>
      </div>
      <div class="process-card">
        <div class="process-num">03</div>
        <h3>I publish it live</h3>
        <p>Once you approve it, I publish the site so it's live on the internet — ready to share with anyone.</p>
      </div>
    </div>
  </div>
</section>

<section class="pricing-section" id="pricing">
  <div class="wrap">
    <div class="section-head">
      <div class="eyebrow">Pricing</div>
      <h2>One flat price per website type</h2>
      <p>Pick the type that matches what you need. Every price includes design, build, and publishing.</p>
    </div>
    <div class="price-grid">
      <div class="price-card">
        <div class="kind">Type 01</div>
        <h3>Personal / Portfolio Website</h3>
        <div class="amount">3,000<sup>PKR</sup></div>
        <div class="amount-note">one-time · design + build + publish</div>
        <ul>
          <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>Built around you or your work</li>
          <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>About, work/projects &amp; contact sections</li>
          <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>Published and live on the internet</li>
        </ul>
        <a class="price-cta" href="tel:+923457708779"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg>Get this one</a>
      </div>

      <div class="price-card featured">
        <div class="ribbon">Most requested</div>
        <div class="kind">Type 02</div>
        <h3>Business Website</h3>
        <div class="amount">4,000<sup>PKR</sup></div>
        <div class="amount-note">one-time · design + build + publish</div>
        <ul>
          <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>Services, pricing &amp; about pages</li>
          <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>Contact form &amp; location details</li>
          <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>Published and live on the internet</li>
        </ul>
        <a class="price-cta" href="tel:+923457708779"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg>Get this one</a>
      </div>

      <div class="price-card">
        <div class="kind">Type 03</div>
        <h3>E-commerce Website</h3>
        <div class="amount">3,500<sup>PKR</sup></div>
        <div class="amount-note">one-time · design + build + publish</div>
        <ul>
          <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>Product listings &amp; product pages</li>
          <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>Cart &amp; checkout flow</li>
          <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>Published and live on the internet</li>
        </ul>
        <a class="price-cta" href="tel:+923457708779"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg>Get this one</a>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="wrap">
    <div class="section-head">
      <div class="eyebrow">Get in touch</div>
      <h2>Call or message either number</h2>
      <p>Reach out with what kind of website you need and I'll get back to you to start planning it.</p>
    </div>
    <div class="contact-grid">
      <div class="phone-card">
        <div class="phone-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg></div>
        <div>
          <div class="label">Phone number 1</div>
          <div class="number">0345 7708779</div>
        </div>
        <div class="phone-actions">
          <a class="icon-btn" href="tel:+923457708779" title="Call"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg></a>
          <a class="icon-btn" href="https://wa.me/923457708779" target="_blank" rel="noopener" title="WhatsApp"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M12.04 2c-5.5 0-9.96 4.46-9.96 9.96 0 1.76.46 3.45 1.32 4.95L2 22l5.2-1.36a9.9 9.9 0 0 0 4.84 1.24h.01c5.5 0 9.96-4.46 9.96-9.96S17.54 2 12.04 2zm0 18.2h-.01a8.2 8.2 0 0 1-4.2-1.15l-.3-.18-3.12.82.83-3.04-.2-.31a8.2 8.2 0 0 1-1.26-4.38c0-4.54 3.7-8.24 8.26-8.24 2.2 0 4.27.86 5.83 2.42a8.18 8.18 0 0 1 2.42 5.83c0 4.54-3.7 8.23-8.25 8.23z"/></svg></a>
        </div>
      </div>

      <div class="phone-card">
        <div class="phone-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg></div>
        <div>
          <div class="label">Phone number 2</div>
          <div class="number">0303 9209110</div>
        </div>
        <div class="phone-actions">
          <a class="icon-btn" href="tel:+923039209110" title="Call"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg></a>
          <a class="icon-btn" href="https://wa.me/923039209110" target="_blank" rel="noopener" title="WhatsApp"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M12.04 2c-5.5 0-9.96 4.46-9.96 9.96 0 1.76.46 3.45 1.32 4.95L2 22l5.2-1.36a9.9 9.9 0 0 0 4.84 1.24h.01c5.5 0 9.96-4.46 9.96-9.96S17.54 2 12.04 2zm0 18.2h-.01a8.2 8.2 0 0 1-4.2-1.15l-.3-.18-3.12.82.83-3.04-.2-.31a8.2 8.2 0 0 1-1.26-4.38c0-4.54 3.7-8.24 8.26-8.24 2.2 0 4.27.86 5.83 2.42a8.18 8.18 0 0 1 2.42 5.83c0 4.54-3.7 8.23-8.25 8.23z"/></svg></a>
        </div>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="wrap">
    <div class="final-cta">
      <h2>Have a website in mind?</h2>
      <p>Call or message either number with what you're looking for — personal, business, or an online store — and I'll take it from there.</p>
      <a class="btn-primary" href="tel:+923457708779">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.5.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.9 21 3 13.1 3 3.9c0-.6.4-1 1-1h3.4c.6 0 1 .4 1 1 0 1.2.2 2.4.6 3.5.1.4 0 .8-.2 1.1l-2.2 2.2Z"/></svg>
        Call 0345 7708779
      </a>
    </div>
  </div>
</section>

<footer>
  <div class="wrap">
    <div class="footer-row">
      <div class="footer-brand">
        <div class="logo-mark" style="width:32px;height:32px;"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" style="width:18px;height:18px;"><rect x="3" y="4" width="18" height="16" rx="2"/><path d="M3 9h18M8 4v5"/><path d="M11 13h6M11 16h4"/></svg></div>
        <span>WebForge Studio</span>
      </div>
      <div class="footer-note">DESIGN · BUILD · PUBLISH · CALL OR WHATSAPP TO ORDER</div>
    </div>
  </div>
</footer>

</body>
</html>
