<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#69734b">
<title>VRUTO Café | Café sin filtro</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{--olive:#69734b;--dark:#343a27;--butter:#f2d77a;--cream:#f7f3e8;--white:#fffdf7;--border:#e5e0d2;--muted:#777765}
*{box-sizing:border-box}html{scroll-behavior:smooth}body{margin:0;font-family:'Quicksand',Arial,sans-serif;background:var(--cream);color:var(--dark)}
button,input,select,textarea{font:inherit}button{cursor:pointer}a{color:inherit;text-decoration:none}
header{background:var(--cream);padding:18px 6%;display:flex;justify-content:space-between;align-items:center;gap:12px;border-bottom:1px solid var(--border);position:sticky;top:0;z-index:10}
.logo{font-size:27px;font-weight:700;letter-spacing:2px}.logo span{color:var(--olive)}
.header-cart{border:0;background:var(--olive);color:white;border-radius:30px;padding:11px 16px;font-weight:700}
.hero{padding:65px 7% 60px;background:var(--butter);text-align:center}.eyebrow{text-transform:uppercase;letter-spacing:3px;font-size:12px;font-weight:700}
.hero h1{font-size:clamp(42px,8vw,76px);line-height:1;margin:18px 0;letter-spacing:-2px}.hero p{font-size:17px;margin:0 auto 24px}
.primary-btn{display:inline-block;border:0;background:var(--olive);color:white;padding:14px 23px;border-radius:30px;font-weight:700}
section{padding:48px 6%}.section-heading{text-align:center;margin-bottom:28px}.section-heading h2{font-size:32px;margin:0 0 8px}.section-heading p{color:var(--muted);margin:0}
.filters{display:flex;justify-content:center;flex-wrap:wrap;gap:9px;margin:25px 0}.filter{padding:9px 16px;border:1px solid var(--border);border-radius:30px;background:var(--white);color:var(--dark)}
.filter.active{background:var(--olive);color:white;border-color:var(--olive)}
.menu-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:17px;max-width:1100px;margin:auto}
.product{background:var(--white);border:1px solid var(--border);border-radius:18px;padding:22px;display:flex;flex-direction:column;min-height:210px}
.product-top{display:flex;justify-content:space-between;gap:10px}.product h3{margin:0 0 8px;font-size:19px}.product p{color:var(--muted);font-size:13px;line-height:1.5;margin:0 0 15px}
.price{color:var(--olive);font-weight:700;white-space:nowrap}.category-label{font-size:10px;text-transform:uppercase;letter-spacing:1px;color:var(--olive);font-weight:700;margin-bottom:12px}
.add-btn{margin-top:auto;width:100%;padding:11px;background:var(--olive);color:white;border:0;border-radius:10px;font-weight:700}.add-btn:hover,.primary-btn:hover{opacity:.9}
#pedido{background:#eeeadc}.order-layout{max-width:1000px;margin:auto;display:grid;grid-template-columns:1fr 1fr;gap:22px;align-items:start}
.panel{background:var(--white);padding:23px;border-radius:18px;border:1px solid var(--border)}.panel h3{margin-top:0}.empty{color:var(--muted);font-size:14px}
.cart-item{border-bottom:1px solid var(--border);padding:15px 0}.cart-item:last-child{border-bottom:0}
.cart-item-head{display:flex;justify-content:space-between;gap:10px;font-weight:700}.cart-item small{color:var(--muted)}
.cart-options{margin-top:10px;display:grid;gap:9px}.cart-options label,.field label{display:block;font-size:12px;font-weight:700;margin-bottom:5px}
.qty-row{display:flex;align-items:center;gap:12px;margin-top:9px}.qty-btn{width:31px;height:31px;border:1px solid var(--border);background:var(--cream);border-radius:50%}
.remove-btn{border:0;background:transparent;color:#a14b3d;font-size:12px;padding:5px 0}
.field{margin-bottom:14px}.field input,.field select,.field textarea,.cart-options select,.cart-options textarea{width:100%;border:1px solid var(--border);border-radius:9px;background:white;padding:11px;color:var(--dark)}
.field textarea,.cart-options textarea{resize:vertical;min-height:65px}
.total-row{display:flex;justify-content:space-between;font-weight:700;font-size:19px;padding-top:17px;border-top:1px solid var(--border);margin-top:12px}
.notice{background:#f7f0d8;padding:12px;border-radius:10px;font-size:13px;line-height:1.5;margin:14px 0}
.whatsapp-btn{width:100%;border:0;border-radius:12px;padding:15px;background:var(--olive);color:white;font-weight:700;font-size:15px}.whatsapp-btn:disabled{opacity:.45;cursor:not-allowed}
.about{text-align:center;background:var(--cream);padding-top:42px;padding-bottom:42px}.about p{max-width:560px;margin:12px auto;line-height:1.7}
footer{background:var(--dark);color:white;text-align:center;padding:25px 15px;font-size:13px}
.mobile-cart{display:none;position:fixed;z-index:20;bottom:14px;left:14px;right:14px;padding:14px;background:var(--olive);color:white;border:0;border-radius:14px;box-shadow:0 4px 18px #0002;font-weight:700}
@media(max-width:700px){header{padding:14px 5%}.logo{font-size:23px}.hero{padding:55px 6%}section{padding:38px 5%}.order-layout{grid-template-columns:1fr}.menu-grid{grid-template-columns:1fr 1fr;gap:10px}.product{padding:14px;min-height:215px}.product h3{font-size:16px}.product-top{flex-direction:column;gap:5px}.price{font-size:15px}.mobile-cart{display:block}footer{padding-bottom:85px}}
@media(max-width:370px){.menu-grid{grid-template-columns:1fr}}
</style>
</head>
<body>
<header>
  <a class="logo" href="#inicio">VRUTO<span>®</span></a>
  <button class="header-cart" onclick="goToCart()">🛒 Carrito (<span id="cartCount">0</span>)</button>
</header>
<main>
  <section class="hero" id="inicio">
    <div class="eyebrow">Coffee · Matcha · Chill</div>
    <h1>café sin<br>filtro.</h1>
    <p>Tu próximo café favorito, hasta tu puerta.</p>
    <a class="primary-btn" href="#menu">Explorar menú ↓</a>
  </section>
  <section id="menu">
    <div class="section-heading"><h2>Menú</h2><p>Elige tus favoritos y arma tu pedido.</p></div>
    <div class="filters">
      <button class="filter active" data-filter="Todos">Todo</button>
      <button class="filter" data-filter="Calientes">Calientes</button>
      <button class="filter" data-filter="Fríos">Fríos</button>
      <button class="filter" data-filter="Especiales">Especiales</button>
    </div>
    <div class="menu-grid" id="menuGrid"></div>
  </section>
  <section id="pedido">
    <div class="section-heading"><h2>Tu pedido</h2><p>Revisa tu carrito y dinos dónde entregarlo.</p></div>
    <div class="order-layout">
      <div class="panel" id="cartPanel">
        <h3>🛒 Mi carrito</h3>
        <div id="cartItems"><p class="empty">Tu carrito está vacío. Agrega algo rico del menú.</p></div>
        <div class="total-row"><span>Subtotal</span><span id="subtotal">$0.00 MXN</span></div>
        <p class="empty">El costo de envío se confirma por WhatsApp.</p>
      </div>
      <div class="panel">
        <h3>📍 Datos de entrega</h3>
        <form id="orderForm">
          <div class="field"><label for="customerName">Nombre *</label><input id="customerName" name="customerName" required placeholder="¿A nombre de quién?"></div>
          <div class="field"><label for="customerPhone">Teléfono de contacto *</label><input id="customerPhone" name="customerPhone" type="tel" required placeholder="Tu número de teléfono"></div>
          <div class="field"><label for="deliveryAddress">Dirección completa *</label><textarea id="deliveryAddress" name="deliveryAddress" required placeholder="Calle, número, colonia y ciudad"></textarea></div>
          <div class="field"><label for="references">Referencias de entrega</label><input id="references" name="references" placeholder="Entre calles, color de portón, oficina, etc."></div>
          <div class="field"><label for="generalNotes">Notas adicionales</label><textarea id="generalNotes" name="generalNotes" placeholder="Indicaciones para tu pedido"></textarea></div>
          <div class="field"><label for="payment">Método de pago</label><select id="payment" disabled><option>Transferencia bancaria</option></select></div>
          <div class="notice"><strong>Pago por transferencia bancaria.</strong><br>Al enviar tu pedido por WhatsApp te compartiremos los datos para realizar el pago. Tu pedido se confirma con el negocio.</div>
          <button type="submit" class="whatsapp-btn" id="sendOrder">Enviar pedido por WhatsApp</button>
        </form>
      </div>
    </div>
  </section>
  <section class="about">
    <div class="eyebrow">VRUTO Café</div><h2>Un buen café cambia el día.</h2>
    <p>Preparamos tus bebidas favoritas con mucho café y cero complicaciones. Pide en línea y disfruta VRUTO donde estés.</p>
    <p><strong>Servicio a domicilio · Mazatlán, Sinaloa</strong></p>
  </section>
</main>
<footer><strong>VRUTO Café</strong><br>café sin filtro. · Mazatlán, Sinaloa<br>© <span id="year"></span> VRUTO Café</footer>
<button class="mobile-cart" onclick="goToCart()">Ver carrito · <span id="mobileCartCount">0</span> artículos</button>
