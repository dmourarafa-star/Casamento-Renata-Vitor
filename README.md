<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Lista de Casamento — Renata & Vitor</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #faf6f1;
      --warm: #f0e8dc;
      --gold: #b8935a;
      --gold-light: #d4aa72;
      --text: #2c2416;
      --text-light: #7a6a54;
      --green: #4a6741;
      --green-light: #6b9466;
      --white: #ffffff;
      --rose: #c0747a;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Jost', sans-serif;
      background: var(--cream);
      color: var(--text);
      overflow-x: hidden;
    }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 40px 20px;
      position: relative;
      background: linear-gradient(160deg, #faf6f1 0%, #f0e8dc 60%, #e8dccf 100%);
      overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute;
      inset: 0;
      background-image:
        radial-gradient(ellipse at 20% 20%, rgba(184,147,90,0.12) 0%, transparent 60%),
        radial-gradient(ellipse at 80% 80%, rgba(74,103,65,0.08) 0%, transparent 60%);
    }
    .hero-deco { position: absolute; top:0; left:0; right:0; bottom:0; pointer-events:none; overflow:hidden; }
    .petal {
      position: absolute;
      width: 6px; height: 10px;
      border-radius: 50% 50% 50% 0;
      opacity: 0.15;
      animation: fall linear infinite;
    }
    @keyframes fall {
      0%   { transform: translateY(-20px) rotate(0deg); opacity: 0; }
      10%  { opacity: 0.15; }
      90%  { opacity: 0.1; }
      100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
    }
    .hero-content { position: relative; z-index: 1; }
    .hero-label {
      font-family: 'Jost', sans-serif;
      font-weight: 300;
      font-size: 0.75rem;
      letter-spacing: 0.35em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 24px;
      animation: fadeUp 0.8s ease both;
    }
    .hero-names {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(3.5rem, 10vw, 7rem);
      font-weight: 300;
      line-height: 0.9;
      color: var(--text);
      animation: fadeUp 0.8s 0.15s ease both;
    }
    .hero-names span { color: var(--gold); font-style: italic; }
    .hero-divider {
      margin: 28px auto;
      width: 120px; height: 1px;
      background: linear-gradient(to right, transparent, var(--gold), transparent);
      animation: fadeUp 0.8s 0.3s ease both;
    }
    .hero-date {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.4rem;
      font-weight: 300;
      font-style: italic;
      color: var(--text-light);
      letter-spacing: 0.05em;
      animation: fadeUp 0.8s 0.45s ease both;
    }
    .hero-sub {
      margin-top: 14px;
      font-size: 0.85rem;
      font-weight: 300;
      letter-spacing: 0.12em;
      color: var(--text-light);
      animation: fadeUp 0.8s 0.55s ease both;
    }
    .hero-cta {
      margin-top: 40px;
      display: inline-block;
      padding: 14px 40px;
      border: 1px solid var(--gold);
      color: var(--gold);
      font-family: 'Jost', sans-serif;
      font-size: 0.78rem;
      font-weight: 400;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      text-decoration: none;
      transition: background 0.3s, color 0.3s;
      animation: fadeUp 0.8s 0.7s ease both;
      cursor: pointer;
      background: transparent;
    }
    .hero-cta:hover { background: var(--gold); color: var(--white); }
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── RSVP SECTION ── */
    .rsvp-section {
      background: var(--white);
      padding: 80px 24px;
    }
    .rsvp-inner {
      max-width: 600px;
      margin: 0 auto;
      text-align: center;
    }
    .rsvp-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 5vw, 2.8rem);
      font-weight: 300;
      margin-bottom: 12px;
    }
    .rsvp-subtitle {
      font-size: 0.85rem;
      font-weight: 300;
      color: var(--text-light);
      letter-spacing: 0.08em;
      margin-bottom: 40px;
    }
    .rsvp-form {
      display: flex;
      flex-direction: column;
      gap: 16px;
      text-align: left;
    }
    .rsvp-label {
      font-size: 0.7rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--text-light);
      margin-bottom: 6px;
      display: block;
    }
    .rsvp-input, .rsvp-select {
      width: 100%;
      padding: 13px 16px;
      border: 1px solid #ddd;
      border-radius: 3px;
      font-family: 'Jost', sans-serif;
      font-size: 0.9rem;
      color: var(--text);
      background: var(--cream);
      outline: none;
      transition: border-color 0.2s;
      appearance: none;
    }
    .rsvp-input:focus, .rsvp-select:focus { border-color: var(--gold); }
    .rsvp-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
    @media (max-width: 500px) { .rsvp-row { grid-template-columns: 1fr; } }
    .rsvp-btn {
      padding: 15px;
      background: var(--gold);
      color: white;
      border: none;
      border-radius: 3px;
      font-family: 'Jost', sans-serif;
      font-size: 0.78rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      cursor: pointer;
      transition: background 0.25s;
      margin-top: 4px;
    }
    .rsvp-btn:hover { background: #a07840; }
    .rsvp-success {
      display: none;
      background: linear-gradient(135deg, #f0faf0, #e8f5e8);
      border: 1px solid rgba(74,103,65,0.3);
      border-radius: 6px;
      padding: 32px;
      text-align: center;
    }
    .rsvp-success-icon { font-size: 3rem; margin-bottom: 12px; }
    .rsvp-success-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.8rem;
      font-weight: 400;
      color: var(--green);
      margin-bottom: 8px;
    }
    .rsvp-success-text { font-size: 0.9rem; color: var(--text-light); line-height: 1.6; }
    .rsvp-success .goto-gifts {
      display: inline-block;
      margin-top: 20px;
      padding: 12px 32px;
      background: var(--text);
      color: white;
      font-family: 'Jost', sans-serif;
      font-size: 0.75rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      text-decoration: none;
      border-radius: 3px;
      transition: background 0.25s;
      cursor: pointer;
      border: none;
    }
    .rsvp-success .goto-gifts:hover { background: var(--gold); }

    /* declined state */
    .rsvp-declined {
      display: none;
      background: linear-gradient(135deg, #fdf5f5, #faeaea);
      border: 1px solid rgba(192,116,122,0.3);
      border-radius: 6px;
      padding: 32px;
      text-align: center;
    }
    .rsvp-declined-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.8rem;
      font-weight: 400;
      color: var(--rose);
      margin-bottom: 8px;
    }
    .rsvp-declined-text { font-size: 0.9rem; color: var(--text-light); line-height: 1.6; }

    /* ── MESSAGE ── */
    .message-section {
      max-width: 640px;
      margin: 0 auto;
      padding: 80px 24px;
      text-align: center;
    }
    .section-label {
      font-size: 0.7rem;
      letter-spacing: 0.35em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 20px;
    }
    .message-text {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.35rem;
      font-weight: 300;
      line-height: 1.9;
      color: var(--text-light);
      font-style: italic;
    }

    /* ── GIFTS SECTION ── */
    .gifts-section {
      background: var(--warm);
      padding: 80px 24px;
    }
    .gifts-inner { max-width: 1100px; margin: 0 auto; }
    .gifts-header { text-align: center; margin-bottom: 56px; }
    .gifts-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 5vw, 3.2rem);
      font-weight: 300;
      color: var(--text);
      margin-bottom: 12px;
    }
    .gifts-subtitle {
      font-size: 0.85rem;
      font-weight: 300;
      color: var(--text-light);
      letter-spacing: 0.08em;
    }
    .filter-bar {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      justify-content: center;
      margin-bottom: 48px;
    }
    .filter-btn {
      padding: 8px 20px;
      border: 1px solid var(--gold-light);
      background: transparent;
      color: var(--text-light);
      font-family: 'Jost', sans-serif;
      font-size: 0.75rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      cursor: pointer;
      transition: all 0.25s;
      border-radius: 2px;
    }
    .filter-btn:hover, .filter-btn.active {
      background: var(--gold);
      border-color: var(--gold);
      color: var(--white);
    }
    .gifts-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 24px;
    }
    .gift-card {
      background: var(--white);
      border-radius: 4px;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      transition: transform 0.3s, box-shadow 0.3s;
      position: relative;
    }
    .gift-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 16px 40px rgba(44,36,22,0.1);
    }
    .gift-card.purchased { opacity: 0.65; }
    .gift-card.purchased::after {
      content: 'Presenteado ✓';
      position: absolute;
      top: 12px; right: 12px;
      background: var(--green);
      color: white;
      font-size: 0.65rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      padding: 4px 10px;
      border-radius: 2px;
    }
    .card-emoji {
      font-size: 3.5rem;
      text-align: center;
      padding: 36px 20px 20px;
      background: linear-gradient(135deg, var(--cream), var(--warm));
      line-height: 1;
    }
    .card-body {
      padding: 20px 24px 24px;
      flex: 1;
      display: flex;
      flex-direction: column;
    }
    .card-category {
      font-size: 0.65rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 8px;
    }
    .card-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.35rem;
      font-weight: 400;
      color: var(--text);
      margin-bottom: 8px;
      line-height: 1.3;
    }
    .card-desc {
      font-size: 0.82rem;
      font-weight: 300;
      color: var(--text-light);
      line-height: 1.6;
      flex: 1;
      margin-bottom: 20px;
    }
    .card-price {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.6rem;
      font-weight: 600;
      color: var(--text);
      margin-bottom: 16px;
    }
    .card-price small { font-size: 0.9rem; font-weight: 300; color: var(--text-light); }
    .gift-btn {
      width: 100%;
      padding: 13px;
      background: var(--text);
      color: var(--white);
      border: none;
      font-family: 'Jost', sans-serif;
      font-size: 0.75rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      cursor: pointer;
      transition: background 0.25s;
      border-radius: 2px;
    }
    .gift-btn:hover { background: var(--gold); }
    .gift-btn:disabled { background: #ccc; cursor: not-allowed; }

    /* ── MODAL ── */
    .modal-overlay {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(44,36,22,0.55);
      backdrop-filter: blur(4px);
      z-index: 1000;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }
    .modal-overlay.open { display: flex; }
    .modal {
      background: var(--white);
      max-width: 480px;
      width: 100%;
      border-radius: 6px;
      overflow: hidden;
      animation: modalIn 0.35s cubic-bezier(0.34,1.56,0.64,1) both;
      max-height: 90vh;
      overflow-y: auto;
    }
    @keyframes modalIn {
      from { opacity: 0; transform: scale(0.88) translateY(20px); }
      to   { opacity: 1; transform: scale(1) translateY(0); }
    }
    .modal-header {
      background: linear-gradient(135deg, var(--cream), var(--warm));
      padding: 32px 32px 24px;
      text-align: center;
      border-bottom: 1px solid rgba(184,147,90,0.2);
    }
    .modal-emoji { font-size: 3rem; margin-bottom: 12px; }
    .modal-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.6rem;
      font-weight: 400;
      color: var(--text);
      margin-bottom: 4px;
    }
    .modal-price {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.3rem;
      color: var(--gold);
      font-weight: 300;
    }
    .modal-body { padding: 28px 32px 32px; }
    .modal-label {
      font-size: 0.7rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--text-light);
      margin-bottom: 8px;
      margin-top: 20px;
      display: block;
    }
    .modal-label:first-child { margin-top: 0; }
    .modal-input {
      width: 100%;
      padding: 12px 16px;
      border: 1px solid #ddd;
      border-radius: 3px;
      font-family: 'Jost', sans-serif;
      font-size: 0.9rem;
      color: var(--text);
      background: var(--cream);
      transition: border-color 0.2s;
      outline: none;
    }
    .modal-input:focus { border-color: var(--gold); }
    .pix-box {
      background: linear-gradient(135deg, #f0faf0, #e8f5e8);
      border: 1px solid rgba(74,103,65,0.3);
      border-radius: 4px;
      padding: 20px;
      margin: 20px 0;
      text-align: center;
    }
    .pix-box-label {
      font-size: 0.65rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--green);
      margin-bottom: 6px;
    }
    .pix-key {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.4rem;
      font-weight: 600;
      color: var(--text);
      margin: 8px 0 4px;
      word-break: break-all;
    }
    .pix-name { font-size: 0.8rem; color: var(--text-light); }
    .copy-btn {
      margin-top: 12px;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 8px 18px;
      background: var(--green);
      color: white;
      border: none;
      border-radius: 3px;
      font-family: 'Jost', sans-serif;
      font-size: 0.72rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      cursor: pointer;
      transition: background 0.2s;
    }
    .copy-btn:hover { background: var(--green-light); }
    .copy-btn.copied { background: #2d7a2d; }
    .pix-amount-box {
      background: var(--cream);
      border: 1px dashed var(--gold-light);
      border-radius: 4px;
      padding: 14px;
      text-align: center;
      margin: 12px 0;
    }
    .pix-amount-label { font-size: 0.72rem; color: var(--text-light); margin-bottom: 4px; }
    .pix-amount-value {
      font-family: 'Cormorant Garamond', serif;
      font-size: 2rem;
      font-weight: 600;
      color: var(--gold);
    }
    .modal-confirm-btn {
      width: 100%;
      margin-top: 20px;
      padding: 15px;
      background: var(--green);
      color: white;
      border: none;
      border-radius: 3px;
      font-family: 'Jost', sans-serif;
      font-size: 0.78rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      cursor: pointer;
      transition: background 0.25s;
    }
    .modal-confirm-btn:hover { background: var(--green-light); }
    .modal-close-btn {
      width: 100%;
      margin-top: 10px;
      padding: 12px;
      background: transparent;
      color: var(--text-light);
      border: 1px solid #ddd;
      border-radius: 3px;
      font-family: 'Jost', sans-serif;
      font-size: 0.78rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      cursor: pointer;
      transition: border-color 0.2s;
    }
    .modal-close-btn:hover { border-color: var(--text-light); }

    /* ── FOOTER ── */
    footer {
      padding: 60px 24px;
      text-align: center;
      background: var(--text);
      color: rgba(255,255,255,0.5);
    }
    .footer-names {
      font-family: 'Cormorant Garamond', serif;
      font-size: 2rem;
      font-style: italic;
      font-weight: 300;
      color: var(--gold-light);
      margin-bottom: 12px;
    }
    .footer-date {
      font-size: 0.75rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
    }

    /* ── TOAST ── */
    .toast {
      position: fixed;
      bottom: 30px;
      left: 50%;
      transform: translateX(-50%) translateY(80px);
      background: var(--text);
      color: white;
      padding: 14px 28px;
      border-radius: 4px;
      font-size: 0.85rem;
      letter-spacing: 0.05em;
      z-index: 2000;
      transition: transform 0.4s cubic-bezier(0.34,1.56,0.64,1);
      white-space: nowrap;
    }
    .toast.show { transform: translateX(-50%) translateY(0); }

    @media (max-width: 600px) {
      .modal-body { padding: 20px; }
      .modal-header { padding: 24px 20px 20px; }
      .pix-key { font-size: 1.1rem; }
    }
  </style>
</head>
<body>

<div class="hero-deco" id="petals"></div>

<!-- HERO -->
<section class="hero">
  <div class="hero-content">
    <p class="hero-label">Lista de Casamento</p>
    <h1 class="hero-names">Renata<br><span>&</span><br>Vitor</h1>
    <div class="hero-divider"></div>
    <p class="hero-date">24 de Outubro de 2026</p>
    <p class="hero-sub">Celebre esse momento conosco</p>
    <button class="hero-cta" onclick="scrollToRSVP()">Confirmar Presença</button>
  </div>
</section>

<!-- MESSAGE -->
<section class="message-section">
  <p class="section-label">Nossa Mensagem</p>
  <p class="message-text">
    "Sua presença já é o maior presente, mas se quiser nos presentear com algo especial, confirme sua presença e escolha um item abaixo — você ajudará a construir nossa nova vida juntos. Cada gesto de carinho ficará guardado para sempre em nossos corações."
  </p>
</section>

<!-- RSVP -->
<section class="rsvp-section" id="rsvp">
  <div class="rsvp-inner">
    <p class="section-label">Confirmação de Presença</p>
    <h2 class="rsvp-title">Você vai ao nosso casamento?</h2>
    <p class="rsvp-subtitle">Confirme sua presença para acessar a lista de presentes</p>

    <div id="rsvpForm">
      <div class="rsvp-form">
        <div>
          <span class="rsvp-label">Seu nome completo</span>
          <input class="rsvp-input" type="text" id="rsvpName" placeholder="Ex: Ana Paula Silva"/>
        </div>
        <div class="rsvp-row">
          <div>
            <span class="rsvp-label">Número de acompanhantes</span>
            <select class="rsvp-select" id="rsvpGuests">
              <option value="0">Somente eu</option>
              <option value="1">+ 1 acompanhante</option>
              <option value="2">+ 2 acompanhantes</option>
              <option value="3">+ 3 acompanhantes</option>
              <option value="4">+ 4 ou mais</option>
            </select>
          </div>
          <div>
            <span class="rsvp-label">Confirmação</span>
            <select class="rsvp-select" id="rsvpAttend">
              <option value="yes">✓ Sim, vou comparecer!</option>
              <option value="no">✗ Não poderei comparecer</option>
            </select>
          </div>
        </div>
        <div>
          <span class="rsvp-label">Mensagem para os noivos (opcional)</span>
          <input class="rsvp-input" type="text" id="rsvpMsg" placeholder="Deixe um recado carinhoso 💛"/>
        </div>
        <button class="rsvp-btn" onclick="submitRSVP()">Confirmar Presença →</button>
      </div>
    </div>

    <div class="rsvp-success" id="rsvpSuccess">
      <div class="rsvp-success-icon">🎉</div>
      <div class="rsvp-success-title">Presença Confirmada!</div>
      <div class="rsvp-success-text" id="rsvpSuccessText">Que alegria! Mal podemos esperar para celebrar com você.</div>
      <button class="goto-gifts" onclick="scrollToGifts()">Ver Lista de Presentes →</button>
    </div>

    <div class="rsvp-declined" id="rsvpDeclined">
      <div style="font-size:2.5rem; margin-bottom:12px;">🥺</div>
      <div class="rsvp-declined-title">Que saudade antecipada...</div>
      <div class="rsvp-declined-text">Sentiremos muito a sua falta, mas entendemos. Você pode nos presentear mesmo à distância se quiser! 💛</div>
      <button class="goto-gifts" style="margin-top:20px; display:inline-block; padding:12px 32px; background:var(--gold); color:white; font-family:'Jost',sans-serif; font-size:0.75rem; letter-spacing:0.2em; text-transform:uppercase; text-decoration:none; border-radius:3px; transition:background 0.25s; cursor:pointer; border:none;" onclick="scrollToGifts()">Ver Lista de Presentes mesmo assim →</button>
    </div>
  </div>
</section>

<!-- GIFTS -->
<section class="gifts-section" id="presentes">
  <div class="gifts-inner">
    <div class="gifts-header">
      <div class="section-label">Lista de Presentes</div>
      <h2 class="gifts-title">Escolha seu presente</h2>
      <p class="gifts-subtitle">Após escolher, você receberá a chave Pix para enviar o valor diretamente para os noivos</p>
    </div>

    <div class="filter-bar">
      <button class="filter-btn active" onclick="filterGifts('todos', this)">Todos</button>
      <button class="filter-btn" onclick="filterGifts('lar', this)">Lar</button>
      <button class="filter-btn" onclick="filterGifts('cozinha', this)">Cozinha</button>
      <button class="filter-btn" onclick="filterGifts('viagem', this)">Viagem & Lua de Mel</button>
      <button class="filter-btn" onclick="filterGifts('experiencia', this)">Experiências</button>
      <button class="filter-btn" onclick="filterGifts('especial', this)">Especiais</button>
    </div>

    <div class="gifts-grid" id="giftsGrid"></div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p class="footer-names">Renata & Vitor</p>
  <p class="footer-date">24 · 10 · 2026</p>
</footer>

<!-- MODAL -->
<div class="modal-overlay" id="modalOverlay">
  <div class="modal" id="modal">
    <div class="modal-header">
      <div class="modal-emoji" id="modalEmoji">🎁</div>
      <div class="modal-title" id="modalTitle">Presente</div>
      <div class="modal-price" id="modalPrice">R$ 0,00</div>
    </div>
    <div class="modal-body">
      <span class="modal-label">Seu nome (para nossa memória 💛)</span>
      <input class="modal-input" type="text" id="gifterName" placeholder="Ex: Ana e João"/>

      <div class="pix-amount-box">
        <div class="pix-amount-label">Valor a transferir via Pix</div>
        <div class="pix-amount-value" id="pixAmountDisplay">R$ 0,00</div>
      </div>

      <div class="pix-box">
        <div class="pix-box-label">📱 Chave Pix — CPF</div>
        <div class="pix-key" id="pixKeyDisplay">430.306.118-25</div>
        <div class="pix-name" id="pixNameDisplay">Renata Dominicheli de Moura</div>
        <button class="copy-btn" onclick="copyPix()" id="copyBtn">📋 Copiar chave</button>
      </div>

      <p style="font-size:0.78rem; color:var(--text-light); line-height:1.6; text-align:center; margin-bottom:4px;">
        Após realizar a transferência Pix, clique em <strong>"Confirmar presente"</strong> para que seu nome apareça na nossa lista. 🎉
      </p>

      <button class="modal-confirm-btn" onclick="confirmGift()">✓ Confirmar presente</button>
      <button class="modal-close-btn" onclick="closeModal()">Cancelar</button>
    </div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
  // ─── CONFIGURAÇÃO PIX ────────────────────────────────────────────
  const PIX_KEY   = "430.306.118-25";
  const PIX_OWNER = "Renata Dominicheli de Moura";

  // ─── LISTA DE PRESENTES ─────────────────────────────────────────
  const gifts = [
    // LAR
    { id:1,  emoji:"🛋️",  category:"lar",        name:"Sofá para a Sala",            desc:"Aquele sofá confortável para relaxar juntos depois de um longo dia.",               price:800  },
    { id:2,  emoji:"🛏️",  category:"lar",        name:"Jogo de Cama King",           desc:"Lençóis de algodão egípcio para noites perfeitas.",                                price:420  },
    { id:3,  emoji:"🪴",  category:"lar",        name:"Vasos Decorativos",           desc:"Para deixar nosso cantinho ainda mais bonito e aconchegante.",                     price:160  },
    { id:4,  emoji:"🍽️",  category:"lar",        name:"Jogo de Jantar Completo",     desc:"Louças para receber família e amigos com estilo.",                                 price:390  },
    { id:5,  emoji:"🪞",  category:"lar",        name:"Espelho Decorativo",          desc:"Um espelho grande e elegante para a sala ou quarto.",                              price:180  },
    { id:6,  emoji:"🧴",  category:"lar",        name:"Kit Banheiro Luxo",           desc:"Conjunto de acessórios para deixar o banheiro elegante e organizado.",             price:220  },
    { id:7,  emoji:"🕯️",  category:"lar",        name:"Kit Aromatizadores",          desc:"Difusores e velas aromáticas para criar um lar perfumado e acolhedor.",           price:140  },
    { id:8,  emoji:"🛁",  category:"lar",        name:"Jogo de Toalhas",             desc:"Toalhas macias e absorventes para o casal.",                                       price:190  },
    { id:9,  emoji:"📺",  category:"lar",        name:"Smart TV",                    desc:"Contribuição para a TV da sala, para filmes e séries a dois.",                     price:500  },
    { id:10, emoji:"🧹",  category:"lar",        name:"Aspirador Robô",              desc:"Para facilitar a rotina e manter a casa sempre limpa.",                            price:450  },

    // COZINHA
    { id:11, emoji:"🍳",  category:"cozinha",    name:"Jogo de Panelas",             desc:"Conjunto completo para as primeiras receitas do nosso lar.",                        price:350  },
    { id:12, emoji:"☕",  category:"cozinha",    name:"Cafeteira Especial",          desc:"Porque toda manhã boa começa com um café delicioso.",                               price:280  },
    { id:13, emoji:"🥤",  category:"cozinha",    name:"Liquidificador de Alta Potência", desc:"Para smoothies, sopas e muito mais na rotina do casal.",                       price:260  },
    { id:14, emoji:"🍞",  category:"cozinha",    name:"Air Fryer",                   desc:"Praticidade e sabor nas refeições do dia a dia.",                                  price:320  },
    { id:15, emoji:"🍷",  category:"cozinha",    name:"Adega de Vinhos",             desc:"Para guardar e servir vinhos na temperatura certa.",                               price:480  },
    { id:16, emoji:"🥄",  category:"cozinha",    name:"Kit Utensílios de Cozinha",   desc:"Espátulas, colheres e acessórios de qualidade para o dia a dia.",                 price:130  },
    { id:17, emoji:"🍰",  category:"cozinha",    name:"Batedeira Planetária",        desc:"Para bolos, pães e sobremesas deliciosas feitas em casa.",                         price:370  },
    { id:18, emoji:"🫖",  category:"cozinha",    name:"Jogo de Copos e Taças",       desc:"Conjunto completo para água, suco, vinho e drinks.",                              price:200  },

    // VIAGEM
    { id:19, emoji:"✈️",  category:"viagem",     name:"Passagem Aérea",              desc:"Contribuição para levarmos nosso amor para longe nessa viagem especial.",          price:600  },
    { id:20, emoji:"🏨",  category:"viagem",     name:"Diária de Hotel",             desc:"Uma noite especial em hotel romântico na lua de mel.",                             price:450  },
    { id:21, emoji:"🌅",  category:"viagem",     name:"Passeio Romântico",           desc:"Jantar à beira-mar ou passeio de barco ao pôr do sol.",                           price:300  },
    { id:22, emoji:"🏖️",  category:"viagem",     name:"Pacote de Praia",             desc:"Ajude-nos a aproveitar a praia na lua de mel.",                                   price:500  },
    { id:23, emoji:"🧳",  category:"viagem",     name:"Mala de Viagem",              desc:"Uma mala linda e resistente para nossas aventuras juntos.",                        price:380  },
    { id:24, emoji:"🤿",  category:"viagem",     name:"Mergulho a Dois",             desc:"Uma experiência incrível debaixo d'água na lua de mel.",                          price:280  },

    // EXPERIÊNCIAS
    { id:25, emoji:"🍴",  category:"experiencia",name:"Jantar a Dois",               desc:"Uma noite especial em restaurante para celebrar o amor.",                          price:220  },
    { id:26, emoji:"🎭",  category:"experiencia",name:"Show ou Teatro",              desc:"Uma experiência cultural e inesquecível para o casal.",                            price:180  },
    { id:27, emoji:"💆",  category:"experiencia",name:"Spa para o Casal",            desc:"Massagem relaxante e tratamentos para renovar as energias.",                       price:340  },
    { id:28, emoji:"🍾",  category:"experiencia",name:"Degustação de Vinhos",        desc:"Uma tarde especial explorando rótulos e sabores incríveis.",                      price:260  },
    { id:29, emoji:"🎬",  category:"experiencia",name:"Cinema Premium a Dois",       desc:"Uma sessão especial em sala VIP com pipoca e conforto.",                          price:120  },
    { id:30, emoji:"🧗",  category:"experiencia",name:"Aventura em Casal",           desc:"Trilha, tirolesa ou outra aventura para criar memórias juntos.",                  price:200  },

    // ESPECIAIS
    { id:31, emoji:"💍",  category:"especial",   name:"Aliança da Memória",          desc:"Contribuição simbólica para a jornada que está apenas começando.",                 price:1000 },
    { id:32, emoji:"📸",  category:"especial",   name:"Álbum de Fotos Premium",      desc:"Para eternizar cada momento especial dessa nova fase.",                            price:450  },
    { id:33, emoji:"🌸",  category:"especial",   name:"Buquê Eterno",                desc:"Flores preservadas que durarão para sempre, como nosso amor.",                    price:250  },
    { id:34, emoji:"🏡",  category:"especial",   name:"Fundo do Lar",                desc:"Contribuição livre para ajudar a construir nosso ninho.",                         price:300  },
    { id:35, emoji:"🎁",  category:"especial",   name:"Surpresa dos Noivos",         desc:"Deixe um valor à sua escolha e os noivos decidem como usar com carinho.",          price:100  },
  ];

  // ─── ESTADO ──────────────────────────────────────────────────────
  const purchased = JSON.parse(localStorage.getItem('rv_purchased') || '[]');
  let currentGift = null;
  let currentFilter = 'todos';
  let rsvpDone = localStorage.getItem('rv_rsvp') === 'done';

  // ─── RSVP ────────────────────────────────────────────────────────
  function scrollToRSVP() {
    document.getElementById('rsvp').scrollIntoView({ behavior: 'smooth' });
  }

  function scrollToGifts() {
    document.getElementById('presentes').scrollIntoView({ behavior: 'smooth' });
  }

  function submitRSVP() {
    const name = document.getElementById('rsvpName').value.trim();
    if (!name) {
      document.getElementById('rsvpName').focus();
      showToast('Por favor, insira seu nome 😊');
      return;
    }
    const attend = document.getElementById('rsvpAttend').value;
    const guests = document.getElementById('rsvpGuests').value;
    const msg    = document.getElementById('rsvpMsg').value.trim();

    localStorage.setItem('rv_rsvp', 'done');
    rsvpDone = true;

    document.getElementById('rsvpForm').style.display = 'none';

    if (attend === 'yes') {
      const extra = parseInt(guests);
      const total = extra === 0 ? 'só você' : `você + ${extra} acompanhante${extra>1?'s':''}`;
      document.getElementById('rsvpSuccessText').textContent =
        `Que alegria, ${name}! Confirmamos sua presença (${total}). Mal podemos esperar para celebrar com você no dia 24 de outubro de 2026! ${msg ? '💌 "' + msg + '"' : ''}`;
      document.getElementById('rsvpSuccess').style.display = 'block';
    } else {
      document.getElementById('rsvpDeclined').style.display = 'block';
    }
  }

  // ─── RENDER GIFTS ────────────────────────────────────────────────
  function formatBRL(val) {
    return val.toLocaleString('pt-BR', { style:'currency', currency:'BRL' });
  }

  function renderGifts(filter) {
    const grid = document.getElementById('giftsGrid');
    const list = filter === 'todos' ? gifts : gifts.filter(g => g.category === filter);
    grid.innerHTML = list.map(g => {
      const done = purchased.includes(g.id);
      return `
        <div class="gift-card ${done ? 'purchased' : ''}">
          <div class="card-emoji">${g.emoji}</div>
          <div class="card-body">
            <div class="card-category">${catLabel(g.category)}</div>
            <div class="card-name">${g.name}</div>
            <div class="card-desc">${g.desc}</div>
            <div class="card-price">${formatBRL(g.price)} <small>sugerido</small></div>
            <button class="gift-btn" ${done ? 'disabled' : ''} onclick="openGift(${g.id})">
              ${done ? 'Presenteado ✓' : 'Presentear'}
            </button>
          </div>
        </div>`;
    }).join('');
  }

  function catLabel(cat) {
    return { lar:'Lar', cozinha:'Cozinha', viagem:'Viagem & Lua de Mel', experiencia:'Experiências', especial:'Especial' }[cat] || cat;
  }

  function filterGifts(cat, btn) {
    currentFilter = cat;
    document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    renderGifts(cat);
  }

  // ─── MODAL ───────────────────────────────────────────────────────
  function openGift(id) {
    currentGift = gifts.find(g => g.id === id);
    if (!currentGift) return;
    document.getElementById('modalEmoji').textContent = currentGift.emoji;
    document.getElementById('modalTitle').textContent = currentGift.name;
    document.getElementById('modalPrice').textContent = formatBRL(currentGift.price);
    document.getElementById('pixAmountDisplay').textContent = formatBRL(currentGift.price);
    document.getElementById('pixKeyDisplay').textContent = PIX_KEY;
    document.getElementById('pixNameDisplay').textContent = PIX_OWNER;
    document.getElementById('gifterName').value = '';
    document.getElementById('copyBtn').textContent = '📋 Copiar chave';
    document.getElementById('copyBtn').classList.remove('copied');
    document.getElementById('modalOverlay').classList.add('open');
    document.body.style.overflow = 'hidden';
  }

  function closeModal() {
    document.getElementById('modalOverlay').classList.remove('open');
    document.body.style.overflow = '';
    currentGift = null;
  }

  document.getElementById('modalOverlay').addEventListener('click', e => {
    if (e.target === e.currentTarget) closeModal();
  });

  function copyPix() {
    navigator.clipboard.writeText(PIX_KEY).then(() => {
      const btn = document.getElementById('copyBtn');
      btn.textContent = '✓ Copiado!';
      btn.classList.add('copied');
      showToast('Chave Pix copiada! 🎉');
      setTimeout(() => { btn.textContent = '📋 Copiar chave'; btn.classList.remove('copied'); }, 3000);
    });
  }

  function confirmGift() {
    if (!currentGift) return;
    const name = document.getElementById('gifterName').value.trim();
    if (!name) { document.getElementById('gifterName').focus(); showToast('Por favor, insira seu nome 😊'); return; }
    purchased.push(currentGift.id);
    localStorage.setItem('rv_purchased', JSON.stringify(purchased));
    closeModal();
    renderGifts(currentFilter);
    showToast(`Obrigado, ${name}! Presente confirmado 💛`);
  }

  // ─── TOAST ───────────────────────────────────────────────────────
  function showToast(msg) {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.classList.add('show');
    setTimeout(() => t.classList.remove('show'), 3500);
  }

  // ─── PETALS ──────────────────────────────────────────────────────
  (function() {
    const c = document.getElementById('petals');
    const colors = ['#b8935a','#d4aa72','#c4a882','#8b7355','#4a6741'];
    for (let i = 0; i < 18; i++) {
      const p = document.createElement('div');
      p.className = 'petal';
      p.style.cssText = `left:${Math.random()*100}%;width:${4+Math.random()*5}px;height:${7+Math.random()*8}px;background:${colors[Math.floor(Math.random()*colors.length)]};animation-duration:${8+Math.random()*12}s;animation-delay:${-Math.random()*15}s;border-radius:${Math.random()>0.5?'50% 50% 50% 0':'50%'};`;
      c.appendChild(p);
    }
  })();

  // ─── INIT ────────────────────────────────────────────────────────
  // Restore RSVP state if already done
  if (rsvpDone) {
    document.getElementById('rsvpForm').style.display = 'none';
    document.getElementById('rsvpSuccess').style.display = 'block';
    document.getElementById('rsvpSuccessText').textContent = 'Sua presença já está confirmada! Escolha um presente especial abaixo. 💛';
  }
  renderGifts('todos');
</script>
</body>
</html>
