<!doctype html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Portfolio mannequin de Noé Cordel, disponible pour éditoriaux, campagnes, e-commerce et collaborations.">
  <meta name="theme-color" content="#090909">
  <title>Noé Cordel — Portfolio Mannequin</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400&display=swap" rel="stylesheet">

  <style>
    :root {
      --black: #090909;
      --surface: #151515;
      --surface-soft: #1b1b1b;
      --paper: #f4f0e8;
      --muted: #aaa59b;
      --gold: #d5b56b;
      --gold-light: #e5ca8d;
      --line: rgba(229, 202, 141, 0.30);
      --content-width: 1180px;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      overflow-x: hidden;
      background: var(--black);
      color: var(--paper);
      font-family: "DM Sans", Arial, sans-serif;
    }

    body.no-scroll { overflow: hidden; }
    img { display: block; width: 100%; max-width: 100%; }
    a { color: inherit; text-decoration: none; }
    button { font: inherit; }

    .container {
      width: min(var(--content-width), calc(100% - 40px));
      margin: 0 auto;
    }

    .serif { font-family: "Playfair Display", Georgia, serif; }

    .eyebrow {
      margin: 0 0 18px;
      color: var(--gold-light);
      font-size: 0.70rem;
      font-weight: 700;
      letter-spacing: 0.20em;
      line-height: 1.4;
      text-transform: uppercase;
    }

    .section-title {
      margin: 0;
      font-size: clamp(2.8rem, 6vw, 5.2rem);
      font-weight: 400;
      line-height: 0.95;
    }

    .button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-height: 48px;
      padding: 13px 20px;
      border: 1px solid var(--line);
      background: var(--surface);
      color: var(--paper);
      cursor: pointer;
      font-size: 0.72rem;
      font-weight: 700;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      transition: transform 0.25s ease, border-color 0.25s ease, background-color 0.25s ease;
    }

    .button:hover {
      transform: translateY(-2px);
      border-color: var(--gold);
      background: var(--surface-soft);
    }

    .button--gold {
      border-color: var(--gold);
      background: var(--gold);
      color: var(--black);
    }

    .button--gold:hover { background: var(--gold-light); }

    :focus-visible {
      outline: 2px solid var(--gold-light);
      outline-offset: 4px;
    }

    /* Header */
    .site-header {
      position: fixed;
      top: 0;
      right: 0;
      left: 0;
      z-index: 20;
      padding: 22px 0;
      background: linear-gradient(to bottom, rgba(9, 9, 9, 0.94), rgba(9, 9, 9, 0));
    }

    .header-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
    }

    .brand {
      font-size: 0.82rem;
      font-weight: 700;
      letter-spacing: 0.20em;
      text-transform: uppercase;
    }

    .menu-button {
      display: inline-flex;
      align-items: center;
      gap: 12px;
      padding: 12px 16px;
      border: 1px solid var(--line);
      background: rgba(21, 21, 21, 0.92);
      color: var(--paper);
      cursor: pointer;
      font-size: 0.72rem;
      font-weight: 700;
      letter-spacing: 0.14em;
      text-transform: uppercase;
    }

    .menu-icon {
      display: grid;
      width: 16px;
      gap: 4px;
    }

    .menu-icon span {
      display: block;
      width: 16px;
      height: 1px;
      background: currentColor;
    }

    /* Hero */
    .hero {
      min-height: 720px;
      padding: 145px 0 82px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: minmax(0, 0.9fr) minmax(0, 1.1fr);
      align-items: center;
      gap: 70px;
    }

    .hero-title {
      max-width: 580px;
      margin: 0;
      font-size: clamp(4.3rem, 9vw, 8.8rem);
      font-weight: 500;
      letter-spacing: -0.04em;
      line-height: 0.79;
    }

    .gold-rule {
      width: 155px;
      height: 1px;
      margin: 34px 0;
      background: linear-gradient(90deg, var(--gold), transparent);
    }

    .hero-intro {
      max-width: 470px;
      margin: 0;
      color: #d4d0c8;
      font-size: 1.08rem;
      line-height: 1.7;
    }

    .details {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 23px 30px;
      max-width: 520px;
      margin: 42px 0 0;
      padding-top: 22px;
      border-top: 1px solid var(--line);
    }

    .details dt {
      margin-bottom: 7px;
      color: var(--gold);
      font-size: 0.66rem;
      font-weight: 700;
      letter-spacing: 0.15em;
      text-transform: uppercase;
    }

    .details dd {
      margin: 0;
      color: var(--paper);
      font-size: 0.84rem;
      line-height: 1.5;
      overflow-wrap: anywhere;
    }

    .hero-photo {
      position: relative;
      min-height: 610px;
      overflow: hidden;
      background: var(--surface);
    }

    .hero-photo img {
      height: 610px;
      object-fit: cover;
      object-position: center;
      transition: transform 0.7s ease;
    }

    .hero-photo:hover img { transform: scale(1.03); }

    .hero-photo::after {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(0, 0, 0, 0.56), transparent 48%);
      pointer-events: none;
    }

    .photo-label {
      position: absolute;
      z-index: 1;
      right: 20px;
      bottom: 20px;
      margin: 0;
      padding: 10px 12px;
      border: 1px solid var(--line);
      background: rgba(9, 9, 9, 0.75);
      color: var(--gold-light);
      font-size: 0.65rem;
      font-weight: 700;
      letter-spacing: 0.13em;
      text-transform: uppercase;
    }

    /* Sections */
    section { padding: 110px 0; }

    .section-heading {
      display: flex;
      align-items: end;
      justify-content: space-between;
      gap: 32px;
      margin-bottom: 46px;
    }

    .section-heading-description {
      max-width: 360px;
      margin: 0;
      color: var(--muted);
      font-size: 0.94rem;
      line-height: 1.65;
    }

    /* Portfolio */
    .portfolio-grid {
      display: grid;
      grid-template-columns: repeat(12, minmax(0, 1fr));
      gap: 18px;
    }

    .portfolio-card {
      position: relative;
      min-height: 300px;
      overflow: hidden;
      border: 0;
      padding: 0;
      background: var(--surface);
      color: var(--paper);
      cursor: pointer;
    }

    .portfolio-card:nth-child(1) {
      grid-column: span 7;
      grid-row: span 2;
      min-height: 618px;
    }

    .portfolio-card:nth-child(2),
    .portfolio-card:nth-child(3) { grid-column: span 5; }

    .portfolio-card:nth-child(n + 4) { grid-column: span 4; }

    .portfolio-card img {
      height: 100%;
      object-fit: cover;
      filter: grayscale(100%);
      transition: transform 0.55s ease, filter 0.45s ease;
    }

    .portfolio-card:hover img,
    .portfolio-card:focus-visible img {
      transform: scale(1.05);
      filter: grayscale(0);
    }

    .portfolio-card::after {
      content: "";
      position: absolute;
      inset: 35% 0 0;
      background: linear-gradient(to bottom, transparent, rgba(0, 0, 0, 0.82));
      pointer-events: none;
    }

    .card-caption {
      position: absolute;
      z-index: 1;
      bottom: 19px;
      left: 20px;
      margin: 0;
      font-size: 1.3rem;
      font-style: italic;
    }

    .gallery-link { margin-top: 42px; text-align: center; }

    /* Gallery */
    .gallery-section { border-top: 1px solid var(--line); }

    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 18px;
    }

    .gallery-item {
      overflow: hidden;
      border: 0;
      padding: 0;
      background: var(--surface);
      cursor: pointer;
    }

    .gallery-item img {
      height: 370px;
      object-fit: cover;
      transition: transform 0.45s ease;
    }

    .gallery-item:hover img,
    .gallery-item:focus-visible img { transform: scale(1.05); }

    /* About */
    .about-section { border-block: 1px solid var(--line); }

    .about-grid {
      display: grid;
      grid-template-columns: minmax(0, 0.8fr) minmax(0, 1.2fr);
      gap: 80px;
    }

    .about-copy {
      max-width: 780px;
      margin: 0;
      font-size: clamp(1.7rem, 3vw, 2.75rem);
      font-weight: 400;
      line-height: 1.35;
    }

    .profile-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 0 30px;
      margin-top: 45px;
    }

    .profile-line {
      padding: 18px 0;
      border-top: 1px solid var(--line);
    }

    .profile-line-label {
      display: block;
      color: var(--gold);
      font-size: 0.68rem;
      font-weight: 700;
      letter-spacing: 0.14em;
      text-transform: uppercase;
    }

    .profile-line-value {
      display: block;
      margin-top: 9px;
      font-size: 0.94rem;
      font-weight: 500;
      line-height: 1.5;
    }

    .measurements {
      margin-top: 30px;
      padding: 25px;
      border: 1px solid var(--line);
      background: var(--surface);
    }

    .measurements-label {
      margin: 0;
      color: var(--gold);
      font-size: 0.68rem;
      font-weight: 700;
      letter-spacing: 0.15em;
      text-transform: uppercase;
    }

    .measurements-value {
      display: block;
      margin-top: 14px;
      font-size: 1.12rem;
      font-weight: 400;
      line-height: 1.55;
    }

    /* Contact */
    .contact-title { max-width: 870px; }

    .contact-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 35px;
      margin-top: 55px;
      padding-top: 25px;
      border-top: 1px solid var(--line);
    }

    .contact-info p { margin: 6px 0; font-size: 1.05rem; }
    .contact-info .contact-location { color: var(--muted); font-s
