# faruksocialmedia.github.io
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Gestão de Instagram</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
  :root {
    --blue-deep:  #1A3A5C;
    --blue-mid:   #2563A8;
    --blue-light: #4A90D9;
    --blue-pale:  #EBF3FB;
    --blue-soft:  #D6E8F7;
    --white:      #FFFFFF;
    --gray-1:     #F7F9FC;
    --gray-2:     #EEF2F7;
    --text:       #0F1E2E;
    --text-mid:   #3A5068;
    --muted:      #6A8AA8;
    --r:          14px;
    --r-lg:       20px;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html {
    scroll-behavior: smooth;
    overflow-x: hidden;
    max-width: 100%;
  }

  body {
    background: var(--white);
    color: var(--text);
    font-family: 'Montserrat', sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 1.75;
    overflow-x: hidden;
    -webkit-text-size-adjust: 100%;
    width: 100%;
    max-width: 100vw;
  }

  img { max-width: 100%; display: block; }

  /* ── NAV ── */
  nav {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(255,255,255,0.94);
    backdrop-filter: blur(14px);
    -webkit-backdrop-filter: blur(14px);
    border-bottom: 1px solid var(--gray-2);
    padding: 0 1.4rem;
    height: 60px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    max-width: 100%;
  }

  .nav-brand {
    font-size: 0.78rem;
    font-weight: 800;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--blue-deep);
    text-decoration: none;
    white-space: nowrap;
  }

  .nav-links {
    display: flex;
    gap: 1.6rem;
    list-style: none;
  }

  .nav-links a {
    font-size: 0.75rem;
    font-weight: 600;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    white-space: nowrap;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--blue-mid); }

  @media (max-width: 640px) { .nav-links { display: none; } }
  @media (min-width: 641px) { nav { padding: 0 clamp(1.5rem, 4vw, 5rem); } }

  /* ── HERO ── */
  .hero {
    background: linear-gradient(150deg, var(--blue-deep) 0%, #1e4d82 55%, var(--blue-mid) 100%);
    padding: clamp(3.5rem, 10vw, 7rem) 1.4rem clamp(3rem, 8vw, 5rem);
    position: relative;
    overflow: hidden;
    width: 100%;
    max-width: 100%;
  }

  @media (min-width: 641px) {
    .hero { padding-left: clamp(2rem, 6vw, 6rem); padding-right: clamp(2rem, 6vw, 6rem); }
  }

  .hero-bg {
    position: absolute; inset: 0;
    background-image:
      radial-gradient(circle at 85% 15%, rgba(74,144,217,0.2) 0%, transparent 45%),
      radial-gradient(circle at 10% 85%, rgba(255,255,255,0.04) 0%, transparent 40%);
    pointer-events: none;
  }

  .hero-lines {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
    background-size: 44px 44px;
    pointer-events: none;
  }

  .hero-inner { position: relative; max-width: 680px; }

  .hero-chip {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    background: rgba(255,255,255,0.1);
    border: 1px solid rgba(255,255,255,0.2);
    color: rgba(255,255,255,0.85);
    font-size: 0.68rem;
    font-weight: 700;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    padding: 0.4rem 1rem;
    border-radius: 100px;
    margin-bottom: 1.8rem;
    opacity: 0;
    animation: up 0.7s ease forwards 0.1s;
  }

  .hero h1 {
    font-size: clamp(2.2rem, 7vw, 4rem);
    font-weight: 900;
    color: #fff;
    line-height: 1.08;
    letter-spacing: -0.025em;
    margin-bottom: 1.2rem;
    opacity: 0;
    animation: up 0.7s ease forwards 0.25s;
  }

  .hero h1 span { color: var(--blue-light); }

  .hero-sub {
    font-size: clamp(0.95rem, 2.5vw, 1.05rem);
    font-weight: 400;
    color: rgba(255,255,255,0.65);
    max-width: 440px;
    margin-bottom: 2.2rem;
    line-height: 1.7;
    opacity: 0;
    animation: up 0.7s ease forwards 0.4s;
  }

  .hero-btns {
    display: flex;
    gap: 0.8rem;
    flex-wrap: wrap;
    opacity: 0;
    animation: up 0.7s ease forwards 0.55s;
  }

  @media (max-width: 400px) {
    .hero-btns { flex-direction: column; }
    .btn-white, .btn-ghost { text-align: center; width: 100%; }
  }

  .btn-white {
    background: #fff;
    color: var(--blue-deep);
    padding: 0.85rem 1.7rem;
    border-radius: var(--r);
    font-family: 'Montserrat', sans-serif;
    font-size: 0.88rem;
    font-weight: 800;
    letter-spacing: 0.02em;
    text-decoration: none;
    display: inline-block;
    transition: transform 0.2s, box-shadow 0.2s;
    border: none;
    cursor: pointer;
    white-space: nowrap;
  }
  .btn-white:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,0,0,0.22); }

  .btn-ghost {
    background: transparent;
    border: 1.5px solid rgba(255,255,255,0.3);
    color: rgba(255,255,255,0.9);
    padding: 0.85rem 1.7rem;
    border-radius: var(--r);
    font-family: 'Montserrat', sans-serif;
    font-size: 0.88rem;
    font-weight: 600;
    text-decoration: none;
    display: inline-block;
    transition: background 0.2s;
    white-space: nowrap;
  }
  .btn-ghost:hover { background: rgba(255,255,255,0.1); }

  .hero-stats {
    display: flex;
    gap: 2.2rem;
    margin-top: 3rem;
    flex-wrap: wrap;
    opacity: 0;
    animation: up 0.7s ease forwards 0.7s;
  }

  .stat-num {
    font-size: 1.7rem;
    font-weight: 900;
    color: #fff;
    line-height: 1;
    letter-spacing: -0.02em;
  }

  .stat-label {
    font-size: 0.68rem;
    font-weight: 600;
    color: rgba(255,255,255,0.45);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-top: 0.25rem;
  }

  /* ── LAYOUT ── */
  .wrap {
    max-width: 1040px;
    margin: 0 auto;
    padding-left: 1.4rem;
    padding-right: 1.4rem;
    width: 100%;
    box-sizing: border-box;
  }

  @media (min-width: 641px) {
    .wrap {
      padding-left: clamp(2rem, 4vw, 3.5rem);
      padding-right: clamp(2rem, 4vw, 3.5rem);
    }
  }

  section {
    width: 100%;
    max-width: 100%;
    overflow-x: hidden;
  }

  .sec { padding: clamp(3.2rem, 6vw, 5.5rem) 0; }

  .bg-gray { background: var(--gray-1); }

  .sec-label {
    font-size: 0.68rem;
    font-weight: 800;
    letter-spacing: 0.28em;
    text-transform: uppercase;
    color: var(--blue-mid);
    margin-bottom: 0.6rem;
  }

  h2 {
    font-size: clamp(1.65rem, 3.8vw, 2.4rem);
    font-weight: 900;
    color: var(--blue-deep);
    line-height: 1.15;
    letter-spacing: -0.02em;
    margin-bottom: 0.8rem;
  }

  h2 em { font-style: normal; color: var(--blue-mid); }

  .sec-desc {
    font-size: clamp(0.92rem, 2vw, 1rem);
    color: var(--muted);
    max-width: 520px;
    margin-bottom: 2.4rem;
    font-weight: 400;
    line-height: 1.7;
  }

  .divider { height: 1px; background: var(--gray-2); }

  /* ── DIFERENCIAIS ── */
  .diff-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1rem;
  }

  @media (min-width: 480px) { .diff-grid { grid-template-columns: 1fr 1fr; } }
  @media (min-width: 720px) { .diff-grid { grid-template-columns: repeat(4, 1fr); } }

  .diff-card {
    background: var(--white);
    border: 1px solid var(--gray-2);
    border-radius: var(--r-lg);
    padding: 1.6rem 1.3rem;
    transition: border-color 0.22s, transform 0.22s, box-shadow 0.22s;
  }

  #diferenciais .diff-card { background: var(--gray-1); }

  .diff-card:hover {
    border-color: var(--blue-soft);
    transform: translateY(-3px);
    box-shadow: 0 10px 28px rgba(37,99,168,0.09);
  }

  .diff-icon {
    width: 42px; height: 42px;
    border-radius: 10px;
    background: var(--blue-pale);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.15rem;
    margin-bottom: 1rem;
    flex-shrink: 0;
  }

  .diff-card h3 {
    font-size: 0.88rem;
    font-weight: 800;
    color: var(--blue-deep);
    margin-bottom: 0.4rem;
    line-height: 1.3;
  }

  .diff-card p {
    font-size: 0.82rem;
    color: var(--muted);
    line-height: 1.6;
  }

  /* ── SERVIÇOS ── */
  .srv-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 0.85rem;
  }

  @media (min-width: 640px) { .srv-grid { grid-template-columns: 1fr 1fr; } }

  .srv-item {
    background: var(--white);
    border: 1px solid var(--gray-2);
    border-radius: var(--r);
    padding: 1.3rem 1.5rem;
    display: flex;
    gap: 1rem;
    align-items: flex-start;
    transition: border-color 0.2s;
  }

  .srv-item:hover { border-color: var(--blue-light); }

  .srv-bar {
    width: 3px;
    min-height: 40px;
    border-radius: 4px;
    background: linear-gradient(to bottom, var(--blue-mid), var(--blue-light));
    flex-shrink: 0;
    align-self: stretch;
  }

  .srv-item h4 {
    font-size: 0.92rem;
    font-weight: 800;
    color: var(--blue-deep);
    margin-bottom: 0.25rem;
  }

  .srv-item p {
    font-size: 0.84rem;
    color: var(--muted);
    line-height: 1.6;
  }

  /* identidade visual — destaque especial */
  .srv-item.srv-iv {
    border-color: var(--blue-soft);
    background: var(--blue-pale);
    grid-column: 1 / -1;
  }

  .srv-item.srv-iv .srv-bar {
    background: linear-gradient(to bottom, var(--blue-deep), var(--blue-mid));
  }

  .srv-iv-price {
    display: inline-block;
    margin-top: 0.5rem;
    background: var(--blue-mid);
    color: #fff;
    font-size: 0.72rem;
    font-weight: 700;
    padding: 0.22rem 0.7rem;
    border-radius: 6px;
    letter-spacing: 0.03em;
  }

  /* ── PACOTES ── */
  .pkg-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.1rem;
  }

  @media (min-width: 760px) { .pkg-grid { grid-template-columns: repeat(3, 1fr); } }

  .pkg {
    background: var(--white);
    border: 1.5px solid var(--gray-2);
    border-radius: var(--r-lg);
    padding: 2rem 1.6rem;
    position: relative;
    transition: transform 0.25s, box-shadow 0.25s;
  }

  .pkg:hover { transform: translateY(-4px); box-shadow: 0 14px 36px rgba(37,99,168,0.1); }

  .pkg.featured {
    border-color: var(--blue-mid);
    background: linear-gradient(145deg, #fff, var(--blue-pale));
  }

  .pkg-badge {
    position: absolute;
    top: -13px; left: 50%;
    transform: translateX(-50%);
    background: var(--blue-mid);
    color: #fff;
    font-size: 0.62rem;
    font-weight: 800;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    padding: 0.28rem 1rem;
    border-radius: 100px;
    white-space: nowrap;
  }

  .pkg-tier {
    font-size: 0.65rem;
    font-weight: 800;
    letter-spacing: 0.24em;
    text-transform: uppercase;
    color: var(--blue-mid);
    margin-bottom: 0.6rem;
  }

  .pkg-price {
    font-size: 2.2rem;
    font-weight: 900;
    color: var(--blue-deep);
    line-height: 1;
    letter-spacing: -0.03em;
  }

  .pkg-period {
    font-size: 0.8rem;
    font-weight: 500;
    color: var(--muted);
    margin-bottom: 1.4rem;
  }

  .pkg-div { height: 1px; background: var(--gray-2); margin-bottom: 1.4rem; }

  .pkg ul { list-style: none; display: flex; flex-direction: column; gap: 0.6rem; }

  .pkg ul li {
    font-size: 0.85rem;
    color: var(--text-mid);
    display: flex;
    gap: 0.6rem;
    font-weight: 500;
    line-height: 1.5;
    align-items: flex-start;
  }

  .pkg ul li::before {
    content: '✓';
    color: var(--blue-mid);
    font-weight: 900;
    flex-shrink: 0;
    margin-top: 0.05rem;
  }

  .visit-note {
    margin-top: 1.3rem;
    background: var(--blue-pale);
    border-radius: 8px;
    padding: 0.7rem 1rem;
    font-size: 0.8rem;
    font-weight: 700;
    color: var(--blue-deep);
    line-height: 1.5;
  }

  /* ── PROCESSO ── */
  .steps {
    display: grid;
    grid-template-columns: 1fr;
    gap: 0.85rem;
  }

  @media (min-width: 640px) { .steps { grid-template-columns: 1fr 1fr; } }
  @media (min-width: 900px) { .steps { grid-template-columns: repeat(3, 1fr); } }

  .step {
    background: var(--white);
    border: 1px solid var(--gray-2);
    border-radius: var(--r);
    padding: 1.5rem 1.3rem;
    display: flex;
    gap: 1rem;
    transition: border-color 0.2s;
  }

  .step:hover { border-color: var(--blue-light); }

  .step-num {
    width: 36px; height: 36px;
    border-radius: 50%;
    background: var(--blue-pale);
    border: 1.5px solid var(--blue-soft);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.7rem;
    font-weight: 900;
    color: var(--blue-mid);
    flex-shrink: 0;
    margin-top: 0.1rem;
  }

  .step h4 {
    font-size: 0.92rem;
    font-weight: 800;
    color: var(--blue-deep);
    margin-bottom: 0.25rem;
  }

  .step p {
    font-size: 0.84rem;
    color: var(--muted);
    line-height: 1.6;
  }

  /* ── CONTATO ── */
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1rem;
    margin-top: 2rem;
  }

  @media (min-width: 560px) { .contact-grid { grid-template-columns: 1fr 1fr; } }

  .contact-card {
    background: var(--white);
    border: 1px solid var(--gray-2);
    border-radius: var(--r-lg);
    padding: 1.8rem 1.5rem;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    transition: border-color 0.2s, box-shadow 0.2s;
    text-decoration: none;
  }

  .contact-card:hover {
    border-color: var(--blue-light);
    box-shadow: 0 8px 24px rgba(37,99,168,0.08);
  }

  .contact-icon {
    font-size: 1.5rem;
    margin-bottom: 0.3rem;
  }

  .contact-label {
    font-size: 0.68rem;
    font-weight: 800;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--blue-mid);
  }

  .contact-value {
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--blue-deep);
    word-break: break-all;
  }

  .contact-hint {
    font-size: 0.78rem;
    color: var(--muted);
  }

  /* ── CTA ── */
  .cta-sec {
    background: linear-gradient(135deg, var(--blue-deep), var(--blue-mid));
    padding: clamp(3rem, 7vw, 6rem) 1.4rem;
    text-align: center;
    position: relative;
    overflow: hidden;
    width: 100%;
    max-width: 100%;
  }

  @media (min-width: 641px) { .cta-sec { padding-left: clamp(2rem, 6vw, 6rem); padding-right: clamp(2rem, 6vw, 6rem); } }

  .cta-sec::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(circle at 25% 50%, rgba(255,255,255,0.05), transparent 60%);
    pointer-events: none;
  }

  .cta-inner { position: relative; }

  .cta-sec .sec-label { color: rgba(255,255,255,0.55); }

  .cta-sec h2 {
    color: #fff;
    font-size: clamp(1.5rem, 3.8vw, 2.2rem);
    max-width: 480px;
    margin: 0.8rem auto 1rem;
  }

  .cta-sec h2 em { color: var(--blue-light); }

  .cta-sec > .cta-inner > p {
    font-size: 0.92rem;
    color: rgba(255,255,255,0.55);
    margin-bottom: 2rem;
  }

  /* ── FOOTER ── */
  footer {
    background: var(--blue-deep);
    padding: 1.6rem 1.4rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 0.5rem;
    border-top: 1px solid rgba(255,255,255,0.06);
    width: 100%;
    max-width: 100%;
    box-sizing: border-box;
  }

  @media (min-width: 641px) { footer { padding: 1.6rem clamp(2rem, 5vw, 5rem); } }

  footer p {
    font-size: 0.75rem;
    font-weight: 500;
    color: rgba(255,255,255,0.3);
    letter-spacing: 0.04em;
  }

  /* ── ANIM ── */
  @keyframes up {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0;
    transform: translateY(16px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .reveal.visible { opacity: 1; transform: none; }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-brand" href="#">Social Media</a>
  <ul class="nav-links">
    <li><a href="#diferenciais">Diferenciais</a></li>
    <li><a href="#servicos">Serviços</a></li>
    <li><a href="#pacotes">Pacotes</a></li>
    <li><a href="#como-funciona">Como funciona</a></li>
    <li><a href="#contato">Contato</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-lines"></div>
  <div class="hero-inner">
    <span class="hero-chip">📍 Jequié, BA · Gestão de Instagram</span>
    <h1>Seu perfil,<br>cuidado com<br><span>propósito.</span></h1>
    <p class="hero-sub">Conteúdo estratégico, visual profissional e linguagem certa para o seu público — com consistência real.</p>
    <div class="hero-btns">
      <a href="#pacotes" class="btn-white">Ver pacotes e valores</a>
      <a href="#como-funciona" class="btn-ghost">Como funciona</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">3</div>
        <div class="stat-label">Planos disponíveis</div>
      </div>
      <div>
        <div class="stat-num">8</div>
        <div class="stat-label">Serviços incluídos</div>
      </div>
      <div>
        <div class="stat-num">100%</div>
        <div class="stat-label">Aprovação prévia</div>
      </div>
    </div>
  </div>
</section>

<!-- DIFERENCIAIS -->
<section id="diferenciais">
  <div class="wrap sec reveal">
    <p class="sec-label">Por que me escolher</p>
    <h2>Vantagens de trabalhar <em>comigo</em></h2>
    <p class="sec-desc">Atendimento pessoal, da sua cidade, com comprometimento real e conhecimento da área de saúde.</p>
    <div class="diff-grid">
      <div class="diff-card">
        <div class="diff-icon">🎓</div>
        <h3>Formação em saúde</h3>
        <p>Acadêmico de Fisioterapia. Comunico saúde com precisão técnica e responsabilidade.</p>
      </div>
      <div class="diff-card">
        <div class="diff-icon">📍</div>
        <h3>Sou de Jequié</h3>
        <p>Atendimento presencial disponível. Conheço o público local e vou até você para captar conteúdo real.</p>
      </div>
      <div class="diff-card">
        <div class="diff-icon">🎨</div>
        <h3>Design com cuidado</h3>
        <p>Feed organizado, estética coerente e identidade visual consistente em cada publicação.</p>
      </div>
      <div class="diff-card">
        <div class="diff-icon">✅</div>
        <h3>Você aprova tudo</h3>
        <p>Nada vai ao ar sem sua aprovação. Comunicação direta, sem intermediários.</p>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- SERVIÇOS -->
<section id="servicos" class="bg-gray">
  <div class="wrap sec reveal">
    <p class="sec-label">O que está incluído</p>
    <h2>O que você <em>recebe</em></h2>
    <p class="sec-desc">Tudo que seu perfil precisa para crescer com consistência e profissionalismo.</p>
    <div class="srv-grid">

      <div class="srv-item">
        <div class="srv-bar"></div>
        <div>
          <h4>Posts para o Feed</h4>
          <p>Artes visuais com identidade do negócio, legenda e hashtags estratégicas.</p>
        </div>
      </div>

      <div class="srv-item">
        <div class="srv-bar"></div>
        <div>
          <h4>Stories</h4>
          <p>Bastidores, rotina, enquetes e informações rápidas para manter o engajamento diário.</p>
        </div>
      </div>

      <div class="srv-item">
        <div class="srv-bar"></div>
        <div>
          <h4>Reels com roteiro</h4>
          <p>Crio o roteiro e edito os vídeos curtos para ampliar o alcance orgânico.</p>
        </div>
      </div>

      <div class="srv-item">
        <div class="srv-bar"></div>
        <div>
          <h4>Visitas para captação</h4>
          <p>Vou até você para filmar e fotografar o dia a dia. Conteúdo real gera mais conexão.</p>
        </div>
      </div>

      <div class="srv-item">
        <div class="srv-bar"></div>
        <div>
          <h4>Agenda de conteúdo</h4>
          <p>Planejo as visitas conforme os dias mais movimentados do seu negócio.</p>
        </div>
      </div>

      <div class="srv-item">
        <div class="srv-bar"></div>
        <div>
          <h4>Planejamento mensal</h4>
          <p>Calendário completo com todos os conteúdos organizados com antecedência.</p>
        </div>
      </div>

      <div class="srv-item">
        <div class="srv-bar"></div>
        <div>
          <h4>Relatório de resultados</h4>
          <p>Resumo mensal com alcance, engajamento e crescimento do perfil.</p>
        </div>
      </div>

      <!-- IDENTIDADE VISUAL — SERVIÇO SEPARADO -->
      <div class="srv-item srv-iv">
        <div class="srv-bar"></div>
        <div>
          <h4>Identidade Visual</h4>
          <p>Criação de logo, paleta de cores, tipografia e manual de marca — para que o negócio tenha uma cara profissional e reconhecível em todos os canais.</p>
          <span class="srv-iv-price">💰 Precificação à parte · valor consultado e repassado ao cliente</span>
        </div>
      </div>

    </div>
  </div>
</section>

<div class="divider"></div>

<!-- PACOTES -->
<section id="pacotes">
  <div class="wrap sec reveal">
    <p class="sec-label">Investimento</p>
    <h2>Pacotes e <em>valores</em></h2>
    <p class="sec-desc">Planos pensados para negócios em Jequié e região. Sem surpresas, sem taxas ocultas.</p>

    <div class="pkg-grid">

      <!-- BASIC -->
      <div class="pkg">
        <p class="pkg-tier">Basic</p>
        <p class="pkg-price">R$ 400</p>
        <p class="pkg-period">por mês</p>
        <div class="pkg-div"></div>
        <ul>
          <li>6 posts no feed por mês</li>
          <li>3 stories por publicação, 3× por semana</li>
          <li>1 reel por mês com roteiro</li>
          <li>Legenda e hashtags em cada post</li>
          <li>Planejamento mensal</li>
          <li>Aprovação prévia de tudo</li>
        </ul>
        <div class="visit-note">📅 2 visitas presenciais por mês para captação de material</div>
      </div>

      <!-- INTERMEDIÁRIO -->
      <div class="pkg featured">
        <span class="pkg-badge">Recomendado</span>
        <p class="pkg-tier">Intermediário</p>
        <p class="pkg-price">R$ 700</p>
        <p class="pkg-period">por mês</p>
        <div class="pkg-div"></div>
        <ul>
          <li>10 posts no feed por mês</li>
          <li>5 stories todos os dias</li>
          <li>2 reels por mês com roteiro</li>
          <li>Legenda e hashtags em cada post</li>
          <li>Agenda de conteúdo personalizada</li>
          <li>Planejamento mensal</li>
          <li>Aprovação prévia de tudo</li>
          <li>Relatório de resultados</li>
        </ul>
        <div class="visit-note">📅 4 visitas presenciais por mês para captação de material</div>
      </div>

      <!-- COMPLETO -->
      <div class="pkg">
        <p class="pkg-tier">Completo</p>
        <p class="pkg-price">R$ 1.100</p>
        <p class="pkg-period">por mês</p>
        <div class="pkg-div"></div>
        <ul>
          <li>12 posts no feed por mês</li>
          <li>5 a 8 stories todos os dias</li>
          <li>4 reels por mês com roteiro</li>
          <li>Legenda e hashtags em cada post</li>
          <li>Agenda de conteúdo personalizada</li>
          <li>Planejamento mensal</li>
          <li>Aprovação prévia de tudo</li>
          <li>Relatório completo de resultados</li>
        </ul>
        <div class="visit-note">📅 6 visitas presenciais por mês para captação de material</div>
      </div>

    </div>
  </div>
</section>

<!-- PROCESSO -->
<section id="como-funciona" class="bg-gray">
  <div class="wrap sec reveal">
    <p class="sec-label">Processo de trabalho</p>
    <h2>Como <em>funciona</em></h2>
    <p class="sec-desc">Do primeiro contato até o perfil no ar, de forma simples e organizada.</p>
    <div class="steps">
      <div class="step">
        <div class="step-num">01</div>
        <div>
          <h4>Briefing</h4>
          <p>Entendo seus objetivos, público e expectativas. Presencial ou WhatsApp.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">02</div>
        <div>
          <h4>Proposta</h4>
          <p>Apresento o pacote mais adequado com escopo, valor e prazo definidos.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">03</div>
        <div>
          <h4>Agenda de visitas</h4>
          <p>Organizamos os melhores dias conforme a rotina do seu negócio.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">04</div>
        <div>
          <h4>Produção e aprovação</h4>
          <p>Crio cada conteúdo e envio para aprovação. Ajustes sem custo extra.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">05</div>
        <div>
          <h4>Publicação</h4>
          <p>Publico nos melhores horários e acompanho o desempenho ao longo do mês.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">06</div>
        <div>
          <h4>Relatório e renovação</h4>
          <p>Resultados do mês e alinhamento para o próximo ciclo.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTATO -->
<section id="contato">
  <div class="wrap sec reveal">
    <p class="sec-label">Fale comigo</p>
    <h2>Entre em <em>contato</em></h2>
    <p class="sec-desc">Sem compromisso. Respondo rápido pelo WhatsApp ou por e-mail.</p>
    <div class="contact-grid">
      <a class="contact-card" href="https://wa.me/5573988498375">
        <div class="contact-icon">💬</div>
        <div class="contact-label">WhatsApp</div>
        <div class="contact-value">+55 (73) 98849-8375</div>
        <div class="contact-hint">Atendimento rápido · clique para abrir</div>
      </a>
      <a class="contact-card" href="mailto:brtwfaruk010@gmail.com">
        <div class="contact-icon">✉️</div>
        <div class="contact-label">E-mail</div>
        <div class="contact-value">brtwfaruk010@gmail.com</div>
        <div class="contact-hint">Para propostas e orçamentos</div>
      </a>
    </div>
  </div>
</section>

<!-- CTA FINAL -->
<section class="cta-sec reveal">
  <div class="cta-inner">
    <p class="sec-label">Vamos começar</p>
    <h2>Pronto para um Instagram que <em>funciona de verdade?</em></h2>
    <p>Entre em contato agora, sem compromisso.</p>
    <a href="https://wa.me/5573988498375" class="btn-white">💬 Falar no WhatsApp</a>
  </div>
</section>

<footer>
  <p>Gestão de Instagram · Jequié, BA</p>
  <p>© 2025 · Todos os direitos reservados</p>
</footer>

<script>
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); }
    });
  }, { threshold: 0.06 });
  document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
</script>
</body>
</html>
