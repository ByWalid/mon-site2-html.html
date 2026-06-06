<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Snack XL – Charleroi | Grillades & Friterie</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:ital,wght@0,300;0,400;0,600;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --fire: #E8420A;
    --ember: #FF7A1A;
    --gold: #F5B800;
    --dark: #111009;
    --char: #1C1A15;
    --ash: #2E2B22;
    --smoke: #3D3A30;
    --cream: #F7F0E0;
    --text: #D4C9A8;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--dark);
    color: var(--cream);
    font-family: 'Barlow', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.2rem 3rem;
    background: linear-gradient(to bottom, rgba(17,16,9,0.97), transparent);
    backdrop-filter: blur(2px);
  }
  .nav-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2rem;
    letter-spacing: 3px;
    color: var(--cream);
  }
  .nav-logo span { color: var(--fire); }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    color: var(--text);
    text-decoration: none;
    font-size: 0.8rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    transition: color 0.3s;
  }
  .nav-links a:hover { color: var(--gold); }
  .nav-cta {
    background: var(--fire);
    color: white !important;
    padding: 0.6rem 1.4rem;
    border-radius: 2px;
    font-weight: 600 !important;
    transition: background 0.3s !important;
  }
  .nav-cta:hover { background: var(--ember) !important; color: white !important; }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: flex; align-items: center;
    position: relative; overflow: hidden;
    padding: 0 3rem;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background: 
      radial-gradient(ellipse 60% 80% at 70% 50%, rgba(232,66,10,0.18) 0%, transparent 70%),
      radial-gradient(ellipse 40% 60% at 30% 80%, rgba(245,184,0,0.08) 0%, transparent 60%),
      linear-gradient(160deg, #0d0c07 0%, #1a1710 40%, #0f0e0a 100%);
  }
  .hero-grid {
    position: absolute; inset: 0;
    background-image: 
      linear-gradient(rgba(232,66,10,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(232,66,10,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 40%, transparent 100%);
  }
  .flame-particles {
    position: absolute; inset: 0; pointer-events: none;
  }
  .particle {
    position: absolute;
    width: 3px; height: 3px;
    border-radius: 50%;
    background: var(--gold);
    animation: rise linear infinite;
    opacity: 0;
  }
  @keyframes rise {
    0% { transform: translateY(0) scale(1); opacity: 0.8; }
    100% { transform: translateY(-200px) scale(0); opacity: 0; }
  }

  .hero-content { position: relative; z-index: 2; max-width: 700px; }
  .hero-badge {
    display: inline-block;
    border: 1px solid rgba(232,66,10,0.5);
    color: var(--ember);
    font-size: 0.7rem;
    letter-spacing: 4px;
    text-transform: uppercase;
    padding: 0.4rem 1rem;
    margin-bottom: 2rem;
    animation: fadeUp 0.8s ease both;
  }
  .hero-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(5rem, 12vw, 10rem);
    line-height: 0.9;
    letter-spacing: 4px;
    color: var(--cream);
    animation: fadeUp 0.8s 0.15s ease both;
  }
  .hero-title .fire-text {
    color: var(--fire);
    display: block;
    font-size: clamp(7rem, 16vw, 13rem);
    -webkit-text-stroke: 2px var(--fire);
    text-shadow: 0 0 60px rgba(232,66,10,0.5);
  }
  .hero-sub {
    font-size: 1rem;
    color: var(--text);
    letter-spacing: 1px;
    margin-top: 1.5rem;
    font-style: italic;
    animation: fadeUp 0.8s 0.3s ease both;
  }
  .hero-actions {
    display: flex; gap: 1rem; margin-top: 3rem;
    animation: fadeUp 0.8s 0.45s ease both;
  }
  .btn-primary {
    background: var(--fire);
    color: white;
    padding: 1rem 2.5rem;
    border: none; border-radius: 2px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.1rem;
    letter-spacing: 3px;
    cursor: pointer;
    text-decoration: none;
    display: inline-flex; align-items: center; gap: 0.5rem;
    transition: all 0.3s;
    position: relative; overflow: hidden;
  }
  .btn-primary::before {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(255,255,255,0.1), transparent);
    opacity: 0; transition: opacity 0.3s;
  }
  .btn-primary:hover { background: var(--ember); transform: translateY(-2px); box-shadow: 0 10px 30px rgba(232,66,10,0.4); }
  .btn-primary:hover::before { opacity: 1; }
  .btn-secondary {
    border: 1px solid rgba(212,201,168,0.3);
    color: var(--cream);
    padding: 1rem 2rem;
    border-radius: 2px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.1rem;
    letter-spacing: 3px;
    cursor: pointer;
    text-decoration: none;
    display: inline-flex; align-items: center; gap: 0.5rem;
    transition: all 0.3s;
  }
  .btn-secondary:hover { border-color: var(--gold); color: var(--gold); }

  .hero-info-strip {
    position: absolute; bottom: 3rem; right: 3rem;
    display: flex; flex-direction: column; gap: 1rem;
    align-items: flex-end;
    animation: fadeUp 0.8s 0.6s ease both;
  }
  .info-item {
    display: flex; align-items: center; gap: 0.8rem;
    color: var(--text); font-size: 0.85rem;
  }
  .info-icon { color: var(--fire); font-size: 1rem; }
  .scroll-hint {
    position: absolute; bottom: 2rem; left: 50%;
    transform: translateX(-50%);
    display: flex; flex-direction: column; align-items: center; gap: 0.5rem;
    color: var(--smoke); font-size: 0.7rem; letter-spacing: 3px;
    text-transform: uppercase;
    animation: bounce 2s infinite;
  }
  .scroll-line { width: 1px; height: 40px; background: linear-gradient(to bottom, transparent, var(--fire)); }
  @keyframes bounce { 0%,100% { transform: translateX(-50%) translateY(0); } 50% { transform: translateX(-50%) translateY(8px); } }
  @keyframes fadeUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }

  /* ── SECTIONS ── */
  section { padding: 6rem 3rem; }
  .section-label {
    font-size: 0.7rem;
    letter-spacing: 5px;
    text-transform: uppercase;
    color: var(--fire);
    margin-bottom: 0.8rem;
  }
  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(3rem, 6vw, 5rem);
    letter-spacing: 3px;
    line-height: 1;
    color: var(--cream);
    margin-bottom: 1.5rem;
  }
  .section-line {
    width: 60px; height: 2px;
    background: var(--fire);
    margin-bottom: 2rem;
  }

  /* ── ABOUT ── */
  #about {
    background: var(--char);
    display: grid; grid-template-columns: 1fr 1fr; gap: 6rem; align-items: center;
  }
  .about-visual {
    position: relative; height: 500px;
  }
  .about-box {
    position: absolute;
    background: var(--ash);
    border: 1px solid rgba(232,66,10,0.15);
  }
  .about-box-main {
    inset: 0;
    display: flex; align-items: center; justify-content: center;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 8rem;
    color: rgba(232,66,10,0.06);
    letter-spacing: 10px;
    overflow: hidden;
  }
  .about-accent {
    width: 140px; height: 140px;
    background: var(--fire);
    bottom: -20px; right: -20px;
    display: flex; align-items: center; justify-content: center;
    flex-direction: column;
  }
  .about-accent-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 3rem;
    color: white;
    line-height: 1;
  }
  .about-accent-txt { font-size: 0.6rem; letter-spacing: 2px; color: rgba(255,255,255,0.7); text-transform: uppercase; }
  .about-tag {
    position: absolute; top: -12px; left: 20px;
    background: var(--gold);
    color: var(--dark);
    font-family: 'Bebas Neue', sans-serif;
    letter-spacing: 2px;
    padding: 0.3rem 1rem;
    font-size: 0.85rem;
  }
  .about-text p {
    color: var(--text);
    line-height: 1.8;
    margin-bottom: 1.5rem;
    font-size: 1rem;
  }
  .about-pills {
    display: flex; flex-wrap: wrap; gap: 0.5rem; margin-top: 2rem;
  }
  .pill {
    border: 1px solid rgba(232,66,10,0.4);
    color: var(--ember);
    padding: 0.4rem 1rem;
    font-size: 0.75rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    border-radius: 1px;
  }

  /* ── MENU ── */
  #menu { background: var(--dark); }
  .menu-tabs {
    display: flex; gap: 0; margin-bottom: 3rem;
    border-bottom: 1px solid rgba(255,255,255,0.05);
    overflow-x: auto; -webkit-overflow-scrolling: touch;
  }
  .tab {
    padding: 1rem 1.5rem;
    border: none;
    background: none;
    color: var(--smoke);
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1rem;
    letter-spacing: 2px;
    cursor: pointer;
    border-bottom: 2px solid transparent;
    transition: all 0.3s;
    white-space: nowrap;
  }
  .tab.active, .tab:hover { color: var(--cream); border-bottom-color: var(--fire); }
  .menu-grid { display: none; }
  .menu-grid.active { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 1px; }
  .menu-item {
    background: var(--char);
    padding: 1.5rem;
    display: flex; justify-content: space-between; align-items: flex-start;
    gap: 1rem;
    transition: background 0.3s;
    position: relative; overflow: hidden;
  }
  .menu-item::before {
    content: '';
    position: absolute; left: 0; top: 0; bottom: 0;
    width: 3px;
    background: var(--fire);
    transform: scaleY(0);
    transition: transform 0.3s;
    transform-origin: bottom;
  }
  .menu-item:hover { background: var(--ash); }
  .menu-item:hover::before { transform: scaleY(1); }
  .menu-item-name {
    font-weight: 400;
    color: var(--cream);
    font-size: 0.95rem;
    margin-bottom: 0.3rem;
  }
  .menu-item-desc { color: var(--smoke); font-size: 0.8rem; line-height: 1.4; }
  .menu-item-price {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.3rem;
    color: var(--gold);
    letter-spacing: 1px;
    white-space: nowrap;
    flex-shrink: 0;
  }

  /* ── ORDER ── */
  #order {
    background: var(--fire);
    text-align: center;
    padding: 5rem 3rem;
    position: relative;
    overflow: hidden;
  }
  #order::before {
    content: 'XL';
    position: absolute;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 25rem;
    color: rgba(0,0,0,0.08);
    top: 50%; left: 50%;
    transform: translate(-50%,-50%);
    pointer-events: none;
    line-height: 1;
  }
  #order .section-label { color: rgba(255,255,255,0.6); }
  #order .section-title { color: white; }
  #order .section-line { background: rgba(255,255,255,0.4); margin: 0 auto 2rem; }
  #order p { color: rgba(255,255,255,0.8); max-width: 500px; margin: 0 auto 2.5rem; font-size: 1.05rem; }
  .order-btns { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; }
  .order-platform {
    background: rgba(0,0,0,0.2);
    border: 2px solid rgba(255,255,255,0.3);
    color: white;
    padding: 1rem 2rem;
    border-radius: 2px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.1rem;
    letter-spacing: 3px;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.3s;
    display: flex; align-items: center; gap: 0.5rem;
  }
  .order-platform:hover { background: rgba(0,0,0,0.4); border-color: white; }
  .order-phone {
    background: white;
    color: var(--fire);
    padding: 1rem 2rem;
    border-radius: 2px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.1rem;
    letter-spacing: 3px;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.3s;
    display: inline-flex; align-items: center; gap: 0.5rem;
  }
  .order-phone:hover { background: var(--cream); transform: translateY(-2px); }

  /* ── AVIS ── */
  #avis { background: var(--char); }
  .reviews-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1.5rem; margin-top: 3rem;
  }
  .review-card {
    background: var(--ash);
    padding: 2rem;
    border-top: 3px solid var(--fire);
    position: relative;
  }
  .review-stars { color: var(--gold); font-size: 1rem; margin-bottom: 1rem; letter-spacing: 2px; }
  .review-text { color: var(--text); font-size: 0.9rem; line-height: 1.7; font-style: italic; margin-bottom: 1.5rem; }
  .review-author { color: var(--cream); font-size: 0.8rem; letter-spacing: 2px; text-transform: uppercase; }
  .review-quote {
    position: absolute; top: 1.5rem; right: 1.5rem;
    font-size: 4rem;
    color: rgba(232,66,10,0.1);
    font-family: 'Bebas Neue', sans-serif;
    line-height: 1;
  }

  /* ── CONTACT ── */
  #contact {
    background: var(--dark);
    display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start;
  }
  .contact-info-block { display: flex; flex-direction: column; gap: 2rem; }
  .contact-item {
    display: flex; gap: 1.5rem; align-items: flex-start;
  }
  .contact-icon {
    width: 48px; height: 48px;
    background: var(--ash);
    border: 1px solid rgba(232,66,10,0.3);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.2rem;
    flex-shrink: 0;
  }
  .contact-detail { display: flex; flex-direction: column; gap: 0.3rem; }
  .contact-label { font-size: 0.7rem; letter-spacing: 3px; text-transform: uppercase; color: var(--fire); }
  .contact-val { color: var(--cream); font-size: 1rem; }
  .hours-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 0.5rem; }
  .hours-row { display: flex; justify-content: space-between; gap: 1rem; }
  .hours-day { color: var(--text); font-size: 0.85rem; }
  .hours-time { color: var(--cream); font-size: 0.85rem; }
  .map-embed {
    background: var(--ash);
    border: 1px solid rgba(232,66,10,0.15);
    height: 320px;
    overflow: hidden;
    position: relative;
  }
  .map-embed iframe { width: 100%; height: 100%; border: none; filter: grayscale(60%) contrast(1.1); }
  .map-tag {
    position: absolute; top: 1rem; left: 1rem;
    background: var(--fire);
    color: white;
    font-family: 'Bebas Neue', sans-serif;
    letter-spacing: 2px;
    padding: 0.3rem 0.8rem;
    font-size: 0.85rem;
    z-index: 2;
  }

  /* ── FOOTER ── */
  footer {
    background: #0a0900;
    padding: 2rem 3rem;
    display: flex; justify-content: space-between; align-items: center;
    border-top: 1px solid rgba(255,255,255,0.05);
    flex-wrap: wrap; gap: 1rem;
  }
  .footer-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.5rem;
    letter-spacing: 3px;
    color: var(--cream);
  }
  .footer-logo span { color: var(--fire); }
  .footer-copy { color: var(--smoke); font-size: 0.75rem; }
  .footer-social { display: flex; gap: 1rem; }
  .social-link {
    width: 36px; height: 36px;
    border: 1px solid rgba(255,255,255,0.1);
    display: flex; align-items: center; justify-content: center;
    color: var(--text);
    text-decoration: none;
    font-size: 0.85rem;
    transition: all 0.3s;
    border-radius: 2px;
  }
  .social-link:hover { border-color: var(--fire); color: var(--fire); }

  /* ── MOBILE ── */
  .mobile-order-bar {
    display: none;
    position: fixed; bottom: 0; left: 0; right: 0;
    background: var(--fire);
    z-index: 100; padding: 1rem 2rem;
    justify-content: center; align-items: center; gap: 1rem;
  }
  .mobile-order-bar a {
    color: white;
    text-decoration: none;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1rem;
    letter-spacing: 2px;
    display: flex; align-items: center; gap: 0.5rem;
  }
  .mobile-divider { width: 1px; height: 24px; background: rgba(255,255,255,0.3); }

  @media (max-width: 900px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    section { padding: 4rem 1.5rem; }
    #about, #contact { grid-template-columns: 1fr; gap: 3rem; }
    .hero-info-strip { display: none; }
    #hero { padding: 0 1.5rem; }
    .hero-title { font-size: clamp(4rem, 15vw, 7rem); }
    .hero-title .fire-text { font-size: clamp(5rem, 20vw, 9rem); }
    footer { flex-direction: column; text-align: center; }
    .mobile-order-bar { display: flex; }
    body { padding-bottom: 60px; }
    .about-visual { height: 300px; }
    .about-accent { width: 100px; height: 100px; bottom: -12px; right: -12px; }
    .about-accent-num { font-size: 2rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">SNACK <span>XL</span></div>
  <ul class="nav-links">
    <li><a href="#about">Notre Histoire</a></li>
    <li><a href="#menu">Menu</a></li>
    <li><a href="#avis">Avis</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="tel:071703418" class="nav-cta">📞 Commander</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="flame-particles" id="particles"></div>

  <div class="hero-content">
    <div class="hero-badge">🔥 Grillades au feu de charbon · Charleroi</div>
    <h1 class="hero-title">
      SNACK
      <span class="fire-text">XL</span>
    </h1>
    <p class="hero-sub">Grillades turques, friterie belge & saveurs généreuses —<br>Place de la Digue, Charleroi.</p>
    <div class="hero-actions">
      <a href="#menu" class="btn-primary">🍽 Voir le menu</a>
      <a href="#contact" class="btn-secondary">📍 Nous trouver</a>
    </div>
  </div>

  <div class="hero-info-strip">
    <div class="info-item"><span class="info-icon">📍</span><span>Place de la Digue 41, Charleroi</span></div>
    <div class="info-item"><span class="info-icon">🕙</span><span>Lun – Dim : 11h00 – 02h00</span></div>
    <div class="info-item"><span class="info-icon">📞</span><span>071 70 34 18</span></div>
  </div>

  <div class="scroll-hint">
    <span>Découvrir</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-visual">
    <div class="about-box about-box-main">GRILL</div>
    <div class="about-box about-accent">
      <div class="about-accent-num">XL</div>
      <div class="about-accent-txt">Charleroi</div>
    </div>
    <div class="about-tag">Depuis des années</div>
  </div>
  <div class="about-text">
    <div class="section-label">Notre histoire</div>
    <h2 class="section-title">L'art du<br>grill à Charleroi</h2>
    <div class="section-line"></div>
    <p>Le Snack XL, c'est l'adresse incontournable de la Place de la Digue. Une cuisine généreuse où les grillades au feu de charbon côtoient les classiques de la friterie belge et les spécialités turques.</p>
    <p>Ambiance chaleureuse, service rapide et des assiettes qui ne laissent personne sur sa faim — voilà ce qui nous définit depuis le premier jour.</p>
    <div class="about-pills">
      <span class="pill">🔥 Feu de charbon</span>
      <span class="pill">🌯 Cuisine turque</span>
      <span class="pill">🍟 Friterie belge</span>
      <span class="pill">🥗 Salades fraîches</span>
      <span class="pill">🧆 Falafel</span>
    </div>
  </div>
</section>

<!-- MENU -->
<section id="menu">
  <div class="section-label">Ce qu'on mange</div>
  <h2 class="section-title">Le menu</h2>
  <div class="section-line"></div>

  <div class="menu-tabs">
    <button class="tab active" onclick="showTab('grillades')">🔥 Grillades</button>
    <button class="tab" onclick="showTab('mitraillettes')">🥖 Mitraillettes</button>
    <button class="tab" onclick="showTab('durums')">🌯 Dürüms & Pitas</button>
    <button class="tab" onclick="showTab('burgers')">🍔 Burgers</button>
    <button class="tab" onclick="showTab('assiettes')">🍽 Assiettes</button>
    <button class="tab" onclick="showTab('salades')">🥗 Salades & Soupes</button>
    <button class="tab" onclick="showTab('desserts')">🍨 Desserts</button>
  </div>

  <div class="menu-grid active" id="grillades">
    <div class="menu-item"><div><div class="menu-item-name">Assiette Grillade XL</div><div class="menu-item-desc">Assortiment généreux : brochettes, köfte, merguez</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Brochette d'agneau</div><div class="menu-item-desc">Marinée au charbon, servie avec frites</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Brochette de bœuf</div><div class="menu-item-desc">Tendre et juteuse, feu de charbon</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Brochette de poulet</div><div class="menu-item-desc">Marinade maison, dorée à la braise</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Brochette de dinde</div><div class="menu-item-desc">Légère et savoureuse</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Côtes d'agneau</div><div class="menu-item-desc">Grillées au charbon, tendres et parfumées</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Côte à l'os</div><div class="menu-item-desc">La pièce incontournable de la maison</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Köfte</div><div class="menu-item-desc">Boulettes épicées grillées à la braise</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Merguez</div><div class="menu-item-desc">Merguez grillées, relevées</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Steak nature</div><div class="menu-item-desc">Pur bœuf, simplement grillé</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Pilons de poulet</div><div class="menu-item-desc">Marinés et grillés</div></div><div class="menu-item-price">—</div></div>
  </div>

  <div class="menu-grid" id="mitraillettes">
    <div class="menu-item"><div><div class="menu-item-name">Mitraillette Pita</div><div class="menu-item-desc">Pain pita, viande grillée, frites, sauces</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Mitraillette Poulet Mariné</div><div class="menu-item-desc">Poulet mariné maison, crudités, frites</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Mexicano</div><div class="menu-item-desc">Épicé, jalapeños, sauce mexicaine</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Mitraillette Hamburger</div><div class="menu-item-desc">Pain hamburger, steak, frites intégrées</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Mitraillette Boulettes</div><div class="menu-item-desc">Boulettes maison, sauce tomate, frites</div></div><div class="menu-item-price">—</div></div>
  </div>

  <div class="menu-grid" id="durums">
    <div class="menu-item"><div><div class="menu-item-name">Dürüm XL</div><div class="menu-item-desc">Feta, crudités fraîches, sauce maison</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Dürüm Classique</div><div class="menu-item-desc">Viande grillée, crudités, sauce</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Dürüm Végétarien</div><div class="menu-item-desc">Légumes grillés, fromage, sauce yaourt</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Dürüm Falafel</div><div class="menu-item-desc">Falafels maison, houmous, salade</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Dürüm Exotique</div><div class="menu-item-desc">Ananas, maïs, sauce exotique</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Pita Classique</div><div class="menu-item-desc">Pain pita, viande, crudités, sauce</div></div><div class="menu-item-price">—</div></div>
  </div>

  <div class="menu-grid" id="burgers">
    <div class="menu-item"><div><div class="menu-item-name">Burger Normal</div><div class="menu-item-desc">Steak, salade, tomate, sauce maison</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Burger Géant</div><div class="menu-item-desc">Double steak, extra garni</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Cheeseburger</div><div class="menu-item-desc">Steak, cheddar fondu</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Bicky Burger</div><div class="menu-item-desc">Le classique belge</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Fish Burger</div><div class="menu-item-desc">Filet de poisson pané, sauce tartare</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Chicken Burger</div><div class="menu-item-desc">Filet de poulet croustillant</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Köfte Burger</div><div class="menu-item-desc">Boulette épicée, sauce piquante</div></div><div class="menu-item-price">—</div></div>
  </div>

  <div class="menu-grid" id="assiettes">
    <div class="menu-item"><div><div class="menu-item-name">Assiette Pita</div><div class="menu-item-desc">Pita garni, salade, frites</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Assiette Poulet Mariné</div><div class="menu-item-desc">Poulet grillé, accompagnements</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Assiette Frites</div><div class="menu-item-desc">Frites maison, sauce au choix</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Vol-au-vent</div><div class="menu-item-desc">Le classique belge, sauce veloutée</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Boulettes sauce tomate</div><div class="menu-item-desc">Boulettes maison, sauce tomate maison</div></div><div class="menu-item-price">—</div></div>
  </div>

  <div class="menu-grid" id="salades">
    <div class="menu-item"><div><div class="menu-item-name">Salade Mixte</div><div class="menu-item-desc">Feta, olives, crudités fraîches, vinaigrette</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Salade de Poulet</div><div class="menu-item-desc">Poulet grillé, légumes de saison</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Soupe aux Lentilles</div><div class="menu-item-desc">Recette traditionnelle turque, épices douces</div></div><div class="menu-item-price">—</div></div>
  </div>

  <div class="menu-grid" id="desserts">
    <div class="menu-item"><div><div class="menu-item-name">Tiramisu Maison</div><div class="menu-item-desc">Recette maison, mascarpone et café</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Dame Blanche</div><div class="menu-item-desc">Glace vanille, chantilly, sauce chocolat</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Brésilienne</div><div class="menu-item-desc">Glace, fruits, crème chantilly</div></div><div class="menu-item-price">—</div></div>
    <div class="menu-item"><div><div class="menu-item-name">Boissons</div><div class="menu-item-desc">Sodas, eaux, Ayran (boisson au yaourt turc)</div></div><div class="menu-item-price">—</div></div>
  </div>

  <p style="color:var(--smoke); font-size:0.8rem; margin-top:2rem; text-align:center;">
    * Les prix ne sont pas affichés sur ce site. Contactez-nous ou passez directement pour connaître les tarifs actuels.
  </p>
</section>

<!-- ORDER -->
<section id="order">
  <div class="section-label">Commandez facilement</div>
  <h2 class="section-title">Emporter ou<br>livraison</h2>
  <div class="section-line"></div>
  <p>Commandez par téléphone pour emporter, ou retrouvez-nous sur vos plateformes de livraison préférées.</p>
  <div class="order-btns">
    <a href="tel:071703418" class="order-phone">📞 071 70 34 18</a>
    <a href="#" class="order-platform">🛵 Uber Eats</a>
    <a href="#" class="order-platform">🍕 Deliveroo</a>
    <a href="#" class="order-platform">📦 Take Away</a>
  </div>
</section>

<!-- AVIS -->
<section id="avis">
  <div class="section-label">Ce qu'ils en disent</div>
  <h2 class="section-title">Avis clients</h2>
  <div class="section-line"></div>
  <div class="reviews-grid">
    <div class="review-card">
      <div class="review-stars">★★★★★</div>
      <div class="review-quote">"</div>
      <p class="review-text">L'atmosphère est fantastique, la musique au bon goût et le personnel très attentif. Je me suis senti vraiment bien et j'y retourne sans hésitation !</p>
      <div class="review-author">— Anna S.</div>
    </div>
    <div class="review-card">
      <div class="review-stars">★★★★★</div>
      <div class="review-quote">"</div>
      <p class="review-text">L'endroit parfait pour passer une soirée inoubliable entre amis. Ambiance détendue et toujours animée. Je le recommande à tout le monde !</p>
      <div class="review-author">— Max M.</div>
    </div>
    <div class="review-card">
      <div class="review-stars">★★★★★</div>
      <div class="review-quote">"</div>
      <p class="review-text">La nourriture était délicieuse et l'ambiance électrisante. Une expérience vraiment mémorable que je n'hésiterai pas à renouveler.</p>
      <div class="review-author">— Sarah K.</div>
    </div>
    <div class="review-card">
      <div class="review-stars">★★★★☆</div>
      <div class="review-quote">"</div>
      <p class="review-text">Excellent rapport qualité-prix. Les boissons sont abordables et il y a régulièrement des offres spéciales. Un incontournable de Charleroi.</p>
      <div class="review-author">— Peter J.</div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div>
    <div class="section-label">Venez nous voir</div>
    <h2 class="section-title">Contact &<br>Localisation</h2>
    <div class="section-line"></div>
    <div class="contact-info-block">
      <div class="contact-item">
        <div class="contact-icon">📍</div>
        <div class="contact-detail">
          <span class="contact-label">Adresse</span>
          <span class="contact-val">Place de la Digue 41<br>6000 Charleroi, Belgique</span>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">📞</div>
        <div class="contact-detail">
          <span class="contact-label">Téléphone</span>
          <a href="tel:071703418" class="contact-val" style="color:var(--cream);text-decoration:none;">071 70 34 18</a>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">🕙</div>
        <div class="contact-detail">
          <span class="contact-label">Horaires</span>
          <div style="display:flex;flex-direction:column;gap:0.3rem;margin-top:0.3rem;">
            <div class="hours-row"><span class="hours-day">Lundi – Jeudi</span><span class="hours-time">11:00 – 02:00</span></div>
            <div class="hours-row"><span class="hours-day">Vendredi – Samedi</span><span class="hours-time">11:00 – 03:00</span></div>
            <div class="hours-row"><span class="hours-day">Dimanche</span><span class="hours-time">11:00 – 02:00</span></div>
          </div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">🧾</div>
        <div class="contact-detail">
          <span class="contact-label">TVA</span>
          <span class="contact-val">BE 0757 635 920</span>
        </div>
      </div>
    </div>
  </div>
  <div>
    <div class="map-embed">
      <div class="map-tag">📍 Snack XL</div>
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2532.3!2d4.4440!3d50.4105!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47c22b2b3d3d3d3d%3A0x0!2sPlace+de+la+Digue+41%2C+6000+Charleroi!5e0!3m2!1sfr!2sbe!4v1000000000000"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </div>
    <a href="https://maps.google.com/?q=Place+de+la+Digue+41,+6000+Charleroi" 
       target="_blank" class="btn-primary" style="margin-top:1rem;display:inline-flex;">
      🗺 Ouvrir dans Google Maps
    </a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">SNACK <span>XL</span></div>
  <div class="footer-copy">© 2025 Snack XL · Place de la Digue 41, Charleroi · TVA BE 0757 635 920</div>
  <div class="footer-social">
    <a href="#" class="social-link" title="Facebook">f</a>
    <a href="#" class="social-link" title="Instagram">ig</a>
  </div>
</footer>

<!-- MOBILE BAR -->
<div class="mobile-order-bar">
  <a href="tel:071703418">📞 Appeler</a>
  <div class="mobile-divider"></div>
  <a href="#menu">🍽 Menu</a>
  <div class="mobile-divider"></div>
  <a href="#contact">📍 Trouver</a>
</div>

<script>
  // Particles
  const container = document.getElementById('particles');
  for (let i = 0; i < 20; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    p.style.left = Math.random() * 100 + '%';
    p.style.bottom = Math.random() * 30 + '%';
    p.style.animationDuration = (3 + Math.random() * 5) + 's';
    p.style.animationDelay = (Math.random() * 5) + 's';
    p.style.width = p.style.height = (2 + Math.random() * 4) + 'px';
    p.style.background = Math.random() > 0.5 ? 'var(--gold)' : 'var(--fire)';
    container.appendChild(p);
  }

  // Tabs
  function showTab(id) {
    document.querySelectorAll('.menu-grid').forEach(g => g.classList.remove('active'));
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    event.target.classList.add('active');
  }

  // Scroll animation
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.review-card, .menu-item, .contact-item').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(20px)';
    el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
