<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>WLLEY — Vivre Sainement, Sans Compromis</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:ital,opsz,wght@0,9..40,200;0,9..40,400;0,9..40,500;1,9..40,200&family=Playfair+Display:ital,wght@0,700;0,900;1,700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="style.css">
</head>
<body>

<!-- CURSOR -->
<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- TOAST -->
<div class="toast" id="toast">
  <span class="toast-icon">🌿</span>
  <span id="toastMsg">Ajouté au panier !</span>
</div>

<!-- NAV -->
<nav id="navbar">
  <a href="#" class="nav-logo">WLLEY</a>
  <button class="nav-toggle" id="navToggle" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
  <ul class="nav-links" id="navLinks">
    <li><a href="#manifeste">Notre Vision</a></li>
    <li><a href="#pilliers">Piliers</a></li>
    <li><a href="#produits">Produits</a></li>
    <li><a href="#lifestyle">Lifestyle</a></li>
    <li><a href="#newsletter" class="nav-cta">Rejoindre</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-landscape">
    <!-- Animated SVG landscape -->
    <svg class="landscape-svg" viewBox="0 0 1440 900" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="skyGrad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#0d1f14"/>
          <stop offset="40%" stop-color="#1a3d24"/>
          <stop offset="100%" stop-color="#2d6a4f"/>
        </linearGradient>
        <linearGradient id="mountainGrad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#1a4a2a"/>
          <stop offset="100%" stop-color="#0d2215"/>
        </linearGradient>
        <linearGradient id="mountain2Grad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#22603a"/>
          <stop offset="100%" stop-color="#1a4a2a"/>
        </linearGradient>
        <linearGradient id="foreGrad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#2d7a50"/>
          <stop offset="100%" stop-color="#1a4a30"/>
        </linearGradient>
        <linearGradient id="waterGrad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#3d9970" stop-opacity="0.6"/>
          <stop offset="100%" stop-color="#1a5a38" stop-opacity="0.8"/>
        </linearGradient>
        <filter id="glow">
          <feGaussianBlur stdDeviation="3" result="blur"/>
          <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
        </filter>
        <radialGradient id="sunGrad" cx="50%" cy="30%" r="50%">
          <stop offset="0%" stop-color="#a8e6c1" stop-opacity="0.4"/>
          <stop offset="100%" stop-color="transparent"/>
        </radialGradient>
      </defs>
      <!-- Sky -->
      <rect width="1440" height="900" fill="url(#skyGrad)"/>
      <!-- Atmospheric glow -->
      <ellipse cx="720" cy="200" rx="500" ry="250" fill="url(#sunGrad)"/>
      <!-- Stars -->
      <g class="stars" opacity="0.6">
        <circle cx="120" cy="80" r="1.2" fill="#a8e6c1"/>
        <circle cx="280" cy="50" r="0.8" fill="white"/>
        <circle cx="450" cy="100" r="1" fill="#a8e6c1"/>
        <circle cx="650" cy="40" r="1.5" fill="white" opacity="0.7"/>
        <circle cx="900" cy="70" r="0.9" fill="#a8e6c1"/>
        <circle cx="1100" cy="45" r="1.2" fill="white"/>
        <circle cx="1300" cy="90" r="0.8" fill="#a8e6c1"/>
        <circle cx="200" cy="150" r="0.7" fill="white" opacity="0.5"/>
        <circle cx="1200" cy="160" r="0.9" fill="#a8e6c1" opacity="0.6"/>
        <circle cx="760" cy="30" r="1.1" fill="white" opacity="0.8"/>
        <circle cx="380" cy="170" r="0.6" fill="#a8e6c1" opacity="0.5"/>
        <circle cx="980" cy="120" r="0.8" fill="white" opacity="0.6"/>
      </g>
      <!-- Mountains back -->
      <path d="M0,550 L120,350 L240,420 L360,280 L480,370 L600,240 L720,320 L840,200 L960,300 L1080,230 L1200,340 L1320,260 L1440,380 L1440,900 L0,900 Z" fill="url(#mountainGrad)" opacity="0.7"/>
      <!-- Mountains mid -->
      <path d="M0,620 L180,420 L300,490 L420,370 L540,450 L660,340 L780,420 L900,360 L1020,440 L1140,380 L1260,460 L1380,400 L1440,450 L1440,900 L0,900 Z" fill="url(#mountain2Grad)"/>
      <!-- Animated mist layer -->
      <g class="mist-layer">
        <path d="M-200,680 Q200,650 600,670 Q1000,690 1400,660 Q1600,650 1800,670 L1800,720 Q1400,710 1000,720 Q600,730 200,710 Q-100,700 -200,720 Z" fill="#2d6a4f" opacity="0.3">
          <animateTransform attributeName="transform" type="translate" values="0,0;200,0;0,0" dur="12s" repeatCount="indefinite"/>
        </path>
        <path d="M-400,700 Q200,680 600,695 Q1000,710 1400,690 Q1800,675 2000,690 L2000,740 Q1400,750 1000,740 Q600,730 200,745 Q-200,755 -400,740 Z" fill="#3d8a60" opacity="0.2">
          <animateTransform attributeName="transform" type="translate" values="0,0;-150,0;0,0" dur="18s" repeatCount="indefinite"/>
        </path>
      </g>
      <!-- Foreground hills -->
      <path d="M0,750 Q200,700 400,730 Q600,760 800,720 Q1000,680 1200,710 Q1400,740 1440,730 L1440,900 L0,900 Z" fill="url(#foreGrad)"/>
      <!-- Water/lake -->
      <ellipse cx="720" cy="800" rx="300" ry="30" fill="url(#waterGrad)"/>
      <!-- Water ripples -->
      <g opacity="0.4">
        <ellipse cx="720" cy="800" rx="280" ry="8" fill="none" stroke="#6fcf9a" stroke-width="1">
          <animate attributeName="rx" values="280;320;280" dur="4s" repeatCount="indefinite"/>
          <animate attributeName="opacity" values="0.4;0;0.4" dur="4s" repeatCount="indefinite"/>
        </ellipse>
        <ellipse cx="720" cy="800" rx="200" ry="5" fill="none" stroke="#6fcf9a" stroke-width="0.5">
          <animate attributeName="rx" values="200;260;200" dur="4s" begin="1s" repeatCount="indefinite"/>
          <animate attributeName="opacity" values="0.4;0;0.4" dur="4s" begin="1s" repeatCount="indefinite"/>
        </ellipse>
      </g>
      <!-- Trees left -->
      <g class="trees-left">
        <polygon points="60,700 80,600 100,700" fill="#1a5a30"/>
        <polygon points="55,720 82,620 109,720" fill="#1d6535"/>
        <polygon points="20,720 50,640 80,720" fill="#165028"/>
        <polygon points="90,710 115,620 140,710" fill="#1a5a30" opacity="0.8"/>
      </g>
      <!-- Trees right -->
      <g class="trees-right">
        <polygon points="1340,700 1360,600 1380,700" fill="#1a5a30"/>
        <polygon points="1370,720 1395,620 1420,720" fill="#1d6535"/>
        <polygon points="1300,715 1330,635 1360,715" fill="#165028"/>
        <polygon points="1390,710 1415,625 1440,710" fill="#1a5a30" opacity="0.8"/>
      </g>
      <!-- Fireflies / particles -->
      <g class="fireflies" filter="url(#glow)">
        <circle cx="300" cy="650" r="2" fill="#a8e6c1" opacity="0.8">
          <animate attributeName="opacity" values="0.8;0;0.8" dur="3s" repeatCount="indefinite"/>
          <animateTransform attributeName="transform" type="translate" values="0,0;10,-15;0,0" dur="3s" repeatCount="indefinite"/>
        </circle>
        <circle cx="500" cy="680" r="1.5" fill="#74d7a3" opacity="0.7">
          <animate attributeName="opacity" values="0.7;0;0.7" dur="4s" begin="1s" repeatCount="indefinite"/>
          <animateTransform attributeName="transform" type="translate" values="0,0;-8,-20;0,0" dur="4s" begin="1s" repeatCount="indefinite"/>
        </circle>
        <circle cx="900" cy="660" r="2" fill="#a8e6c1" opacity="0.6">
          <animate attributeName="opacity" values="0.6;0;0.6" dur="5s" begin="2s" repeatCount="indefinite"/>
          <animateTransform attributeName="transform" type="translate" values="0,0;12,-12;0,0" dur="5s" begin="2s" repeatCount="indefinite"/>
        </circle>
        <circle cx="1100" cy="690" r="1.5" fill="#74d7a3" opacity="0.8">
          <animate attributeName="opacity" values="0.8;0;0.8" dur="3.5s" begin="0.5s" repeatCount="indefinite"/>
          <animateTransform attributeName="transform" type="translate" values="0,0;-5,-18;0,0" dur="3.5s" begin="0.5s" repeatCount="indefinite"/>
        </circle>
        <circle cx="650" cy="670" r="1.8" fill="#a8e6c1" opacity="0.7">
          <animate attributeName="opacity" values="0.7;0;0.7" dur="4.5s" begin="1.5s" repeatCount="indefinite"/>
          <animateTransform attributeName="transform" type="translate" values="0,0;8,-14;0,0" dur="4.5s" begin="1.5s" repeatCount="indefinite"/>
        </circle>
      </g>
    </svg>
  </div>

  <div class="hero-content">
    <p class="hero-eyebrow">Bienvenue dans le monde de</p>
    <h1 class="hero-title">WLLEY</h1>
    <p class="hero-tagline">Vivre sainement, <em>sans compromis</em></p>
    <p class="hero-sub">Pour tous ceux qui choisissent de prendre soin d'eux — de leur corps, de leur esprit, de leur âme. Naturellement.</p>
    <div class="hero-btns">
      <a href="#produits" class="btn-primary">Découvrir nos produits</a>
      <a href="#manifeste" class="btn-ghost">Notre philosophie</a>
    </div>
  </div>

  <div class="hero-scroll">
    <span>Découvrir</span>
    <div class="scroll-arrow">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
        <path d="M12 5v14M5 12l7 7 7-7" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-section">
  <div class="marquee-track">
    <span class="marquee-item">NATUREL <span class="dot">✦</span></span>
    <span class="marquee-item">100% VEGAN <span class="dot">✦</span></span>
    <span class="marquee-item">BIEN-ÊTRE GLOBAL <span class="dot">✦</span></span>
    <span class="marquee-item">FORCES VÉGÉTALES <span class="dot">✦</span></span>
    <span class="marquee-item">SANS COMPROMIS <span class="dot">✦</span></span>
    <span class="marquee-item">POUR TOUS <span class="dot">✦</span></span>
    <span class="marquee-item">WLLEY <span class="dot">✦</span></span>
    <span class="marquee-item">NATUREL <span class="dot">✦</span></span>
    <span class="marquee-item">100% VEGAN <span class="dot">✦</span></span>
    <span class="marquee-item">BIEN-ÊTRE GLOBAL <span class="dot">✦</span></span>
    <span class="marquee-item">FORCES VÉGÉTALES <span class="dot">✦</span></span>
    <span class="marquee-item">SANS COMPROMIS <span class="dot">✦</span></span>
    <span class="marquee-item">POUR TOUS <span class="dot">✦</span></span>
    <span class="marquee-item">WLLEY <span class="dot">✦</span></span>
  </div>
</div>

<!-- MANIFESTE -->
<section id="manifeste" class="section">
  <div class="container">
    <div class="manifeste-grid">
      <div class="manifeste-left reveal">
        <span class="section-tag">Notre Vision</span>
        <h2 class="display-heading">
          La santé<br>
          <em>n'est pas un<br>privilège.</em>
        </h2>
        <div class="manifeste-stats">
          <div class="stat-item reveal" style="--delay:0.1s">
            <div class="stat-number">100<span>%</span></div>
            <div class="stat-label">Ingrédients naturels</div>
          </div>
          <div class="stat-item reveal" style="--delay:0.2s">
            <div class="stat-number">0</div>
            <div class="stat-label">Compromis sur la qualité</div>
          </div>
          <div class="stat-item reveal" style="--delay:0.3s">
            <div class="stat-number">∞</div>
            <div class="stat-label">Potentiel en chacun de nous</div>
          </div>
        </div>
      </div>
      <div class="manifeste-right reveal" style="--delay:0.2s">
        <p>WLLEY est née d'une conviction profonde : <strong>prendre soin de soi devrait être accessible à tous</strong>. Pas seulement aux athlètes, pas seulement aux plus jeunes — à chacun qui choisit de vivre pleinement.</p>
        <p>Nous avons créé des soins capillaires naturels, des compléments végétaux et une communauté fondée sur le respect — de son corps, de la nature, des autres.</p>
        <p><strong>WLLEY, c'est un choix de vie.</strong> Celui qui commence par un geste simple, et qui transforme tout.</p>
        <div class="values-list">
          <div class="value-item reveal" style="--delay:0.1s">
            <span class="value-icon">🌿</span>
            <div>
              <h4>Formules éthiques</h4>
              <p>Véganes, sans sulfates, sans paraffine. Respectueux de ton corps et de notre planète.</p>
            </div>
          </div>
          <div class="value-item reveal" style="--delay:0.2s">
            <span class="value-icon">💚</span>
            <div>
              <h4>Pour tout le monde</h4>
              <p>Que tu aies 18 ou 60 ans, que tu sois sportif ou sédentaire — le bien-être est universel.</p>
            </div>
          </div>
          <div class="value-item reveal" style="--delay:0.3s">
            <span class="value-icon">🌍</span>
            <div>
              <h4>Impact positif</h4>
              <p>Chaque achat contribue à des projets de reforestation et d'agriculture durable.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- NATURE BREAK - IMMERSIVE LANDSCAPE -->
<section class="nature-break">
  <div class="nature-landscape">
    <svg viewBox="0 0 1440 500" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="dawnGrad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#0f2a18"/>
          <stop offset="50%" stop-color="#1e5c35"/>
          <stop offset="100%" stop-color="#2d8a52"/>
        </linearGradient>
        <linearGradient id="fieldGrad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#3aaa6a"/>
          <stop offset="100%" stop-color="#1a5a30"/>
        </linearGradient>
        <radialGradient id="sunriseGrad" cx="50%" cy="60%" r="60%">
          <stop offset="0%" stop-color="#74d7a3" stop-opacity="0.5"/>
          <stop offset="60%" stop-color="#2d6a4f" stop-opacity="0.2"/>
          <stop offset="100%" stop-color="transparent"/>
        </radialGradient>
      </defs>
      <rect width="1440" height="500" fill="url(#dawnGrad)"/>
      <ellipse cx="720" cy="300" rx="600" ry="300" fill="url(#sunriseGrad)"/>
      <!-- Rolling hills -->
      <path d="M0,320 Q180,260 360,290 Q540,320 720,270 Q900,220 1080,270 Q1260,320 1440,290 L1440,500 L0,500 Z" fill="#1a5030" opacity="0.8"/>
      <path d="M0,370 Q180,330 360,350 Q540,370 720,340 Q900,310 1080,340 Q1260,370 1440,350 L1440,500 L0,500 Z" fill="url(#fieldGrad)"/>
      <!-- Grass blades -->
      <g opacity="0.6" stroke="#5dba7d" stroke-width="1.5" fill="none">
        <line x1="100" y1="380" x2="95" y2="355"><animate attributeName="x2" values="95;88;95" dur="3s" repeatCount="indefinite"/></line>
        <line x1="150" y1="375" x2="147" y2="348"><animate attributeName="x2" values="147;141;147" dur="4s" repeatCount="indefinite"/></line>
        <line x1="350" y1="365" x2="345" y2="338"><animate attributeName="x2" values="345;338;345" dur="3.5s" repeatCount="indefinite"/></line>
        <line x1="700" y1="355" x2="694" y2="328"><animate attributeName="x2" values="694;688;694" dur="4.5s" repeatCount="indefinite"/></line>
        <line x1="950" y1="360" x2="945" y2="333"><animate attributeName="x2" values="945;939;945" dur="3.2s" repeatCount="indefinite"/></line>
        <line x1="1200" y1="370" x2="1195" y2="343"><animate attributeName="x2" values="1195;1189;1195" dur="4s" repeatCount="indefinite"/></line>
        <line x1="1350" y1="375" x2="1345" y2="348"><animate attributeName="x2" values="1345;1339;1345" dur="3.8s" repeatCount="indefinite"/></line>
      </g>
      <!-- Birds -->
      <g class="birds" fill="none" stroke="#a8e6c1" stroke-width="1.2">
        <path d="M200,150 Q210,145 220,150">
          <animateTransform attributeName="transform" type="translate" values="0,0;800,-20;0,0" dur="20s" repeatCount="indefinite"/>
        </path>
        <path d="M210,158 Q220,153 230,158">
          <animateTransform attributeName="transform" type="translate" values="0,0;800,-20;0,0" dur="20s" repeatCount="indefinite"/>
        </path>
        <path d="M400,120 Q410,115 420,120">
          <animateTransform attributeName="transform" type="translate" values="0,0;700,-30;0,0" dur="25s" begin="5s" repeatCount="indefinite"/>
        </path>
      </g>
    </svg>
    <div class="nature-quote">
      <blockquote>"La nature ne se presse pas,<br>pourtant tout s'accomplit."</blockquote>
      <cite>— Lao Tseu</cite>
    </div>
  </div>
</section>

<!-- PILLIERS -->
<section id="pilliers" class="section dark-section">
  <div class="container">
    <div class="section-header reveal">
      <span class="section-tag">Nos Piliers</span>
      <h2 class="display-heading">Ce qui nous<br><em>définit</em></h2>
    </div>
    <div class="pilliers-grid">
      <div class="pillier-card reveal" style="--delay:0s">
        <div class="pillier-visual" style="--color:#74d7a3">
          <div class="pillier-orb"></div>
          <span class="pillier-emoji">🌱</span>
        </div>
        <div class="pillier-num">01</div>
        <h3>Corps en Harmonie</h3>
        <p>Des soins capillaires au beurre de karité, des protéines végétales complètes, des compléments alimentaires issus de la nature. Tout ce que ton corps mérite.</p>
        <a href="#produits" class="pillier-link">Explorer →</a>
      </div>
      <div class="pillier-card reveal" style="--delay:0.15s">
        <div class="pillier-visual" style="--color:#52a0b7">
          <div class="pillier-orb"></div>
          <span class="pillier-emoji">🧘</span>
        </div>
        <div class="pillier-num">02</div>
        <h3>Équilibre Mental</h3>
        <p>Le bien-être commence dans la tête. Des routines guidées, des adaptogènes naturels, une philosophie du quotidien pour cultiver sérénité et concentration.</p>
        <a href="#lifestyle" class="pillier-link">Explorer →</a>
      </div>
      <div class="pillier-card reveal" style="--delay:0.3s">
        <div class="pillier-visual" style="--color:#c9a84c">
          <div class="pillier-orb"></div>
          <span class="pillier-emoji">🌍</span>
        </div>
        <div class="pillier-num">03</div>
        <h3>Communauté Vivante</h3>
        <p>WLLEY, c'est un mouvement. Des milliers de personnes de tous âges et horizons qui choisissent ensemble une vie plus saine, plus consciente, plus belle.</p>
        <a href="#newsletter" class="pillier-link">Rejoindre →</a>
      </div>
    </div>
  </div>
</section>

<!-- PRODUITS -->
<section id="produits" class="section">
  <div class="container">
    <div class="products-header reveal">
      <div>
        <span class="section-tag">Notre Gamme</span>
        <h2 class="display-heading">Nos<br><em>Produits</em></h2>
      </div>
      <p class="products-subtitle">Formulés avec soin, testés avec exigence. Chaque produit est une promesse envers toi.</p>
    </div>

    <div class="product-tabs">
      <button class="tab-btn active" onclick="switchTab('soin', this)">🌿 Soins & Corps</button>
      <button class="tab-btn" onclick="switchTab('protein', this)">💪 Protéines</button>
      <button class="tab-btn" onclick="switchTab('supplement', this)">⚡ Compléments</button>
    </div>

    <!-- SOINS -->
    <div class="tab-panel active" id="tab-soin">
      <div class="product-grid">

        <div class="product-card reveal" style="--delay:0s">
          <div class="product-visual soin-visual">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 120" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="25" y="20" width="50" height="80" rx="8" fill="#1a4a2a" stroke="#74d7a3" stroke-width="1.5"/>
                <rect x="35" y="10" width="30" height="14" rx="4" fill="#2d6a4f"/>
                <path d="M35,45 Q50,38 65,45" stroke="#74d7a3" stroke-width="1" fill="none"/>
                <path d="M35,55 Q50,48 65,55" stroke="#74d7a3" stroke-width="1" fill="none" opacity="0.6"/>
                <text x="50" y="75" text-anchor="middle" fill="#a8e6c1" font-size="8" font-family="serif">WLLEY</text>
              </svg>
            </div>
            <span class="product-badge">Bestseller</span>
          </div>
          <div class="product-info">
            <p class="product-category">Capillaire</p>
            <h3 class="product-name">Shampoing Menthe & Aloe</h3>
            <p class="product-desc">Formule légère, sans sulfates. Purifie le cuir chevelu et apporte une fraîcheur longue durée.</p>
            <div class="product-footer">
              <div class="product-price">12.90€ <small>250ml</small></div>
              <button class="add-btn" onclick="addToCart('Shampoing Menthe & Aloe')">+ Panier</button>
            </div>
          </div>
        </div>

        <div class="product-card reveal" style="--delay:0.1s">
          <div class="product-visual soin-visual2">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 120" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="20" y="25" width="60" height="75" rx="10" fill="#1a3a4a" stroke="#52b7d7" stroke-width="1.5"/>
                <rect x="35" y="14" width="30" height="14" rx="4" fill="#1e4a5a"/>
                <circle cx="50" cy="60" r="15" fill="none" stroke="#52b7d7" stroke-width="1" opacity="0.5"/>
                <circle cx="50" cy="60" r="8" fill="#52b7d7" opacity="0.3"/>
                <text x="50" y="90" text-anchor="middle" fill="#a0d8e8" font-size="7" font-family="serif">WLLEY</text>
              </svg>
            </div>
          </div>
          <div class="product-info">
            <p class="product-category">Capillaire</p>
            <h3 class="product-name">Après-Shampoing Revitalisant</h3>
            <p class="product-desc">Kératine végétale + huile de coco. Démêle, nourrit et protège sans alourdir.</p>
            <div class="product-footer">
              <div class="product-price">13.90€ <small>250ml</small></div>
              <button class="add-btn" onclick="addToCart('Après-Shampoing Revitalisant')">+ Panier</button>
            </div>
          </div>
        </div>

        <div class="product-card reveal" style="--delay:0.2s">
          <div class="product-visual soin-visual3">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 120" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <ellipse cx="50" cy="80" rx="30" ry="35" fill="#2a1a3a" stroke="#c9a84c" stroke-width="1.5"/>
                <ellipse cx="50" cy="42" rx="12" ry="14" fill="#3a2a4a"/>
                <path d="M38,80 Q50,72 62,80" stroke="#c9a84c" stroke-width="1" fill="none"/>
                <path d="M40,90 Q50,84 60,90" stroke="#c9a84c" stroke-width="1" fill="none" opacity="0.6"/>
                <text x="50" y="108" text-anchor="middle" fill="#e8c87c" font-size="7" font-family="serif">WLLEY</text>
              </svg>
            </div>
            <span class="product-badge new-badge">Nouveau</span>
          </div>
          <div class="product-info">
            <p class="product-category">Corps</p>
            <h3 class="product-name">Huile Corps Argan & Jojoba</h3>
            <p class="product-desc">Mélange d'argan, jojoba et vitamine E. Hydrate en profondeur, peau soyeuse dès la 1ère utilisation.</p>
            <div class="product-footer">
              <div class="product-price">18.90€ <small>100ml</small></div>
              <button class="add-btn" onclick="addToCart('Huile Corps Argan & Jojoba')">+ Panier</button>
            </div>
          </div>
        </div>

        <div class="product-card reveal" style="--delay:0.3s">
          <div class="product-visual soin-visual4">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 120" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="22" y="22" width="56" height="78" rx="6" fill="#1a2a1a" stroke="#74d7a3" stroke-width="1.5"/>
                <rect x="32" y="12" width="36" height="12" rx="3" fill="#243424"/>
                <rect x="30" y="45" width="40" height="3" rx="1.5" fill="#74d7a3" opacity="0.5"/>
                <rect x="30" y="55" width="30" height="2" rx="1" fill="#74d7a3" opacity="0.3"/>
                <rect x="30" y="62" width="35" height="2" rx="1" fill="#74d7a3" opacity="0.3"/>
                <text x="50" y="90" text-anchor="middle" fill="#a8e6c1" font-size="7" font-family="serif">WLLEY</text>
              </svg>
            </div>
          </div>
          <div class="product-info">
            <p class="product-category">Visage</p>
            <h3 class="product-name">Gel Nettoyant Eau de Rose</h3>
            <p class="product-desc">Purifie sans dessécher à l'eau de rose et zinc. Idéal peau mixte à grasse, tout âge.</p>
            <div class="product-footer">
              <div class="product-price">11.90€ <small>150ml</small></div>
              <button class="add-btn" onclick="addToCart('Gel Nettoyant Eau de Rose')">+ Panier</button>
            </div>
          </div>
        </div>

      </div>
    </div>

    <!-- PROTÉINES -->
    <div class="tab-panel" id="tab-protein">
      <div class="product-grid">

        <div class="product-card reveal" style="--delay:0s">
          <div class="product-visual prot-visual1">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 130" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="15" y="30" width="70" height="90" rx="10" fill="#2a1a10" stroke="#c9a84c" stroke-width="1.5"/>
                <rect x="25" y="20" width="50" height="14" rx="5" fill="#3a2a18"/>
                <ellipse cx="50" cy="75" rx="22" ry="22" fill="none" stroke="#c9a84c" stroke-width="1" opacity="0.4"/>
                <text x="50" y="72" text-anchor="middle" fill="#e8c87c" font-size="7" font-family="serif">25g</text>
                <text x="50" y="82" text-anchor="middle" fill="#c9a84c" font-size="5" font-family="serif">PROTÉINES</text>
                <text x="50" y="108" text-anchor="middle" fill="#e8c87c" font-size="7" font-family="serif">WLLEY</text>
              </svg>
            </div>
            <span class="product-badge">Pro</span>
          </div>
          <div class="product-info">
            <p class="product-category">Protéine Végétale</p>
            <h3 class="product-name">Whey Végétale Chocolat Noir</h3>
            <p class="product-desc">25g de protéines par dose. Isolat de pois + riz brun. Sans lactose, sans gluten, goût premium.</p>
            <div class="product-footer">
              <div class="product-price">34.90€ <small>500g · 20 doses</small></div>
              <button class="add-btn" onclick="addToCart('Whey Végétale Chocolat Noir')">+ Panier</button>
            </div>
          </div>
        </div>

        <div class="product-card reveal" style="--delay:0.1s">
          <div class="product-visual prot-visual2">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 130" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="15" y="30" width="70" height="90" rx="10" fill="#1a1a2a" stroke="#74d7a3" stroke-width="1.5"/>
                <rect x="25" y="20" width="50" height="14" rx="5" fill="#252535"/>
                <text x="50" y="72" text-anchor="middle" fill="#a8e6c1" font-size="7" font-family="serif">22g</text>
                <text x="50" y="82" text-anchor="middle" fill="#74d7a3" font-size="5" font-family="serif">PROTÉINES</text>
                <ellipse cx="50" cy="75" rx="22" ry="22" fill="none" stroke="#74d7a3" stroke-width="1" opacity="0.4"/>
                <text x="50" y="108" text-anchor="middle" fill="#a8e6c1" font-size="7" font-family="serif">WLLEY</text>
              </svg>
            </div>
          </div>
          <div class="product-info">
            <p class="product-category">Protéine Végétale</p>
            <h3 class="product-name">Shake Banane Vanille</h3>
            <p class="product-desc">22g de protéines. Chanvre + pois. Parfait post-entraînement, digestion facile et goût doux.</p>
            <div class="product-footer">
              <div class="product-price">31.90€ <small>500g · 20 doses</small></div>
              <button class="add-btn" onclick="addToCart('Shake Banane Vanille')">+ Panier</button>
            </div>
          </div>
        </div>

        <div class="product-card reveal" style="--delay:0.2s">
          <div class="product-visual prot-visual3">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 80" width="90" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="5" y="15" width="90" height="50" rx="8" fill="#2a2a1a" stroke="#c9a84c" stroke-width="1.5"/>
                <rect x="15" y="25" width="70" height="30" rx="4" fill="#3a3a22"/>
                <text x="50" y="44" text-anchor="middle" fill="#e8c87c" font-size="8" font-family="serif">BARRE RISE</text>
                <text x="50" y="55" text-anchor="middle" fill="#c9a84c" font-size="5" font-family="serif">15g protéines</text>
              </svg>
            </div>
            <span class="product-badge new-badge">Nouveau</span>
          </div>
          <div class="product-info">
            <p class="product-category">Barres Protéinées</p>
            <h3 class="product-name">Barre WLLEY Cacahuète</h3>
            <p class="product-desc">15g de protéines végétales par barre. Sucre réduit, fibres élevées. Snack sain et rassasiant.</p>
            <div class="product-footer">
              <div class="product-price">2.90€ <small>par barre · Pack ×12</small></div>
              <button class="add-btn" onclick="addToCart('Barre WLLEY Cacahuète')">+ Panier</button>
            </div>
          </div>
        </div>

        <div class="product-card reveal" style="--delay:0.3s">
          <div class="product-visual prot-visual4">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 130" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="10" y="20" width="80" height="100" rx="12" fill="#1a2a1a" stroke="#52b788" stroke-width="1.5"/>
                <rect x="25" y="10" width="50" height="14" rx="5" fill="#243424"/>
                <text x="50" y="68" text-anchor="middle" fill="#a8e6c1" font-size="7" font-family="serif">40g</text>
                <text x="50" y="78" text-anchor="middle" fill="#52b788" font-size="5" font-family="serif">PROTÉINES</text>
                <text x="50" y="90" text-anchor="middle" fill="#74d7a3" font-size="5" font-family="serif">+ SPIRULINE</text>
                <text x="50" y="112" text-anchor="middle" fill="#a8e6c1" font-size="7" font-family="serif">WLLEY</text>
              </svg>
            </div>
          </div>
          <div class="product-info">
            <p class="product-category">Protéine Végétale</p>
            <h3 class="product-name">Gainer Nature Vert</h3>
            <p class="product-desc">Pour prise de masse propre. 40g protéines + glucides complexes. Spiruline & chlorella inclus.</p>
            <div class="product-footer">
              <div class="product-price">39.90€ <small>1kg · 20 doses</small></div>
              <button class="add-btn" onclick="addToCart('Gainer Nature Vert')">+ Panier</button>
            </div>
          </div>
        </div>

      </div>
    </div>

    <!-- COMPLÉMENTS -->
    <div class="tab-panel" id="tab-supplement">
      <div class="product-grid">

        <div class="product-card reveal" style="--delay:0s">
          <div class="product-visual supp-visual1">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 120" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="25" y="20" width="50" height="80" rx="25" fill="#1a1a2a" stroke="#74d7a3" stroke-width="1.5"/>
                <circle cx="50" cy="55" r="12" fill="#74d7a3" opacity="0.3"/>
                <circle cx="50" cy="55" r="6" fill="#74d7a3" opacity="0.6"/>
                <text x="50" y="85" text-anchor="middle" fill="#a8e6c1" font-size="6" font-family="serif">MATCHA</text>
                <text x="50" y="93" text-anchor="middle" fill="#74d7a3" font-size="5" font-family="serif">PRE-WORKOUT</text>
              </svg>
            </div>
          </div>
          <div class="product-info">
            <p class="product-category">Énergie</p>
            <h3 class="product-name">Pre-Workout Matcha Citron</h3>
            <p class="product-desc">Caféine naturelle du thé vert + L-théanine. Énergie propre sans crash. Concentration maximale.</p>
            <div class="product-footer">
              <div class="product-price">24.90€ <small>200g · 30 doses</small></div>
              <button class="add-btn" onclick="addToCart('Pre-Workout Matcha')">+ Panier</button>
            </div>
          </div>
        </div>

        <div class="product-card reveal" style="--delay:0.1s">
          <div class="product-visual supp-visual2">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 120" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="25" y="20" width="50" height="80" rx="6" fill="#1a1030" stroke="#8b5cf6" stroke-width="1.5"/>
                <path d="M40,50 Q50,42 60,50 Q60,70 50,78 Q40,70 40,50Z" fill="#8b5cf6" opacity="0.4"/>
                <text x="50" y="90" text-anchor="middle" fill="#c4b5fd" font-size="6" font-family="serif">SLEEP &</text>
                <text x="50" y="98" text-anchor="middle" fill="#8b5cf6" font-size="5" font-family="serif">RECOVER</text>
              </svg>
            </div>
            <span class="product-badge" style="background:#8b5cf6">Top</span>
          </div>
          <div class="product-info">
            <p class="product-category">Récupération</p>
            <h3 class="product-name">Sleep & Recover</h3>
            <p class="product-desc">Magnésium bisglycinate + ashwagandha + mélatonine végétale. Sommeil profond, récupération optimale.</p>
            <div class="product-footer">
              <div class="product-price">22.90€ <small>60 gélules</small></div>
              <button class="add-btn" onclick="addToCart('Sleep & Recover')">+ Panier</button>
            </div>
          </div>
        </div>

        <div class="product-card reveal" style="--delay:0.2s">
          <div class="product-visual supp-visual3">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 120" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="25" y="20" width="50" height="80" rx="6" fill="#1a2a10" stroke="#84cc16" stroke-width="1.5"/>
                <circle cx="50" cy="58" r="18" fill="none" stroke="#84cc16" stroke-width="1" opacity="0.4"/>
                <text x="50" y="55" text-anchor="middle" fill="#bef264" font-size="7" font-family="serif">D3</text>
                <text x="50" y="65" text-anchor="middle" fill="#84cc16" font-size="5" font-family="serif">+ K2</text>
                <text x="50" y="90" text-anchor="middle" fill="#bef264" font-size="6" font-family="serif">WLLEY</text>
              </svg>
            </div>
          </div>
          <div class="product-info">
            <p class="product-category">Immunité</p>
            <h3 class="product-name">Vitamines D3 + K2 Vegan</h3>
            <p class="product-desc">Combo essentiel pour os, immunité et humeur. Source algue D3 — 100% végétalien, pour tous.</p>
            <div class="product-footer">
              <div class="product-price">16.90€ <small>90 gélules</small></div>
              <button class="add-btn" onclick="addToCart('Vitamines D3 + K2')">+ Panier</button>
            </div>
          </div>
        </div>

        <div class="product-card reveal" style="--delay:0.3s">
          <div class="product-visual supp-visual4">
            <div class="product-blob"></div>
            <div class="product-3d-icon">
              <svg viewBox="0 0 100 120" width="80" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="25" y="20" width="50" height="80" rx="6" fill="#2a1010" stroke="#f97316" stroke-width="1.5"/>
                <path d="M50,35 L58,55 L75,55 L62,65 L67,85 L50,73 L33,85 L38,65 L25,55 L42,55 Z" fill="#f97316" opacity="0.4"/>
                <text x="50" y="100" text-anchor="middle" fill="#fed7aa" font-size="6" font-family="serif">BRAIN BOOST</text>
              </svg>
            </div>
          </div>
          <div class="product-info">
            <p class="product-category">Focus</p>
            <h3 class="product-name">Brain Boost Rhodiola</h3>
            <p class="product-desc">Adaptogènes naturels — rhodiola, bacopa, ginkgo. Clarté mentale, mémoire, anti-stress. Pour tous.</p>
            <div class="product-footer">
              <div class="product-price">27.90€ <small>60 gélules</small></div>
              <button class="add-btn" onclick="addToCart('Brain Boost Rhodiola')">+ Panier</button>
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>
</section>

<!-- LIFESTYLE / ROUTINE -->
<section id="lifestyle" class="section lifestyle-section">
  <div class="lifestyle-landscape">
    <svg viewBox="0 0 1440 600" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="forestGrad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#0a1f10"/>
          <stop offset="100%" stop-color="#1a4a25"/>
        </linearGradient>
        <linearGradient id="lightBeam" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#74d7a3" stop-opacity="0.3"/>
          <stop offset="100%" stop-color="transparent"/>
        </linearGradient>
      </defs>
      <rect width="1440" height="600" fill="url(#forestGrad)"/>
      <!-- Light rays -->
      <g opacity="0.15">
        <polygon points="600,0 620,0 750,600 530,600" fill="#74d7a3">
          <animate attributeName="opacity" values="0.15;0.25;0.15" dur="6s" repeatCount="indefinite"/>
        </polygon>
        <polygon points="750,0 770,0 900,600 680,600" fill="#a8e6c1" opacity="0.1">
          <animate attributeName="opacity" values="0.1;0.2;0.1" dur="8s" begin="2s" repeatCount="indefinite"/>
        </polygon>
        <polygon points="850,0 870,0 1020,600 800,600" fill="#74d7a3" opacity="0.08">
          <animate attributeName="opacity" values="0.08;0.15;0.08" dur="7s" begin="4s" repeatCount="indefinite"/>
        </polygon>
      </g>
      <!-- Tree silhouettes left -->
      <g fill="#0a1a0d">
        <rect x="0" y="100" width="30" height="500"/>
        <polygon points="15,100 -20,250 50,250" fill="#0d2010"/>
        <polygon points="15,160 -15,290 45,290" fill="#0a1a0d"/>
        <rect x="60" y="150" width="20" height="450"/>
        <polygon points="70,150 40,280 100,280" fill="#0d2010"/>
        <rect x="120" y="80" width="35" height="520"/>
        <polygon points="137,80 95,240 179,240" fill="#0d2010"/>
        <polygon points="137,140 105,280 169,280" fill="#0a1a0d"/>
      </g>
      <!-- Tree silhouettes right -->
      <g fill="#0a1a0d">
        <rect x="1410" y="100" width="30" height="500"/>
        <polygon points="1425,100 1390,250 1460,250" fill="#0d2010"/>
        <rect x="1360" y="150" width="20" height="450"/>
        <polygon points="1370,150 1340,280 1400,280" fill="#0d2010"/>
        <rect x="1285" y="80" width="35" height="520"/>
        <polygon points="1302,80 1260,240 1344,240" fill="#0d2010"/>
      </g>
      <!-- Ground mist -->
      <path d="M0,520 Q360,490 720,510 Q1080,530 1440,510 L1440,600 L0,600 Z" fill="#1a4a25" opacity="0.7"/>
      <path d="M0,550 Q360,535 720,545 Q1080,555 1440,540 L1440,600 L0,600 Z" fill="#0f2a14" opacity="0.8"/>
    </svg>
  </div>
  <div class="lifestyle-content">
    <div class="container">
      <div class="lifestyle-header reveal">
        <span class="section-tag">La Routine WLLEY</span>
        <h2 class="display-heading">Le quotidien<br><em>qui transforme</em></h2>
        <p>La discipline, ce n'est pas se priver. C'est se respecter assez pour choisir ce qui te fait grandir.</p>
      </div>
      <div class="routine-timeline">
        <div class="routine-item reveal" style="--delay:0s">
          <div class="routine-time">5H30</div>
          <div class="routine-connector"></div>
          <div class="routine-card">
            <span class="routine-icon">🌅</span>
            <h4>Réveil & Hydratation</h4>
            <p>Un verre d'eau citronné, 5 minutes de respiration consciente. Corps et esprit s'éveillent en douceur.</p>
          </div>
        </div>
        <div class="routine-item reveal" style="--delay:0.1s">
          <div class="routine-time">6H00</div>
          <div class="routine-connector"></div>
          <div class="routine-card">
            <span class="routine-icon">💪</span>
            <h4>Mouvement</h4>
            <p>30 minutes d'activité physique — course, yoga, musculation. Le mouvement libère, énergise, construit.</p>
          </div>
        </div>
        <div class="routine-item reveal" style="--delay:0.2s">
          <div class="routine-time">6H45</div>
          <div class="routine-connector"></div>
          <div class="routine-card">
            <span class="routine-icon">🌿</span>
            <h4>Rituel WLLEY</h4>
            <p>Soins capillaires, gel nettoyant, huile corps. Prendre soin de soi est un acte d'amour propre.</p>
          </div>
        </div>
        <div class="routine-item reveal" style="--delay:0.3s">
          <div class="routine-time">7H15</div>
          <div class="routine-connector"></div>
          <div class="routine-card">
            <span class="routine-icon">🥤</span>
            <h4>Nutrition Végétale</h4>
            <p>Shake protéiné, petit-déjeuner équilibré. Nourris ton corps pour la journée qui t'attend.</p>
          </div>
        </div>
        <div class="routine-item reveal" style="--delay:0.4s">
          <div class="routine-time">7H30</div>
          <div class="routine-connector last"></div>
          <div class="routine-card">
            <span class="routine-icon">✨</span>
            <h4>Intention du jour</h4>
            <p>3 objectifs écrits. Une gratitude. Tu sors prêt — corps nourri, esprit aligné.</p>
          </div>
        </div>
      </div>
      <div class="routine-cta reveal">
        <a href="#newsletter" class="btn-primary">Télécharger le guide gratuit</a>
      </div>
    </div>
  </div>
</section>

<!-- QUOTES -->
<section id="quotes" class="section quotes-section">
  <div class="container">
    <div class="quote-wrapper">
      <div class="quote-marks">"</div>
      <blockquote id="quoteText" class="quote-text">La discipline est le pont entre les objectifs et les accomplissements.</blockquote>
      <cite id="quoteAuthor" class="quote-author">— Jim Rohn</cite>
      <div class="quote-dots">
        <button class="quote-dot active" onclick="setQuote(0)"></button>
        <button class="quote-dot" onclick="setQuote(1)"></button>
        <button class="quote-dot" onclick="setQuote(2)"></button>
        <button class="quote-dot" onclick="setQuote(3)"></button>
      </div>
    </div>
  </div>
</section>

<!-- NEWSLETTER -->
<section id="newsletter" class="section newsletter-section">
  <div class="newsletter-landscape">
    <svg viewBox="0 0 1440 400" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="nlGrad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#0d2a18"/>
          <stop offset="100%" stop-color="#1a4a2a"/>
        </linearGradient>
      </defs>
      <rect width="1440" height="400" fill="url(#nlGrad)"/>
      <path d="M0,250 Q360,200 720,230 Q1080,260 1440,230 L1440,400 L0,400 Z" fill="#1a5030" opacity="0.5"/>
      <path d="M0,300 Q360,270 720,285 Q1080,300 1440,275 L1440,400 L0,400 Z" fill="#0f2a18" opacity="0.7"/>
      <!-- Floating particles -->
      <g fill="#74d7a3">
        <circle cx="200" cy="150" r="2" opacity="0.5"><animate attributeName="cy" values="150;130;150" dur="4s" repeatCount="indefinite"/></circle>
        <circle cx="500" cy="100" r="1.5" opacity="0.4"><animate attributeName="cy" values="100;80;100" dur="5s" begin="1s" repeatCount="indefinite"/></circle>
        <circle cx="900" cy="120" r="2" opacity="0.5"><animate attributeName="cy" values="120;100;120" dur="6s" begin="2s" repeatCount="indefinite"/></circle>
        <circle cx="1200" cy="150" r="1.5" opacity="0.4"><animate attributeName="cy" values="150;130;150" dur="4.5s" begin="0.5s" repeatCount="indefinite"/></circle>
        <circle cx="1350" cy="80" r="2" opacity="0.5"><animate attributeName="cy" values="80;60;80" dur="5.5s" begin="1.5s" repeatCount="indefinite"/></circle>
      </g>
    </svg>
  </div>
  <div class="newsletter-content">
    <span class="section-tag">La Communauté</span>
    <h2 class="display-heading">Rejoins le<br><em>mouvement</em></h2>
    <p>Guide de routine matinale offert + 10% sur ta première commande. Des milliers de personnes de tous âges ont déjà choisi WLLEY.</p>
    <div class="newsletter-form">
      <input type="email" id="emailInput" class="newsletter-input" placeholder="ton@email.com">
      <button class="btn-primary" onclick="subscribe()">Je rejoins</button>
    </div>
    <p class="newsletter-hint">Pas de spam. Juste de l'inspiration, des conseils et des offres exclusives.</p>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="container">
    <div class="footer-grid">
      <div class="footer-brand">
        <div class="footer-logo">WLLEY</div>
        <p>Une marque née pour tous ceux qui choisissent de prendre soin d'eux. Naturellement. Sans compromis.</p>
        <div class="social-links">
          <a href="#" class="social-link" aria-label="Instagram">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg>
          </a>
          <a href="#" class="social-link" aria-label="TikTok">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M19.59 6.69a4.83 4.83 0 01-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 01-2.88 2.5 2.89 2.89 0 01-2.89-2.89 2.89 2.89 0 012.89-2.89c.28 0 .54.04.79.1V9.01a6.32 6.32 0 00-.79-.05 6.34 6.34 0 00-6.34 6.34 6.34 6.34 0 006.34 6.34 6.34 6.34 0 006.33-6.34V8.59a8.15 8.15 0 004.79 1.54V6.69a4.86 4.86 0 01-1.02-.00z"/></svg>
          </a>
          <a href="#" class="social-link" aria-label="YouTube">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M23 7s-.3-2-1.2-2.8C20.7 3 19.5 3 19 2.9 15.9 2.7 12 2.7 12 2.7s-3.9 0-7 .2c-.5.1-1.7.1-2.8 1.2C1.3 5 1 7 1 7S.7 9.2.7 11.5v2.1C.7 16 1 18 1 18s.3 2 1.2 2.8C3.3 22 4.7 22 5.3 22.1c2.1.2 8.7.3 8.7.3s3.9 0 7-.2c.5-.1 1.7-.1 2.8-1.2C24.7 20 25 18 25 18s.3-2.2.3-4.5v-2.1C23.3 9.2 23 7 23 7zM9.7 15.5v-7l7.6 3.5-7.6 3.5z"/></svg>
          </a>
        </div>
      </div>
      <div class="footer-col">
        <h4>Produits</h4>
        <ul>
          <li><a href="#">Soins Capillaires</a></li>
          <li><a href="#">Protéines Végétales</a></li>
          <li><a href="#">Compléments</a></li>
          <li><a href="#">Packs Découverte</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>La Marque</h4>
        <ul>
          <li><a href="#">Notre Mission</a></li>
          <li><a href="#">Nos Valeurs</a></li>
          <li><a href="#">Routine WLLEY</a></li>
          <li><a href="#">Communauté</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Support</h4>
        <ul>
          <li><a href="#">FAQ</a></li>
          <li><a href="#">Livraisons</a></li>
          <li><a href="#">Retours</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2025 WLLEY. Tous droits réservés. Fait avec 🌿 pour tous.</p>
      <div class="footer-links">
        <a href="#">Confidentialité</a>
        <a href="#">CGV</a>
        <a href="#">Mentions légales</a>
      </div>
    </div>
  </div>
</footer>

<script src="script.js"></script>
</body>
</html>
