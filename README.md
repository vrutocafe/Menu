<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#69734b">
<title>VRUTO | Café sin filtro</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --olive: #69734b;
    --dark: #343a27;
    --butter: #f2d77a;
    --cream: #f7f3e8;
    --white: #fffdf7;
    --border: #e5e0d2;
    --muted: #777765;
  }

  * { box-sizing: border-box; }
  [hidden] { display: none !important; }
  html { scroll-behavior: smooth; }
  body { margin: 0; font-family: 'Quicksand', Arial, sans-serif; background: var(--cream); color: var(--dark); }
  button, input, select, textarea { font: inherit; }
  button { cursor: pointer; }
  a { color: inherit; text-decoration: none; }

  .site-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    padding: 12px 6%;
    background: var(--cream);
    border-bottom: 1px solid var(--border);
    position: sticky;
    top: 0;
    z-index: 100;
  }

  .brand-logo {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    width: auto;
    margin: 0;
    background: transparent;
  }

  .brand-logo img {
    display: block;
    width: 160px;
    height: auto;
    object-fit: contain;
    background: transparent;
  }

  .nav-menu {
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 2px;
  }

  .header-cart {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 9px;
    position: relative;
    background: var(--olive);
    color: var(--white);
    border: none;
    border-radius: 30px;
    padding: 11px 17px;
    font-size: 13px;
    font-weight: 700;
    transition: background .2s ease, transform .2s ease;
  }

  .header-cart:hover {
    background: #535d3b;
    transform: translateY(-1px);
  }

  .header-cart svg {
    width: 21px;
    height: 21px;
    flex-shrink: 0;
  }

  .cart-badge {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-width: 23px;
    height: 23px;
    padding: 0 5px;
    border-radius: 50%;
    background: #d94343;
    color: white;
    font-size: 11px;
    font-weight: 700;
    line-height: 1;
    box-shadow: 0 0 0 2px var(--olive);
  }

  .hero {
    padding: 65px 7% 60px;
    background-image:
      linear-gradient(rgba(30,32,24,.35), rgba(30,32,24,.35)),
      url("1787366429118.jpg");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    color: var(--white);
    text-align: center;
    border-radius: 18px;
  }

  .eyebrow {
    text-transform: uppercase;
    letter-spacing: 3px;
    font-size: 12px;
    font-weight: 700;
  }

  .hero h1 {
    font-size: clamp(42px, 8vw, 76px);
    line-height: 1;
    margin: 18px 0;
    letter-spacing: -2px;
  }

  .hero p { font-size: 17px; margin: 0 auto 24px; }
  .hero h1, .hero p, .hero .eyebrow { color: var(--white); }

  .primary-btn {
    display: inline-block;
    border: 0;
    background: var(--olive);
    color: white;
    padding: 14px 23px;
    border-radius: 30px;
    font-weight: 700;
  }

  section { padding: 48px 6%; }

  .section-heading { text-align: center; margin-bottom: 28px; }
  .section-heading h2 { font-size: 32px; margin: 0 0 8px; }
  .section-heading p { color: var(--muted); margin: 0; }

  .filters {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 9px;
    margin: 25px 0;
  }

  .filter {
    padding: 9px 16px;
    border: 1px solid var(--border);
    border-radius: 30px;
    background: var(--white);
    color: var(--dark);
  }

  .filter.active { background: var(--olive); color: white; border-color: var(--olive); }

  .menu-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 17px;
    max-width: 1100px;
    margin: auto;
  }

  .product {
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: 18px;
    padding: 18px;
    display: flex;
    flex-direction: column;
    min-height: 210px;
    min-width: 0;
    overflow: hidden;
  }

  .product-top { display: flex; justify-content: space-between; gap: 10px; }
  .product h3 { margin: 0 0 8px; overflow-wrap: anywhere; line-height: 1.25; font-size: 19px; }
  .product p { color: var(--muted); font-size: 13px; line-height: 1.5; margin: 0 0 15px; }

  .price {
    color: var(--olive);
    font-weight: 700;
    white-space: normal;
    font-size: 14px;
    line-height: 1.65;
    display: flex;
    flex-direction: column;
    gap: 2px;
    margin: 5px 0 8px;
  }

  .price-line { display: block; font-size: 13px; line-height: 1.45; }

  .category-label {
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--olive);
    font-weight: 700;
    margin-bottom: 12px;
  }

  .add-btn {
    margin-top: auto;
    width: 100%;
    padding: 11px;
    background: var(--olive);
    color: white;
    border: 0;
    border-radius: 10px;
    font-weight: 700;
  }

  .add-btn:hover, .primary-btn:hover { opacity: .9; }

  #pedido { background: #eeeadc; }

  .order-layout {
    max-width: 1000px;
    margin: auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 22px;
    align-items: start;
  }

  .panel { background: var(--white); padding: 23px; border-radius: 18px; border: 1px solid var(--border); }
  .panel h3 { margin-top: 0; }
  .empty { color: var(--muted); font-size: 14px; }
  .cart-item { border-bottom: 1px solid var(--border); padding: 15px 0; }
  .cart-item:last-child { border-bottom: 0; }
  .cart-item-head { display: flex; justify-content: space-between; gap: 10px; font-weight: 700; }
  .cart-item small { color: var(--muted); }
  .cart-options { margin-top: 10px; display: grid; gap: 9px; }
  .cart-options label, .field label { display: block; font-size: 12px; font-weight: 700; margin-bottom: 5px; }
  .remove-btn { border: 0; background: transparent; color: #a14b3d; font-size: 12px; padding: 5px 0; }

  .field { margin-bottom: 14px; }

  .field input,
  .field select,
  .field textarea,
  .cart-options select,
  .cart-options textarea {
    width: 100%;
    border: 1px solid var(--border);
    border-radius: 9px;
    background: white;
    padding: 11px;
    color: var(--dark);
  }

  .field textarea, .cart-options textarea { resize: vertical; min-height: 65px; }

  .total-row {
    display: flex;
    justify-content: space-between;
    font-weight: 700;
    font-size: 19px;
    padding-top: 17px;
    border-top: 1px solid var(--border);
    margin-top: 12px;
  }

  .notice {
    background: #f7f0d8;
    padding: 12px;
    border-radius: 10px;
    font-size: 13px;
    line-height: 1.5;
    margin: 14px 0;
  }

  .whatsapp-btn {
    width: 100%;
    border: 0;
    border-radius: 12px;
    padding: 15px;
    background: var(--olive);
    color: white;
    font-weight: 700;
    font-size: 15px;
  }

  .whatsapp-btn:disabled { opacity: .45; cursor: not-allowed; }

  .about { text-align: center; background: var(--cream); padding: 22px 6%; }
  .about h2 { font-size: 24px; margin: 0 0 8px; }

  .about p {
    max-width: 500px;
    margin: 7px auto;
    line-height: 1.5;
    font-size: 14px;
  }

  .about p strong { font-size: 12px; }

  footer {
    background: var(--dark);
    color: white;
    text-align: center;
    padding: 10px 12px 20px;
    font-size: 11px;
    line-height: 1.3;
    margin-bottom: 0;
  }

  footer p { margin: 0; }

  .mobile-cart {
    display: none;
    position: fixed;
    z-index: 999;
    bottom: 14px;
    left: 14px;
    right: 14px;
    padding: 14px;
    background: var(--olive);
    color: white;
    border: 0;
    border-radius: 14px;
    box-shadow: 0 4px 18px #0002;
    font-weight: 700;
  }

  /* SECCIÓN DE TEMPORADA */
  .seasonal {
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    gap: 45px;
    padding: 65px 8%;
    background: #e9e4d5;
  }

  .seasonal-image {
    height: 370px;
    overflow: hidden;
    border-radius: 5px;
  }

  .seasonal-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: transform .5s;
  }

  .seasonal-image:hover img { transform: scale(1.04); }
  .seasonal-content { max-width: 470px; }

  .seasonal-label {
    color: var(--olive);
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
  }

  .seasonal-content h2 {
    font-size: clamp(35px, 5vw, 58px);
    line-height: 1;
    margin: 18px 0;
  }

  .seasonal-content p { font-size: 15px; line-height: 1.9; color: #666653; }

  .seasonal-prices {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin: 24px 0;
  }

  .seasonal-prices span {
    padding: 10px 13px;
    background: var(--cream);
    border-radius: 30px;
    font-size: 12px;
    font-weight: 700;
  }

  .seasonal-button {
    display: inline-block;
    background: var(--olive);
    color: white;
    padding: 14px 20px;
    border-radius: 30px;
    font-size: 12px;
    font-weight: 700;
  }

  .seasonal-products { display: none; }

  .section-heading h2 a,
  .section-heading h2 .anchor,
  .section-heading h2 .header-anchor,
  .section-heading h2 a.anchor,
  a.anchor,
  .anchor,
  .header-anchor,
  h1 a,
  h2 a,
  h3 a {
    display: none !important;
  }

  @keyframes vrutoEntrada {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero .eyebrow { animation: vrutoEntrada .8s ease-out both; }
  .hero h1 { animation: vrutoEntrada .9s ease-out .15s both; }
  .hero p { animation: vrutoEntrada .9s ease-out .3s both; }
  .hero .primary-btn { animation: vrutoEntrada .9s ease-out .45s both; }

  .reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity .7s ease, transform .7s ease;
  }

  .reveal.visible { opacity: 1; transform: translateY(0); }
  .product.reveal { transition-delay: var(--delay, 0ms); }

  .cart-quantity { display: flex; align-items: center; gap: 14px; margin-top: 14px; }

  .cart-quantity button {
    width: 36px;
    height: 36px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid #d9ddce;
    border-radius: 12px;
    background: #f7f5ec;
    color: #454b35;
    font-size: 22px;
    font-weight: 500;
    cursor: pointer;
    transition: all .2s ease;
    padding: 0;
  }

  .cart-quantity button:hover {
    background: #687451;
    color: var(--white);
    border-color: #687451;
    transform: translateY(-1px);
  }

  .cart-quantity button:active { transform: scale(.94); }

  .cart-quantity .quantity-number {
    min-width: 18px;
    text-align: center;
    font-size: 15px;
    font-weight: 600;
    color: #33382b;
  }

  .cart-quantity .quantity-label { font-size: 12px; color: #858575; }
  .cart-remove { border: none; background: transparent; color: #9a766c; font-size: 12px; cursor: pointer; padding: 6px 0; }
  .cart-remove:hover { color: #b34738; }

  .discount-box {
    margin-top: 20px;
    padding: 15px;
    background: var(--cream);
    border: 1px solid var(--border);
    border-radius: 12px;
  }

  .discount-box label { display: block; font-size: 13px; font-weight: 700; margin-bottom: 8px; }

  .discount-input-row { display: flex; gap: 8px; }

  .discount-input-row input {
    flex: 1;
    min-width: 0;
    padding: 11px;
    border: 1px solid var(--border);
    border-radius: 9px;
    text-transform: uppercase;
  }

  .discount-input-row button {
    border: 0;
    border-radius: 9px;
    padding: 10px 14px;
    background: var(--olive);
    color: white;
    font-weight: 700;
  }

  .discount-status { margin: 9px 0 0; font-size: 12px; line-height: 1.5; }
  .discount-success { color: #426b36; }
  .discount-error { color: #a14b3d; }
  .discount-summary { display: none; justify-content: space-between; gap: 10px; margin-top: 12px; font-size: 14px; }
  .discount-amount { color: #426b36; font-weight: 700; }
  .final-total { font-size: 21px; }

  .social-footer {
    background: #f4f0e6;
    color: #454a35;
    text-align: center;
    padding: 45px 20px 30px;
    margin-top: 50px;
  }

  .social-footer h2 { letter-spacing: 3px; margin-bottom: 8px; }
  .social-footer p { margin-bottom: 22px; }

  .social-links {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 12px;
    margin: 4px 0;
  }

  .social-links a { color: var(--olive); text-decoration: none; font-weight: 600; }
  .social-links a:hover { color: #454a35; }

  .main-footer {
    background: var(--olive);
    color: var(--white);
    text-align: center;
    padding: 12px 15px !important;
    font-size: 12px;
    line-height: 1.2 !important;
    margin-bottom: 0 !important;
  }

  .main-footer strong {
    display: block;
    font-size: 17px;
    letter-spacing: 2px;
    margin-bottom: 2px;
  }

  .main-footer > span { display: block; margin-bottom: 8px; }

  .footer-logo {
    display: block;
    width: 65px;
    height: auto;
    margin: 0 auto 3px;
    padding: 0;
    background: none !important;
    border: none !important;
    box-shadow: none !important;
    filter: none !important;
    mix-blend-mode: normal;
    object-fit: contain;
  }

  .main-footer .social-links { justify-content: center; gap: 12px; margin: 4px 0; }
  .main-footer .social-links a { color: var(--white); font-size: 12px; margin: 0; padding: 0; line-height: 1.2; }

  .main-footer small {
    display: block;
    margin: 3px 0 0;
    padding: 0;
    line-height: 1.2;
    font-size: 11px;
  }

  .how-to-order { background: var(--cream); padding: 24px 6%; }
  .how-to-order .section-heading { margin-bottom: 12px !important; }
  .how-to-order .section-heading h2 { font-size: 26px; margin-bottom: 5px; }
  .how-to-order .section-heading p { font-size: 13px; }

  .how-to-grid {
    max-width: 900px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 12px;
  }

  .how-to-card {
    display: flex;
    align-items: flex-start;
    gap: 11px;
    padding: 15px;
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: 12px;
    min-width: 0;
    opacity: 0;
    animation: vrutoStepAppear .6s ease forwards;
    transition: transform .25s ease, box-shadow .25s ease;
  }

  .how-to-number {
    flex: 0 0 29px;
    width: 29px;
    height: 29px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--olive);
    color: white;
    border-radius: 50%;
    font-size: 13px;
    font-weight: 700;
  }

  .how-to-card h3 { font-size: 14px; line-height: 1.3; margin: 2px 0 5px; }
  .how-to-card p { font-size: 12px; line-height: 1.5; color: var(--muted); margin: 0; }
  .how-to-card:nth-child(1) { animation-delay: .1s; }
  .how-to-card:nth-child(2) { animation-delay: .25s; }
  .how-to-card:nth-child(3) { animation-delay: .4s; }
  .how-to-card:hover { transform: translateY(-4px); box-shadow: 0 8px 20px rgba(49,57,37,.10); }
  .how-to-order { padding-bottom: 8px !important; margin-bottom: 0 !important; }
  .how-to-grid { margin-bottom: 0 !important; }
  #menu { margin-top: 0 !important; padding-top: 20px !important; }

  @keyframes vrutoStepAppear {
    from { opacity: 0; transform: translateY(18px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .vruto-instagram {
    background: var(--cream);
    padding: 48px 18px 15px;
    text-align: center;
    overflow: hidden;
    margin-bottom: 0 !important;
  }

  .instagram-heading { margin: 0 auto 10px !important; }
  .instagram-eyebrow { display: inline-block; color: var(--olive); font-size: 10px; font-weight: 700; letter-spacing: 3px; margin-bottom: 8px; }

  .instagram-heading h2 {
    color: var(--dark);
    font-size: clamp(25px, 4vw, 34px);
    font-weight: 600;
    letter-spacing: -1px;
    line-height: 1.2;
    margin: 5px 0 9px;
  }

  .instagram-heading p { color: var(--muted); font-size: 13px; line-height: 1.7; margin: 0 auto; }

  .instagram-reels {
    display: flex !important;
    justify-content: center !important;
    width: 100% !important;
    max-width: 400px !important;
    margin: 0 auto !important;
    padding-bottom: 0 !important;
  }

  .instagram-reels > .instagram-media {
    display: block !important;
    flex: 0 1 380px !important;
    width: 100% !important;
    min-width: 0 !important;
    max-width: 380px !important;
    margin: 0 auto !important;
    box-sizing: border-box !important;
    background: var(--white) !important;
    border: 1px solid var(--border) !important;
    border-radius: 20px !important;
    box-shadow: 0 10px 28px rgba(52,58,39,.09) !important;
  }

  .vruto-instagram + section { margin-top: 0 !important; padding-top: 20px !important; }

  html, body {
    margin: 0 !important;
    padding: 0 !important;
    min-height: 0 !important;
  }

  body { height: auto !important; }
  main, .main-footer { margin-bottom: 0 !important; padding-bottom: 0; }
  body > script { display: none !important; }

  @media (max-width: 700px) {
    .brand-logo img { width: 100px; max-height: 50px; }
    .site-header { padding: 12px 4%; gap: 10px; }
    .header-cart { gap: 7px; padding: 10px 12px; font-size: 12px; }
    .header-cart svg { width: 20px; height: 20px; }
    .cart-badge { min-width: 22px; height: 22px; }
    .hero { padding: 55px 6%; }
    section { padding: 38px 5%; }
    .order-layout { grid-template-columns: 1fr; }
    .menu-grid { grid-template-columns: 1fr 1fr; gap: 10px; }
    .product { padding: 14px; min-height: 215px; }
    .product h3 { font-size: 16px; }
    .product-top { flex-direction: column; gap: 5px; }
    .price { font-size: 15px; }

    .mobile-cart {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      position: fixed;
      z-index: 999;
      left: 12px;
      right: 12px;
      bottom: calc(12px + env(safe-area-inset-bottom));
      width: auto;
      min-height: 64px;
      padding: 12px 17px;
      border: 1px solid rgba(255,255,255,.12);
      border-radius: 16px;
      background: var(--dark);
      color: var(--white);
      box-shadow: 0 5px 22px rgba(0,0,0,.20);
      text-align: left;
    }

    .mobile-cart-info { display: flex; flex-direction: column; gap: 4px; }
    #mobileCartLabel { font-size: 14px; font-weight: 700; }
    .mobile-cart-detail { color: #e8e5d9; font-size: 12px; font-weight: 500; }
    .mobile-cart-action { flex-shrink: 0; background: var(--butter); color: var(--dark); padding: 10px 13px; border-radius: 24px; font-size: 12px; font-weight: 700; }

    #pedido {
      width: 100%;
      min-width: 0;
      padding-left: 12px;
      padding-right: 12px;
      overflow: hidden;
    }

    #pedido .order-layout {
      display: grid;
      grid-template-columns: minmax(0, 1fr);
      width: 100%;
      max-width: 100%;
      min-width: 0;
      gap: 16px;
    }

    #pedido .panel {
      width: 100%;
      min-width: 0;
      max-width: 100%;
      padding: 16px;
      margin: 0;
      overflow-wrap: anywhere;
    }

    #pedido #cartItems,
    #pedido .cart-item,
    #pedido .cart-item-head,
    #pedido .cart-options,
    #pedido .field,
    #pedido form {
      width: 100%;
      min-width: 0;
      max-width: 100%;
    }

    #pedido .cart-item-head { align-items: flex-start; overflow-wrap: anywhere; gap: 8px; font-size: 13px; }
    #pedido .cart-item-head span { min-width: 0; overflow-wrap: anywhere; }

    #pedido .field input,
    #pedido .field select,
    #pedido .field textarea,
    #pedido .cart-options select,
    #pedido .cart-options textarea {
      display: block;
      width: 100%;
      min-width: 0;
      max-width: 100%;
      box-sizing: border-box;
    }

    #pedido .discount-input-row { display: flex; width: 100%; min-width: 0; gap: 6px; }
    #pedido .discount-input-row input { flex: 1 1 0; width: 0; min-width: 0; }
    #pedido .discount-input-row button { flex: 0 0 auto; padding-left: 10px; padding-right: 10px; }
    #pedido .total-row { gap: 8px; font-size: 15px; }
    #pedido .total-row span { min-width: 0; overflow-wrap: anywhere; }
    #pedido .final-total { font-size: 17px; }
    #pedido .notice { overflow-wrap: anywhere; }

    .how-to-order { padding: 20px 5%; }
    .how-to-order .section-heading { margin-bottom: 12px; }
    .how-to-order .section-heading h2 { font-size: 23px; }
    .how-to-grid { grid-template-columns: 1fr; gap: 8px; }
    .how-to-card { padding: 11px 12px; gap: 10px; border-radius: 10px; }
    .how-to-number { flex-basis: 26px; width: 26px; height: 26px; font-size: 12px; }
    .how-to-card h3 { font-size: 13px; margin: 1px 0 3px; }
    .how-to-card p { font-size: 11px; line-height: 1.4; }

    .vruto-instagram { padding: 36px 14px 15px; }
    .instagram-reels { max-width: 100% !important; }
    .instagram-reels > .instagram-media { max-width: 380px !important; }

    .add-btn, .filter, .cart-quantity button, .whatsapp-btn {
      min-height: 44px;
      touch-action: manipulation;
    }

    input, select, textarea { font-size: 16px; }
    footer { padding: 8px 10px 20px !important; font-size: 10px; line-height: 1.2; }
    footer strong { font-size: 11px; }
  }

  @media (max-width: 650px) {
    .seasonal { grid-template-columns: 1fr; gap: 25px; padding: 40px 6%; }
    .seasonal-image { height: 290px; }
  }

  @media (max-width: 480px) {
    .vruto-instagram { padding: 36px 14px 15px; }
  }

  @media (max-width: 370px) {
    .menu-grid { grid-template-columns: 1fr; }
  }

  @media (prefers-reduced-motion: reduce) {
    html { scroll-behavior: auto; }
    .hero .eyebrow, .hero h1, .hero p, .hero .primary-btn,
    .reveal, .vruto-instagram.reveal, .vruto-instagram.reveal.visible,
    .how-to-order .section-heading, .how-to-card {
      animation: none !important;
      opacity: 1 !important;
      transform: none !important;
      transition: none !important;
    }
  }
  
/* Nombre de quien recibe cada bebida */
.customer-drink-field {
  margin: 14px 0;
  padding: 14px;
  background: #f7f6f0;
  border: 1px solid #e7e5da;
  border-radius: 12px;
}

.customer-drink-field > label {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
  margin-bottom: 9px;
}

.customer-drink-label {
  color: #454938;
  font-size: 13px;
  font-weight: 600;
}

.customer-drink-optional {
  color: #858576;
  font-size: 10px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: .06em;
}

.customer-drink-field input {
  box-sizing: border-box;
  width: 100%;
  min-height: 44px;
  padding: 11px 12px;
  border: 1px solid #deded2;
  border-radius: 8px;
  background: #fffefa;
  color: #34372b;
  font: inherit;
  font-size: 14px;
  outline: none;
  transition: border-color .2s, box-shadow .2s;
}

.customer-drink-field input:focus {
  border-color: #69734b;
  box-shadow: 0 0 0 3px rgba(105, 115, 75, .12);
}

.customer-drink-field input::placeholder {
  color: #a19f92;
}

.customer-drink-field p {
  margin: 8px 0 0;
  color: #858576;
  font-size: 11px;
  line-height: 1.5;
}
  /* Cuadrícula estándar del menú */
  .menu-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 17px;
    max-width: 1100px;
    margin: auto;
  }

  /* Si solo hay un artículo en la categoría, limitamos el ancho de la cuadrícula para que no se expanda y quede centrado */
  .menu-grid:has(.product:only-child) {
    grid-template-columns: minmax(220px, 320px);
    justify-content: center;
  }

  /* Ajuste específico para celulares cuando hay un solo artículo */
  @media (max-width: 700px) {
    .menu-grid {
      grid-template-columns: 1fr 1fr; /* Mantiene 2 columnas cuando hay varios productos */
      gap: 10px;
    }

    .menu-grid:has(.product:only-child) {
      grid-template-columns: 1fr; /* Una sola columna */
      max-width: 260px;           /* Ancho idéntico al de las demás tarjetas en móvil */
      margin: 0 auto;             /* Centrado automático */
    }
  }
  
  .settings-fab:hover {
    background: var(--olive);
    transform: scale(1.05);
  }

  .settings-fab svg {
    width: 20px;
    height: 20px;
  }
  /* Estilo para el botón de ajustes junto al footer */
  .footer-settings-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    margin-top: 10px;
    padding: 6px 14px;
    background: rgba(255, 255, 255, 0.12);
    color: var(--white);
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 20px;
    font-size: 11px;
    font-weight: 650;
    cursor: pointer;
    transition: background .2s ease;
  }

  .footer-settings-btn:hover {
    background: rgba(255, 255, 255, 0.22);
  }

  .footer-settings-btn svg {
    width: 14px;
    height: 14px;
  }

</style>
</head>
<body>

<header class="site-header">
  <a class="brand-logo" href="#inicio">
    <img src="./vruto-logo-transparente.png" alt="VRUTO CAFÉ">
  </a>

  <button class="header-cart" onclick="goToCart()" aria-label="Ver carrito">
    <svg viewBox="0 0 24 24" aria-hidden="true">
      <path d="M3 3h2l2.4 12.2a2 2 0 0 0 2 1.6h8.8a2 2 0 0 0 2-1.6L22 8H6"
        fill="none" stroke="currentColor" stroke-width="1.8"
        stroke-linecap="round" stroke-linejoin="round"/>
      <circle cx="10" cy="20" r="1.2" fill="currentColor"/>
      <circle cx="18" cy="20" r="1.2" fill="currentColor"/>
    </svg>
    <span>Carrito</span>
    <span class="cart-badge" id="cartCount">0</span>
  </button>
</header>

<main>
<section class="hero" id="inicio">
  <div class="eyebrow">Coffee · Matcha · Chill</div>
  <h1 id="menuBannerTitle">café sin<br>filtro.</h1>
  <p id="menuBannerDescription">Tu próximo café favorito, hasta tu puerta.</p>
  <a id="menuBannerButton" class="primary-btn" href="#menu">Explorar menú ↓</a>
</section>

  <section class="seasonal" id="seasonalSection">
    <div class="seasonal-image">
      <img id="seasonalImage" src="1790312149990.png"
        alt="Bebida de temporada VRUTO Café" loading="lazy">
    </div>

    <div class="seasonal-content">
      <span class="seasonal-label" id="seasonalLabel">EDICIÓN DE TEMPORADA</span>
      <h2 id="seasonalTitle">Pumpkin Spice.</h2>
      <p id="seasonalDescription">
        Espresso, leche y especias de calabaza.
        Tu bebida favorita de otoño, a tu manera.
      </p>

      <div class="seasonal-prices" id="seasonalPrices">
        <span>Caliente desde $70</span>
        <span>Frío $85</span>
      </div>

      <a href="#menu" class="seasonal-button" id="seasonalButton">
        DESCUBRIR EN EL MENÚ →
      </a>
    </div>

    <div id="seasonalProducts" class="seasonal-products"></div>
  </section>

  <section class="how-to-order" id="como-pedir">
    <div class="section-heading">
      <h2>¿Cómo pedir?</h2>
      <p>Tu café favorito en tres pasos.</p>
    </div>

    <div class="how-to-grid">
      <article class="how-to-card">
        <span class="how-to-number">1</span>
        <div>
          <h3>Elige tu café</h3>
          <p>Explora el menú y agrega tus bebidas al carrito.</p>
        </div>
      </article>

      <article class="how-to-card">
        <span class="how-to-number">2</span>
        <div>
          <h3>Completa tus datos</h3>
          <p>Indica tu dirección, zona de entrega y preferencias.</p>
        </div>
      </article>

      <article class="how-to-card">
        <span class="how-to-number">3</span>
        <div>
          <h3>Confirma por WhatsApp</h3>
          <p>Envía tu pedido y confirma el envío y la transferencia.</p>
        </div>
      </article>
    </div>
  </section>

  <section id="menu">
    <div class="section-heading">
      <h2>MENÚ</h2>
      <p>Elige tus favoritos y arma tu pedido.</p>
    </div>
    <div id="menuFilters" class="filters"></div>
    <div class="menu-grid" id="menuGrid"></div>
  </section>

  <section id="pedido">
    <div class="section-heading">
      <h2>Tu pedido</h2>
      <p>Revisa tu carrito y dinos dónde entregarlo.</p>
    </div>

    <div class="order-layout">
      <div class="panel" id="cartPanel">
        <h3>🛒 Mi carrito</h3>
        <div id="cartItems">
          <p class="empty">Tu carrito está vacío. Agrega algo rico del menú.</p>
        </div>

        <div class="total-row">
          <span>Subtotal</span>
          <span id="subtotal">$0.00 MXN</span>
        </div>

        <div class="discount-box">
          <label for="discountCode">¿Tienes un código de descuento?</label>
          <div class="discount-input-row">
            <input type="text" id="discountCode" placeholder="Ingresa tu código"
              autocomplete="off" maxlength="30">
            <button type="button" onclick="applyDiscount()">Aplicar</button>
          </div>
          <p id="discountStatus" class="discount-status" aria-live="polite"></p>
        </div>

        <div id="discountSummary" class="discount-summary">
          <span id="discountLabel">Descuento</span>
          <span id="discountAmount" class="discount-amount">-$0.00 MXN</span>
        </div>

        <div class="total-row final-total">
          <span>Total de bebidas</span>
          <span id="finalTotal">$0.00 MXN</span>
        </div>

        <p class="empty" style="margin-top:10px;">
          El costo de envío se confirma por WhatsApp.
        </p>
      </div>

      <div class="panel">
        <h3>📍 Datos de entrega</h3>
        <form id="orderForm">
          <div class="field">
            <label for="customerName">Nombre *</label>
            <input id="customerName" name="customerName" required placeholder="¿A nombre de quién?">
          </div>

          <div class="field">
            <label for="customerPhone">Teléfono de contacto *</label>
            <input id="customerPhone" name="customerPhone" type="tel" required placeholder="Tu número de teléfono">
          </div>

          <div class="field">
            <label for="deliveryZone">Zona de entrega *</label>
            <select id="deliveryZone" name="deliveryZone" required>
              <option value="">Selecciona tu zona</option>
              <option value="Centro">Centro de Mazatlán</option>
              <option value="Otra zona">Otra zona de Mazatlán</option>
            </select>
          </div>

          <div class="field">
            <label for="deliveryAddress">Dirección completa *</label>
            <textarea id="deliveryAddress" name="deliveryAddress" required placeholder="Calle, número, colonia y ciudad"></textarea>
          </div>

          <div class="field">
            <label for="references">Referencias de entrega</label>
            <input id="references" name="references" placeholder="Entre calles, color de portón, oficina, etc.">
          </div>

          <div class="field">
            <label for="generalNotes">Notas adicionales</label>
            <textarea id="generalNotes" name="generalNotes" placeholder="Indicaciones para tu pedido"></textarea>
          </div>

          <div class="field">
            <label for="payment">Método de pago</label>
            <select id="payment" disabled>
              <option>Transferencia bancaria</option>
            </select>
          </div>

          <div class="notice">
            <strong>Pago por transferencia bancaria.</strong><br>
            Al enviar tu pedido por WhatsApp te compartiremos los datos para realizar el pago. Tu pedido se confirma con el negocio.
          </div>

          <button type="submit" class="whatsapp-btn" id="sendOrder">
            Enviar pedido por WhatsApp
          </button>
        </form>
      </div>
    </div>
  </section>

  <section class="vruto-instagram" id="instagram">
    <div class="instagram-heading">
      <span class="instagram-eyebrow">CAFÉ SIN FILTRO.</span>
      <h2>Un poco más de VRUTO</h2>
      <p>Café, matcha y momentos que se antojan.</p>
    </div>

    <div class="instagram-reels">
      <blockquote class="instagram-media"
        data-instgrm-permalink="https://www.instagram.com/reel/DdKdgsnSvoB/"
        data-instgrm-version="14">
      </blockquote>
    </div>
  </section>

  <section class="about">
    <h2>Un buen café cambia el día.</h2>
    <p>Preparamos tus bebidas favoritas con mucho café y cero complicaciones. Pide en línea y disfruta VRUTO donde estés.</p>
    <p><strong>Servicio a domicilio · Mazatlán, Sinaloa</strong></p>
  </section>
</main>

<footer class="main-footer">
  <img src="./vruto-logo-transparente.png" alt="VRUTO Café" class="footer-logo">
  <span>café sin filtro. · Mazatlán, Sinaloa</span>
  <div class="social-links">
    <a href="https://www.instagram.com/vrutocafe/" target="_blank" rel="noopener noreferrer">Instagram</a>
    <a href="https://wa.me/526693683462" target="_blank" rel="noopener noreferrer">WhatsApp</a>
  </div>
  <!-- Botón de ajustes integrado en el footer -->
  <div>
    <a href="https://vrutocafe.github.io/VRUTO/admin.html" class="footer-settings-btn" style="text-decoration: none;">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <circle cx="12" cy="12" r="3"></circle>
        <path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1 0 2.83 2 2 0 0 1-2.83 0l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83 0 2 2 0 0 1 0-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 0-2.83 2 2 0 0 1 2.83 0l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 0 2 2 0 0 1 0 2.83l-.06-.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z"></path>
      </svg>
      Ajustes
    </a>
  </div>

  <small>© <span id="year"></span> VRUTO Café</small>
</footer>

<button class="mobile-cart" onclick="goToCart()">
  <span class="mobile-cart-info">
    <span id="mobileCartLabel">Ver carrito</span>
    <span class="mobile-cart-detail">
      <span id="mobileCartCount">0</span> bebidas · <span id="mobileCartTotal">$0.00</span>
    </span>
  </span>
  <span class="mobile-cart-action">Revisar →</span>
</button>

<script>
"use strict";

const WHATSAPP_NUMBER = "526693683462";
const SUPABASE_URL = "https://eqguxuacvdvdbxtxbogf.supabase.co";
const SUPABASE_PUBLIC_KEY = "sb_publishable_Y0Qdy8M6MBssMeHy52WhMQ_5mcCnMfD";

let menuData = [
  {id:1,name:"Americano",category:"Calientes",description:"Espresso con agua caliente.",hot:true,milk:false,prices:{"12 oz":50,"16 oz":60},sugar:true},
  {id:2,name:"Latte Regular",category:"Calientes",description:"Espresso con leche cremosa.",hot:true,milk:true,prices:{"12 oz":65,"16 oz":75},sugar:true},
  {id:3,name:"Latte Caramel",category:"Calientes",description:"Espresso, leche y caramelo.",hot:true,milk:true,prices:{"12 oz":70,"16 oz":80},coldPrice:78},
  {id:4,name:"Latte Vainilla",category:"Calientes",description:"Latte suave con un toque de vainilla.",hot:true,milk:true,prices:{"12 oz":70,"16 oz":80},coldPrice:75},
  {id:5,name:"Moka Latte",category:"Calientes",description:"Latte con chocolate.",hot:true,milk:true,prices:{"12 oz":70,"16 oz":80},coldPrice:78},
  {id:6,name:"Chai Latte",category:"Calientes",description:"Té chai especiado con leche.",hot:true,milk:true,prices:{"12 oz":70,"16 oz":80},coldPrice:78},
  {id:7,name:"Chai Sucio",category:"Calientes",description:"Chai especiado con espresso.",hot:true,milk:true,prices:{"12 oz":80,"16 oz":90},coldPrice:85},
  {id:8,name:"Matcha",category:"Calientes",description:"Matcha cremoso y equilibrado.",hot:true,milk:true,prices:{"12 oz":75,"16 oz":85},coldPrice:85},
  {id:9,name:"Taro Latte",category:"Calientes",description:"Bebida cremosa de taro.",hot:true,milk:true,prices:{"12 oz":75,"16 oz":85},coldPrice:80},
  {id:10,name:"Americano Frío",displayName:"Americano",category:"Fríos",description:"Espresso con agua y hielo.",hot:false,milk:false,coldPrice:60,sugar:true},
  {id:11,name:"Latte Regular Frío",displayName:"Latte Reg.",category:"Fríos",description:"Latte helado, suave y cremoso.",hot:false,milk:true,coldPrice:75,sugar:true},
  {id:12,name:"Caramelo Frío",displayName:"Caramelo",category:"Fríos",description:"Latte helado con caramelo.",hot:false,milk:true,coldPrice:78},
  {id:13,name:"Vainilla Fría",displayName:"Vainilla",category:"Fríos",description:"Latte helado con vainilla.",hot:false,milk:true,coldPrice:75},
  {id:14,name:"Moka Latte Frío",displayName:"Moka Latte",category:"Fríos",description:"Latte helado con chocolate.",hot:false,milk:true,coldPrice:78},
  {id:15,name:"Chai Latte Frío",displayName:"Chai Latte",category:"Fríos",description:"Chai especiado con leche y hielo.",hot:false,milk:true,coldPrice:78},
  {id:16,name:"Chai Sucio Frío",displayName:"Chai Sucio",category:"Fríos",description:"Chai con espresso, leche y hielo.",hot:false,milk:true,coldPrice:85},
  {id:17,name:"Matcha Frío",displayName:"Matcha",category:"Fríos",description:"Matcha helado y cremoso.",hot:false,milk:true,coldPrice:85},
  {id:18,name:"Taro Latte Frío",displayName:"Taro Latte",category:"Fríos",description:"Taro con leche y hielo.",hot:false,milk:true,coldPrice:80},
  {id:19,name:"Pumpkin Spice Caliente",displayName:"Pumpkin Spice Caliente",category:"Especiales",description:"Espresso, leche y especias de calabaza.",hot:true,milk:true,prices:{"12 oz":70,"16 oz":80},isSpecial:true},
  {id:20,name:"Pumpkin Spice Frío",displayName:"Pumpkin Spice Frío",category:"Especiales",description:"Pumpkin Spice Latte helado con notas de calabaza y especias.",hot:false,milk:true,coldPrice:85,isSpecial:true}
];

const milkOptions = [
  {value:"Entera",label:"Leche entera"},
  {value:"Deslactosada",label:"Leche deslactosada"},
  {value:"Deslactosada Light",label:"Leche deslactosada Light"},
  {value:"Almendra",label:"Leche de almendra (+$15)",extra:15},
  {value:"Sin leche",label:"Sin leche"}
];

const extraOptions = [
  {value:"shot",label:"Shot extra (+$15)",price:15},
  {value:"syrup",label:"Jarabe extra (+$15)",price:15}
];

let menuCategories = [];
let cart = [];
let currentFilter = "Fríos";
const money = amount => "$" + Number(amount || 0).toFixed(2) + " MXN";

/* CÓDIGOS PROMOCIONALES VRUTO CAFÉ */
const DISCOUNT_CODES = {
  OFFICE15: {percentage:15,minDrinks:3,zone:"Centro"}
};

let appliedPromo = null;

function getDrinkCount() {
  return cart.reduce((sum,item) => sum + Number(item.quantity || 1),0);
}

function getSubtotal() {
  return cart.reduce((sum,item) => sum + itemPrice(item) * Number(item.quantity || 1),0);
}

function getDiscount() {
  if (!appliedPromo) return 0;
  return Math.round(getSubtotal() * appliedPromo.percentage) / 100;
}

function getFinalTotal() {
  return Math.max(0,getSubtotal() - getDiscount());
}

function setDiscountStatus(message,success=false) {
  const status = document.getElementById("discountStatus");
  status.textContent = message;
  status.className = "discount-status " + (success ? "discount-success" : "discount-error");
}

function applyDiscount() {
  const code = document.getElementById("discountCode").value.trim().toUpperCase();
  const zone = document.getElementById("deliveryZone").value;
  const promo = DISCOUNT_CODES[code];

  if (!code) {
    appliedPromo = null;
    setDiscountStatus("Ingresa un código promocional.");
    renderCart();
    return;
  }

  if (!promo) {
    appliedPromo = null;
    setDiscountStatus("El código ingresado no es válido.");
    renderCart();
    return;
  }

  if (getDrinkCount() < promo.minDrinks) {
    appliedPromo = null;
    setDiscountStatus("Necesitas al menos " + promo.minDrinks + " bebidas para usar este código.");
    renderCart();
    return;
  }

  if (zone !== promo.zone) {
    appliedPromo = null;
    setDiscountStatus("OFFICE15 solo es válido para entregas en el Centro de Mazatlán.");
    renderCart();
    return;
  }

  appliedPromo = {
    code,
    percentage:promo.percentage,
    minDrinks:promo.minDrinks,
    zone:promo.zone
  };

  setDiscountStatus("¡Código aplicado! Tienes " + promo.percentage + "% de descuento.",true);
  renderCart();
}

function renderDiscountTotals() {
  const subtotal = getSubtotal();

  if (appliedPromo) {
    if (getDrinkCount() < appliedPromo.minDrinks) {
      appliedPromo = null;
      setDiscountStatus("Descuento eliminado: necesitas al menos 3 bebidas.");
    } else if (document.getElementById("deliveryZone").value !== appliedPromo.zone) {
      appliedPromo = null;
      setDiscountStatus("Descuento eliminado: la promoción solo aplica en el Centro.");
    }
  }

  const discount = getDiscount();
  const finalTotal = Math.max(0,subtotal - discount);

  document.getElementById("subtotal").textContent = money(subtotal);
  document.getElementById("finalTotal").textContent = money(finalTotal);

  const summary = document.getElementById("discountSummary");

  if (appliedPromo && discount > 0) {
    summary.style.display = "flex";
    document.getElementById("discountLabel").textContent = "Descuento " + appliedPromo.percentage + "%";
    document.getElementById("discountAmount").textContent = "-" + money(discount);
  } else {
    summary.style.display = "none";
  }
}

document.getElementById("deliveryZone").addEventListener("change",() => {
  const code = document.getElementById("discountCode").value.trim().toUpperCase();
  const zone = document.getElementById("deliveryZone").value;
  const promo = DISCOUNT_CODES[code];

  if (promo && getDrinkCount() >= promo.minDrinks && zone === promo.zone) {
    appliedPromo = {
      code,
      percentage:promo.percentage,
      minDrinks:promo.minDrinks,
      zone:promo.zone
    };
    setDiscountStatus("¡Código aplicado! Tienes " + promo.percentage + "% de descuento.",true);
  } else if (appliedPromo && zone !== appliedPromo.zone) {
    appliedPromo = null;
    setDiscountStatus("Descuento eliminado: la promoción solo aplica en el Centro.");
  }

  renderCart();
});

document.getElementById("discountCode").addEventListener("keydown",event => {
  if (event.key === "Enter") {
    event.preventDefault();
    applyDiscount();
  }
});

document.getElementById("discountCode").addEventListener("input",() => {
  appliedPromo = null;
  document.getElementById("discountStatus").textContent = "";
  renderCart();
});

function getPrice(product,size) {
  return product.hot
    ? Number(product.prices?.[size] || 0)
    : Number(product.coldPrice || 0);
}

function renderMenu() {
  const grid = document.getElementById("menuGrid");

  const filtered = menuData.filter(item => {
    if (currentFilter === "Especiales") return item.isSpecial === true;
    if (currentFilter === "Calientes") return item.hot === true;
    if (currentFilter === "Fríos") return item.hot === false;
    return item.category === currentFilter;
  });

  // Detecta si solo hay 1 artículo en la categoría actual
  const isSingle = filtered.length === 1;

  grid.innerHTML = filtered.map((item, index) => {
    const label = escapeHTML(item.displayName || item.name);
    const category = escapeHTML(item.category || "");
    const description = escapeHTML(item.description || "");

    const priceText = item.hot
      ? `<span class="price-line">12 oz · ${money(item.prices["12 oz"])}</span><span class="price-line">16 oz · ${money(item.prices["16 oz"])}</span>`
      : `<span class="price-line">16 oz · ${money(item.coldPrice)}</span>`;

    return `<article class="product reveal" style="--delay:${Math.min(index % 4, 3)*100}ms">
      <div class="category-label">${category}</div>
      <div class="product-top"><h3>${label}</h3></div>
      <div class="price">${priceText}</div>
      <p>${description}</p>
      <button class="add-btn" onclick="addToCart('${String(item.id)}')">+ Agregar al carrito</button>
    </article>`;
  }).join("");

  observeRevealElements();
}


function renderFilters() {
  const filters = document.getElementById("menuFilters");
  if (!filters) return;

  const activeCategories = menuCategories
    .filter(category => category.active)
    .sort((a,b) => Number(a.sort_order || 0) - Number(b.sort_order || 0));

  if (!activeCategories.length) {
    filters.innerHTML = "";
    return;
  }

  if (!activeCategories.some(category => category.name === currentFilter)) {
    currentFilter = activeCategories.some(category => category.name === "Fríos")
      ? "Fríos"
      : activeCategories[0].name;
  }

  filters.innerHTML = activeCategories.map(category => `
    <button class="filter ${category.name === currentFilter ? "active" : ""}"
      data-filter="${escapeHTML(category.name)}">${escapeHTML(category.name)}</button>
  `).join("");

  filters.querySelectorAll(".filter").forEach(button => {
    button.addEventListener("click",() => {
      currentFilter = button.dataset.filter;
      renderFilters();
      renderMenu();
    });
  });
}

function addToCart(id) {
  const product = menuData.find(p => String(p.id) === String(id));
  if (!product) return;

  const size = product.hot ? "12 oz" : "16 oz";

  cart.push({
    cartId: String(Date.now()) + Math.random().toString(36).slice(2,7),
    id:product.id,
    name:product.name,
    size,
    quantity:1,
    price:getPrice(product,size),
    milk:product.milk ? "Entera" : "Sin leche",
    sugar:product.sugar ? "Sin azúcar" : "No aplica",
    extras:[],
    note:"",
    customerName: ""
  });

  renderCart();
}

function itemPrice(item) {
  const milk = milkOptions.find(option => option.value === item.milk);
  return Number(item.price || 0)
    + Number(milk?.extra || 0)
    + item.extras.reduce((sum,key) => {
      return sum + Number(extraOptions.find(option => option.value === key)?.price || 0);
    },0);
}

function changeQuantity(id,change) {
  const item = cart.find(i => i.cartId === id);
  if (!item) return;
  item.quantity = Math.max(1,Number(item.quantity || 1) + change);
  renderCart();
}

function renderCart() {
  const container = document.getElementById("cartItems");
  const count = getDrinkCount();

  document.getElementById("cartCount").textContent = count;
  document.getElementById("mobileCartCount").textContent = count;
  document.getElementById("mobileCartTotal").textContent = "$" + getFinalTotal().toFixed(2);
  document.getElementById("mobileCartLabel").textContent = count > 0 ? "Revisar pedido" : "Ver carrito";

  if (!count) {
    container.innerHTML = '<p class="empty">Tu carrito está vacío. Agrega algo rico del menú.</p>';
    renderDiscountTotals();
    return;
  }

  container.innerHTML = cart.map(item => {
    const product = menuData.find(p => String(p.id) === String(item.id));
    if (!product) return "";

    const hasMilk = Boolean(product.milk);
    const sizeOptions = product.hot ? ["12 oz","16 oz"] : ["16 oz"];

    return `<div class="cart-item">
      <div class="cart-item-head">
        <span>${escapeHTML(item.name)} · ${escapeHTML(item.size)}</span>
        <span>${money(itemPrice(item) * (item.quantity || 1))}</span>
      </div>

      <div class="cart-quantity">
        <button type="button" onclick="changeQuantity('${item.cartId}',-1)" aria-label="Restar una bebida">−</button>
        <span class="quantity-number">${item.quantity || 1}</span>
        <button type="button" onclick="changeQuantity('${item.cartId}',1)" aria-label="Agregar una bebida">+</button>
        <span class="quantity-label">bebida(s)</span>
      </div>

      <div class="cart-options">
        <div class="customer-drink-field">
          <label for="customer-${item.cartId}">
            <span class="customer-drink-label">¿Para quién es esta bebida?</span>
            <span class="customer-drink-optional">Opcional</span>
          </label>
          <input
            type="text"
            id="customer-${item.cartId}"
            maxlength="40"
            placeholder="Ej. Ana, Carlos..."
            value="${escapeHTML(item.customerName || "")}"
                oninput="updateCustomerName('${item.cartId}', this.value)" 
                >
          <p>Identifica cada bebida si tu pedido es para varias personas.</p>
        </div>

        <div>
          <label for="size-${item.cartId}">Tamaño</label>
          <select id="size-${item.cartId}" onchange="updateSize('${item.cartId}',this.value)">
            ${sizeOptions.map(size => `<option value="${size}" ${item.size === size ? "selected" : ""}>${size} · ${money(getPrice(product,size))}</option>`).join("")}
          </select>
        </div>

        ${hasMilk ? `<div>
          <label for="milk-${item.cartId}">Tipo de leche</label>
          <select id="milk-${item.cartId}" onchange="updateMilk('${item.cartId}',this.value)">
            ${milkOptions.map(option => `<option value="${option.value}" ${item.milk === option.value ? "selected" : ""}>${option.label}</option>`).join("")}
          </select>
        </div>` : ""}

        ${product.sugar ? `<div>
          <label for="sugar-${item.cartId}">Azúcar</label>
          <select id="sugar-${item.cartId}" onchange="updateSugar('${item.cartId}',this.value)">
            <option value="Sin azúcar" ${item.sugar === "Sin azúcar" ? "selected" : ""}>Sin azúcar</option>
            <option value="Azúcar blanca" ${item.sugar === "Azúcar blanca" ? "selected" : ""}>Azúcar blanca</option>
            <option value="Stevia" ${item.sugar === "Stevia" ? "selected" : ""}>Stevia</option>
          </select>
        </div>` : ""}

        <div>
          <label>Extras (cada uno +$15)</label>
          ${extraOptions.map(option => `<label style="font-weight:500;display:flex;align-items:center;gap:8px;margin:7px 0">
            <input type="checkbox" ${item.extras.includes(option.value) ? "checked" : ""}
              onchange="toggleExtra('${item.cartId}','${option.value}',this.checked)" style="width:auto">
            ${option.label}
          </label>`).join("")}
        </div>

        <div>
          <label for="note-${item.cartId}">Notas de esta bebida</label>
          <textarea id="note-${item.cartId}" placeholder="Ej. sin hielo, poco dulce..."
            onchange="updateNote('${item.cartId}',this.value)">${escapeHTML(item.note)}</textarea>
        </div>
      </div>

      <button type="button" class="remove-btn" onclick="removeFromCart('${item.cartId}')">Eliminar producto</button>
    </div>`;
  }).join("");

  renderDiscountTotals();
}

function updateCustomerName(id, value) {
const item = cart.find(i => String(i.cartId) === String(id));

if (item) {
item.customerName = value;
}
}
function updateSize(id,size) {
  const item = cart.find(i => i.cartId === id);
  const product = item && menuData.find(p => String(p.id) === String(item.id));
  if (!item || !product) return;
  item.size = size;
  item.price = getPrice(product,size);
  renderCart();
}

function updateMilk(id,value) {
  const item = cart.find(i => i.cartId === id);
  if (item) { item.milk = value; renderCart(); }
}

function updateSugar(id,value) {
  const item = cart.find(i => i.cartId === id);
  if (item) { item.sugar = value; renderCart(); }
}

function toggleExtra(id,key,checked) {
  const item = cart.find(i => i.cartId === id);
  if (!item) return;
  item.extras = checked
    ? [...new Set([...item.extras,key])]
    : item.extras.filter(value => value !== key);
  renderCart();
}

function updateNote(id,value) {
  const item = cart.find(i => i.cartId === id);
  if (item) item.note = value;
}

function removeFromCart(id) {
  cart = cart.filter(item => item.cartId !== id);
  renderCart();
}

function escapeHTML(value) {
  return String(value).replace(/[&<>"']/g,char => ({
    "&":"&amp;",
    "<":"&lt;",
    ">":"&gt;",
    '"':"&quot;",
    "'":"&#039;"
  }[char]));
}

function goToCart() {
  document.getElementById("pedido").scrollIntoView({behavior:"smooth"});
}

document.getElementById("orderForm").addEventListener("submit",function(event) {
  event.preventDefault();

  if (!cart.length) {
    alert("Agrega al menos una bebida a tu carrito antes de enviar el pedido.");
    return;
  }

  const name = document.getElementById("customerName").value.trim();
  const phone = document.getElementById("customerPhone").value.trim();
  const address = document.getElementById("deliveryAddress").value.trim();
  const references = document.getElementById("references").value.trim();
  const generalNotes = document.getElementById("generalNotes").value.trim();
  const zone = document.getElementById("deliveryZone").value;

  if (!name || !phone || !address || !zone) {
    alert("Completa tu nombre, teléfono, zona y dirección de entrega.");
    return;
  }

  const subtotal = getSubtotal();
  const discount = getDiscount();
  const total = getFinalTotal();
  const totalDrinks = getDrinkCount();

  let message =
    "☕ *VRUTO CAFÉ* ☕\n" +
    "_café sin filtro._\n" +
    "━━━━━━━━━━━━━━━━━━\n" +
    "🧾 *NUEVO PEDIDO*\n" +
    "━━━━━━━━━━━━━━━━━━\n\n";

  message +=
    "👤 *DATOS DEL CLIENTE*\n" +
    "• Nombre: " + name + "\n" +
    "• Teléfono: " + phone + "\n\n" +
    "📍 *DIRECCIÓN DE ENTREGA*\n" +
    "• Zona: " + zone + "\n" +
    "• Dirección: " + address + "\n";

  if (references) message += "• Referencias: " + references + "\n";

  message +=
    "\n━━━━━━━━━━━━━━━━━━\n" +
    "🛍️ *DETALLE DEL PEDIDO*\n" +
    "━━━━━━━━━━━━━━━━━━\n";

  cart.forEach((item,index) => {
    const product = menuData.find(p => String(p.id) === String(item.id));
    const quantity = item.quantity || 1;

    
if (item.customerName && item.customerName.trim()) {
  message += "\n👤 *" + item.customerName.trim() + "*\n";
}

message +=
  "*BEBIDA " + (index + 1) + " · " + item.name + "*\n" +
  "• Tamaño: " + item.size + "\n" +
  "• Cantidad: " + quantity + "\n";


    if (product && product.milk) message += "• Leche: " + item.milk + "\n";
    if (product && product.sugar) message += "• Azúcar: " + item.sugar + "\n";

    if (item.extras.length) {
      message += "• Extras: " + item.extras.map(key => {
        const extra = extraOptions.find(option => option.value === key);
        return extra ? extra.label : key;
      }).join(", ") + "\n";
    }

    if (item.note.trim()) message += "• Indicaciones: " + item.note.trim() + "\n";

    
const precioBebida = itemPrice(item) * quantity;

message +=
  "• Precio por bebida: " + money(itemPrice(item)) + "\n";

if (appliedPromo && discount > 0 && subtotal > 0) {
  const descuentoBebida = precioBebida * (discount / subtotal);
  const importeConDescuento = precioBebida - descuentoBebida;

  message +=
    "• Importe original: " + money(precioBebida) + "\n" +
    "• *Importe con descuento: " + money(importeConDescuento) + "*\n";
} else {
  message +=
    "• *Importe: " + money(precioBebida) + "*\n";
}
}); // Cierra cart.forEach

  message +=
    "\n━━━━━━━━━━━━━━━━━━\n" +
    "💰 *RESUMEN DE COMPRA*\n" +
    "━━━━━━━━━━━━━━━━━━\n" +
    "• Total de bebidas: " + totalDrinks + "\n" +
    "• Zona de entrega: " + zone + "\n" +
    "• Subtotal: " + money(subtotal) + "\n";

  if (appliedPromo && discount > 0) {
    message +=
      "• Código promocional: " + appliedPromo.code + "\n" +
      "• Descuento (" + appliedPromo.percentage + "%): -" + money(discount) + "\n";
  }

  
message +=
  "• Envío: Por confirmar\n" +
  "• *TOTAL DE BEBIDAS: " + money(total) + "*\n" +
  "• Total final con envío: Por confirmar\n\n" +
  "💳 *MÉTODO DE PAGO*\n" +
  "Transferencia bancaria\n\n" +
  "━━━━━━━━━━━━━━━━━━\n" +
  "🏦 *VRUTO CAFÉ · DATOS DE PAGO*\n" +
  "━━━━━━━━━━━━━━━━━━\n" +
  "• Banco: BanCoppel\n" +
  "• Titular: Daniel Camacho\n" +
  "• Tarjeta: 4169 1608 5448 6710\n\n" +
  "_Envía tu comprobante por este medio para confirmar tu pedido._\n";

  if (generalNotes) message += "\n📝 *NOTAS ADICIONALES*\n" + generalNotes + "\n";

  message +=
    "\n━━━━━━━━━━━━━━━━━━\n" +
    "¡Gracias por elegir *VRUTO CAFÉ*! ☕\n\n" +
    "Hola, quiero confirmar este pedido.";

  const url = "https://wa.me/" + WHATSAPP_NUMBER + "?text=" + encodeURIComponent(message);
  const whatsappWindow = window.open(url,"_blank");

  if (!whatsappWindow) window.location.href = url;
});

document.getElementById("year").textContent = new Date().getFullYear();

function observeRevealElements() {
  const elements = document.querySelectorAll(".reveal:not(.visible)");

  if (!("IntersectionObserver" in window)) {
    elements.forEach(element => element.classList.add("visible"));
    return;
  }

  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add("visible");
        observer.unobserve(entry.target);
      }
    });
  },{threshold:.12});

  elements.forEach(element => observer.observe(element));
}

const revealElements = document.querySelectorAll(
  ".seasonal-image, .seasonal-content, #menu .section-heading, " +
  "#menu .filters, #pedido .section-heading, #pedido .panel, " +
  ".vruto-instagram, .about > *"
);

revealElements.forEach(element => element.classList.add("reveal"));

async function loadMenuFromSupabase() {
  try {
    const headers = {
      apikey: SUPABASE_PUBLIC_KEY,
      Authorization: `Bearer ${SUPABASE_PUBLIC_KEY}`
    };

    const [productsResponse,categoriesResponse] = await Promise.all([
      fetch(
        `${SUPABASE_URL}/rest/v1/products?select=id,name,category_id,description,product_type,cold_price,hot_price_12,hot_price_16,available,sort_order,is_special&available=eq.true&order=sort_order.asc`,
        {headers,cache:"no-store"}
      ),
      fetch(
        `${SUPABASE_URL}/rest/v1/categories?select=id,name,sort_order,active&active=eq.true&order=sort_order.asc`,
        {headers,cache:"no-store"}
      )
    ]);

    if (!productsResponse.ok) throw new Error(`Error al cargar productos: ${productsResponse.status}`);
    if (!categoriesResponse.ok) throw new Error(`Error al cargar categorías: ${categoriesResponse.status}`);

    const products = await productsResponse.json();
    menuCategories = await categoriesResponse.json();

    if (!Array.isArray(products) || products.length === 0) {
      console.warn("No hay productos disponibles en Supabase; se conserva el menú de respaldo.");
      renderFilters();
      renderMenu();
      return;
    }

    menuData = products.map(product => {
      const isHot = String(product.product_type || "").toLowerCase() === "hot";
      const categoryInfo = menuCategories.find(category =>
        String(category.id) === String(product.category_id)
      );
      const productName = String(product.name || "");
      const isAmericano = productName.toLowerCase().includes("americano");
      const isLatteRegular = productName.toLowerCase().includes("latte regular");

      return {
        id:product.id,
        name:productName,
        displayName:!isHot && isLatteRegular ? "Latte Reg." : productName,
        category:categoryInfo ? categoryInfo.name : (isHot ? "Calientes" : "Fríos"),
        description:product.description || "",
        hot:isHot,
        milk:!isAmericano,
        sugar:isAmericano || isLatteRegular,
        prices:isHot ? {
          "12 oz":Number(product.hot_price_12 || 0),
          "16 oz":Number(product.hot_price_16 || 0)
        } : {},
        coldPrice:isHot ? null : Number(product.cold_price || 0),
        isSpecial:product.is_special === true
      };
    });

    renderFilters();
    renderMenu();
    renderCart();

    console.log(`VRUTO Café: ${menuData.length} productos cargados desde Supabase.`);
  } catch (error) {
    console.error("No se pudo cargar el menú desde Supabase:",error);
    renderFilters();
    renderMenu();
  }
}

async function loadSeasonalFromSupabase() {
  try {
    const response = await fetch(
      `${SUPABASE_URL}/rest/v1/site_settings?select=value&key=eq.seasonal`,
      {
        headers:{
          apikey:SUPABASE_PUBLIC_KEY,
          Authorization:`Bearer ${SUPABASE_PUBLIC_KEY}`
        },
        cache:"no-store"
      }
    );

    if (!response.ok) throw new Error(`Error ${response.status} al cargar temporada`);

    const rows = await response.json();
    if (!Array.isArray(rows) || !rows.length) return;

    const season = rows[0].value;
    if (!season || typeof season !== "object") return;

    const section = document.getElementById("seasonalSection");
    if (!section) return;

    section.hidden = season.active === false;

    const image = document.getElementById("seasonalImage");
    const safeImageUrl = typeof season.image_url === "string" ? season.image_url.trim() : "";

    if (safeImageUrl) image.src = safeImageUrl;
    image.alt = season.title || "Bebida de temporada VRUTO Café";

    document.getElementById("seasonalLabel").textContent = season.label || "";
    document.getElementById("seasonalTitle").textContent = season.title || "";
    document.getElementById("seasonalDescription").textContent = season.description || "";

    const pricesContainer = document.getElementById("seasonalPrices");
    pricesContainer.replaceChildren();

    if (Array.isArray(season.prices)) {
      season.prices.forEach(price => {
        const span = document.createElement("span");
        span.textContent = String(price);
        pricesContainer.appendChild(span);
      });
    }

    const button = document.getElementById("seasonalButton");
    button.textContent = season.button_text || "DESCUBRIR EN EL MENÚ →";
    button.href = season.button_url || "#menu";
  } catch (error) {
    console.error("No se pudo cargar la temporada:",error);
  }
}
async function loadMenuBannerFromSupabase() {
  try {
    const headers = {
      apikey: SUPABASE_PUBLIC_KEY,
      Authorization: `Bearer ${SUPABASE_PUBLIC_KEY}`
    };

    const response = await fetch(
      `${SUPABASE_URL}/rest/v1/site_settings?select=key,value&key=eq.menu_banner`,
      { headers, cache: "no-store" }
    );

    if (!response.ok) {
      throw new Error(`Error al cargar el banner: ${response.status}`);
    }

    const rows = await response.json();
    if (!rows.length || !rows[0].value) return;

    const banner = rows[0].value;

    // No aplicar los valores de ejemplo de la configuración inicial.
    if (
      banner.title === "Café sin filtro" &&
      banner.description === "Tu café favorito, directo hasta ti." &&
      !(banner.image_url || banner.image)
    ) {
      return;
    }

    const hero = document.querySelector(".hero");
    if (!hero) return;

    if (banner.active === false) {
      hero.hidden = true;
      return;
    }

    hero.hidden = false;

    const title = document.getElementById("menuBannerTitle");
    const description = document.getElementById("menuBannerDescription");
    const button = document.getElementById("menuBannerButton");

    if (title && banner.title) title.textContent = banner.title;
    if (description && banner.description) {
      description.textContent = banner.description;
    }

    if (button && banner.button_text) {
      button.textContent = banner.button_text;
      button.href = banner.button_url || banner.button_link || "#menu";
    }

    const imageUrl = banner.image_url || banner.image;

    if (imageUrl) {
      const validUrl = /^https?:\/\//i.test(imageUrl);

      if (validUrl) {
        hero.style.backgroundImage =
          `linear-gradient(rgba(30,32,24,.35),rgba(30,32,24,.35)),url("${imageUrl}")`;
      }
    }
  } catch (error) {
    console.error("No se pudo cargar el banner de VRUTO:", error);
  }
}
  
loadMenuBannerFromSupabase();
renderFilters();
renderMenu();
renderCart();
observeRevealElements();
loadMenuFromSupabase();
loadSeasonalFromSupabase();
</script>

<script async src="https://www.instagram.com/embed.js"></script>

</body>
</html>
