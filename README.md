<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="Portfolio mannequin de Noé Cordel — éditorial, campagnes et collaborations." />
  <title>NOÉ CORDEL | Portfolio Mannequin</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Manrope:wght@400;500;600;700;800&family=Playfair+Display:ital,wght@0,600;0,700;1,600&display=swap" rel="stylesheet" />
  <style>
    :root {
      --black: #080808;
      --deep: #0d0d0d;
      --panel: #121212;
      --white: #f7f5ef;
      --muted: #aaa79f;
      --gold: #d6ae55;
      --gold-light: #f3d68e;
      --line: rgba(247, 245, 239, 0.16);
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; scroll-padding-top: 90px; }
    body {
      margin: 0;
      overflow-x: hidden;
      color: var(--white);
      background: var(--black);
      font-family: Manrope, Arial, sans-serif;
    }
    body.no-scroll { overflow: hidden; }
    button, a { font: inherit; }
    button { -webkit-tap-highlight-color: transparent; }
    a { color: inherit; text-decoration: none; }

    .topbar {
      position: fixed;
      z-index: 30;
      top: 0;
      right: 0;
      left: 0;
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 82px;
      padding: 0 5.5vw;
      background: linear-gradient(to bottom, rgba(8, 8, 8, 0.96), rgba(8, 8, 8, 0));
    }
    .brand { font-size: 0.78rem; font-weight: 800; letter-spacing: 0.2em; }
    .brand span { color: var(--gold); }
    .menu-toggle {
      display: inline-flex;
      gap: 10px;
      align-items: center;
      padding: 11px 15px;
      cursor: pointer;
      color: var(--white);
      border: 1px solid var(--line);
      background: transparent;
      font-size: 0.69rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      transition: 0.25s ease;
    }
    .menu-toggle:hover { color: var(--gold-light); border-color: var(--gold); }
    .menu-icon { display: grid; gap: 4px; width: 15px; }
    .menu-icon i { display: block; width: 100%; height: 1px; background: currentColor; }

    .hero {
      position: relative;
      display: grid;
      min-height: 100svh;
      padding: 130px 5.5vw 8vh;
      overflow: hidden;
      isolation: isolate;
      align-items: end;
    }
    .hero::before {
      position: absolute;
      z-index: -1;
      inset: 0;
      content: "";
      background: linear-gradient(90deg, rgba(8, 8, 8, 0.94) 0%, rgba(8, 8, 8, 0.48) 48%, rgba(8, 8, 8, 0.16) 100%), linear-gradient(0deg, rgba(8, 8, 8, 0.92) 0%, transparent 50%);
    }
    .hero::after {
      position: absolute;
      z-index: -1;
      top: -21vw;
      right: -14vw;
      width: 55vw;
      height: 55vw;
      content: "";
      border: 1px solid rgba(214, 174, 85, 0.25);
      border-radius: 50%;
    }
    .hero-image {
      position: absolute;
      z-index: -2;
      inset: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: center 32%;
      filter: grayscale(20%) contrast(1.07);
    }
    .hero-content { max-width: 900px; }
    .eyebrow {
      display: flex;
      gap: 12px;
      align-items: center;
      margin: 0 0 22px;
      color: var(--gold-light);
      font: 500 0.68rem/1 "DM Mono", monospace;
      letter-spacing: 0.15em;
      text-transform: uppercase;
    }
    .eyebrow::before { width: 34px; height: 1px; content: ""; background: var(--gold); }
    h1 {
      max-width: 760px;
      margin: 0;
      font-family: "Playfair Display", Georgia, serif;
      font-size: clamp(4rem, 10vw, 9rem);
      font-weight: 600;
      line-height: 0.82;
      letter-spacing: -0.065em;
      text-transform: uppercase;
    }
    h1 em { display: block; color: var(--gold-light); font-weight: 600; }
    .hero-bottom {
      display: flex;
      flex-wrap: wrap;
      gap: 25px 5vw;
      align-items: flex-end;
      margin-top: 43px;
    }
    .intro { max-width: 365px; margin: 0; color: #dedbd1; font-size: 0.94rem; line-height: 1.7; }
    .contact-links { display: flex; flex-wrap: wrap; gap: 14px; }
    .contact-links a {
      padding-bottom: 7px;
      color: var(--gold-light);
      border-bottom: 1px solid var(--gold);
      font: 0.7rem "DM Mono", monospace;
      letter-spacing: 0.07em;
    }
    .scroll-cue {
      position: absolute;
      right: 5.5vw;
      bottom: 8vh;
      color: var(--muted);
      font: 0.63rem "DM Mono", monospace;
      letter-spacing: 0.17em;
      text-transform: uppercase;
      writing-mode: vertical-rl;
    }

    .gallery-section { padding: 120px 5.5vw; }
    .section-heading {
      display: flex;
      gap: 25px;
      align-items: end;
      justify-content: space-between;
      margin-bottom: 45px;
    }
    .section-heading h2,
    .description-heading h2,
    .contact-heading h2 {
      margin: 0;
      font: 600 clamp(2.4rem, 5vw, 4.8rem) / 0.95 "Playfair Display", serif;
      letter-spacing: -0.05em;
    }
    .section-heading p { max-width: 300px; margin: 0; color: var(--muted); font-size: 0.85rem; line-height: 1.6; }
    .gallery-preview { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; }
    .gallery-preview button,
    .gallery-preview a {
      position: relative;
      display: block;
      min-height: 350px;
      padding: 0;
      overflow: hidden;
      cursor: pointer;
      border: 0;
      background: #222;
    }
    .gallery-preview img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      filter: grayscale(40%);
      transition: transform 0.55s ease, filter 0.4s ease;
    }
    .gallery-preview button:hover img { filter: grayscale(0); transform: scale(1.06); }
    .gallery-preview button::after {
      position: absolute;
      right: 16px;
      bottom: 16px;
      padding: 7px 10px;
      content: "Voir";
      opacity: 0;
      color: var(--gold-light);
      border: 1px solid rgba(214, 174, 85, 0.65);
      background: rgba(8, 8, 8, 0.5);
      font: 0.62rem "DM Mono", monospace;
      text-transform: uppercase;
      transition: 0.25s ease;
    }
    .gallery-preview button:hover::after { opacity: 1; }
    .view-all-card {
      display: flex !important;
      flex-direction: column;
      gap: 20px;
      justify-content: space-between;
      padding: 24px !important;
      border: 1px solid rgba(214, 174, 85, 0.6) !important;
      background: linear-gradient(145deg, #17130a, #0e0e0e) !important;
      transition: background 0.3s ease, transform 0.3s ease;
    }
    .view-all-card:hover { background: linear-gradient(145deg, #241b09, #101010) !important; transform: translateY(-4px); }
    .view-all-number { color: var(--gold); font: 500 clamp(3rem, 5vw, 5rem) / 1 "Playfair Display", serif; }
    .view-all-label { color: var(--white); font: 600 1.2rem "Playfair Display", serif; }
    .view-all-arrow { align-self: flex-end; color: var(--gold-light); font-size: 2rem; line-height: 1; }

    .description-section {
      display: grid;
      grid-template-columns: minmax(180px, 0.8fr) minmax(0, 1.6fr);
      gap: 7vw;
      padding: 20px 5.5vw 120px;
    }
    .description-heading { padding-top: 9px; }
    .description-copy { padding: 35px 0 0; border-top: 1px solid var(--gold); }
    .description-copy p { max-width: 670px; margin: 0; color: #dedbd1; font-size: clamp(1.08rem, 1.75vw, 1.45rem); line-height: 1.65; }
    .description-copy strong { color: var(--gold-light); font-weight: 600; }
    .description-tags { display: flex; flex-wrap: wrap; gap: 9px; margin-top: 28px; }
    .description-tags span {
      padding: 8px 10px;
      color: var(--muted);
      border: 1px solid var(--line);
      font: 0.62rem "DM Mono", monospace;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    .details { padding: 0 5.5vw 120px; }
    .details-box {
      display: grid;
      grid-template-columns: 1.3fr repeat(3, 1fr);
      gap: 20px;
      padding: 25px 0;
      border-top: 1px solid var(--line);
      border-bottom: 1px solid var(--line);
    }
    .detail-label {
      display: block;
      margin-bottom: 8px;
      color: var(--muted);
      font: 0.58rem "DM Mono", monospace;
      letter-spacing: 0.13em;
      text-transform: uppercase;
    }
    .detail-value { font-size: 0.85rem; }

    .contact-section {
      position: relative;
      padding: 100px 5.5vw;
      overflow: hidden;
      background: var(--panel);
    }
    .contact-section::after {
      position: absolute;
      top: -220px;
      right: -160px;
      width: 520px;
      height: 520px;
      content: "";
      border: 1px solid rgba(214, 174, 85, 0.22);
      border-radius: 50%;
      pointer-events: none;
    }
    .contact-heading { position: relative; z-index: 1; max-width: 860px; }
    .contact-heading h2 { font-size: clamp(3.2rem, 8vw, 7.6rem); }
    .contact-heading p { max-width: 490px; margin: 27px 0 0; color: #dedbd1; font-size: 1rem; line-height: 1.7; }
    .contact-actions {
      position: relative;
      z-index: 1;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
      max-width: 1000px;
      margin-top: 46px;
    }
    .contact-action {
      display: flex;
      gap: 16px;
      align-items: center;
      justify-content: space-between;
      min-height: 130px;
      padding: 23px;
      border: 1px solid var(--line);
      background: rgba(8, 8, 8, 0.38);
      transition: border-color 0.25s ease, background 0.25s ease, transform 0.25s ease;
    }
    .contact-action:hover { border-color: var(--gold); background: rgba(214, 174, 85, 0.08); transform: translateY(-4px); }
    .contact-action small { display: block; margin-bottom: 8px; color: var(--gold-light); font: 0.58rem "DM Mono", monospace; letter-spacing: 0.13em; text-transform: uppercase; }
    .contact-action span { display: block; overflow: hidden; font-size: clamp(0.75rem, 1.4vw, 0.95rem); font-weight: 600; text-overflow: ellipsis; white-space: nowrap; }
    .contact-action b { color: var(--gold-light); font-size: 1.4rem; font-weight: 400; }

    .side-panel {
      position: fixed;
      z-index: 40;
      inset: 0 auto 0 0;
      width: min(460px, 92vw);
      padding: 27px 24px 36px;
      overflow-y: auto;
      transform: translateX(-102%);
      border-right: 1px solid rgba(214, 174, 85, 0.35);
      background: var(--deep);
      transition: transform 0.45s cubic-bezier(0.77, 0, 0.18, 1);
    }
    .side-panel.open { transform: translateX(0); }
    .side-panel-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 34px; }
    .side-panel h2 { margin: 0; font: 600 2.25rem "Playfair Display", serif; }
    .close-panel { cursor: pointer; color: var(--white); border: 0; background: transparent; font-size: 1.8rem; line-height: 1; }
    .album-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 11px; }
    .album-item {
      position: relative;
      min-height: 210px;
      padding: 0;
      overflow: hidden;
      cursor: pointer;
      text-align: left;
      border: 0;
      background: #1d1d1d;
    }
    .album-item img { width: 100%; height: 100%; object-fit: cover; filter: grayscale(55%); transition: 0.35s; }
    .album-item:hover img { filter: grayscale(0); transform: scale(1.04); }
    .album-item span {
      position: absolute;
      bottom: 10px;
      left: 10px;
      padding: 5px 7px;
      color: var(--gold-light);
      background: rgba(8, 8, 8, 0.7);
      font: 0.56rem "DM Mono", monospace;
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }
    .overlay {
      position: fixed;
      z-index: 35;
      inset: 0;
      visibility: hidden;
      opacity: 0;
      background: rgba(0, 0, 0, 0.62);
      transition: 0.3s;
    }
    .overlay.visible { visibility: visible; opacity: 1; }

    .nav-panel {
      position: fixed;
      z-index: 50;
      top: 82px;
      right: 5.5vw;
      width: min(300px, calc(100vw - 11vw));
      padding: 11px;
      visibility: hidden;
      opacity: 0;
      transform: translateY(-12px);
      border: 1px solid rgba(214, 174, 85, 0.48);
      background: rgba(13, 13, 13, 0.98);
      box-shadow: 0 15px 50px rgba(0, 0, 0, 0.45);
      transition: 0.25s ease;
    }
    .nav-panel.open { visibility: visible; opacity: 1; transform: translateY(0); }
    .nav-panel a,
    .nav-panel button {
      display: flex;
      width: 100%;
      padding: 14px 12px;
      cursor: pointer;
      text-align: left;
      color: var(--white);
      border: 0;
      border-bottom: 1px solid var(--line);
      background: transparent;
      font: 0.72rem "DM Mono", monospace;
      letter-spacing: 0.09em;
      text-transform: uppercase;
      transition: 0.2s ease;
    }
    .nav-panel > :last-child { border-bottom: 0; }
    .nav-panel a:hover,
    .nav-panel button:hover { padding-left: 18px; color: var(--gold-light); background: rgba(214, 174, 85, 0.08); }

    .lightbox {
      position: fixed;
      z-index: 60;
      inset: 0;
      display: grid;
      visibility: hidden;
      place-items: center;
      padding: 28px;
      opacity: 0;
      background: rgba(0, 0, 0, 0.94);
      transition: 0.25s;
    }
    .lightbox.open { visibility: visible; opacity: 1; }
    .lightbox img { max-width: min(100%, 1100px); max-height: 82vh; object-fit: contain; box-shadow: 0 0 80px rgba(214, 174, 85, 0.13); }
    .lightbox-close {
      position: absolute;
      top: 26px;
      right: 5vw;
      cursor: pointer;
      color: var(--white);
      border: 0;
      background: transparent;
      font: 1.7rem "DM Mono", monospace;
    }
    .lightbox-caption { position: absolute; bottom: 25px; color: var(--gold-light); font: 0.65rem "DM Mono", monospace; letter-spacing: 0.12em; text-transform: uppercase; }
    footer { display: flex; justify-content: space-between; padding: 26px 5.5vw; color: var(--muted); border-top: 1px solid var(--line); font: 0.62rem "DM Mono", monospace; letter-spacing: 0.06em; }

    @media (max-width: 700px) {
      .hero { padding-bottom: 90px; }
      .scroll-cue { display: none; }
      .gallery-preview { grid-template-columns: 1fr; }
      .gallery-preview button,
      .gallery-preview a { min-height: 330px; }
      .gallery-preview button:nth-child(n + 4) { display: none; }
      .description-section { grid-template-columns: 1fr; gap: 24px; padding-bottom: 90px; }
      .description-copy { padding-top: 25px; }
      .details { padding-bottom: 90px; }
      .details-box { grid-template-columns: 1fr 1fr; }
      .details-box > :first-child { grid-column: 1 / -1; }
      .section-heading { display: block; }
      .section-heading p { margin-top: 18px; }
      .hero-bottom { margin-top: 35px; }
      .contact-section { padding: 80px 5.5vw; }
      .contact-actions { grid-template-columns: 1fr; margin-top: 34px; }
      .contact-action { min-height: 95px; }
      footer { gap: 14px; flex-direction: column; }
    }
  </style>
</head>
<body>
  <header class="topbar">
    <a class="brand" href="#accueil">NOÉ <span>/</span> PORTFOLIO</a>
    <button class="menu-toggle" id="menuToggle" aria-controls="navPanel" aria-expanded="false">
      <span class="menu-icon" aria-hidden="true"><i></i><i></i><i></i></span>
      Menu
    </button>
  </header>

  <nav class="nav-panel" id="navPanel" aria-label="Navigation principale">
    <a href="#accueil" data-nav>Accueil</a>
    <a href="#selection" data-nav>Sélection</a>
    <button type="button" id="navGallery">Galerie complète</button>
    <a href="#a-propos" data-nav>À propos</a>
    <a href="#infos" data-nav>Informations</a>
    <a href="#contact" data-nav>Contact</a>
  </nav>

  <main>
    <section class="hero" id="accueil">
      <img class="hero-image" src="https://i.ibb.co/q3jM999p/DSF0121.png" alt="Noé Cordel — portrait principal" />
      <div class="hero-content">
        <p class="eyebrow">Mannequin · Éditorial · France</p>
        <h1>NOÉ <em>CORDEL</em></h1>
        <div class="hero-bottom">
          <p class="intro">Un regard contemporain, une présence affirmée. Disponible pour campagnes, éditoriaux, e-commerce et collaborations créatives.</p>
          <div class="contact-links">
            <!-- Remplace ces coordonnées par les tiennes -->
            <a href="mailto:contact@noecordel.fr">contact@noecordel.fr</a>
            <a href="tel:+33600000000">+33 6 00 00 00 00</a>
            <a href="https://instagram.com/" target="_blank" rel="noreferrer">Instagram ↗</a>
          </div>
        </div>
      </div>
      <span class="scroll-cue">Défiler pour explorer</span>
    </section>

    <section class="gallery-section" id="selection">
      <div class="section-heading">
        <h2>En lumière.</h2>
        <p>Une sélection de portraits et d'éditoriaux. Clique sur une image pour l'afficher en grand format.</p>
      </div>
      <div class="gallery-preview" id="previewGallery">
        <a class="view-all-card" href="#" id="viewAllGallery" aria-label="Ouvrir la galerie complète">
          <span class="view-all-number">09</span>
          <span class="view-all-label">Explorer la<br>galerie complète</span>
          <span class="view-all-arrow" aria-hidden="true">↗</span>
        </a>
      </div>
    </section>

    <section class="description-section" id="a-propos">
      <div class="description-heading">
        <p class="eyebrow">Mon univers</p>
        <h2>À propos.</h2>
      </div>
      <div class="description-copy">
        <!-- Modifie librement ce texte pour raconter ton parcours et ton positionnement. -->
        <p>Je suis <strong>Noé Cordel</strong>, mannequin basé en France. J'explore une esthétique moderne, élégante et expressive, au croisement de la mode, de l'éditorial et de l'image de marque. Mon objectif : donner à chaque projet une <strong>présence singulière</strong>, naturelle et mémorable.</p>
        <div class="description-tags" aria-label="Domaines de collaboration">
          <span>Éditorial</span>
          <span>Campagne</span>
          <span>E-commerce</span>
          <span>Beauté</span>
          <span>Création de contenu</span>
        </div>
      </div>
    </section>

    <section class="details" id="infos">
      <div class="details-box">
        <div><span class="detail-label">Disponibilité</span><span class="detail-value">France · International</span></div>
        <div><span class="detail-label">Taille</span><span class="detail-value">À compléter</span></div>
        <div><span class="detail-label">Mensurations</span><span class="detail-value">À compléter</span></div>
        <div><span class="detail-label">Pointure</span><span class="detail-value">À compléter</span></div>
      </div>
    </section>

    <section class="contact-section" id="contact">
      <div class="contact-heading">
        <p class="eyebrow">Travaillons ensemble</p>
        <h2>Entrons en contact.</h2>
        <p>Pour une campagne, un éditorial, une collaboration ou toute demande professionnelle, utilise le canal qui te convient le mieux.</p>
      </div>
      <div class="contact-actions">
        <!-- Remplace email, téléphone et lien Instagram ci-dessous par tes coordonnées. -->
        <a class="contact-action" href="mailto:contact@noecordel.fr">
          <div><small>E-mail</small><span>contact@noecordel.fr</span></div>
          <b aria-hidden="true">↗</b>
        </a>
        <a class="contact-action" href="tel:+33600000000">
          <div><small>Téléphone</small><span>+33 6 00 00 00 00</span></div>
          <b aria-hidden="true">↗</b>
        </a>
        <a class="contact-action" href="https://instagram.com/" target="_blank" rel="noreferrer">
          <div><small>Instagram</small><span>@ton.compte</span></div>
          <b aria-hidden="true">↗</b>
        </a>
      </div>
    </section>
  </main>

  <aside class="side-panel" id="sidePanel" aria-label="Galerie complète">
    <div class="side-panel-header">
      <div>
        <p class="eyebrow">Archives visuelles</p>
        <h2>Galerie</h2>
      </div>
      <button class="close-panel" id="closeGallery" aria-label="Fermer la galerie">×</button>
    </div>
    <div class="album-grid" id="albumGrid"></div>
  </aside>
  <div class="overlay" id="overlay"></div>

  <div class="lightbox" id="lightbox" role="dialog" aria-modal="true" aria-label="Image agrandie">
    <button class="lightbox-close" id="closeLightbox" aria-label="Fermer l'image">×</button>
    <img id="lightboxImage" src="" alt="" />
    <span class="lightbox-caption" id="lightboxCaption"></span>
  </div>

  <footer>
    <span>© 2026 NOÉ CORDEL</span>
    <span>MODEL PORTFOLIO / FR</span>
  </footer>

  <script>
    const photos = [
      { src: 'https://i.ibb.co/q3jM999p/DSF0121.png', title: 'Éditorial 01' },
      { src: 'https://i.ibb.co/LXpT8dKp/IMG-20260531-WA0014.jpg', title: 'Portrait 02' },
      { src: 'https://i.ibb.co/zVNFcpfK/IMG-4765.jpg', title: 'Studio 03' },
      { src: 'https://i.ibb.co/7tBp1fbt/IMG-20260723-223822.png', title: 'Mode 04' },
      { src: 'https://i.ibb.co/RWTgzGg/IMG-4739.jpg', title: 'Campagne 05' },
      { src: 'https://i.ibb.co/FLrNdVkM/DSC05702.jpg', title: 'Éditorial 06' },
      { src: 'https://i.ibb.co/sJbk0zb7/DSC05153.jpg', title: 'Portrait 07' },
      { src: 'https://i.ibb.co/Wp6hbRXQ/DSC04877.jpg', title: 'Studio 08' },
      { src: 'https://i.ibb.co/BVLntBZQ/DSC05099.jpg', title: 'Mode 09' }
    ];

    const previewGallery = document.getElementById('previewGallery');
    const albumGrid = document.getElementById('albumGrid');
    const sidePanel = document.getElementById('sidePanel');
    const overlay = document.getElementById('overlay');
    const menuToggle = document.getElementById('menuToggle');
    const navPanel = document.getElementById('navPanel');
    const navGallery = document.getElementById('navGallery');
    const viewAllGallery = document.getElementById('viewAllGallery');
    const closeGalleryButton = document.getElementById('closeGallery');
    const lightbox = document.getElementById('lightbox');
    const lightboxImage = document.getElementById('lightboxImage');
    const lightboxCaption = document.getElementById('lightboxCaption');
    const closeLightboxButton = document.getElementById('closeLightbox');

    function createPhotoButton(photo, className = '') {
      const button = document.createElement('button');
      button.className = className;
      button.type = 'button';
      button.innerHTML = `<img src="${photo.src}" alt="${photo.title}" loading="lazy"><span>${photo.title}</span>`;
      button.addEventListener('click', () => openLightbox(photo));
      return button;
    }

    photos.slice(0, 2).forEach(photo => previewGallery.appendChild(createPhotoButton(photo)));
    photos.forEach(photo => albumGrid.appendChild(createPhotoButton(photo, 'album-item')));

    function setMenu(isOpen) {
      navPanel.classList.toggle('open', isOpen);
      menuToggle.setAttribute('aria-expanded', String(isOpen));
    }

    function setGallery(isOpen) {
      sidePanel.classList.toggle('open', isOpen);
      overlay.classList.toggle('visible', isOpen);
      document.body.classList.toggle('no-scroll', isOpen);
    }

    function openGallery(event) {
      if (event) event.preventDefault();
      setMenu(false);
      setGallery(true);
    }

    function openLightbox(photo) {
      lightboxImage.src = photo.src;
      lightboxImage.alt = photo.title;
      lightboxCaption.textContent = photo.title;
      lightbox.classList.add('open');
      setGallery(false);
      document.body.classList.add('no-scroll');
    }

    function closeLightbox() {
      lightbox.classList.remove('open');
      document.body.classList.remove('no-scroll');
    }

    menuToggle.addEventListener('click', () => setMenu(!navPanel.classList.contains('open')));
    document.querySelectorAll('[data-nav]').forEach(link => link.addEventListener('click', () => setMenu(false)));
    navGallery.addEventListener('click', openGallery);
    viewAllGallery.addEventListener('click', openGallery);
    closeGalleryButton.addEventListener('click', () => setGallery(false));
    overlay.addEventListener('click', () => setGallery(false));
    closeLightboxButton.addEventListener('click', closeLightbox);
    lightbox.addEventListener('click', event => {
      if (event.target === lightbox) closeLightbox();
    });
    document.addEventListener('click', event => {
      if (!navPanel.contains(event.target) && !menuToggle.contains(event.target)) setMenu(false);
    });
    document.addEventListener('keydown', event => {
      if (event.key === 'Escape') {
        setMenu(false);
        setGallery(false);
        closeLightbox();
      }
    });
  </script>
</body>
</html>
