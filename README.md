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
    .contact-action b { color: var(-
