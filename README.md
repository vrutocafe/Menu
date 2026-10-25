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
  html { scroll-behavior: smooth; }
  body { margin: 0; font-family: 'Quicksand', Arial, sans-serif; background: var(--cream); color: var(--dark); }
  button, input, select, textarea { font: inherit; }
  button { cursor: pointer; }
  a { color: inherit; text-decoration: none; }

  /* ENCABEZADO PREMIUM VRUTO */
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
    align-items: center;
  }

  .brand-logo img {
    display: block;
    width: 125px;
    max-height: 65px;
    object-fit: contain;
  }

  .nav-menu {
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 2px;
  }

  .header-cart {
    background: var(--olive);
    color: white;
    border: none;
    border-radius: 30px;
    padding: 11px 16px;
    font-weight: 700;
  }

  .hero { padding: 65px 7% 60px; background: var(--butter); text-align: center; }
  .eyebrow { text-transform: uppercase; letter-spacing: 3px; font-size: 12px; font-weight: 700; }
  .hero h1 { font-size: clamp(42px, 8vw, 76px); line-height: 1; margin: 18px 0; letter-spacing: -2px; }
  .hero p { font-size: 17px; margin: 0 auto 24px; }
  .primary-btn { display: inline-block; border: 0; background: var(--olive); color: white; padding: 14px 23px; border-radius: 30px; font-weight: 700; }
  
  section { padding: 48px 6%; }
  .section-heading { text-align: center; margin-bottom: 28px; }
  .section-heading h2 { font-size: 32px; margin: 0 0 8px; }
  .section-heading p { color: var(--muted); margin: 0; }
  
  .filters { display: flex; justify-content: center; flex-wrap: wrap; gap: 9px; margin: 25px 0; }
  .filter { padding: 9px 16px; border: 1px solid var(--border); border-radius: 30px; background: var(--white); color: var(--dark); }
  .filter.active { background: var(--olive); color: white; border-color: var(--olive); }
  
  .menu-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 17px; max-width: 1100px; margin: auto; }
  .product { background: var(--white); border: 1px solid var(--border); border-radius: 18px; padding: 18px; display: flex; flex-direction: column; min-height: 210px; min-width: 0; overflow: hidden; }
  .product-top { display: flex; justify-content: space-between; gap: 10px; }
  .product h3 { margin: 0 0 8px; overflow-wrap: anywhere; line-height: 1.25; font-size: 19px; }
  .product p { color: var(--muted); font-size: 13px; line-height: 1.5; margin: 0 0 15px; }
  .price { color: var(--olive); font-weight: 700; white-space: normal; font-size: 14px; line-height: 1.65; display: flex; flex-direction: column; gap: 2px; margin: 5px 0 8px; }
  .price-line { display: block; font-size: 13px; line-height: 1.45; }
  .category-label { font-size: 10px; text-transform: uppercase; letter-spacing: 1px; color: var(--olive); font-weight: 700; margin-bottom: 12px; }
  .add-btn { margin-top: auto; width: 100%; padding: 11px; background: var(--olive); color: white; border: 0; border-radius: 10px; font-weight: 700; }
  .add-btn:hover, .primary-btn:hover { opacity: .9; }
  
  #pedido { background: #eeeadc; }
  .order-layout { max-width: 1000px; margin: auto; display: grid; grid-template-columns: 1fr 1fr; gap: 22px; align-items: start; }
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
  .field input, .field select, .field textarea, .cart-options select, .cart-options textarea { width: 100%; border: 1px solid var(--border); border-radius: 9px; background: white; padding: 11px; color: var(--dark); }
  .field textarea, .cart-options textarea { resize: vertical; min-height: 65px; }
  
  .total-row { display: flex; justify-content: space-between; font-weight: 700; font-size: 19px; padding-top: 17px; border-top: 1px solid var(--border); margin-top: 12px; }
  .notice { background: #f7f0d8; padding: 12px; border-radius: 10px; font-size: 13px; line-height: 1.5; margin: 14px 0; }
  .whatsapp-btn { width: 100%; border: 0; border-radius: 12px; padding: 15px; background: var(--olive); color: white; font-weight: 700; font-size: 15px; }
  .whatsapp-btn:disabled { opacity: .45; cursor: not-allowed; }
  
  .about { text-align: center; background: var(--cream); padding-top: 42px; padding-bottom: 42px; }
  .about p { max-width: 560px; margin: 12px auto; line-height: 1.7; }
  footer { background: var(--dark); color: white; text-align: center; padding: 25px 15px; font-size: 13px; }
  
  .mobile-cart { display: none; position: fixed; z-index: 20; bottom: 14px; left: 14px; right: 14px; padding: 14px; background: var(--olive); color: white; border: 0; border-radius: 14px; box-shadow: 0 4px 18px #0002; font-weight: 700; }

  @media(max-width: 700px) {
    .brand-logo img { width: 100px; max-height: 50px; }
    .site-header { padding: 12px 4%; gap: 10px; }
    .header-cart { padding: 10px 12px; font-size: 12px; }
    .hero { padding: 55px 6%; }
    section { padding: 38px 5%; }
    .order-layout { grid-template-columns: 1fr; }
    .menu-grid { grid-template-columns: 1fr 1fr; gap: 10px; }
    .product { padding: 14px; min-height: 215px; }
    .product h3 { font-size: 16px; }
    .product-top { flex-direction: column; gap: 5px; }
    .price { font-size: 15px; }
    .mobile-cart { display: block; }
    footer { padding-bottom: 85px; }
  }
  @media(max-width: 370px) { .menu-grid { grid-template-columns: 1fr; } }
  .hero {
  background-image:
    linear-gradient(rgba(30, 32, 24, 0.35), rgba(30, 32, 24, 0.35)),
    url("portada.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  color: #fffdf7;
  border-radius: 18px;
}

.hero h1,
.hero p,
.hero .eyebrow {
  color: #fffdf7;
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
  transition: transform 0.5s;
}

.seasonal-image:hover img {
  transform: scale(1.04);
}

.seasonal-content {
  max-width: 470px;
}

.seasonal-label {
  color: #69734b;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 2px;
}

.seasonal-content h2 {
  font-size: clamp(35px, 5vw, 58px);
  line-height: 1;
  margin: 18px 0;
}

.seasonal-content p {
  font-size: 15px;
  line-height: 1.9;
  color: #666653;
}

.seasonal-prices {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin: 24px 0;
}

.seasonal-prices span {
  padding: 10px 13px;
  background: #f7f3e8;
  border-radius: 30px;
  font-size: 12px;
  font-weight: 700;
}

.seasonal-button {
  display: inline-block;
  background: #69734b;
  color: white;
  padding: 14px 20px;
  border-radius: 30px;
  font-size: 12px;
  font-weight: 700;
}

@media (max-width: 650px) {
  .seasonal {
    grid-template-columns: 1fr;
    gap: 25px;
    padding: 40px 6%;
  }

  .seasonal-image {
    height: 290px;
  }
}
</style>
</head>
<body>
<header class="site-header">
  <a class="brand-logo" href="#inicio">
    <img src="imagenes/logo.png" alt="VRUTO CAFÉ">
  </a>
  <button class="header-cart" onclick="goToCart()">
    🛒 Carrito (<span id="cartCount">0</span>)
  </button>
</header>
<main>
  <section class="hero" id="inicio">
    <div class="eyebrow">Coffee · Matcha · Chill</div>
    <h1>café sin<br>filtro.</h1>
    <p>Tu próximo café favorito, hasta tu puerta.</p>
    <a class="primary-btn" href="#menu">Explorar menú ↓</a>
  </section>
  <section class="seasonal">
  <div class="seasonal-image">
    <img
      src="imagenes/pumpkin.jpg"
      alt="Pumpkin Spice Latte de VRUTO Café"
      loading="lazy"
    >
  </div>  <div class="seasonal-content">
    <span class="seasonal-label">EDICIÓN DE TEMPORADA</span><h2>Pumpkin Spice.</h2>

<p>
  Espresso, leche y especias de calabaza.
  Tu bebida favorita de otoño, a tu manera.
</p>

<div class="seasonal-prices">
  <span>Caliente desde $70</span>
  <span>Frío $85</span>
</div>

<a href="#menu" class="seasonal-button">
  DESCUBRIR EN EL MENÚ →
</a>

  </div>
</section>
  <section id="menu">
    <div class="section-heading"><h2></h2><p>Elige tus favoritos y arma tu pedido.</p></div>
    <div class="filters">
      
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
        <p class="empty" style="margin-top: 10px;">El costo de envío se confirma por WhatsApp.</p>
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
    <div class="eyebrow">VRUTO</div>
    <h2>Un buen café cambia el día.</h2>
    <p>Preparamos tus bebidas favoritas con mucho café y cero complicaciones. Pide en línea y disfruta VRUTO donde estés.</p>
    <p><strong>Servicio a domicilio · Mazatlán, Sinaloa</strong></p>
  </section>
</main>
<footer><strong>VRUTO</strong><br>café sin filtro. · Mazatlán, Sinaloa<br>© <span id="year"></span> VRUTO</footer>
<button class="mobile-cart" onclick="goToCart()">Ver carrito · <span id="mobileCartCount">0</span> artículos</button>

<script>
const WHATSAPP_NUMBER = "526693683462";

const menuData = [
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
  {id:19,name:"Pumpkin Spice Caliente",displayName:"Pumpkin Spice Caliente",category:"Especiales",description:"Espresso, leche y especias de calabaza.",hot:true,milk:true,prices:{"12 oz":70,"16 oz":80}},
  {id:20,name:"Pumpkin Spice Frío",displayName:"Pumpkin Spice Frío",category:"Especiales",description:"Pumpkin Spice Latte helado con notas de calabaza y especias.",hot:false,milk:true,coldPrice:85}
];

const milkOptions = [
  {value:"Entera",label:"Leche entera"},
  {value:"Deslactosada",label:"Leche deslactosada"},
  {value:"Almendra",label:"Leche de almendra (+$15)",extra:15},
  {value:"Sin leche",label:"Sin leche"}
];

const extraOptions = [
  {value:"shot",label:"Shot extra (+$15)",price:15},
  {value:"syrup",label:"Jarabe extra (+$15)",price:15}
];

let cart = [], currentFilter = "Todos";
const money = amount => "$" + amount.toFixed(2) + " MXN";

function getPrice(product, size) {
  return product.hot ? product.prices[size] : product.coldPrice;
}

function renderMenu() {
 const grid = document.getElementById("menuGrid");
 const filtered = currentFilter === "Todos"
  ? menuData
  : currentFilter === "Calientes"
    ? menuData.filter(item => item.hot === true)
    : currentFilter === "Fríos"
      ? menuData.filter(item => item.hot === false)
      : menuData.filter(item => item.category === "Especiales");

 grid.innerHTML = filtered.map(item => {
   const label = item.displayName || item.name;
   const priceText = item.hot
     ? `<span class="price-line">12 oz · ${money(item.prices["12 oz"])}</span><span class="price-line">16 oz · ${money(item.prices["16 oz"])}</span>`
     : `<span class="price-line">16 oz · ${money(item.coldPrice)}</span>`;

   return `<article class="product">
     <div class="category-label">${item.category}</div>
     <div class="product-top"><h3>${label}</h3></div>
     <div class="price">${priceText}</div>
     <p>${item.description}</p>
     <button class="add-btn" onclick="addToCart(${item.id})">+ Agregar al carrito</button>
   </article>`;
 }).join("");
}

document.querySelectorAll(".filter").forEach(button => button.addEventListener("click", () => {
 document.querySelectorAll(".filter").forEach(b => b.classList.remove("active"));
 button.classList.add("active");
 currentFilter = button.dataset.filter;
 renderMenu();
}));

function addToCart(id) {
 const product = menuData.find(p => p.id === id);
 if(!product) return;
 const size = product.hot ? "12 oz" : "16 oz";
 cart.push({
   cartId: String(Date.now()) + Math.random().toString(36).slice(2,7),
   id: product.id, name: product.name, size,
   price: getPrice(product, size),
   milk: product.milk ? "Entera" : "Sin leche",
   sugar: product.sugar ? "Sin azúcar" : "No aplica",
   extras: [], note: ""
 });
 renderCart();
 document.getElementById("pedido").scrollIntoView({behavior: "smooth"});
}

function itemPrice(item) {
 const milk = milkOptions.find(o => o.value === item.milk);
 return item.price + (milk?.extra || 0) + item.extras.reduce((sum, key) => sum + (extraOptions.find(o => o.value === key)?.price || 0), 0);
}

function renderCart() {
 const container = document.getElementById("cartItems");
 const count = cart.length;
 document.getElementById("cartCount").textContent = count;
 document.getElementById("mobileCartCount").textContent = count;

 if(!count) {
   container.innerHTML = '<p class="empty">Tu carrito está vacío. Agrega algo rico del menú.</p>';
   document.getElementById("subtotal").textContent = money(0);
   return;
 }

 container.innerHTML = cart.map(item => {
  const product = menuData.find(p => p.id === item.id);
  const hasMilk = product && product.milk;
  const sizeOptions = product.hot ? ["12 oz", "16 oz"] : ["16 oz"];

  return `<div class="cart-item">
    <div class="cart-item-head">
      <span>${escapeHTML(item.name)} · ${item.size}</span>
      <span>${money(itemPrice(item))}</span>
    </div>
    <div class="cart-options">
      <div>
        <label for="size-${item.cartId}">Tamaño</label>
        <select id="size-${item.cartId}" onchange="updateSize('${item.cartId}',this.value)">
          ${sizeOptions.map(s => `<option value="${s}" ${item.size === s ? "selected" : ""}>${s} · ${money(getPrice(product, s))}</option>`).join("")}
        </select>
      </div>
      ${hasMilk ? `<div>
        <label for="milk-${item.cartId}">Tipo de leche</label>
        <select id="milk-${item.cartId}" onchange="updateMilk('${item.cartId}',this.value)">
          ${milkOptions.map(o => `<option value="${o.value}" ${item.milk === o.value ? "selected" : ""}>${o.label}</option>`).join("")}
        </select>
      </div>` : ""}
      ${product.sugar ? `<div>
        <label for="sugar-${item.cartId}">Azúcar</label>
        <select id="sugar-${item.cartId}" onchange="updateSugar('${item.cartId}',this.value)">
          <option ${item.sugar === "Sin azúcar" ? "selected" : ""}>Sin azúcar</option>
          <option ${item.sugar === "Azúcar blanca" ? "selected" : ""}>Azúcar blanca</option>
          <option ${item.sugar === "Stevia" ? "selected" : ""}>Stevia</option>
        </select>
      </div>` : ""}
      <div>
        <label>Extras (cada uno +$15)</label>
        ${extraOptions.map(o => `<label style="font-weight:500;display:flex;align-items:center;gap:8px;margin:7px 0">
          <input type="checkbox" ${item.extras.includes(o.value) ? "checked" : ""} onchange="toggleExtra('${item.cartId}','${o.value}',this.checked)" style="width:auto">
          ${o.label}
        </label>`).join("")}
      </div>
      <div>
        <label for="note-${item.cartId}">Notas de esta bebida</label>
        <textarea id="note-${item.cartId}" placeholder="Ej. sin hielo, poco dulce..." onchange="updateNote('${item.cartId}',this.value)">${escapeHTML(item.note)}</textarea>
      </div>
    </div>
    <button class="remove-btn" onclick="removeFromCart('${item.cartId}')">Eliminar producto</button>
  </div>`;
 }).join("");

 document.getElementById("subtotal").textContent = money(cart.reduce((sum, item) => sum + itemPrice(item), 0));
}

function updateSize(id, size) {
 const item = cart.find(i => i.cartId === id);
 const p = item && menuData.find(p => p.id === item.id);
 if(!item || !p) return;
 item.size = size;
 item.price = getPrice(p, size);
 renderCart();
}

function updateMilk(id, value) {
 const item = cart.find(i => i.cartId === id);
 if(item) { item.milk = value; renderCart(); }
}

function updateSugar(id, value) {
 const item = cart.find(i => i.cartId === id);
 if(item) { item.sugar = value; renderCart(); }
}

function toggleExtra(id, key, checked) {
 const item = cart.find(i => i.cartId === id);
 if(!item) return;
 item.extras = checked ? [...new Set([...item.extras, key])] : item.extras.filter(x => x !== key);
 renderCart();
}

function updateNote(id, value) {
 const item = cart.find(i => i.cartId === id);
 if(item) item.note = value;
}

function removeFromCart(id) {
 cart = cart.filter(item => item.cartId !== id);
 renderCart();
}

function escapeHTML(value) {
 return String(value).replace(/[&<>"']/g, char => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#039;" }[char]));
}

function goToCart() {
 document.getElementById("pedido").scrollIntoView({behavior: "smooth"});
}

document.getElementById("orderForm").addEventListener("submit", function(event) {
 event.preventDefault();

 if(!cart.length) {
   alert("Agrega al menos una bebida a tu carrito antes de enviar el pedido.");
   return;
 }

 const name = document.getElementById("customerName").value.trim();
 const phone = document.getElementById("customerPhone").value.trim();
 const address = document.getElementById("deliveryAddress").value.trim();
 const references = document.getElementById("references").value.trim();
 const generalNotes = document.getElementById("generalNotes").value.trim();

 if(!name || !phone || !address) {
   alert("Completa tu nombre, teléfono y dirección de entrega.");
   return;
 }

 const total = cart.reduce((sum, item) => sum + itemPrice(item), 0);
 let message = "☕ *VRUTO CAFÉ* ☕\n_café sin filtro._\n━━━━━━━━━━━━━━━━━━\n🧾 *NUEVO PEDIDO*\n━━━━━━━━━━━━━━━━━━\n\n";

 message += "👤 *DATOS DEL CLIENTE*\n• Nombre: " + name + "\n• Teléfono: " + phone + "\n\n📍 *DATOS DE ENTREGA*\n• Dirección: " + address + "\n";

 if(references) message += "• Referencias: " + references + "\n";

 message += "\n━━━━━━━━━━━━━━━━━━\n🛍️ *DETALLE DEL PEDIDO*\n━━━━━━━━━━━━━━━━━━\n";

 cart.forEach((item, index) => {
  const product = menuData.find(p => p.id === item.id);
  message += "\n*Bebida " + (index + 1) + ": " + item.name + "*\n• Tamaño: " + item.size + "\n• Cantidad: 1\n";

  if(product && product.milk) {
    message += "• Leche: " + item.milk + (item.milk === "Almendra" ? " (+$15.00 MXN)" : "") + "\n";
  }

  if(product && product.sugar) message += "• Azúcar: " + item.sugar + "\n";

  if(item.extras.length) {
    message += "• Extras: " + item.extras.map(key => extraOptions.find(o => o.value === key).label).join(", ") + "\n";
  }

  if(item.note.trim()) message += "• Indicaciones: " + item.note.trim() + "\n";

  message += "• Precio: " + money(itemPrice(item)) + "\n";
 });

 message += "\n━━━━━━━━━━━━━━━━━━\n💰 *RESUMEN DE COMPRA*\n━━━━━━━━━━━━━━━━━━\n• Productos: " + cart.length + "\n• Subtotal: " + money(total) + "\n• Envío: Por confirmar\n• *TOTAL A PAGAR: " + money(total) + " + envío*\n\n💳 *MÉTODO DE PAGO*\nTransferencia bancaria\n_Los datos bancarios se compartirán por este medio._\n";

 if(generalNotes) message += "\n📝 *NOTAS ADICIONALES*\n" + generalNotes + "\n";

 message += "\n━━━━━━━━━━━━━━━━━━\n¡Gracias por elegir *VRUTO Café*! ☕\nHola, quiero confirmar este pedido. ¿Me comparten los datos para realizar la transferencia y confirmar el costo del envío?";

 const url = "https://wa.me/" + WHATSAPP_NUMBER + "?text=" + encodeURIComponent(message);
 window.open(url, "_blank");
});

document.getElementById("year").textContent = new Date().getFullYear();
renderMenu();
renderCart();
</script>
</body>
</html>
