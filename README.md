<!doctype html>
<html lang="fr">
<head>
  <script>
    window["__codeletBootstrap__"] = JSON.parse('{"A":"A","B":"20260907-05-0068bad","C":{"Abril Fatface":"YACgEZbkUVE,0","Alfa Slab One":"YACgEYS9sJU,0","Anton":"YACgEcYqQ-A,0","Archivo":"YAHO2-t-jNE,0","Arial":"YAGyDvJ_4Ts,0","Bebas Neue":"YACgESME5ew,0","Bricolage Grotesque":"YAFyMcdwzpc,0","Canva Sans":"YAFLd8sKbwc,2","Caveat":"YALBs2ploWQ,0","Comic Sans MS":"YAHO2VMiyZo,0","Cormorant Garamond":"YAFdJhX-538,0","Courier New":"YAGzXiGs0_8,0","DM Sans":"YAD1aU3sLnI,0","DM Serif Display":"YAD1aYG82rc,0","Forum":"YACgEcnnqB4,0","Fraunces":"YAEul-FRQw4,0","Georgia":"YAGzXkO0pEM,0","Helvetica Neue":"YAFcf6CtJfI,0","Impact":"YAFcfnjI7Vk,0","Inter":"YAFdJvSyp_k,3","Iowan Old Style":"YAGNIFa8j9o,0","Jacques Francois":"YAHO2a5g66Q,0","JetBrains Mono":"YAFdJksXcAk,0","Libre Baskerville":"YACgEUFdPdA,0","Manrope":"YAHO2b2feC4,0","Merriweather":"YACgEXvHxxs,0","Montserrat":"YADLjI9qxTA,0","Nunito":"YACgEX8C5Gg,0","Oleo Script":"YACgEQQ14jI,0","Phantom Sans":"YAHO2E8Pb88,0","Playfair Display":"YACgEYmuCJE,0","Poppins":"YAFdJjbTu24,1","Press Start 2P":"YAFyGr-8pmQ,0","Quicksand":"YADWjpfPmdk,0","Raleway":"YACgEVg3xZg,0","Segoe UI":"YAHNdRD1Klw,0","Source Sans 3":"YAG4lO1Mj10,0","Spectral":"YAHO2rVUHIM,0","Times New Roman":"YAGzXW3gftg,0","Times":"YAGzXW3gftg,0","Ubuntu":"YACgERDU--Q,0","Work Sans":"YAGXhLOKv44,0","Yellowtail":"YACgEYG4kG4,0","ui-monospace":"YADlN8CFZ8Q,0","ui-sans-serif":"YACkoN-xg4g,0"}}');
  </script>
  <script src="/_sdk/9e99ecf74af2a081.telemetry_sdk.js" integrity="sha512-tZ7fmfTx2KpCLjXQnEuL9azQ4A5+7+xumsx6r/WYVD0zCP/8LP8hDeCypMQesmP+WyAew4g7l5Ah23Bjd6yoVg=="></script>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Portfolio Mannequin</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.577.0/dist/umd/lucide.min.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&amp;family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400&amp;display=swap" rel="stylesheet">
  <style>
    :root {
      --ink: #090909;
      --surface: #141414;
      --paper: #f4f0e8;
      --muted: #aaa59b;
      --gold: #c4a05a;
      --gold-soft: #e2c98d;
      --line: rgba(226, 201, 141, 0.28);
    }

    html { scroll-behavior: smooth; }
    body { font-family: "DM Sans", sans-serif; background: var(--ink); color: var(--paper); }
    .editorial { font-family: "Playfair Display", serif; }
    .gold-rule { background: linear-gradient(90deg, transparent, var(--gold), transparent); }
    .noise {
      background-image: radial-gradient(rgba(255,255,255,.09) .55px, transparent .55px);
      background-size: 7px 7px;
      opacity: .13;
    }
    .menu-panel { transform: translateX(104%); transition: transform .45s cubic-bezier(.22,1,.36,1); }
    .menu-panel.is-open { transform: translateX(0); }
    .menu-backdrop { opacity: 0; pointer-events: none; transition: opacity .35s ease; }
    .menu-backdrop.is-open { opacity: 1; pointer-events: auto; }
    .portfolio-card img { transition: transform .7s cubic-bezier(.22,1,.36,1), filter .5s ease; }
    .portfolio-card:hover img, .portfolio-card:focus-visible img { transform: scale(1.06); filter: grayscale(0); }
    .hero-photo img { transition: transform 1s cubic-bezier(.22,1,.36,1); }
    .hero-photo:hover img { transform: scale(1.045); }
    .lightbox { opacity: 0; pointer-events: none; transition: opacity .3s ease; }
    .lightbox.is-open { opacity: 1; pointer-events: auto; }
    .lightbox-stage { transform: scale(.96); transition: transform .35s cubic-bezier(.22,1,.36,1); }
    .lightbox.is-open .lightbox-stage { transform: scale(1); }
    .lightbox-slide { display: none; }
    .lightbox-slide.is-active { display: block; animation: reveal .38s ease both; }
    @keyframes reveal { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    .section-kicker { letter-spacing: .19em; text-transform: uppercase; font-size: .68rem; }
    .focus-ring:focus-visible { outline: 2px solid var(--gold-soft); outline-offset: 4px; }

    /* Galerie page */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 1.25rem;
    }
    .gallery-item {
      position: relative;
      overflow: hidden;
      background: #111;
      border-radius: 6px;
      cursor: pointer;
      transition: transform .25s ease, box-shadow .25s ease;
    }
    .gallery-item:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 25px rgba(0,0,0,.35);
    }
    .gallery-item img {
      width: 100%;
      height: 260px;
      object-fit: cover;
      display: block;
      transition: transform .4s ease;
    }
    .gallery-item:hover img {
      transform: scale(1.05);
    }

    /* Lightbox plein écran pour la galerie */
    .gallery-lightbox {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,.95);
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 70;
      opacity: 0;
      pointer-events: none;
      transition: opacity .3s ease;
    }
    .gallery-lightbox.is-open {
      opacity: 1;
      pointer-events: auto;
    }
    .gallery-lightbox img {
      max-width: 90vw;
      max-height: 90vh;
      object-fit: contain;
      border-radius: 4px;
      box-shadow: 0 15px 40px rgba(0,0,0,.5);
    }
    .gallery-lightbox-close {
      position: absolute;
      top: 1rem;
      right: 1rem;
      background: #141414;
      color: #f4f0e8;
      border: 1px solid #333;
      width: 44px;
      height: 44px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 6px;
      cursor: pointer;
    }

    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      *, *::before, *::after { animation-duration: .01ms !important; transition-duration: .01ms !important; }
    }
  </style>
  <script src="/_sdk/fbe2ebfd64647c54.data_sdk.js" type="text/javascript" integrity="sha512-vkTX6CfvpHc3WbjK+tFJCaDuw4ERA4aEV/e5/7+MMJPMTF4RJYCI6CAwJBT/gtDW+dba4uLSsPUgDjVDHWtgUQ=="></script>
  <script src="/_sdk/fcb6dc01f91829ac.resizing_sdk.js" type="text/javascript" integrity="sha512-YK8JfnN705qaEaVhiL7pcVB2Rs/BbdX5yxV55Az8zT/1JanyEWTw9HqCF915m9iV1YEaoil8qsjJz03l1Kb0Ug=="></script>
</head>
<body data-template-id="__page-root" class="w-full overflow-x-hidden" style="background: rgb(9, 9, 9);">
  <div class="noise fixed inset-0 pointer-events-none"></div>

  <!-- HEADER -->
  <header class="fixed top-0 z-40 w-full px-5 py-5 md:px-10">
    <div class="mx-auto flex max-w-7xl items-center justify-between">
      <a href="#accueil" data-template-id="brand-mark" class="canva-link focus-ring text-sm font-semibold tracking-[0.28em]" style="color: rgb(244, 240, 232); font-weight: 600; font-style: normal; font-size: 13px; letter-spacing: 0.18rem;">MUSE / 01</a>
      <button id="menu-button" type="button" data-template-id="menu-button" class="canva-button focus-ring flex items-center gap-3 border px-4 py-3 text-xs font-semibold uppercase tracking-[0.16em]" aria-controls="site-menu" aria-expanded="false" style="background: rgb(20, 20, 20); color: rgb(244, 240, 232);">
        <span data-template-id="menu-button-label" class="canva-text" style="color: rgb(244, 240, 232); font-weight: 600; font-style: normal; font-size: 12px;">Menu</span>
        <i data-lucide="menu" aria-hidden="true" class="h-4 w-4"></i>
      </button>
    </div>
  </header>

  <!-- MENU BACKDROP & PANEL -->
  <div id="menu-backdrop" class="menu-backdrop fixed inset-0 z-40 bg-black/75" aria-hidden="true"></div>
  <aside id="site-menu" class="menu-panel fixed right-0 top-0 z-50 flex h-[calc(100*min(var(--vh,1vh),1vh))] w-full max-w-md flex-col border-l p-7 md:p-10" aria-label="Navigation principale" aria-hidden="true">
    <div class="flex items-center justify-between">
      <span data-template-id="menu-title" class="canva-text editorial text-2xl italic" style="color: rgb(226, 201, 141); font-weight: 400; font-style: italic; font-size: 16px;">Index</span>
      <button id="menu-close" type="button" data-template-id="menu-close-button" class="canva-button focus-ring flex h-11 w-11 items-center justify-center border" aria-label="Fermer le menu" style="background: rgb(20, 20, 20); color: rgb(244, 240, 232);">
        <i data-lucide="x" aria-hidden="true" class="h-5 w-5"></i>
      </button>
    </div>
    <nav class="mt-20" aria-label="Liens de section">
      <ul class="space-y-7">
        <li><a href="#accueil" data-template-id="nav-home" class="canva-link focus-ring editorial block text-4xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Accueil</a></li>
        <li><a href="#portfolio" data-template-id="nav-portfolio" class="canva-link focus-ring editorial block text-4xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Portfolio</a></li>
        <li><a href="#galerie" data-template-id="nav-gallery" class="canva-link focus-ring editorial block text-4xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Galerie</a></li>
        <li><a href="#apropos" data-template-id="nav-about" class="canva-link focus-ring editorial block text-4xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">À propos</a></li>
        <li><a href="#contact" data-template-id="nav-contact" class="canva-link focus-ring editorial block text-4xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Contact</a></li>
      </ul>
    </nav>
    <p data-template-id="menu-note" class="canva-text mt-auto max-w-xs text-sm leading-6" style="color: rgb(170, 165, 155); font-weight: 400; font-style: normal; font-size: 14px; line-height: 1.5;">Portfolio professionnel — informations et images à remplacer dans Canva.</p>
  </aside>

  <main>
    <!-- ACCUEIL -->
    <section id="accueil" class="relative min-h-[calc(100*min(var(--vh,1vh),1vh))] w-full px-5 pb-10 pt-28 md:px-10 md:pb-12">
      <div class="mx-auto grid min-h-[calc(100*min(var(--vh,1vh),1vh)-10rem)] max-w-7xl items-end gap-8 lg:grid-cols-12">
        <div class="relative z-10 lg:col-span-5 lg:pb-8">
          <p data-template-id="hero-kicker" class="canva-text section-kicker mb-6" style="color: rgb(226, 201, 141); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.18rem;">Portfolio mannequin / 2026</p>
          <h1 data-template-id="hero-name" class="canva-text editorial max-w-xl text-6xl leading-[.88] sm:text-7xl lg:text-8xl" style="color: rgb(244, 240, 232); font-weight: 500; font-style: normal; font-size: 32px; line-height: 0.9;">CORDEL Noé</h1>
          <div class="gold-rule my-8 h-px w-40"></div>
          <p data-template-id="hero-tagline" class="canva-text max-w-md text-base leading-7 md:text-lg" style="color: rgb(212, 208, 200); font-weight: 400; font-style: normal; font-size: 18px; line-height: 1.55;">Une présence singulière pour l’éditorial, le commercial et les campagnes contemporaines.</p>
          <dl class="mt-10 grid max-w-md gap-3 border-t pt-5 text-xs leading-5 sm:grid-cols-2">
            <div>
              <dt data-template-id="hero-email-label" class="canva-text uppercase tracking-[.14em]" style="color: rgb(196, 160, 90); font-weight: 600; font-style: normal; font-size: 10px; letter-spacing: 0.12rem;">Email</dt>
              <dd data-template-id="hero-email" class="canva-text mt-1 break-all" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 12px;">noe.cordel@gmail.com</dd>
            </div>
            <div>
              <dt data-template-id="hero-phone-label" class="canva-text uppercase tracking-[.14em]" style="color: rgb(196, 160, 90); font-weight: 600; font-style: normal; font-size: 10px; letter-spacing: 0.12rem;">Téléphone</dt>
              <dd data-template-id="hero-phone" class="canva-text mt-1" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 12px;">+33 07 81 85 45 03</dd>
            </div>
            <div>
              <dt data-template-id="hero-agency-label" class="canva-text uppercase tracking-[.14em]" style="color: rgb(196, 160, 90); font-weight: 600; font-style: normal; font-size: 10px; letter-spacing: 0.12rem;">Agence</dt>
              <dd data-template-id="hero-agency" class="canva-text mt-1" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 12px;">RECHERCHE AGENCE/MARQUE</dd>
            </div>
            <div>
              <dt data-template-id="hero-location-label" class="canva-text uppercase tracking-[.14em]" style="color: rgb(196, 160, 90); font-weight: 600; font-style: normal; font-size: 10px; letter-spacing: 0.12rem;">Localisation</dt>
              <dd data-template-id="hero-location" class="canva-text mt-1" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 12px;">GRENOBLE / FRANCE</dd>
            </div>
          </dl>
        </div>
        <div class="hero-photo relative overflow-hidden bg-neutral-900 lg:col-span-7 lg:h-[calc(100*min(var(--vh,1vh),1vh)-9rem)]">
          <img data-template-id="hero-image" loading="lazy" class="canva-image h-[58vh] w-full object-cover object-center lg:h-full" src="[https://images.pexels.com/photos/13660182/pexels-photo-13660182.jpeg](https://ibb.co/Q7XTyrjM)" alt="Placeholder photo héroïque : portrait studio noir et blanc d’un mannequin">
          <div class="absolute inset-0 bg-gradient-to-t from-black/45 via-transparent to-transparent"></div>
          <p data-template-id="hero-image-caption" class="canva-text absolute bottom-5 right-5 border px-3 py-2 text-[10px] uppercase tracking-[.17em]" style="background: rgba(9, 9, 9, 0.65); color: rgb(226, 201, 141); font-weight: 600; font-style: normal; font-size: 10px; letter-spacing: 0.12rem;">Image placeholder — à remplacer</p>
        </div>
      </div>
    </section>

    <!-- PORTFOLIO -->
    <section id="portfolio" class="w-full px-5 py-24 md:px-10 md:py-32">
      <div class="mx-auto max-w-7xl">
        <div class="mb-12 flex flex-wrap items-end justify-between gap-6">
          <div>
            <p data-template-id="portfolio-kicker" class="canva-text section-kicker mb-4" style="color: rgb(226, 201, 141); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.18rem;">Selected work</p>
            <h2 data-template-id="portfolio-title" class="canva-text editorial text-5xl italic md:text-6xl" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 24px;">Portfolio</h2>
          </div>
          <p data-template-id="portfolio-helper" class="canva-text max-w-xs text-sm leading-6" style="color: rgb(170, 165, 155); font-weight: 400; font-style: normal; font-size: 14px; line-height: 1.5;">Sélectionnez une image pour l’agrandir. Chaque visuel est un emplacement facilement remplaçable.</p>
        </div>

        <!-- 6 PHOTOS PORTFOLIO -->
        <div class="grid grid-cols-2 gap-3 md:grid-cols-12 md:gap-5">
          <button type="button" class="portfolio-card focus-ring group relative col-span-2 overflow-hidden bg-neutral-900 md:col-span-7 md:row-span-2" data-gallery-index="0" aria-label="Ouvrir Editorial 01">
            <img data-template-id="portfolio-image-1" loading="lazy" class="canva-image h-80 w-full object-cover grayscale md:h-full" src="[https://images.pexels.com/photos/24972993/pexels-photo-24972993.jpeg](https://ibb.co/wZ64mHXq)" alt="Placeholder Editorial 01 : portrait bleu flou">
            <span class="absolute inset-x-0 bottom-0 flex items-end justify-between bg-gradient-to-t from-black/80 to-transparent p-5 text-left">
              <span data-template-id="portfolio-caption-1" class="canva-text editorial text-2xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Editorial / 01</span>
              <i data-lucide="expand" aria-hidden="true" class="h-5 w-5 text-[#e2c98d]"></i>
            </span>
          </button>
          <button type="button" class="portfolio-card focus-ring group relative col-span-1 overflow-hidden bg-neutral-900 md:col-span-5" data-gallery-index="1" aria-label="Ouvrir Runway 02">
            <img data-template-id="portfolio-image-2" loading="lazy" class="canva-image h-64 w-full object-cover grayscale md:h-80" src="[https://images.pexels.com/photos/1655841/pexels-photo-1655841.jpeg](https://ibb.co/zTcCFDs3)" alt="Placeholder Runway 02 : mannequin défilant dans une robe élégante">
            <span data-template-id="portfolio-caption-2" class="canva-text absolute bottom-4 left-4 editorial text-xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Runway / 02</span>
          </button>
          <button type="button" class="portfolio-card focus-ring group relative col-span-1 overflow-hidden bg-neutral-900 md:col-span-5" data-gallery-index="2" aria-label="Ouvrir Beauty 03">
            <img data-template-id="portfolio-image-3" loading="lazy" class="canva-image h-64 w-full object-cover grayscale md:h-80" src="[https://images.pexels.com/photos/17566314/pexels-photo-17566314.jpeg](https://ibb.co/RTqDxB47)" alt="Placeholder Beauty 03 : gros plan beauté avec maquillage élégant">
            <span data-template-id="portfolio-caption-3" class="canva-text absolute bottom-4 left-4 editorial text-xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Beauty / 03</span>
          </button>
          <button type="button" class="portfolio-card focus-ring group relative col-span-1 overflow-hidden bg-neutral-900 md:col-span-4" data-gallery-index="3" aria-label="Ouvrir Campaign 04">
            <img data-template-id="portfolio-image-4" loading="lazy" class="canva-image h-64 w-full object-cover grayscale md:h-96" src="[https://images.pexels.com/photos/9150031/pexels-photo-9150031.jpeg](https://ibb.co/PZqJZk1j)" alt="Placeholder Campaign 04 : portrait studio d’une femme en veste argentée">
            <span data-template-id="portfolio-caption-4" class="canva-text absolute bottom-4 left-4 editorial text-xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Campaign / 04</span>
          </button>
          <button type="button" class="portfolio-card focus-ring group relative col-span-1 overflow-hidden bg-neutral-900 md:col-span-4" data-gallery-index="4" aria-label="Ouvrir Editorial 05">
            <img data-template-id="portfolio-image-5" loading="lazy" class="canva-image h-64 w-full object-cover grayscale md:h-96" src="[https://images.pexels.com/photos/4456616/pexels-photo-4456616.jpeg](https://ibb.co/5gjZR75t)" alt="Placeholder Editorial 05 : portrait monochrome d’un mannequin dans une pose mode">
            <span data-template-id="portfolio-caption-5" class="canva-text absolute bottom-4 left-4 editorial text-xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Editorial / 05</span>
          </button>
          <button type="button" class="portfolio-card focus-ring group relative col-span-2 overflow-hidden bg-neutral-900 md:col-span-4" data-gallery-index="5" aria-label="Ouvrir Campaign 06">
            <img data-template-id="portfolio-image-6" loading="lazy" class="canva-image h-64 w-full object-cover grayscale md:h-96" src="[https://images.pexels.com/photos/11311327/pexels-photo-11311327.jpeg](https://ibb.co/9Jmsw3v)" alt="Placeholder Campaign 06 : mannequin posant devant une architecture en pierre">
            <span data-template-id="portfolio-caption-6" class="canva-text absolute bottom-4 left-4 editorial text-xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Campaign / 06</span>
          </button>
        </div>

        <!-- LIEN VERS GALERIE SOUS LES 6 PHOTOS -->
        <div class="mt-10 text-center">
          <a href="#galerie" class="inline-flex items-center gap-3 border px-6 py-3 text-xs font-semibold uppercase tracking-[.14em] focus-ring" style="background: rgb(20, 20, 20); color: rgb(244, 240, 232);">
            Voir la galerie complète
            <i data-lucide="arrow-right" class="h-4 w-4"></i>
          </a>
        </div>
      </div>
    </section>

    <!-- GALERIE -->
    <section id="galerie" class="w-full px-5 py-24 md:px-10 md:py-32">
      <div class="mx-auto max-w-7xl">
        <div class="mb-12">
          <p data-template-id="gallery-kicker" class="canva-text section-kicker mb-4" style="color: rgb(226, 201, 141); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.18rem;">Galerie</p>
          <h2 data-template-id="gallery-title" class="canva-text editorial text-5xl italic md:text-6xl" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 24px;">Toutes les photos</h2>
          <p class="mt-4 max-w-2xl text-sm leading-6" style="color: rgb(170, 165, 155);">Cliquez sur une image pour l’agrandir.</p>
        </div>

        <div class="gallery-grid">
          <div class="gallery-item" data-gallery-src="https://images.pexels.com/photos/24972993/pexels-photo-24972993.jpeg">
            <img src="[https://images.pexels.com/photos/24972993/pexels-photo-24972993.jpeg](https://ibb.co/wZ64mHXq)">
          </div>
          <div class="gallery-item" data-gallery-src="https://images.pexels.com/photos/1655841/pexels-photo-1655841.jpeg">
            <img src="[https://images.pexels.com/photos/1655841/pexels-photo-1655841.jpeg](https://ibb.co/zTcCFDs3)" alt="Runway 02">
          </div>
          <div class="gallery-item" data-gallery-src="https://images.pexels.com/photos/17566314/pexels-photo-17566314.jpeg">
            <img src="[https://images.pexels.com/photos/17566314/pexels-photo-17566314.jpeg](https://ibb.co/RTqDxB47)">
          </div>
          <div class="gallery-item" data-gallery-src="https://images.pexels.com/photos/9150031/pexels-photo-9150031.jpeg">
            <img src="[https://images.pexels.com/photos/9150031/pexels-photo-9150031.jpeg](https://ibb.co/PZqJZk1j)">
          </div>
          <div class="gallery-item" data-gallery-src="https://images.pexels.com/photos/4456616/pexels-photo-4456616.jpeg">
            <img src="[https://images.pexels.com/photos/4456616/pexels-photo-4456616.jpeg](https://ibb.co/5gjZR75t)">
          </div>
          <div class="gallery-item" data-gallery-src="https://images.pexels.com/photos/11311327/pexels-photo-11311327.jpeg">
            <img src="[https://images.pexels.com/photos/11311327/pexels-photo-11311327.jpeg](https://ibb.co/9Jmsw3v)" alt="Campaign 06">
          </div>
        </div>
      </div>
    </section>

    <!-- LIGHTBOX GALERIE -->
    <div id="gallery-lightbox" class="gallery-lightbox" aria-hidden="true">
      <button id="gallery-lightbox-close" class="gallery-lightbox-close" aria-label="Fermer">
        <i data-lucide="x" class="h-5 w-5"></i>
      </button>
      <img id="gallery-lightbox-img" src="" alt="Aperçu">
    </div>

    <!-- À PROPOS -->
    <section id="apropos" class="w-full border-y px-5 py-24 md:px-10 md:py-32">
      <div class="mx-auto grid max-w-7xl gap-14 lg:grid-cols-12">
        <div class="lg:col-span-5">
          <p data-template-id="about-kicker" class="canva-text section-kicker mb-4" style="color: rgb(226, 201, 141); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.18rem;">Profile</p>
          <h2 data-template-id="about-title" class="canva-text editorial text-5xl italic md:text-6xl" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 24px;">À propos</h2>
        </div>
        <div class="lg:col-span-7">
          <p data-template-id="about-copy" class="canva-text editorial max-w-2xl text-2xl leading-relaxed md:text-3xl" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 26px; line-height: 1.4;">Je m'appel CORDEL Noé, j'ai 19 ans, et je cherche à collaborer avec votre agence/marque ! Passioné par la photo, le sport (football, tennis, etc...) et l'écriture, je suis quelqu'un de curieux qui cherche constamment à apprendre.</p>
          <div class="mt-12 grid gap-x-10 gap-y-0 sm:grid-cols-2">
            <div class="border-t py-4">
              <p data-template-id="profile-line-1-label" class="canva-text text-xs uppercase tracking-[.14em]" style="color: rgb(196, 160, 90); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.12rem;">Location</p>
              <p data-template-id="profile-line-1-value" class="canva-text mt-2" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 15px;">GRENOBLE</p>
            </div>
            <div class="border-t py-4">
              <p data-template-id="profile-line-2-label" class="canva-text text-xs uppercase tracking-[.14em]" style="color: rgb(196, 160, 90); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.12rem;">Disponibilité</p>
              <p data-template-id="profile-line-2-value" class="canva-text mt-2" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 15px;">du Jeudi au Dimanche inclu</p>
            </div>
            <div class="border-t py-4">
              <p data-template-id="profile-line-3-label" class="canva-text text-xs uppercase tracking-[.14em]" style="color: rgb(196, 160, 90); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.12rem;">Langues</p>
              <p data-template-id="profile-line-3-value" class="canva-text mt-2" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 15px;">Anglais, Français</p>
            </div>
            <div class="border-t py-4">
              <p data-template-id="profile-line-4-label" class="canva-text text-xs uppercase tracking-[.14em]" style="color: rgb(196, 160, 90); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.12rem;">Représentation</p>
              <p data-template-id="profile-line-4-value" class="canva-text mt-2" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 15px;">EN RECHERCHE DE MARQUE/AGENCE</p>
            </div>
          </div>
          <div data-template-id="measurements-panel" class="canva-panel mt-8 border p-6" style="background: rgb(20, 20, 20); color: rgb(244, 240, 232);">
            <p data-template-id="measurements-label" class="canva-text section-kicker" style="color: rgb(196, 160, 90); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.18rem;">Mensurations</p>
            <p data-template-id="measurements-value" class="canva-text editorial mt-4 text-2xl italic" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 16px;">Taille / Buste / Taille / Hanches — À REMPLACER</p>
          </div>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="w-full px-5 py-24 md:px-10 md:py-32">
      <div class="mx-auto max-w-7xl">
        <p data-template-id="contact-kicker" class="canva-text section-kicker mb-4" style="color: rgb(226, 201, 141); font-weight: 600; font-style: normal; font-size: 11px; letter-spacing: 0.18rem;">Bookings &amp; collaborations</p>
        <h2 data-template-id="contact-title" class="canva-text editorial max-w-4xl text-5xl leading-tight italic md:text-7xl" style="color: rgb(244, 240, 232); font-weight: 400; font-style: italic; font-size: 24px; line-height: 1.1;">Construisons quelque chose de remarquable.</h2>
        <div class="mt-12 flex flex-col justify-between gap-10 border-t pt-7 md:flex-row">
          <div class="space-y-2">
            <p data-template-id="contact-email" class="canva-text text-lg" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 18px;">email@a-remplacer.example</p>
            <p data-template-id="contact-phone" class="canva-text text-lg" style="color: rgb(244, 240, 232); font-weight: 400; font-style: normal; font-size: 18px;">+00 00 00 00 00</p>
            <p data-template-id="contact-location" class="canva-text text-sm" style="color: rgb(170, 165, 155); font-weight: 400; font-style: normal; font-size: 14px;">VILLE / PAYS À REMPLACER</p>
          </div>
          <div class="flex flex-wrap items-start gap-3">
            <a href="mailto:email@a-remplacer.example" data-template-id="contact-mail-button" class="canva-button focus-ring inline-flex items-center gap-3 border px-5 py-4 text-xs font-semibold uppercase tracking-[.14em]" style="background: rgb(196, 160, 90); color: rgb(9, 9, 9);">
              <span data-template-id="contact-mail-button-label" class="canva-text" style="color: rgb(9, 9, 9); font-weight: 700; font-style: normal; font-size: 12px;">Écrire un email</span>
              <i data-lucide="arrow-up-right" class="h-4 w-4" aria-hidden="true"></i>
            </a>
            <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" data-template-id="social-instagram" class="canva-link focus-ring border px-5 py-4 text-xs font-semibold uppercase tracking-[.14em]" style="background: rgb(20, 20, 20); color: rgb(244, 240, 232); font-weight: 600; font-style: normal; font-size: 12px;">Instagram</a>
            <a href="https://www.linkedin.com" target="_blank" rel="noopener noreferrer" data-template-id="social-linkedin" class="canva-link focus-ring border px-5 py-4 text-xs font-semibold uppercase tracking-[.14em]" style="background: rgb(20, 20, 20); color: rgb(244, 240, 232); font-weight: 600; font-style: normal; font-size: 12px;">LinkedIn</a>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- FOOTER -->
  <footer class="w-full border-t px-5 py-7 md:px-10">
    <div class="mx-auto flex max-w-7xl flex-wrap justify-between gap-3 text-xs">
      <p data-template-id="footer-copy" class="canva-text" style="color: rgb(170, 165, 155); font-weight: 400; font-style: normal; font-size: 11px;">© 2026 — NOM DU MANNEQUIN À REMPLACER</p>
      <p data-template-id="footer-note" class="canva-text" style="color: rgb(196, 160, 90); font-weight: 400; font-style: normal; font-size: 11px;">Portfolio / Informations placeholders</p>
    </div>
  </footer>

  <!-- LIGHTBOX EXISTANT (pour le portfolio) -->
  <div id="lightbox" class="lightbox fixed inset-0 z-[60] flex items-center justify-center bg-black/95 p-5 md:p-10" role="dialog" aria-modal="true" aria-label="Aperçu de la galerie" aria-hidden="true">
    <button id="lightbox-close" type="button" data-template-id="lightbox-close-button" class="canva-button focus-ring absolute right-5 top-5 z-10 flex h-12 w-12 items-center justify-center border md:right-10 md:top-10" aria-label="Fermer l’aperçu" style="background: rgb(20, 20, 20); color: rgb(244, 240, 232);">
      <i data-lucide="x" aria-hidden="true" class="h-5 w-5"></i>
    </button>
    <div id="lightbox-stage" class="lightbox-stage relative h-full w-full max-w-6xl">
      <div class="lightbox-slide h-full" data-lightbox-slide="0">
        <img data-template-id="portfolio-image-1" loading="lazy" class="canva-image h-full w-full object-contain" aria-label="Editorial 01" src="https://images.pexels.com/photos/24972993/pexels-photo-24972993.jpeg" alt="Placeholder Editorial 01 : portrait noir et blanc d’un mannequin en studio">
      </div>
      <div class="lightbox-slide h-full" data-lightbox-slide="1">
        <img data-template-id="portfolio-image-2" loading="lazy" class="canva-image h-full w-full object-contain" aria-label="Runway 02" src="https://images.pexels.com/photos/1655841/pexels-photo-1655841.jpeg" alt="Placeholder Runway 02 : mannequin défilant dans une robe élégante">
      </div>
      <div class="lightbox-slide h-full" data-lightbox-slide="2">
        <img data-template-id="portfolio-image-3" loading="lazy" class="canva-image h-full w-full object-contain" aria-label="Beauty 03" src="https://images.pexels.com/photos/17566314/pexels-photo-17566314.jpeg" alt="Placeholder Beauty 03 : gros plan beauté avec maquillage élégant">
      </div>
      <div class="lightbox-slide h-full" data-lightbox-slide="3">
        <img data-template-id="portfolio-image-4" loading="lazy" class="canva-image h-full w-full object-contain" aria-label="Campaign 04" src="https://images.pexels.com/photos/9150031/pexels-photo-9150031.jpeg" alt="Placeholder Campaign 04 : portrait studio d’une femme en veste argentée">
      </div>
      <div class="lightbox-slide h-full" data-lightbox-slide="4">
        <img data-template-id="portfolio-image-5" loading="lazy" class="canva-image h-full w-full object-contain" aria-label="Editorial 05" src="https://images.pexels.com/photos/4456616/pexels-photo-4456616.jpeg" alt="Placeholder Editorial 05 : portrait monochrome d’un mannequin dans une pose mode">
      </div>
      <div class="lightbox-slide h-full" data-lightbox-slide="5">
        <img data-template-id="portfolio-image-6" loading="lazy" class="canva-image h-full w-full object-contain" aria-label="Campaign 06" src="https://images.pexels.com/photos/11311327/pexels-photo-11311327.jpeg" alt="Placeholder Campaign 06 : mannequin posant devant une architecture en pierre">
      </div>
    </div>
    <div class="absolute bottom-6 left-1/2 flex -translate-x-1/2 items-center gap-5 md:bottom-10">
      <button id="lightbox-prev" type="button" data-template-id="lightbox-prev-button" class="canva-button focus-ring flex h-11 w-11 items-center justify-center border" aria-label="Photo précédente" style="background: rgb(20, 20, 20); color: rgb(244, 240, 232);">
        <i data-lucide="arrow-left" aria-hidden="true" class="h-4 w-4"></i>
      </button>
      <span id="lightbox-counter" class="min-w-16 text-center text-xs tracking-[.16em]" aria-live="polite"></span>
      <button id="lightbox-next" type="button" data-template-id="lightbox-next-button" class="canva-button focus-ring flex h-11 w-11 items-center justify-center border" aria-label="Photo suivante" style="background: rgb(20, 20, 20); color: rgb(244, 240, 232);">
        <i data-lucide="arrow-right" aria-hidden="true" class="h-4 w-4"></i>
      </button>
    </div>
  </div>

  <script src="/_sdk/92570d8e491862b9.editing_sdk.js" integrity="sha512-FgTgBgZOGUl1XBrojWdmYvV2Ka+jYLWeeIrMhp1Q1xMV3FJfF+VJFjO6hw+EDGnXYa+zMZXNIP5UYLxGsdfP6g=="></script>
  <script>
    document.addEventListener("DOMContentLoaded", () => {
      lucide.createIcons();

      // MENU
      const menuButton = document.getElementById("menu-button");
      const menuClose = document.getElementById("menu-close");
      const menu = document.getElementById("site-menu");
      const menuBackdrop = document.getElementById("menu-backdrop");
      let lastFocusedElement = null;

      function openMenu() {
        lastFocusedElement = document.activeElement;
        menu.classList.add("is-open");
        menuBackdrop.classList.add("is-open");
        menu.setAttribute("aria-hidden", "false");
        menuButton.setAttribute("aria-expanded", "true");
        menu.querySelector("a").focus();
      }

      function closeMenu() {
        menu.classList.remove("is-open");
        menuBackdrop.classList.remove("is-open");
        menu.setAttribute("aria-hidden", "true");
        menuButton.setAttribute("aria-expanded", "false");
        if (lastFocusedElement) lastFocusedElement.focus();
      }

      menuButton.addEventListener("click", openMenu);
      menuClose.addEventListener("click", closeMenu);
      menuBackdrop.addEventListener("click", closeMenu);
      menu.querySelectorAll("a").forEach(link => link.addEventListener("click", closeMenu));

      // LIGHTBOX PORTFOLIO
      const lightbox = document.getElementById("lightbox");
      const slides = [...document.querySelectorAll("[data-lightbox-slide]")];
      const galleryButtons = [...document.querySelectorAll("[data-gallery-index]")];
      const counter = document.getElementById("lightbox-counter");
      const closeLightboxButton = document.getElementById("lightbox-close");
      let currentIndex = 0;
      let lastGalleryFocus = null;

      function showSlide(index) {
        currentIndex = (index + slides.length) % slides.length;
        slides.forEach((slide, slideIndex) => slide.classList.toggle("is-active", slideIndex === currentIndex));
        counter.textContent = String(currentIndex + 1).padStart(2, "0") + " / " + String(slides.length).padStart(2, "0");
      }

      function openLightbox(index, trigger) {
        lastGalleryFocus = trigger;
        showSlide(index);
        lightbox.classList.add("is-open");
        lightbox.setAttribute("aria-hidden", "false");
        closeLightboxButton.focus();
      }

      function closeLightbox() {
        lightbox.classList.remove("is-open");
        lightbox.setAttribute("aria-hidden", "true");
        if (lastGalleryFocus) lastGalleryFocus.focus();
      }

      galleryButtons.forEach(button => {
        button.addEventListener("click", () => openLightbox(Number(button.dataset.galleryIndex), button));
      });

      document.getElementById("lightbox-prev").addEventListener("click", () => showSlide(currentIndex - 1));
      document.getElementById("lightbox-next").addEventListener("click", () => showSlide(currentIndex + 1));
      closeLightboxButton.addEventListener("click", closeLightbox);

      lightbox.addEventListener("click", event => {
        if (event.target === lightbox) closeLightbox();
      });

      document.addEventListener("keydown", event => {
        if (event.key === "Escape") {
          if (lightbox.classList.contains("is-open")) closeLightbox();
          else if (menu.classList.contains("is-open")) closeMenu();
        }
        if (lightbox.classList.contains("is-open") && event.key === "ArrowLeft") showSlide(currentIndex - 1);
        if (lightbox.classList.contains("is-open") && event.key === "ArrowRight") showSlide(currentIndex + 1);
      });

      // GALERIE LIGHTBOX
      const galleryItems = document.querySelectorAll(".gallery-item");
      const galleryLightbox = document.getElementById("gallery-lightbox");
      const galleryLightboxImg = document.getElementById("gallery-lightbox-img");
      const galleryLightboxClose = document.getElementById("gallery-lightbox-close");

      galleryItems.forEach(item => {
        item.addEventListener("click", () => {
          const src = item.dataset.gallerySrc;
          galleryLightboxImg.src = src;
          galleryLightbox.classList.add("is-open");
          galleryLightbox.setAttribute("aria-hidden", "false");
        });
      });

      galleryLightboxClose.addEventListener("click", () => {
        galleryLightbox.classList.remove("is-open");
        galleryLightbox.setAttribute("aria-hidden", "true");
      });

      galleryLightbox.addEventListener("click", (e) => {
        if (e.target === galleryLightbox) {
          galleryLightbox.classList.remove("is-open");
          galleryLightbox.setAttribute("aria-hidden", "true");
        }
      });

      document.addEventListener("keydown", (e) => {
        if (e.key === "Escape" && galleryLightbox.classList.contains("is-open")) {
          galleryLightbox.classList.remove("is-open");
          galleryLightbox.setAttribute("aria-hidden", "true");
        }
      });
    });
  </script>
</body>
</html>
