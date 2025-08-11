<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>OutfitShell — All Types of Outfits</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0f1724; --card:#0b1120; --muted:#94a3b8; --accent:#ff6b6b;
      --glass: rgba(255,255,255,0.03);
    }
    *{box-sizing:border-box}
    body{font-family:Inter,system-ui,Segoe UI,Arial;background:linear-gradient(180deg,#071029 0%,#071930 100%);color:#e6eef8;margin:0;min-height:100vh}
    .container{max-width:1100px;margin:32px auto;padding:20px}
    header{display:flex;align-items:center;justify-content:space-between;margin-bottom:18px}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:52px;height:52px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#ff9a6b);display:flex;align-items:center;justify-content:center;font-weight:700;color:#081025}
    nav{display:flex;gap:12px;align-items:center}
    .search{background:var(--glass);border:1px solid rgba(255,255,255,0.03);padding:8px 12px;border-radius:10px;display:flex;gap:8px;align-items:center}
    .search input{background:transparent;border:0;color:var(--muted);outline:none;width:220px}
    .hero{display:flex;gap:20px;align-items:center;margin-bottom:22px}
    .hero-left{flex:1}
    .hero-right{width:320px}
    .card{background:linear-gradient(180deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));padding:16px;border-radius:14px;border:1px solid rgba(255,255,255,0.03)}
    h1{margin:0;font-size:24px}
    p.lead{color:var(--muted);margin:8px 0 0}
    .filters{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}
    .chip{padding:8px 12px;border-radius:999px;background:rgba(255,255,255,0.02);border:1px solid rgba(255,255,255,0.02);cursor:pointer}
    .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:16px;margin-top:18px}
    .product{border-radius:12px;overflow:hidden;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);border:1px solid rgba(255,255,255,0.02)}
    .product img{width:100%;height:220px;object-fit:cover;display:block}
    .p-body{padding:12px}
    .p-title{margin:0;font-weight:600}
    .p-meta{color:var(--muted);font-size:13px;margin-top:6px}
    .cta{display:inline-block;padding:10px 14px;border-radius:10px;background:var(--accent);color:#081025;font-weight:700;text-decoration:none;margin-top:10px}
    footer{margin-top:26px;color:var(--muted);font-size:13px;text-align:center}
    /* responsive */
    @media (max-width:760px){.hero{flex-direction:column}.hero-right{width:100%}.search input{width:120px}}
    /* small utilities */
    .badge{display:inline-block;padding:6px 8px;border-radius:8px;background:rgba(0,0,0,0.25);font-size:13px}
    .grid-empty{padding:40px;text-align:center;color:var(--muted)}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">OS</div>
        <div>
          <div style="font-weight:700">OutfitShell</div>
          <div style="font-size:12px;color:var(--muted)">All types • Single-file demo</div>
        </div>
      </div>
      <nav>
        <div class="search card">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none"><path d="M21 21l-4.35-4.35" stroke="#8fa6c2" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
          <input id="q" placeholder="Search outfits, e.g., 'saree'" />
        </div>
        <div class="badge">Cart • 0</div>
      </nav>
    </header><section class="hero">
  <div class="hero-left card">
    <h1>Discover outfits for every style — casual, formal, sports, ethnic and more</h1>
    <p class="lead">Browse categories and filter by type. This is a ready-to-edit shell — swap images and text with your products.</p>
    <div class="filters" id="categories">
      <div class="chip" data-cat="all">All</div>
      <div class="chip" data-cat="women">Women</div>
      <div class="chip" data-cat="men">Men</div>
      <div class="chip" data-cat="kids">Kids</div>
      <div class="chip" data-cat="ethnic">Ethnic</div>
      <div class="chip" data-cat="sports">Activewear</div>
      <div class="chip" data-cat="accessories">Accessories</div>
      <div class="chip" data-cat="formal">Formal</div>
    </div>
  </div>

  <div class="hero-right card">
    <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px">
      <div style="font-weight:700">Quick picks</div>
      <div style="font-size:12px;color:var(--muted)">12 items shown</div>
    </div>
    <div style="display:grid;grid-template-columns:repeat(2,1fr);gap:8px">
      <img src="https://source.unsplash.com/featured/?saree" alt="saree" style="width:100%;height:88px;object-fit:cover;border-radius:8px" />
      <img src="https://source.unsplash.com/featured/?mens-fashion" alt="mens" style="width:100%;height:88px;object-fit:cover;border-radius:8px" />
      <img src="https://source.unsplash.com/featured/?sportswear" alt="sports" style="width:100%;height:88px;object-fit:cover;border-radius:8px" />
      <img src="https://source.unsplash.com/featured/?accessories-fashion" alt="acc" style="width:100%;height:88px;object-fit:cover;border-radius:8px" />
    </div>
  </div>
</section>

<section>
  <div class="grid" id="productGrid">
    <!-- Products injected by JS -->
  </div>
  <div id="empty" class="grid-empty" style="display:none">No outfits match that filter.</div>
</section>

<footer>
  Built as a free, single-file demo. Replace placeholder images and copy with your own catalogue.
</footer>

  </div>  <script>
    // --- SAMPLE DATA: each product has id,title,category,tag,image,price,desc
    const PRODUCTS = [
      {id:1,title:'Classic Cotton Saree',category:'ethnic',tag:'women',image:'https://source.unsplash.com/600x400/?saree,indian',price:'₹1,499',desc:'Lightweight cotton saree — everyday comfort.'},
      {id:2,title:'Slim Fit Shirt',category:'formal',tag:'men',image:'https://source.unsplash.com/600x400/?mens-shirt,formal',price:'₹899',desc:'Perfect for office and events.'},
      {id:3,title:'Gym Performance Tee',category:'sports',tag:'men',image:'https://source.unsplash.com/600x400/?gym-tshirt,sportswear',price:'₹699',desc:'Moisture-wicking fabric.'},
      {id:4,title:'Designer Kurta Set',category:'ethnic',tag:'men',image:'https://source.unsplash.com/600x400/?kurta,indian',price:'₹2,199',desc:'Festive look for celebrations.'},
      {id:5,title:'Flowy Maxi Dress',category:'women',tag:'women',image:'https://source.unsplash.com/600x400/?maxi-dress',price:'₹1,299',desc:'Casual and elegant.'},
      {id:6,title:'Kids Cool Hoodie',category:'kids',tag:'kids',image:'https://source.unsplash.com/600x400/?kids-hoodie',price:'₹799',desc:'Soft and warm for playtime.'},
      {id:7,title:'Leather Belt',category:'accessories',tag:'men',image:'https://source.unsplash.com/600x400/?leather-belt',price:'₹499',desc:'Durable genuine leather.'},
      {id:8,title:'Statement Necklace',category:'accessories',tag:'women',image:'https://source.unsplash.com/600x400/?necklace,jewelry',price:'₹999',desc:'Adds sparkle to any outfit.'},
      {id:9,title:'Formal Trousers',category:'formal',tag:'men',image:'https://source.unsplash.com/600x400/?formal-trousers',price:'₹1,099',desc:'Tailored fit.'},
      {id:10,title:'Yoga Leggings',category:'sports',tag:'women',image:'https://source.unsplash.com/600x400/?yoga-leggings',price:'₹699',desc:'Stretch-friendly fabric.'},
      {id:11,title:'Ethnic Lehenga',category:'ethnic',tag:'women',image:'https://source.unsplash.com/600x400/?lehenga',price:'₹4,999',desc:'Wedding-ready ensemble.'},
      {id:12,title:'Sneakers',category:'sports',tag:'unisex',image:'https://source.unsplash.com/600x400/?sneakers',price:'₹2,499',desc:'Everyday comfort and grip.'}
    ];

    const grid = document.getElementById('productGrid');
    const empty = document.getElementById('empty');

    function renderList(list){
      grid.innerHTML = '';
      if(list.length === 0){empty.style.display='block'; return} else {empty.style.display='none'}
      list.forEach(p => {
        const node = document.createElement('div'); node.className='product';
        node.innerHTML = `
          <img src="${p.image}&${p.id}" alt="${p.title}" />
          <div class="p-body">
            <div class="p-title">${p.title}</div>
            <div class="p-meta">${p.desc} • <strong>${p.price}</strong></div>
            <a class="cta" href="#" onclick="addCart(${p.id});return false">Add</a>
          </div>
        `;
        grid.appendChild(node);
      })
    }

    function addCart(id){
      alert('Added product '+id+' to cart (demo)');
    }

    // init
    renderList(PRODUCTS);

    // filter handlers
    document.querySelectorAll('.chip').forEach(el=>{
      el.addEventListener('click',()=>{
        const c = el.dataset.cat;
        document.querySelectorAll('.chip').forEach(x=>x.style.boxShadow='');
        el.style.boxShadow='inset 0 -3px 0 rgba(255,255,255,0.03)';
        if(c==='all') renderList(PRODUCTS); else renderList(PRODUCTS.filter(p=>p.category===c || p.tag===c));
      })
    })

    // search
    document.getElementById('q').addEventListener('input',e=>{
      const q = e.target.value.toLowerCase().trim();
      if(!q){renderList(PRODUCTS);return}
      const out = PRODUCTS.filter(p=> (p.title+p.desc+p.category+p.tag).toLowerCase().includes(q));
      renderList(out);
    })

    // NOTE: This is a static shell. To make it a real store, replace images with your CDN, add backend for cart and payments, and integrate inventory.
  </script></body>
</html># outfitshell
