<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>Morall Buscas | Consultas cadastrais em painel privado</title>
  <meta name="description" content="Morall Buscas é uma plataforma privada para consultas cadastrais autorizadas, histórico de uso, planos mensais e integração via API." />
  <meta name="keywords" content="Morall Buscas, consulta cadastral, consulta CPF autorizada, API CPF, validação cadastral, painel de consultas, consulta para empresas" />
  <meta name="author" content="Morall Buscas" />
  <meta name="robots" content="index, follow" />
  <link rel="canonical" href="https://morallbuscas.com/" />

  <meta property="og:title" content="Morall Buscas | Consultas cadastrais em painel privado" />
  <meta property="og:description" content="Plataforma privada para consultas cadastrais autorizadas, histórico, assinatura mensal e pagamento via Pix." />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://morallbuscas.com/" />
  <meta property="og:site_name" content="Morall Buscas" />

  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="Morall Buscas | Consultas cadastrais em painel privado" />
  <meta name="twitter:description" content="Consultas cadastrais autorizadas em painel privado, com histórico, planos mensais e API." />

  <style>
    :root {
      --bg: #050814;
      --bg-2: #07111f;
      --card: rgba(12, 21, 39, 0.78);
      --card-2: rgba(10, 32, 56, 0.66);
      --text: #eef6ff;
      --muted: #9db2c8;
      --line: rgba(121, 203, 255, 0.16);
      --blue: #29b6ff;
      --cyan: #2ef2d0;
      --green: #5cffaa;
      --yellow: #ffd166;
      --danger: #ff6b6b;
      --shadow: 0 30px 80px rgba(0, 0, 0, 0.4);
      --radius: 24px;
      --max: 1180px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      min-height: 100vh;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Arial, sans-serif;
      color: var(--text);
      background:
        radial-gradient(circle at 10% 10%, rgba(41, 182, 255, 0.18), transparent 28%),
        radial-gradient(circle at 90% 15%, rgba(46, 242, 208, 0.12), transparent 26%),
        radial-gradient(circle at 55% 88%, rgba(41, 182, 255, 0.10), transparent 28%),
        linear-gradient(135deg, var(--bg), var(--bg-2));
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      pointer-events: none;
      background-image:
        linear-gradient(rgba(255,255,255,.035) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.035) 1px, transparent 1px);
      background-size: 54px 54px;
      mask-image: linear-gradient(to bottom, rgba(0,0,0,.9), transparent 82%);
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      width: min(var(--max), calc(100% - 36px));
      margin: 0 auto;
      position: relative;
      z-index: 2;
    }

    .nav {
      position: sticky;
      top: 0;
      z-index: 30;
      backdrop-filter: blur(22px);
      background: rgba(5, 8, 20, 0.70);
      border-bottom: 1px solid var(--line);
    }

    .nav-inner {
      height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 18px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 900;
      letter-spacing: -0.04em;
      font-size: 22px;
    }

    .brand-mark {
      width: 42px;
      height: 42px;
      border-radius: 16px;
      display: grid;
      place-items: center;
      background:
        linear-gradient(145deg, rgba(41,182,255,.95), rgba(46,242,208,.85));
      box-shadow: 0 0 32px rgba(41, 182, 255, .32);
      color: #03101d;
      font-weight: 1000;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 22px;
      color: var(--muted);
      font-size: 14px;
      font-weight: 700;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      min-height: 48px;
      padding: 0 18px;
      border-radius: 999px;
      border: 1px solid transparent;
      font-weight: 850;
      letter-spacing: -0.01em;
      transition: transform .22s ease, box-shadow .22s ease, border-color .22s ease, background .22s ease;
      cursor: pointer;
      white-space: nowrap;
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn-primary {
      color: #04111d;
      background: linear-gradient(135deg, var(--blue), var(--cyan));
      box-shadow: 0 18px 42px rgba(41, 182, 255, .25);
    }

    .btn-primary:hover {
      box-shadow: 0 24px 54px rgba(46, 242, 208, .25);
    }

    .btn-soft {
      color: var(--text);
      border-color: var(--line);
      background: rgba(255, 255, 255, .045);
    }

    .hero {
      padding: 86px 0 56px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.04fr) minmax(360px, .96fr);
      gap: 44px;
      align-items: center;
    }

    .eyebrow {
      width: fit-content;
      display: inline-flex;
      align-items: center;
      gap: 9px;
      padding: 9px 13px;
      border-radius: 999px;
      color: #c9faff;
      border: 1px solid rgba(46, 242, 208, .22);
      background: rgba(46, 242, 208, .08);
      font-size: 13px;
      font-weight: 800;
      margin-bottom: 22px;
    }

    .pulse {
      width: 9px;
      height: 9px;
      border-radius: 99px;
      background: var(--green);
      box-shadow: 0 0 0 0 rgba(92, 255, 170, .55);
      animation: pulse 1.8s infinite;
    }

    @keyframes pulse {
      70% { box-shadow: 0 0 0 12px rgba(92, 255, 170, 0); }
      100% { box-shadow: 0 0 0 0 rgba(92, 255, 170, 0); }
    }

    h1 {
      font-size: clamp(42px, 7vw, 78px);
      line-height: .94;
      letter-spacing: -0.075em;
      margin-bottom: 22px;
    }

    .grad {
      background: linear-gradient(135deg, #fff 10%, #8eeaff 45%, #4cffd9 80%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .hero-text {
      color: var(--muted);
      font-size: clamp(17px, 2vw, 21px);
      line-height: 1.72;
      max-width: 700px;
      margin-bottom: 28px;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      align-items: center;
      margin-bottom: 28px;
    }

    .trust-row {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      color: #c3d9ef;
      font-size: 13px;
      font-weight: 750;
    }

    .trust-pill {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 9px 12px;
      border-radius: 999px;
      background: rgba(255, 255, 255, .045);
      border: 1px solid var(--line);
    }

    .dashboard-card {
      position: relative;
      border: 1px solid var(--line);
      border-radius: 32px;
      padding: 16px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.08), rgba(255,255,255,.025)),
        rgba(5, 12, 25, .72);
      box-shadow: var(--shadow);
      overflow: hidden;
    }

    .dashboard-card::before {
      content: "";
      position: absolute;
      width: 260px;
      height: 260px;
      right: -70px;
      top: -70px;
      border-radius: 999px;
      background: radial-gradient(circle, rgba(46, 242, 208, .18), transparent 68%);
    }

    .mock-top {
      height: 58px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 10px 12px;
      border-bottom: 1px solid var(--line);
      position: relative;
      z-index: 1;
    }

    .dots {
      display: flex;
      gap: 7px;
    }

    .dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: rgba(255,255,255,.24);
    }

    .status {
      color: #bdfaf0;
      font-size: 12px;
      font-weight: 850;
      padding: 8px 11px;
      border-radius: 999px;
      background: rgba(46, 242, 208, .08);
      border: 1px solid rgba(46, 242, 208, .18);
    }

    .mock-body {
      padding: 20px 8px 8px;
      position: relative;
      z-index: 1;
    }

    .search-box {
      border-radius: 24px;
      padding: 18px;
      background: rgba(255,255,255,.045);
      border: 1px solid var(--line);
      margin-bottom: 16px;
    }

    .search-label {
      color: var(--muted);
      font-size: 12px;
      font-weight: 850;
      text-transform: uppercase;
      letter-spacing: .12em;
      margin-bottom: 10px;
    }

    .search-input {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
      border-radius: 16px;
      padding: 14px 14px;
      background: rgba(0,0,0,.22);
      border: 1px solid rgba(255,255,255,.08);
      color: #dff7ff;
      font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
      font-size: 14px;
    }

    .mini-btn {
      padding: 9px 12px;
      border-radius: 12px;
      background: linear-gradient(135deg, rgba(41,182,255,.95), rgba(46,242,208,.92));
      color: #03101d;
      font-weight: 900;
      font-size: 12px;
    }

    .result-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 14px;
    }

    .result-card {
      min-height: 112px;
      padding: 16px;
      border-radius: 22px;
      background: rgba(255,255,255,.04);
      border: 1px solid var(--line);
    }

    .result-card strong {
      display: block;
      font-size: 28px;
      letter-spacing: -0.05em;
      margin-bottom: 8px;
    }

    .result-card span {
      color: var(--muted);
      font-size: 13px;
      line-height: 1.55;
    }

    .section {
      padding: 70px 0;
    }

    .section-head {
      max-width: 760px;
      margin-bottom: 30px;
    }

    .kicker {
      color: var(--cyan);
      font-size: 13px;
      font-weight: 950;
      letter-spacing: .16em;
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    h2 {
      font-size: clamp(31px, 4vw, 52px);
      line-height: 1.02;
      letter-spacing: -0.06em;
      margin-bottom: 14px;
    }

    .section-head p {
      color: var(--muted);
      font-size: 17px;
      line-height: 1.7;
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 16px;
    }

    .card {
      border: 1px solid var(--line);
      border-radius: var(--radius);
      background: var(--card);
      padding: 24px;
      box-shadow: 0 18px 40px rgba(0,0,0,.16);
    }

    .icon {
      width: 48px;
      height: 48px;
      border-radius: 17px;
      display: grid;
      place-items: center;
      margin-bottom: 18px;
      background: rgba(41, 182, 255, .10);
      border: 1px solid rgba(41, 182, 255, .20);
      font-size: 22px;
    }

    .card h3 {
      font-size: 20px;
      letter-spacing: -0.03em;
      margin-bottom: 10px;
    }

    .card p, .card li {
      color: var(--muted);
      line-height: 1.65;
      font-size: 15px;
    }

    .split {
      display: grid;
      grid-template-columns: .92fr 1.08fr;
      gap: 20px;
      align-items: stretch;
    }

    .panel {
      border: 1px solid var(--line);
      border-radius: 30px;
      padding: 28px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.065), rgba(255,255,255,.025)),
        rgba(8, 16, 31, .78);
      box-shadow: var(--shadow);
    }

    .feature-list {
      list-style: none;
      display: grid;
      gap: 14px;
      margin-top: 18px;
    }

    .feature-list li {
      display: flex;
      gap: 12px;
      align-items: flex-start;
      color: #c7d9ec;
      line-height: 1.55;
    }

    .check {
      width: 22px;
      height: 22px;
      flex: 0 0 auto;
      border-radius: 999px;
      display: grid;
      place-items: center;
      color: #032014;
      background: var(--green);
      font-size: 13px;
      font-weight: 1000;
      margin-top: 1px;
    }

    .code-box {
      overflow: hidden;
      border-radius: 24px;
      border: 1px solid var(--line);
      background: #030712;
      box-shadow: inset 0 0 0 1px rgba(255,255,255,.025);
    }

    .code-head {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 14px 16px;
      border-bottom: 1px solid rgba(255,255,255,.08);
      color: var(--muted);
      font-size: 13px;
      font-weight: 800;
    }

    pre {
      overflow-x: auto;
      padding: 20px;
      color: #d7f7ff;
      font-size: 13px;
      line-height: 1.75;
    }

    .token {
      color: var(--cyan);
    }

    .plans {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 16px;
    }

    .plan {
      position: relative;
      border: 1px solid var(--line);
      border-radius: 28px;
      background: var(--card);
      padding: 24px;
      overflow: hidden;
    }

    .plan.featured {
      border-color: rgba(46, 242, 208, .42);
      background:
        radial-gradient(circle at 80% 0%, rgba(46, 242, 208, .14), transparent 42%),
        rgba(12, 21, 39, .84);
    }

    .badge {
      display: inline-flex;
      padding: 7px 10px;
      border-radius: 999px;
      color: #04111d;
      background: var(--cyan);
      font-size: 12px;
      font-weight: 950;
      margin-bottom: 14px;
    }

    .price {
      display: flex;
      align-items: baseline;
      gap: 4px;
      margin: 18px 0;
    }

    .price strong {
      font-size: 44px;
      letter-spacing: -0.07em;
    }

    .price span {
      color: var(--muted);
      font-weight: 750;
    }

    .plan ul {
      list-style: none;
      display: grid;
      gap: 11px;
      margin: 18px 0 22px;
    }

    .plan li {
      color: #c7d9ec;
      font-size: 14px;
      line-height: 1.5;
    }

    .notice {
      border: 1px solid rgba(255, 209, 102, .30);
      background: rgba(255, 209, 102, .08);
      color: #ffe7aa;
      border-radius: 24px;
      padding: 18px;
      line-height: 1.62;
      margin-top: 18px;
    }

    .faq {
      display: grid;
      gap: 12px;
    }

    details {
      border: 1px solid var(--line);
      background: rgba(255,255,255,.035);
      border-radius: 20px;
      padding: 18px 20px;
    }

    summary {
      cursor: pointer;
      font-weight: 900;
      letter-spacing: -0.02em;
    }

    details p {
      color: var(--muted);
      line-height: 1.65;
      padding-top: 12px;
    }

    .cta {
      text-align: center;
      border-radius: 34px;
      border: 1px solid rgba(46, 242, 208, .24);
      background:
        radial-gradient(circle at 25% 20%, rgba(41,182,255,.18), transparent 28%),
        radial-gradient(circle at 75% 30%, rgba(46,242,208,.16), transparent 28%),
        rgba(6, 16, 31, .8);
      padding: 52px 22px;
      box-shadow: var(--shadow);
    }

    .cta p {
      color: var(--muted);
      max-width: 720px;
      margin: 0 auto 24px;
      font-size: 17px;
      line-height: 1.7;
    }

    .footer {
      padding: 34px 0 50px;
      color: var(--muted);
      border-top: 1px solid var(--line);
      margin-top: 30px;
    }

    .footer-inner {
      display: flex;
      justify-content: space-between;
      gap: 18px;
      flex-wrap: wrap;
      font-size: 14px;
    }

    .footer a {
      color: #d8f6ff;
      font-weight: 800;
    }

    .floating {
      position: absolute;
      border-radius: 999px;
      filter: blur(4px);
      opacity: .8;
      pointer-events: none;
    }

    .floating.one {
      width: 18px;
      height: 18px;
      background: var(--cyan);
      left: 4%;
      top: 26%;
      animation: float 7s ease-in-out infinite;
    }

    .floating.two {
      width: 12px;
      height: 12px;
      background: var(--blue);
      right: 8%;
      top: 52%;
      animation: float 8s ease-in-out infinite reverse;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-18px); }
    }

    @media (max-width: 980px) {
      .nav-links {
        display: none;
      }

      .hero-grid,
      .split {
        grid-template-columns: 1fr;
      }

      .dashboard-card {
        max-width: 650px;
      }

      .cards,
      .plans {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media (max-width: 640px) {
      .container {
        width: min(100% - 24px, var(--max));
      }

      .nav-inner {
        height: 68px;
      }

      .brand {
        font-size: 18px;
      }

      .brand-mark {
        width: 38px;
        height: 38px;
        border-radius: 14px;
      }

      .hero {
        padding: 52px 0 34px;
      }

      .hero-actions,
      .trust-row {
        align-items: stretch;
        flex-direction: column;
      }

      .btn {
        width: 100%;
      }

      .cards,
      .plans,
      .result-grid {
        grid-template-columns: 1fr;
      }

      .panel,
      .card,
      .plan {
        padding: 20px;
      }

      .section {
        padding: 48px 0;
      }

      .search-input {
        align-items: stretch;
        flex-direction: column;
      }

      .mini-btn {
        text-align: center;
      }
    }
  </style>

  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "SoftwareApplication",
    "name": "Morall Buscas",
    "applicationCategory": "BusinessApplication",
    "operatingSystem": "Web",
    "description": "Plataforma privada para consultas cadastrais autorizadas, histórico, planos mensais e integração via API.",
    "url": "https://morallbuscas.com/",
    "offers": {
      "@type": "Offer",
      "priceCurrency": "BRL",
      "availability": "https://schema.org/InStock"
    }
  }
  </script>
</head>

<body>
  <div class="floating one"></div>
  <div class="floating two"></div>

  <header class="nav">
    <div class="container nav-inner">
      <a class="brand" href="#inicio" aria-label="Morall Buscas">
        <span class="brand-mark">MB</span>
        <span>Morall Buscas</span>
      </a>

      <nav class="nav-links" aria-label="Navegação principal">
        <a href="#recursos">Recursos</a>
        <a href="#api">API</a>
        <a href="#planos">Planos</a>
        <a href="#seguranca">Uso responsável</a>
        <a href="#faq">FAQ</a>
      </nav>

      <a class="btn btn-primary" href="https://morallbuscas.com/" rel="noopener">
        Acessar plataforma
      </a>
    </div>
  </header>

  <main id="inicio">
    <section class="hero">
      <div class="container hero-grid">
        <div>
          <div class="eyebrow">
            <span class="pulse"></span>
            Plataforma privada de consultas cadastrais
          </div>

          <h1>
            Consultas rápidas em um
            <span class="grad">painel organizado</span>
          </h1>

          <p class="hero-text">
            O Morall Buscas reúne consultas cadastrais autorizadas, histórico de uso,
            planos mensais, pagamento via Pix e integração por API em uma experiência
            simples, responsiva e focada em produtividade.
          </p>

          <div class="hero-actions">
            <a class="btn btn-primary" href="https://morallbuscas.com/" rel="noopener">
              Conhecer o Morall Buscas
            </a>
            <a class="btn btn-soft" href="#api">
              Ver exemplo de API
            </a>
          </div>

          <div class="trust-row">
            <span class="trust-pill">✓ Painel privado</span>
            <span class="trust-pill">✓ Histórico de consultas</span>
            <span class="trust-pill">✓ Integração via API</span>
            <span class="trust-pill">✓ Uso autorizado</span>
          </div>
        </div>

        <div class="dashboard-card" aria-label="Prévia visual do painel Morall Buscas">
          <div class="mock-top">
            <div class="dots">
              <span class="dot"></span>
              <span class="dot"></span>
              <span class="dot"></span>
            </div>
            <span class="status">Sistema online</span>
          </div>

          <div class="mock-body">
            <div class="search-box">
              <div class="search-label">Consulta cadastral</div>
              <div class="search-input">
                <span>CPF: 000.000.000-00</span>
                <span class="mini-btn">Consultar</span>
              </div>
            </div>

            <div class="result-grid">
              <div class="result-card">
                <strong>API</strong>
                <span>Integração para sistemas, painéis internos e fluxos operacionais.</span>
              </div>
              <div class="result-card">
                <strong>Pix</strong>
                <span>Assinatura mensal com ativação simples para acesso ao painel.</span>
              </div>
              <div class="result-card">
                <strong>Histórico</strong>
                <span>Organização das consultas realizadas em um ambiente privado.</span>
              </div>
              <div class="result-card">
                <strong>LGPD</strong>
                <span>Comunicação focada em finalidade legítima e uso autorizado.</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="recursos">
      <div class="container">
        <div class="section-head">
          <div class="kicker">Recursos</div>
          <h2>Uma central simples para consultar, organizar e integrar.</h2>
          <p>
            A landing page foi pensada para divulgar o Morall Buscas de forma profissional,
            sem expor dados sensíveis e sem prometer uso indevido de informações pessoais.
          </p>
        </div>

        <div class="cards">
          <article class="card">
            <div class="icon">🔎</div>
            <h3>Consultas rápidas</h3>
            <p>
              Interface objetiva para validações cadastrais em ambiente privado, com foco
              em velocidade, clareza e organização.
            </p>
          </article>

          <article class="card">
            <div class="icon">📊</div>
            <h3>Histórico organizado</h3>
            <p>
              Acompanhe consultas realizadas, uso da conta e informações operacionais em
              um painel limpo e fácil de entender.
            </p>
          </article>

          <article class="card">
            <div class="icon">⚡</div>
            <h3>API para integração</h3>
            <p>
              Endpoints para conectar a plataforma a sistemas internos, automações,
              validações e rotinas empresariais autorizadas.
            </p>
          </article>

          <article class="card">
            <div class="icon">💳</div>
            <h3>Planos mensais</h3>
            <p>
              Modelo de assinatura para acesso ao painel, com pagamento Pix e ativação
              prática conforme o plano contratado.
            </p>
          </article>

          <article class="card">
            <div class="icon">🛡️</div>
            <h3>Uso responsável</h3>
            <p>
              Comunicação baseada em finalidade legítima, autorização e respeito à
              privacidade dos titulares dos dados.
            </p>
          </article>

          <article class="card">
            <div class="icon">📱</div>
            <h3>Responsivo</h3>
            <p>
              Experiência adaptada para desktop, tablet e celular, ideal para divulgação
              via GitHub Pages, links e diretórios.
            </p>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="api">
      <div class="container split">
        <div class="panel">
          <div class="kicker">API</div>
          <h2>Exemplo limpo para documentação pública.</h2>
          <p style="color: var(--muted); line-height: 1.7;">
            Nunca publique tokens reais no GitHub. Use sempre exemplos fictícios, como
            <strong style="color: var(--text);">SEU_TOKEN_AQUI</strong>, e mantenha credenciais
            somente no backend ou em variáveis de ambiente.
          </p>

          <ul class="feature-list">
            <li><span class="check">✓</span><span>Autenticação por Bearer Token.</span></li>
            <li><span class="check">✓</span><span>Resposta em JSON para integração com sistemas.</span></li>
            <li><span class="check">✓</span><span>Exemplo com CPF fictício para evitar exposição de dados pessoais.</span></li>
            <li><span class="check">✓</span><span>Uso indicado apenas para finalidades autorizadas.</span></li>
          </ul>
        </div>

        <div class="code-box">
          <div class="code-head">
            <span>Exemplo de requisição</span>
            <span>curl</span>
          </div>
          <pre><code>curl -X GET "https://morallbuscas.com/api/v1/query/cpf?cpf=00000000000" \
  -H "Authorization: Bearer <span class="token">SEU_TOKEN_AQUI</span>" \
  -H "Accept: application/json"</code></pre>

          <div class="code-head">
            <span>Exemplo de resposta fictícia</span>
            <span>JSON</span>
          </div>
          <pre><code>{
  "success": true,
  "type": "cpf",
  "data": {
    "document": "000.000.000-00",
    "status": "exemplo_ficticio",
    "message": "Resposta demonstrativa para documentação pública."
  }
}</code></pre>
        </div>
      </div>
    </section>

    <section class="section" id="planos">
      <div class="container">
        <div class="section-head">
          <div class="kicker">Planos</div>
          <h2>Divulgação clara para assinatura mensal.</h2>
          <p>
            Edite os valores, limites e benefícios abaixo conforme os planos reais do seu painel.
            Mantive como modelo para página pública no GitHub.
          </p>
        </div>

        <div class="plans">
          <article class="plan">
            <span class="badge" style="background: rgba(41,182,255,.95);">Inicial</span>
            <h3>Plano Essencial</h3>
            <div class="price"><strong>R$30</strong><span>/mês</span></div>
            <ul>
              <li>✓ Acesso ao painel privado</li>
              <li>✓ Consultas cadastrais autorizadas</li>
              <li>✓ Histórico básico</li>
              <li>✓ Suporte inicial</li>
            </ul>
            <a class="btn btn-soft" href="https://morallbuscas.com/" rel="noopener">Assinar</a>
          </article>

          <article class="plan featured">
            <span class="badge">Mais escolhido</span>
            <h3>Plano Profissional</h3>
            <div class="price"><strong>R$50</strong><span>/mês</span></div>
            <ul>
              <li>✓ Tudo do plano Essencial</li>
              <li>✓ Mais volume de consultas</li>
              <li>✓ Histórico organizado</li>
              <li>✓ Melhor custo-benefício</li>
            </ul>
            <a class="btn btn-primary" href="https://morallbuscas.com/" rel="noopener">Começar agora</a>
          </article>

          <article class="plan">
            <span class="badge" style="background: var(--yellow);">Avançado</span>
            <h3>Plano API</h3>
            <div class="price"><strong>R$100</strong><span>/mês</span></div>
            <ul>
              <li>✓ Acesso ao painel</li>
              <li>✓ Integração via API</li>
              <li>✓ Uso para sistemas internos</li>
              <li>✓ Indicado para empresas</li>
            </ul>
            <a class="btn btn-soft" href="https://morallbuscas.com/" rel="noopener">Ver detalhes</a>
          </article>
        </div>

        <div class="notice">
          <strong>Aviso importante:</strong> esta página é uma divulgação institucional.
          Não utilize o serviço para perseguição, exposição de terceiros, invasão de privacidade
          ou qualquer finalidade sem autorização/base legal. Ajuste seus termos de uso e política
          de privacidade conforme sua operação real.
        </div>
      </div>
    </section>

    <section class="section" id="seguranca">
      <div class="container split">
        <div class="panel">
          <div class="kicker">Uso responsável</div>
          <h2>Mais confiança para quem visita sua página.</h2>
          <p style="color: var(--muted); line-height: 1.7;">
            Uma página pública de divulgação precisa passar profissionalismo e segurança.
            Por isso, evite linguagem agressiva como “puxar dados”, “descobrir CPF” ou
            “consultar qualquer pessoa”. Prefira termos como validação cadastral,
            consulta autorizada e uso empresarial.
          </p>
        </div>

        <div class="panel">
          <h3 style="font-size: 24px; letter-spacing: -.04em;">Boas práticas para divulgar</h3>
          <ul class="feature-list">
            <li><span class="check">✓</span><span>Use exemplos fictícios em toda documentação pública.</span></li>
            <li><span class="check">✓</span><span>Nunca publique tokens, chaves, CPFs reais ou respostas reais da API.</span></li>
            <li><span class="check">✓</span><span>Tenha páginas de termos de uso e política de privacidade.</span></li>
            <li><span class="check">✓</span><span>Explique que o acesso é privado e destinado a uso autorizado.</span></li>
            <li><span class="check">✓</span><span>Evite promessas que pareçam violar privacidade ou LGPD.</span></li>
          </ul>
        </div>
      </div>
    </section>

    <section class="section" id="faq">
      <div class="container">
        <div class="section-head">
          <div class="kicker">FAQ</div>
          <h2>Perguntas frequentes</h2>
          <p>
            Respostas curtas para deixar a divulgação mais completa e reduzir dúvidas antes
            do visitante acessar a plataforma.
          </p>
        </div>

        <div class="faq">
          <details>
            <summary>O Morall Buscas é gratuito?</summary>
            <p>
              A página de divulgação pode ficar gratuita no GitHub Pages. Já o acesso à
              plataforma, planos e consultas depende das condições comerciais informadas no site oficial.
            </p>
          </details>

          <details>
            <summary>Posso usar a API em qualquer sistema?</summary>
            <p>
              A integração deve ser feita apenas em sistemas e fluxos com finalidade legítima,
              autorização adequada e respeito à legislação aplicável.
            </p>
          </details>

          <details>
            <summary>Posso publicar meu token no GitHub?</summary>
            <p>
              Não. Tokens, chaves de API, CPFs reais e respostas reais de consultas nunca devem
              ser publicados em repositórios, páginas estáticas ou prints públicos.
            </p>
          </details>

          <details>
            <summary>Essa página já funciona no GitHub Pages?</summary>
            <p>
              Sim. Salve este arquivo como index.html na raiz do repositório e ative o GitHub Pages
              em Settings → Pages → Deploy from a branch → main → root.
            </p>
          </details>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="container">
        <div class="cta">
          <div class="kicker">Comece agora</div>
          <h2>Divulgue o Morall Buscas com uma página limpa, rápida e profissional.</h2>
          <p>
            Hospede este HTML no GitHub Pages, use como página institucional, diretório de divulgação
            ou documentação pública inicial, sempre com exemplos fictícios e comunicação responsável.
          </p>
          <a class="btn btn-primary" href="https://morallbuscas.com/" rel="noopener">
            Acessar site oficial
          </a>
        </div>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="container footer-inner">
      <span>© <span id="year"></span> Morall Buscas. Página pública de divulgação.</span>
      <span>
        <a href="https://morallbuscas.com/" rel="noopener">Site oficial</a>
        ·
        <a href="#seguranca">Uso responsável</a>
      </span>
    </div>
  </footer>

  <script>
    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
