<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cactaïa Wiki – Accueil</title>
<link href="https://fonts.googleapis.com/css2?family=Cinzel+Decorative:wght@700&family=Nunito:wght@400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --sand: #e8c97a;
    --sand-dark: #c9a44a;
    --cactus: #4a7c59;
    --cactus-dark: #2e5e3a;
    --cactus-light: #7ab893;
    --bg: #1a1208;
    --bg2: #211a0a;
    --bg3: #2e2410;
    --text: #f0e8d0;
    --text-muted: #a89870;
    --accent: #f5a623;
    --accent2: #e86c2c;
    --gem: #5bc8f5;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Nunito', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated pixel-sand background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      radial-gradient(ellipse at 20% 50%, rgba(74,124,89,0.08) 0%, transparent 60%),
      radial-gradient(ellipse at 80% 20%, rgba(232,200,122,0.06) 0%, transparent 50%),
      url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23c9a44a' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
  }

  /* ── HEADER ── */
  header {
    position: relative;
    text-align: center;
    padding: 60px 20px 50px;
    overflow: hidden;
  }

  .header-glow {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 600px;
    height: 300px;
    background: radial-gradient(ellipse, rgba(74,124,89,0.25) 0%, transparent 70%);
    pointer-events: none;
  }

  .cactus-deco {
    font-size: 3.5rem;
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-bottom: 16px;
    animation: float 4s ease-in-out infinite;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-8px); }
  }

  h1 {
    font-family: 'Cinzel Decorative', serif;
    font-size: clamp(2.2rem, 6vw, 4rem);
    background: linear-gradient(135deg, var(--sand) 0%, var(--accent) 50%, var(--sand-dark) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    letter-spacing: 4px;
    text-shadow: none;
    position: relative;
    z-index: 1;
    animation: fadeDown 0.8s ease both;
  }

  .tagline {
    color: var(--cactus-light);
    font-size: 1.05rem;
    margin-top: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    font-weight: 600;
    animation: fadeDown 0.8s 0.2s ease both;
    opacity: 0;
  }

  .server-ip-badge {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: var(--bg3);
    border: 1px solid var(--sand-dark);
    border-radius: 40px;
    padding: 8px 22px;
    margin-top: 20px;
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--sand);
    cursor: pointer;
    transition: all 0.3s;
    position: relative;
    z-index: 1;
    animation: fadeDown 0.8s 0.4s ease both;
    opacity: 0;
  }

  .server-ip-badge:hover {
    background: var(--cactus-dark);
    border-color: var(--cactus-light);
    color: #fff;
    transform: scale(1.05);
  }

  .ip-dot {
    width: 8px; height: 8px;
    background: #5dea7a;
    border-radius: 50%;
    box-shadow: 0 0 8px #5dea7a;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(1.4); }
  }

  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ── NAV ── */
  nav {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 8px;
    padding: 0 20px 40px;
    position: relative;
    z-index: 1;
  }

  nav a {
    text-decoration: none;
    color: var(--text-muted);
    font-weight: 700;
    font-size: 0.85rem;
    letter-spacing: 1px;
    text-transform: uppercase;
    padding: 8px 18px;
    border: 1px solid rgba(201,164,74,0.2);
    border-radius: 6px;
    transition: all 0.25s;
  }

  nav a:hover {
    color: var(--sand);
    border-color: var(--sand-dark);
    background: rgba(201,164,74,0.08);
  }

  /* ── MAIN CONTENT ── */
  main {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 20px 60px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO BANNER ── */
  .hero-banner {
    background: linear-gradient(135deg, var(--bg3) 0%, #1e2e1a 100%);
    border: 1px solid rgba(74,124,89,0.4);
    border-radius: 16px;
    padding: 40px 50px;
    margin-bottom: 40px;
    display: flex;
    align-items: center;
    gap: 40px;
    position: relative;
    overflow: hidden;
  }

  .hero-banner::before {
    content: '🌵';
    position: absolute;
    right: -20px;
    bottom: -30px;
    font-size: 14rem;
    opacity: 0.05;
    pointer-events: none;
  }

  .hero-text h2 {
    font-family: 'Cinzel Decorative', serif;
    font-size: 1.5rem;
    color: var(--sand);
    margin-bottom: 12px;
  }

  .hero-text p {
    color: var(--text-muted);
    line-height: 1.7;
    max-width: 620px;
    font-size: 1rem;
  }

  .hero-text p strong {
    color: var(--cactus-light);
  }

  /* ── SECTION TITLE ── */
  .section-title {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 20px;
    margin-top: 40px;
  }

  .section-title h2 {
    font-family: 'Cinzel Decorative', serif;
    font-size: 1.1rem;
    color: var(--sand);
    letter-spacing: 2px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, rgba(201,164,74,0.3), transparent);
  }

  /* ── CARDS GRID ── */
  .cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 16px;
  }

  .card {
    background: var(--bg2);
    border: 1px solid rgba(201,164,74,0.15);
    border-radius: 12px;
    padding: 24px;
    text-decoration: none;
    color: var(--text);
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
    gap: 10px;
    position: relative;
    overflow: hidden;
  }

  .card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, transparent 60%, rgba(74,124,89,0.06) 100%);
    pointer-events: none;
  }

  .card:hover {
    border-color: var(--cactus-light);
    transform: translateY(-4px);
    box-shadow: 0 12px 40px rgba(74,124,89,0.2);
  }

  .card-icon {
    font-size: 2rem;
    line-height: 1;
  }

  .card h3 {
    font-size: 1rem;
    font-weight: 700;
    color: var(--sand);
  }

  .card p {
    font-size: 0.85rem;
    color: var(--text-muted);
    line-height: 1.5;
  }

  /* ── INFO BOXES ── */
  .info-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .info-box {
    background: var(--bg2);
    border-radius: 12px;
    padding: 24px;
    border-left: 3px solid var(--cactus);
  }

  .info-box.gold { border-left-color: var(--sand-dark); }
  .info-box.gem { border-left-color: var(--gem); }
  .info-box.orange { border-left-color: var(--accent2); }

  .info-box h3 {
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 2px;
    color: var(--text-muted);
    margin-bottom: 8px;
  }

  .info-box .value {
    font-family: 'Cinzel Decorative', serif;
    font-size: 1.3rem;
    color: var(--sand);
  }

  .info-box p {
    font-size: 0.85rem;
    color: var(--text-muted);
    margin-top: 6px;
    line-height: 1.5;
  }

  /* ── GETTING STARTED ── */
  .steps {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .step {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    background: var(--bg2);
    border-radius: 10px;
    padding: 18px 22px;
    border: 1px solid rgba(201,164,74,0.1);
    transition: border-color 0.25s;
  }

  .step:hover { border-color: rgba(201,164,74,0.3); }

  .step-num {
    width: 32px;
    height: 32px;
    background: var(--cactus-dark);
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 0.9rem;
    color: var(--cactus-light);
    flex-shrink: 0;
  }

  .step-content h4 {
    font-weight: 700;
    color: var(--text);
    margin-bottom: 3px;
  }

  .step-content p {
    font-size: 0.85rem;
    color: var(--text-muted);
  }

  .step-content code {
    background: rgba(74,124,89,0.2);
    border: 1px solid rgba(74,124,89,0.4);
    padding: 1px 8px;
    border-radius: 4px;
    font-size: 0.85rem;
    color: var(--cactus-light);
    font-family: monospace;
  }

  /* ── FOOTER ── */
  footer {
    text-align: center;
    padding: 30px 20px;
    color: var(--text-muted);
    font-size: 0.8rem;
    border-top: 1px solid rgba(201,164,74,0.1);
    position: relative;
    z-index: 1;
  }

  footer span { color: var(--cactus-light); }

  /* ── RESPONSIVE ── */
  @media (max-width: 640px) {
    .hero-banner { padding: 28px 24px; flex-direction: column; }
    .info-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="header-glow"></div>
  <div class="cactus-deco">🌵 🌵 🌵</div>
  <h1>CACTAÏA WIKI</h1>
  <p class="tagline">Le guide officiel du serveur Skyblock</p>
  <div class="server-ip-badge">
    <div class="ip-dot"></div>
    cactaia.fr &nbsp;·&nbsp; v1.21.1
  </div>
</header>

<!-- NAV -->
<nav>
  <a href="#">🏠 Accueil</a>
  <a href="#">⚔️ Débuter</a>
  <a href="#">💰 Économie</a>
  <a href="#">🔨 Jobs</a>
  <a href="#">💎 Gems</a>
  <a href="#">📜 Règles</a>
  <a href="#">❓ FAQ</a>
</nav>

<!-- MAIN -->
<main>

  <!-- HERO BANNER -->
  <div class="hero-banner">
    <div class="hero-text">
      <h2>Bienvenue sur Cactaïa !</h2>
      <p>
        Cactaïa est un serveur <strong>Skyblock Semi-Vanilla</strong> en version <strong>1.21.1</strong>.
        Construit autour d'une économie dynamique, d'un système de <strong>jobs</strong> et d'une monnaie
        exclusive — les <strong>Gems</strong> — le serveur est entièrement <strong>Farm2Win</strong> :
        tout ce qui compte se gagne en jouant, sans payer.
      </p>
    </div>
  </div>

  <!-- SERVER INFOS -->
  <div class="section-title"><h2>📊 Infos du serveur</h2></div>
  <div class="info-row">
    <div class="info-box gold">
      <h3>Mode de jeu</h3>
      <div class="value">Skyblock</div>
      <p>Commence sur ton île et développe ton empire à partir de rien.</p>
    </div>
    <div class="info-box">
      <h3>Version</h3>
      <div class="value">1.21.1</div>
      <p>Semi-Vanilla avec des plugins personnalisés pour l'économie et les jobs.</p>
    </div>
    <div class="info-box gem">
      <h3>Monnaie principale</h3>
      <div class="value">💎 Gems</div>
      <p>Gagnées en farmant et en utilisant les sellchests. La base de l'économie.</p>
    </div>
    <div class="info-box orange">
      <h3>Philosophie</h3>
      <div class="value">Farm2Win</div>
      <p>Les grades importants sont gratuits. Aucun avantage pay-to-win.</p>
    </div>
  </div>

  <!-- CATEGORIES -->
  <div class="section-title"><h2>📚 Catégories du wiki</h2></div>
  <div class="cards-grid">
    <a href="#" class="card">
      <div class="card-icon">🌱</div>
      <h3>Débuter sur Cactaïa</h3>
      <p>Guide complet pour les nouveaux joueurs : île de départ, commandes essentielles, premiers Gems.</p>
    </a>
    <a href="#" class="card">
      <div class="card-icon">🏪</div>
      <h3>Économie & Sellchests</h3>
      <p>Comment fonctionnent les sellchests, quoi vendre et comment maximiser ses gains.</p>
    </a>
    <a href="#" class="card">
      <div class="card-icon">⛏️</div>
      <h3>Les Jobs</h3>
      <p>Mineur, bûcheron, pêcheur... Découvre chaque job, comment progresser et les bonus associés.</p>
    </a>
    <a href="#" class="card">
      <div class="card-icon">💎</div>
      <h3>Les Gems</h3>
      <p>Comment gagner des Gems, les dépenser et les utiliser pour progresser sur le serveur.</p>
    </a>
    <a href="#" class="card">
      <div class="card-icon">🏝️</div>
      <h3>Gestion de l'île</h3>
      <p>Améliorer son île, inviter des coéquipiers, construire efficacement.</p>
    </a>
    <a href="#" class="card">
      <div class="card-icon">📜</div>
      <h3>Règles du serveur</h3>
      <p>Les règles à respecter pour jouer dans les meilleures conditions et éviter les sanctions.</p>
    </a>
  </div>

  <!-- GETTING STARTED -->
  <div class="section-title"><h2>🚀 Démarrage rapide</h2></div>
  <div class="steps">
    <div class="step">
      <div class="step-num">1</div>
      <div class="step-content">
        <h4>Rejoindre le serveur</h4>
        <p>Lance Minecraft en version <code>1.21.1</code> et connecte-toi à l'adresse du serveur.</p>
      </div>
    </div>
    <div class="step">
      <div class="step-num">2</div>
      <div class="step-content">
        <h4>Créer ton île</h4>
        <p>Utilise la commande <code>/island create</code> pour générer ta première île Skyblock.</p>
      </div>
    </div>
    <div class="step">
      <div class="step-num">3</div>
      <div class="step-content">
        <h4>Choisir un job</h4>
        <p>Rends-toi au spawn et inscris-toi à un job pour commencer à gagner des <code>Gems</code> en farmant.</p>
      </div>
    </div>
    <div class="step">
      <div class="step-num">4</div>
      <div class="step-content">
        <h4>Installer un sellchest</h4>
        <p>Place un sellchest pour vendre automatiquement ta production et remplir ta bourse.</p>
      </div>
    </div>
    <div class="step">
      <div class="step-num">5</div>
      <div class="step-content">
        <h4>Progresser !</h4>
        <p>Améliore ton île, monte de niveau dans ton job et deviens l'un des meilleurs joueurs de Cactaïa.</p>
      </div>
    </div>
  </div>

</main>

<footer>
  Wiki Cactaïa &nbsp;·&nbsp; Serveur <span>Skyblock 1.21.1</span> &nbsp;·&nbsp; Fait avec 🌵 par la communauté
</footer>

</body>
</html>
