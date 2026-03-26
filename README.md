
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ENERTUR — Energia Inteligente</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=Barlow:wght@300;400;500;600&family=Barlow+Condensed:wght@600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --black2: #111111;
    --black3: #1a1a1a;
    --gold: #C9A84C;
    --gold-light: #E8C97A;
    --gold-dark: #8B6914;
    --gold-muted: #8a7240;
    --white: #f5f0e8;
    --white-dim: rgba(245,240,232,0.7);
    --white-faint: rgba(245,240,232,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'Barlow', sans-serif;
    font-weight: 300;
    max-width: 430px;
    margin: 0 auto;
    overflow-x: hidden;
  }

  /* ── SLIDE BASE ── */
  .slide {
    min-height: 100svh;
    padding: 48px 28px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: relative;
    overflow: hidden;
    border-bottom: 1px solid rgba(201,168,76,0.12);
  }

  /* ── GOLD LINE DIVIDER ── */
  .gold-line {
    width: 48px;
    height: 2px;
    background: linear-gradient(90deg, var(--gold), transparent);
    margin: 16px 0;
  }

  /* ── SLIDE 1: CAPA ── */
  #slide-capa {
    background: var(--black);
    justify-content: flex-end;
    padding-bottom: 64px;
    min-height: 100svh;
  }

  #slide-capa::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 50% 20%, rgba(201,168,76,0.12) 0%, transparent 70%),
      radial-gradient(ellipse 50% 40% at 80% 80%, rgba(201,168,76,0.06) 0%, transparent 60%);
    pointer-events: none;
  }

  .capa-grain {
    position: absolute;
    inset: 0;
    opacity: 0.04;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
    pointer-events: none;
  }

  .logo-mark {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 6px;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 40px;
    position: relative;
    z-index: 1;
  }

  .capa-eyebrow {
    font-family: 'Barlow', sans-serif;
    font-size: 11px;
    letter-spacing: 4px;
    color: var(--gold-muted);
    text-transform: uppercase;
    margin-bottom: 20px;
    position: relative;
    z-index: 1;
  }

  .capa-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(52px, 16vw, 80px);
    font-weight: 900;
    line-height: 0.9;
    letter-spacing: -2px;
    color: var(--white);
    position: relative;
    z-index: 1;
    margin-bottom: 8px;
  }

  .capa-title span {
    color: var(--gold);
    display: block;
  }

  .capa-subtitle {
    font-size: 13px;
    font-weight: 300;
    letter-spacing: 2px;
    color: var(--white-dim);
    margin-top: 24px;
    line-height: 1.7;
    position: relative;
    z-index: 1;
    max-width: 280px;
  }

  .capa-scroll {
    margin-top: 48px;
    display: flex;
    align-items: center;
    gap: 12px;
    position: relative;
    z-index: 1;
  }

  .capa-scroll span {
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--gold-muted);
    text-transform: uppercase;
  }

  .scroll-line {
    width: 32px;
    height: 1px;
    background: var(--gold-muted);
    animation: scrollPulse 2s ease-in-out infinite;
  }

  @keyframes scrollPulse {
    0%, 100% { width: 32px; opacity: 0.5; }
    50% { width: 56px; opacity: 1; }
  }

  /* ── SLIDE 2: MISSÃO ── */
  #slide-missao {
    background: var(--black2);
  }

  #slide-missao::before {
    content: '';
    position: absolute;
    top: -40px;
    right: -40px;
    width: 200px;
    height: 200px;
    border: 1px solid rgba(201,168,76,0.1);
    border-radius: 50%;
    pointer-events: none;
  }

  .section-tag {
    font-size: 10px;
    letter-spacing: 4px;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 32px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-tag::before {
    content: '';
    width: 20px;
    height: 1px;
    background: var(--gold);
  }

  .slide-title {
    font-family: 'Playfair Display', serif;
    font-size: 38px;
    font-weight: 700;
    line-height: 1.1;
    color: var(--white);
    margin-bottom: 24px;
  }

  .slide-title em {
    font-style: italic;
    color: var(--gold-light);
  }

  .slide-body {
    font-size: 14px;
    font-weight: 300;
    line-height: 1.8;
    color: var(--white-dim);
    margin-bottom: 32px;
  }

  .mission-highlight {
    border-left: 2px solid var(--gold);
    padding: 16px 20px;
    background: rgba(201,168,76,0.05);
    font-size: 13px;
    line-height: 1.7;
    color: var(--white);
    font-weight: 400;
    letter-spacing: 0.3px;
    margin-top: 24px;
  }

  .mission-highlight strong {
    color: var(--gold-light);
  }

  /* ── SLIDE 3: PILARES ── */
  #slide-pilares {
    background: var(--black);
    padding-top: 56px;
    padding-bottom: 56px;
  }

  .pilares-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-top: 32px;
  }

  .pilar-card {
    background: var(--black3);
    border: 1px solid rgba(201,168,76,0.15);
    padding: 20px 16px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s;
  }

  .pilar-card::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--gold), transparent);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }

  .pilar-card:active::after { transform: scaleX(1); }

  /* ── YEARS BADGE ── */
  .years-badge {
    display: inline-flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 32px;
    position: relative;
    z-index: 1;
  }

  .years-number {
    font-family: 'Playfair Display', serif;
    font-size: 42px;
    font-weight: 900;
    color: var(--gold);
    line-height: 1;
  }

  .years-text {
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .years-text strong {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--white);
  }

  .years-text span {
    font-size: 11px;
    letter-spacing: 1.5px;
    color: var(--gold-muted);
    text-transform: uppercase;
  }

  .years-separator {
    width: 1px;
    height: 40px;
    background: linear-gradient(to bottom, transparent, var(--gold), transparent);
  }

  .pilar-icon {
    width: 28px;
    height: 28px;
    margin-bottom: 12px;
    opacity: 0.9;
  }

  .pilar-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 8px;
  }

  .pilar-desc {
    font-size: 11.5px;
    font-weight: 300;
    line-height: 1.6;
    color: var(--white-dim);
  }

  .pilar-card.full-width {
    grid-column: 1 / -1;
  }

  /* ── SLIDE 4: COMO FUNCIONA ── */
  #slide-bateria {
    background: var(--black2);
  }

  .steps-list {
    margin-top: 28px;
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .step-item {
    display: flex;
    gap: 20px;
    padding: 20px 0;
    border-bottom: 1px solid rgba(201,168,76,0.1);
    align-items: flex-start;
  }

  .step-item:last-child { border-bottom: none; }

  .step-num {
    font-family: 'Playfair Display', serif;
    font-size: 32px;
    font-weight: 900;
    color: rgba(201,168,76,0.18);
    line-height: 1;
    min-width: 36px;
  }

  .step-content h4 {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 14px;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--gold-light);
    margin-bottom: 6px;
  }

  .step-content p {
    font-size: 13px;
    font-weight: 300;
    line-height: 1.7;
    color: var(--white-dim);
  }

  /* ── SLIDE 5: SEGMENTOS ── */
  #slide-segmentos {
    background: var(--black);
    padding-top: 56px;
  }

  .segmentos-list {
    margin-top: 32px;
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .segmento-item {
    background: var(--black3);
    border-left: 3px solid transparent;
    padding: 20px 20px;
    cursor: pointer;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .segmento-item:nth-child(1) { border-left-color: var(--gold); }
  .segmento-item:nth-child(2) { border-left-color: rgba(201,168,76,0.7); }
  .segmento-item:nth-child(3) { border-left-color: rgba(201,168,76,0.5); }
  .segmento-item:nth-child(4) { border-left-color: rgba(201,168,76,0.35); }
  .segmento-item:nth-child(5) { border-left-color: rgba(201,168,76,0.2); }

  .segmento-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .segmento-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 16px;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--white);
  }



  .segmento-benefits {
    margin-top: 12px;
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .benefit-row {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 12.5px;
    color: var(--white-dim);
    line-height: 1.5;
  }

  .benefit-row::before {
    content: '◆';
    color: var(--gold);
    font-size: 6px;
    margin-top: 5px;
    flex-shrink: 0;
  }

  /* ── SLIDE 6: ECOSSISTEMA ── */
  #slide-ecossistema {
    background: var(--black2);
  }

  .eco-cards {
    margin-top: 32px;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .eco-card {
    background: var(--black3);
    border: 1px solid rgba(201,168,76,0.12);
    padding: 24px 20px;
    display: flex;
    align-items: center;
    gap: 20px;
    position: relative;
    overflow: hidden;
  }

  .eco-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 1px;
    background: linear-gradient(90deg, var(--gold), transparent 60%);
  }

  .eco-icon {
    width: 36px;
    height: 36px;
    min-width: 36px;
    opacity: 0.85;
  }

  .segmento-icon {
    width: 20px;
    height: 20px;
    opacity: 0.6;
  }

  .eco-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 15px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--gold-light);
    margin-bottom: 4px;
  }

  .eco-desc {
    font-size: 12.5px;
    font-weight: 300;
    line-height: 1.6;
    color: var(--white-dim);
  }

  /* ── SLIDE 7: DIFERENCIAIS ── */
  #slide-diferenciais {
    background: var(--black);
  }

  .diff-list {
    margin-top: 32px;
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .diff-item {
    display: flex;
    gap: 16px;
    align-items: flex-start;
    padding: 18px 0;
    border-bottom: 1px solid rgba(201,168,76,0.08);
  }

  .diff-item:last-child { border-bottom: none; }

  .diff-dot {
    width: 8px;
    height: 8px;
    background: var(--gold);
    border-radius: 50%;
    margin-top: 6px;
    flex-shrink: 0;
  }

  .diff-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 14px;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--white);
    margin-bottom: 4px;
  }

  .diff-desc {
    font-size: 12.5px;
    font-weight: 300;
    line-height: 1.6;
    color: var(--white-dim);
  }

  /* ── SLIDE 8: CTA ── */
  #slide-cta {
    background: var(--black2);
    text-align: center;
    align-items: center;
    min-height: 80svh;
  }

  #slide-cta::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 70% 50% at 50% 60%, rgba(201,168,76,0.1) 0%, transparent 70%);
    pointer-events: none;
  }

  .cta-pre {
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--gold-muted);
    margin-bottom: 20px;
    position: relative;
    z-index: 1;
  }

  .cta-title {
    font-family: 'Playfair Display', serif;
    font-size: 34px;
    font-weight: 900;
    line-height: 1.15;
    color: var(--white);
    margin-bottom: 16px;
    position: relative;
    z-index: 1;
  }

  .cta-title em {
    font-style: italic;
    color: var(--gold);
  }

  .cta-sub {
    font-size: 13px;
    font-weight: 300;
    color: var(--white-dim);
    line-height: 1.7;
    margin-bottom: 40px;
    position: relative;
    z-index: 1;
    max-width: 300px;
  }

  .cta-btn {
    display: inline-flex;
    align-items: center;
    gap: 12px;
    background: var(--gold);
    color: var(--black);
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 2px;
    text-transform: uppercase;
    padding: 16px 32px;
    border: none;
    cursor: pointer;
    position: relative;
    z-index: 1;
    text-decoration: none;
    transition: background 0.2s;
  }

  .cta-btn:active { background: var(--gold-light); }

  .cta-social {
    margin-top: 36px;
    font-size: 12px;
    letter-spacing: 2px;
    color: var(--gold-muted);
    position: relative;
    z-index: 1;
  }

  .cta-social span {
    color: var(--gold);
  }

  /* ── NAV DOTS ── */
  .nav-dots {
    position: fixed;
    right: 16px;
    top: 50%;
    transform: translateY(-50%);
    display: flex;
    flex-direction: column;
    gap: 8px;
    z-index: 100;
  }

  .nav-dot {
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: rgba(201,168,76,0.25);
    transition: all 0.3s;
    cursor: pointer;
  }

  .nav-dot.active {
    background: var(--gold);
    height: 18px;
    border-radius: 3px;
  }

  /* ── ANIMATIONS ── */
  .fade-in {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }

  .fade-in.visible {
    opacity: 1;
    transform: translateY(0);
  }

  .fade-in:nth-child(2) { transition-delay: 0.1s; }
  .fade-in:nth-child(3) { transition-delay: 0.2s; }
  .fade-in:nth-child(4) { transition-delay: 0.3s; }

  /* ── GOLD BADGE ── */
  .gold-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    border: 1px solid rgba(201,168,76,0.3);
    padding: 8px 16px;
    font-size: 11px;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 24px;
  }

  .gold-badge::before {
    content: '';
    width: 4px;
    height: 4px;
    background: var(--gold);
    border-radius: 50%;
  }

  /* ── DECORATIVE CORNER ── */
  .corner-deco {
    position: absolute;
    bottom: 28px;
    right: 28px;
    width: 48px;
    height: 48px;
    border-right: 1px solid rgba(201,168,76,0.2);
    border-bottom: 1px solid rgba(201,168,76,0.2);
    pointer-events: none;
  }

  .corner-deco-tl {
    position: absolute;
    top: 28px;
    left: 28px;
    width: 32px;
    height: 32px;
    border-left: 1px solid rgba(201,168,76,0.2);
    border-top: 1px solid rgba(201,168,76,0.2);
    pointer-events: none;
  }
</style>
</head>
<body>

<!-- NAV DOTS -->
<nav class="nav-dots" id="navDots">
  <div class="nav-dot active" data-slide="0"></div>
  <div class="nav-dot" data-slide="1"></div>
  <div class="nav-dot" data-slide="2"></div>
  <div class="nav-dot" data-slide="3"></div>
  <div class="nav-dot" data-slide="4"></div>
  <div class="nav-dot" data-slide="5"></div>
  <div class="nav-dot" data-slide="6"></div>
  <div class="nav-dot" data-slide="7"></div>
</nav>

<!-- SLIDE 1: CAPA -->
<section class="slide" id="slide-capa" data-slide="0">
  <div class="capa-grain"></div>
  <div class="corner-deco"></div>
  <div class="corner-deco-tl"></div>

  <div class="logo-mark fade-in">ENERTUR</div>

  <div class="years-badge fade-in">
    <div class="years-number">7+</div>
    <div class="years-separator"></div>
    <div class="years-text">
      <strong>Anos de mercado</strong>
      <span>Referência em energia inteligente</span>
    </div>
  </div>

  <div class="capa-eyebrow fade-in">Soluções em Energia Inteligente</div>

  <h1 class="capa-title fade-in">
    Energia<span>que<br>liberta.</span>
  </h1>

  <p class="capa-subtitle fade-in">
    Autonomia real. Tecnologia de ponta.<br>
    Sustentabilidade em cada projeto.
  </p>

  <div class="capa-scroll fade-in">
    <div class="scroll-line"></div>
    <span>Conheça</span>
  </div>
</section>

<!-- SLIDE 2: MISSÃO -->
<section class="slide" id="slide-missao" data-slide="1">
  <div class="corner-deco"></div>

  <div class="section-tag fade-in">Nossa Missão</div>

  <h2 class="slide-title fade-in">
    Energia<br><em>com propósito</em>
  </h2>

  <p class="slide-body fade-in">
    Desenvolvemos soluções energéticas que unem tecnologia avançada e atendimento consultivo, garantindo continuidade, eficiência e independência para residências e empresas.
  </p>

  <div class="mission-highlight fade-in">
    Nosso compromisso é entregar <strong>autonomia energética real</strong> — hoje, com a tecnologia do futuro.
  </div>
</section>

<!-- SLIDE 3: PILARES -->
<section class="slide" id="slide-pilares" data-slide="2">
  <div class="section-tag fade-in">Nossos Pilares</div>

  <h2 class="slide-title fade-in">O que<br><em>nos move</em></h2>

  <div class="pilares-grid">
    <div class="pilar-card fade-in">
      <svg class="pilar-icon" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
        <polygon points="14,2 17,11 26,11 19,17 22,26 14,20 6,26 9,17 2,11 11,11" stroke="#C9A84C" stroke-width="1.5" fill="none"/>
      </svg>
      <div class="pilar-name">Autonomia</div>
      <p class="pilar-desc">Controle total sobre seu consumo energético.</p>
    </div>
    <div class="pilar-card fade-in">
      <svg class="pilar-icon" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M14 2L4 7v8c0 5.5 4.3 10.7 10 12 5.7-1.3 10-6.5 10-12V7L14 2z" stroke="#C9A84C" stroke-width="1.5" fill="none"/>
        <path d="M9.5 14l3 3 6-6" stroke="#C9A84C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
      <div class="pilar-name">Segurança</div>
      <p class="pilar-desc">Equipamentos premium e suporte técnico especializado.</p>
    </div>
    <div class="pilar-card fade-in">
      <svg class="pilar-icon" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="14" cy="14" r="11" stroke="#C9A84C" stroke-width="1.5"/>
        <path d="M9 14l3.5 3.5L19 10" stroke="#C9A84C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
      <div class="pilar-name">Excelência</div>
      <p class="pilar-desc">Padrão premium em equipamentos, instalação e atendimento.</p>
    </div>
    <div class="pilar-card fade-in">
      <svg class="pilar-icon" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M14 3v4M14 21v4M3 14h4M21 14h4" stroke="#C9A84C" stroke-width="1.5" stroke-linecap="round"/>
        <circle cx="14" cy="14" r="5" stroke="#C9A84C" stroke-width="1.5"/>
        <path d="M7.2 7.2l2.8 2.8M18 18l2.8 2.8M20.8 7.2L18 10M10 18l-2.8 2.8" stroke="#C9A84C" stroke-width="1.2" stroke-linecap="round"/>
      </svg>
      <div class="pilar-name">Inovação</div>
      <p class="pilar-desc">Tecnologia de ponta e antecipação de tendências.</p>
    </div>
    <div class="pilar-card full-width fade-in">
      <svg class="pilar-icon" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M14 25C14 25 4 19 4 11a7 7 0 0 1 10-6.3A7 7 0 0 1 24 11c0 8-10 14-10 14z" stroke="#C9A84C" stroke-width="1.5" fill="none"/>
        <path d="M14 11c0-2.5 2-4 4-3" stroke="#C9A84C" stroke-width="1.2" stroke-linecap="round"/>
      </svg>
      <div class="pilar-name">Sustentabilidade</div>
      <p class="pilar-desc">Compromisso com energia limpa e uso eficiente de recursos — para um futuro mais consciente.</p>
    </div>
  </div>
</section>

<!-- SLIDE 4: COMO FUNCIONA -->
<section class="slide" id="slide-bateria" data-slide="3">
  <div class="section-tag fade-in">Tecnologia</div>

  <h2 class="slide-title fade-in">Como<br><em>funciona</em></h2>

  <div class="steps-list">
    <div class="step-item fade-in">
      <div class="step-num">01</div>
      <div class="step-content">
        <h4>Armazenamento Inteligente</h4>
        <p>A bateria é instalada junto ao quadro elétrico e funciona como um repositório inteligente de energia, garantindo fornecimento contínuo mesmo em quedas ou oscilações da rede.</p>
      </div>
    </div>
    <div class="step-item fade-in">
      <div class="step-num">02</div>
      <div class="step-content">
        <h4>Integração Solar</h4>
        <p>Integrada ao sistema solar, a bateria armazena o excedente gerado durante o dia para uso noturno — maximizando cada kWh de energia renovável produzida.</p>
      </div>
    </div>
    <div class="step-item fade-in">
      <div class="step-num">03</div>
      <div class="step-content">
        <h4>Flexibilidade Total</h4>
        <p>Pode ser carregada por solar, rede elétrica ou gerador. Dimensionada para atender o imóvel completo ou apenas os circuitos essenciais — personalizado ao seu perfil de consumo.</p>
      </div>
    </div>
    <div class="step-item fade-in">
      <div class="step-num">04</div>
      <div class="step-content">
        <h4>100% Silencioso e Automatizado</h4>
        <p>Sem ruídos, sem emissões de CO₂ e totalmente automatizado. Opera de forma invisível, entregando conforto e segurança sem qualquer intervenção manual.</p>
      </div>
    </div>
  </div>
</section>

<!-- SLIDE 5: SEGMENTOS -->
<section class="slide" id="slide-segmentos" data-slide="4">
  <div class="section-tag fade-in">Segmentos</div>

  <h2 class="slide-title fade-in">Para cada<br><em>necessidade</em></h2>

  <div class="segmentos-list">
    <div class="segmento-item fade-in">
      <div class="segmento-header">
        <span class="segmento-name">Residencial</span>
        <svg class="segmento-icon" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M3 9.5L10 3l7 6.5V17H13v-4h-6v4H3V9.5z" stroke="#C9A84C" stroke-width="1.2" fill="none"/>
        </svg>
      </div>
      <div class="segmento-benefits">
        <div class="benefit-row">Vigilância e alarmes sempre ativos, mesmo em apagões</div>
        <div class="benefit-row">Proteção de eletrodomésticos contra picos e falhas</div>
        <div class="benefit-row">Valorização e modernização do imóvel</div>
      </div>
    </div>

    <div class="segmento-item fade-in">
      <div class="segmento-header">
        <span class="segmento-name">Empresarial</span>
        <svg class="segmento-icon" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect x="2" y="5" width="16" height="13" stroke="#C9A84C" stroke-width="1.2" fill="none"/>
          <path d="M7 5V3h6v2" stroke="#C9A84C" stroke-width="1.2"/>
          <path d="M2 10h16" stroke="#C9A84C" stroke-width="1.2"/>
        </svg>
      </div>
      <div class="segmento-benefits">
        <div class="benefit-row">Energia estável para TI, servidores e operações críticas</div>
        <div class="benefit-row">Continuidade operacional sem interrupções</div>
        <div class="benefit-row">Infraestrutura sustentável que agrega valor à marca</div>
      </div>
    </div>

    <div class="segmento-item fade-in">
      <div class="segmento-header">
        <span class="segmento-name">Condomínios</span>
        <svg class="segmento-icon" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect x="4" y="2" width="12" height="17" stroke="#C9A84C" stroke-width="1.2" fill="none"/>
          <path d="M7 6h2M11 6h2M7 10h2M11 10h2M7 14h2M11 14h2" stroke="#C9A84C" stroke-width="1.2" stroke-linecap="round"/>
        </svg>
      </div>
      <div class="segmento-benefits">
        <div class="benefit-row">Elevadores, portaria e iluminação com energia contínua</div>
        <div class="benefit-row">Sistemas de acesso e segurança sempre ativos</div>
        <div class="benefit-row">Valorização imobiliária com modernização sustentável</div>
      </div>
    </div>

    <div class="segmento-item fade-in">
      <div class="segmento-header">
        <span class="segmento-name">Agronegócio</span>
        <svg class="segmento-icon" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M10 17V8" stroke="#C9A84C" stroke-width="1.2" stroke-linecap="round"/>
          <path d="M10 8C10 8 6 8 5 4c3 0 5 2 5 4z" stroke="#C9A84C" stroke-width="1.2" fill="none"/>
          <path d="M10 11C10 11 14 11 15 7c-3 0-5 2-5 4z" stroke="#C9A84C" stroke-width="1.2" fill="none"/>
          <path d="M4 17h12" stroke="#C9A84C" stroke-width="1.2" stroke-linecap="round"/>
        </svg>
      </div>
      <div class="segmento-benefits">
        <div class="benefit-row">Bombeamento e irrigação sem interrupções</div>
        <div class="benefit-row">Proteção de estufas, silos e cadeias de refrigeração</div>
        <div class="benefit-row">Integração solar para reduzir custos operacionais</div>
      </div>
    </div>

    <div class="segmento-item fade-in">
      <div class="segmento-header">
        <span class="segmento-name">Locais Remotos</span>
        <svg class="segmento-icon" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="10" cy="10" r="7" stroke="#C9A84C" stroke-width="1.2" fill="none"/>
          <path d="M3 10h14M10 3c-2 2-3 4.5-3 7s1 5 3 7M10 3c2 2 3 4.5 3 7s-1 5-3 7" stroke="#C9A84C" stroke-width="1.1"/>
        </svg>
      </div>
      <div class="segmento-benefits">
        <div class="benefit-row">Independência total da rede elétrica</div>
        <div class="benefit-row">Atende obras temporárias e comunidades isoladas</div>
      </div>
    </div>
  </div>
</section>

<!-- SLIDE 6: ECOSSISTEMA -->
<section class="slide" id="slide-ecossistema" data-slide="5">
  <div class="gold-badge fade-in">Ecossistema Completo</div>

  <h2 class="slide-title fade-in">Uma solução.<br><em>Tudo integrado.</em></h2>

  <p class="slide-body fade-in">
    Combinamos armazenamento, geração solar e mobilidade elétrica em um único ecossistema energético — sofisticado, inteligente e sob medida.
  </p>

  <div class="eco-cards">
    <div class="eco-card fade-in">
      <svg class="eco-icon" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="8" y="4" width="20" height="28" rx="3" stroke="#C9A84C" stroke-width="1.5" fill="none"/>
        <path d="M13 10h10M13 16h10M13 22h6" stroke="#C9A84C" stroke-width="1.5" stroke-linecap="round"/>
        <circle cx="24" cy="27" r="2" stroke="#C9A84C" stroke-width="1.2" fill="none"/>
      </svg>
      <div>
        <div class="eco-name">Armazenamento</div>
        <p class="eco-desc">Baterias de última geração com gerenciamento inteligente de carga e descarga.</p>
      </div>
    </div>
    <div class="eco-card fade-in">
      <svg class="eco-icon" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="18" cy="18" r="6" stroke="#C9A84C" stroke-width="1.5" fill="none"/>
        <path d="M18 4v4M18 28v4M4 18h4M28 18h4" stroke="#C9A84C" stroke-width="1.5" stroke-linecap="round"/>
        <path d="M8.2 8.2l2.8 2.8M25 25l2.8 2.8M27.8 8.2L25 11M11 25l-2.8 2.8" stroke="#C9A84C" stroke-width="1.3" stroke-linecap="round"/>
      </svg>
      <div>
        <div class="eco-name">Energia Solar</div>
        <p class="eco-desc">Geração fotovoltaica integrada ao sistema de armazenamento, incluindo soluções BIPV.</p>
      </div>
    </div>
    <div class="eco-card fade-in">
      <svg class="eco-icon" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="4" y="12" width="24" height="14" rx="3" stroke="#C9A84C" stroke-width="1.5" fill="none"/>
        <circle cx="10" cy="29" r="3" stroke="#C9A84C" stroke-width="1.3" fill="none"/>
        <circle cx="22" cy="29" r="3" stroke="#C9A84C" stroke-width="1.3" fill="none"/>
        <path d="M28 18h4v4h-4" stroke="#C9A84C" stroke-width="1.3"/>
        <path d="M12 17l-2 4h5l-2 4" stroke="#C9A84C" stroke-width="1.3" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
      <div>
        <div class="eco-name">Mobilidade Elétrica</div>
        <p class="eco-desc">Carregadores para veículos elétricos com controle remoto e integração total ao ecossistema.</p>
      </div>
    </div>
  </div>
</section>

<!-- SLIDE 7: DIFERENCIAIS -->
<section class="slide" id="slide-diferenciais" data-slide="6">
  <div class="section-tag fade-in">Por que a ENERTUR</div>

  <h2 class="slide-title fade-in">Nossa<br><em>entrega</em></h2>

  <div class="diff-list">
    <div class="diff-item fade-in">
      <div class="diff-dot"></div>
      <div>
        <div class="diff-title">Diagnóstico Técnico Especializado</div>
        <p class="diff-desc">Análise detalhada do perfil de consumo para uma solução verdadeiramente personalizada.</p>
      </div>
    </div>
    <div class="diff-item fade-in">
      <div class="diff-dot"></div>
      <div>
        <div class="diff-title">Projeto Sob Medida</div>
        <p class="diff-desc">Design sofisticado aliado a desempenho técnico impecável — sem abrir mão da estética.</p>
      </div>
    </div>
    <div class="diff-item fade-in">
      <div class="diff-dot"></div>
      <div>
        <div class="diff-title">Parceiros de Alta Performance</div>
        <p class="diff-desc">Trabalhamos com líderes globais como Canadian Solar, SolaX e GoodWe, garantindo o melhor do mercado.</p>
      </div>
    </div>
    <div class="diff-item fade-in">
      <div class="diff-dot"></div>
      <div>
        <div class="diff-title">Instalação com Padrão Premium</div>
        <p class="diff-desc">Execução técnica de excelência com acabamento estético que valoriza o ambiente instalado.</p>
      </div>
    </div>
    <div class="diff-item fade-in">
      <div class="diff-dot"></div>
      <div>
        <div class="diff-title">Suporte Contínuo</div>
        <p class="diff-desc">Atendimento ágil e acompanhamento técnico especializado após a instalação.</p>
      </div>
    </div>
  </div>
</section>

<!-- SLIDE 8: CTA -->
<section class="slide" id="slide-cta" data-slide="7">
  <p class="cta-pre fade-in">Dê o próximo passo</p>

  <h2 class="cta-title fade-in">
    Conquiste sua<br><em>independência</em><br>energética
  </h2>

  <p class="cta-sub fade-in">
    Fale com nossos especialistas e descubra qual solução se encaixa no seu projeto.
  </p>

  <a href="#" class="cta-btn fade-in">
    Solicitar Proposta →
  </a>

  <p class="cta-social fade-in" style="margin-top:48px;">
    enertur.com.br &nbsp;·&nbsp; <span>@enertur.energia</span>
  </p>
</section>

<script>
  // Intersection Observer for fade-in
  const fadeEls = document.querySelectorAll('.fade-in');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
      }
    });
  }, { threshold: 0.15 });

  fadeEls.forEach(el => observer.observe(el));

  // Nav dots
  const slides = document.querySelectorAll('.slide');
  const dots = document.querySelectorAll('.nav-dot');

  const slideObserver = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        const idx = e.target.dataset.slide;
        dots.forEach(d => d.classList.remove('active'));
        document.querySelector(`.nav-dot[data-slide="${idx}"]`)?.classList.add('active');
      }
    });
  }, { threshold: 0.5 });

  slides.forEach(s => slideObserver.observe(s));

  dots.forEach(dot => {
    dot.addEventListener('click', () => {
      const idx = dot.dataset.slide;
      slides[idx].scrollIntoView({ behavior: 'smooth' });
    });
  });
</script>
</body>
</html>
