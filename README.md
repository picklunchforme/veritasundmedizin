[What’s for lunch_.html](https://github.com/user-attachments/files/34801053/What.s.for.lunch_.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Lunch">
<meta name="theme-color" content="#F6F3EA" media="(prefers-color-scheme: light)">
<meta name="theme-color" content="#1F2B24" media="(prefers-color-scheme: dark)">
<link rel="apple-touch-icon" id="appleIcon">
<title>What&#8217;s for lunch?</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,600;0,700;1,500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #F6F3EA; --surface: #FFFFFF; --text: #223227; --text-dim: #5B6B5E;
    --accent: #D98E3F; --accent-ink: #241505; --border: #E1DACB; color-scheme: light;
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]) {
      --bg: #1F2B24; --surface: #26332B; --text: #EDE8DA; --text-dim: #A9B6A9;
      --accent: #E3A458; --accent-ink: #241505; --border: #38473C; color-scheme: dark;
    }
  }
  :root[data-theme="dark"] {
    --bg: #1F2B24; --surface: #26332B; --text: #EDE8DA; --text-dim: #A9B6A9;
    --accent: #E3A458; --accent-ink: #241505; --border: #38473C; color-scheme: dark;
  }
  * { box-sizing: border-box; }
  html, body { height: 100%; overflow-x: hidden; width: 100%; }
  body {
    margin: 0; background: var(--bg); color: var(--text);
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    padding-top: env(safe-area-inset-top, 0px); padding-bottom: env(safe-area-inset-bottom, 0px);
    display: flex; justify-content: center;
  }
  .wrap { width: 100%; max-width: 480px; margin: 0 auto; padding: 32px 20px 48px; }
  h1 { font-family: "Fraunces", Georgia, serif; font-weight: 700; font-size: 2rem; line-height: 1.15; margin: 0 0 4px; }
  .sub { color: var(--text-dim); margin: 0 0 20px; font-size: 0.95rem; }
  .filter-row { display: flex; gap: 8px; overflow-x: auto; max-width: 100%; padding-bottom: 6px; margin-bottom: 20px; scrollbar-width: none; -webkit-overflow-scrolling: touch; }
  .filter-row::-webkit-scrollbar { display: none; }
  .pill {
    flex: 0 0 auto; border: 1px solid var(--border); background: var(--surface); color: var(--text-dim);
    border-radius: 999px; padding: 10px 16px; font-size: 0.85rem; font-family: inherit; cursor: pointer; white-space: nowrap;
    touch-action: manipulation; -webkit-tap-highlight-color: transparent;
  }
  .pill.active { background: var(--accent); border-color: var(--accent); color: var(--accent-ink); font-weight: 600; }
  .pill:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; }
  .row {
    background: var(--surface); border: 1px solid var(--border); border-radius: 14px; padding: 14px 16px;
    margin-bottom: 12px; display: flex; align-items: center; gap: 12px;
  }
  .row .icon { font-size: 1.4rem; width: 28px; text-align: center; }
  .row .field { flex: 1; min-width: 0; }
  .row label { display: block; font-size: 0.72rem; letter-spacing: .02em; color: var(--text-dim); margin-bottom: 2px; }
  select { width: 100%; max-width: 100%; border: none; background: transparent; color: var(--text); font-size: 1rem; font-family: inherit; padding: 2px 0; }
  select:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; }
  .shuffle-one {
    background: none; border: none; font-size: 1.2rem; cursor: pointer; color: var(--text-dim);
    padding: 10px; min-width: 44px; min-height: 44px; touch-action: manipulation; -webkit-tap-highlight-color: transparent;
  }
  .shuffle-one:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; border-radius: 6px; }
  .btn-main {
    width: 100%; border: none; border-radius: 14px; padding: 16px; font-size: 1.05rem; font-weight: 600;
    font-family: inherit; background: var(--accent); color: var(--accent-ink); cursor: pointer; margin: 8px 0 28px;
    touch-action: manipulation; -webkit-tap-highlight-color: transparent; min-height: 48px;
  }
  .btn-main:active { transform: scale(0.98); }
  .btn-main:focus-visible { outline: 2px solid var(--text); outline-offset: 2px; }
  .summary { border: 1px dashed var(--border); border-radius: 14px; padding: 18px; background: var(--surface); }
  .summary h2 { font-family: "Fraunces", serif; font-size: 1.1rem; margin: 0 0 2px; }
  .summary .hint { font-size: 0.78rem; color: var(--text-dim); margin: 0 0 10px; }
  .summary ul { margin: 0; padding-left: 0; list-style: none; }
  .summary li.combo-row {
    padding: 10px 0; border-bottom: 1px solid var(--border); cursor: pointer;
    touch-action: manipulation; -webkit-tap-highlight-color: transparent;
  }
  .summary li.combo-row:last-child { border-bottom: none; }
  .combo-head { display: flex; justify-content: space-between; align-items: center; gap: 8px; max-width: 100%; }
  .combo-head span:first-child { min-width: 0; overflow-wrap: anywhere; word-break: break-word; }
  .combo-ing { display: none; margin-top: 6px; font-size: 0.82rem; color: var(--text-dim); line-height: 1.4; }
  .combo-row.open .combo-ing { display: block; }
  .chev { color: var(--text-dim); transition: transform .15s ease; flex: 0 0 auto; }
  .combo-row.open .chev { transform: rotate(180deg); }
  .combo-row:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; border-radius: 6px; }
  @media (prefers-reduced-motion: reduce) { .btn-main:active { transform: none; } }
  .credit {
    position: fixed;
    right: calc(12px + env(safe-area-inset-right, 0px));
    bottom: calc(10px + env(safe-area-inset-bottom, 0px));
    font-size: 0.68rem;
    letter-spacing: .02em;
    color: var(--text-dim);
    opacity: 0.65;
    pointer-events: none;
  }
</style>
</head>
<body>
<div class="wrap">
  <h1>What&#8217;s for lunch? &#127807;</h1>
  <p class="sub">Filter by cuisine, pick one from each, or let it decide.</p>

  <div class="filter-row" id="filterRow">
    <button class="pill active" data-cuisine="all">All</button>
    <button class="pill" data-cuisine="turkmen">Turkmen</button>
    <button class="pill" data-cuisine="turkish">Turkish</button>
    <button class="pill" data-cuisine="russian">Russian</button>
    <button class="pill" data-cuisine="mediterranean">Mediterranean</button>
  </div>

  <div class="row">
    <span class="icon">&#127858;</span>
    <div class="field"><label for="soup">Soup</label><select id="soup"></select></div>
    <button class="shuffle-one" data-cat="soup" aria-label="Shuffle soup">&#128256;</button>
  </div>
  <div class="row">
    <span class="icon">&#127831;</span>
    <div class="field"><label for="main">Main</label><select id="main"></select></div>
    <button class="shuffle-one" data-cat="main" aria-label="Shuffle main">&#128256;</button>
  </div>
  <div class="row">
    <span class="icon">&#127834;</span>
    <div class="field"><label for="side">Side</label><select id="side"></select></div>
    <button class="shuffle-one" data-cat="side" aria-label="Shuffle side">&#128256;</button>
  </div>
  <div class="row">
    <span class="icon">&#129367;</span>
    <div class="field"><label for="salad">Salad</label><select id="salad"></select></div>
    <button class="shuffle-one" data-cat="salad" aria-label="Shuffle salad">&#128256;</button>
  </div>

  <button class="btn-main" id="surprise">&#127922; Surprise me</button>

  <div class="summary">
    <h2>Today&#8217;s combo</h2>
    <p class="hint">Tap a dish for its ingredients</p>
    <ul id="summaryList"></ul>
  </div>
</div>

<div class="credit">Powered by malixrahym</div>

<script>
  const DATA = {
    soup: [
      {name:"Rassolnik", c:"russian", ing:"Pickled cucumbers, potatoes, pearl barley, carrot, onion, pickle brine, dill"},
      {name:"Lagman", c:"russian", ing:"Beef or lamb, hand-pulled noodles, onion, bell pepper, carrot, tomato, garlic, cumin"},
      {name:"Dumpling soup", c:"russian", ing:"Chicken broth, flour, egg, carrot, onion, dill"},
      {name:"Beshbarmak soup", c:"russian", ing:"Lamb or beef, flat noodle squares, onion, broth, black pepper"},
      {name:"Mung bean soup", c:"russian", ing:"Mung beans, onion, carrot, meat broth, cumin, black pepper"},
      {name:"Broccoli soup", c:"russian", ing:"Broccoli, potato, onion, broth, cream, butter"},
      {name:"Vermicelli soup", c:"russian", ing:"Chicken broth, thin vermicelli, carrot, onion"},
      {name:"Unash soup", c:"russian", ing:"Meat broth, hand-cut noodles, potato, onion, carrot, herbs"},
      {name:"Kharcho", c:"russian", ing:"Beef, rice, onion, tomato paste, walnuts, garlic, khmeli-suneli, cilantro"},
      {name:"Chorba (Turkmen lamb soup)", c:"turkmen", ing:"Lamb, onion, carrot, potato, tomato, bay leaf, black pepper"},
      {name:"Mercimek (red lentil)", c:"turkish", ing:"Red lentils, onion, potato, broth, paprika, butter, lemon"},
      {name:"Ezogelin", c:"turkish", ing:"Red lentils, rice or bulgur, onion, tomato paste, mint, butter, paprika"},
      {name:"Yayla soup (yogurt & rice)", c:"turkish", ing:"Yogurt, rice, egg, flour, mint, butter, broth"},
      {name:"Tarhana soup", c:"turkish", ing:"Tarhana (dried yogurt-wheat mix), broth, tomato paste, butter, red pepper flakes"},
      {name:"Fasolada (Greek bean soup)", c:"mediterranean", ing:"White beans, carrot, celery, onion, tomato, olive oil, bay leaf"},
      {name:"Minestrone (Italian vegetable soup)", c:"mediterranean", ing:"Beans, pasta, carrot, celery, onion, tomato, zucchini, parmesan"},
      {name:"Avgolemono (Greek lemon-egg soup)", c:"mediterranean", ing:"Chicken broth, rice, egg, lemon juice, chicken"},
      {name:"Mastava (rice & vegetable soup)", c:"turkmen", ing:"Lamb or beef, rice, potato, carrot, tomato, onion, garlic"},
      {name:"Kashk (sour milk soup)", c:"turkmen", ing:"Fermented yogurt (kashk), onion, mint, butter, flour"},
      {name:"Domates \u00e7orbas\u0131 (tomato soup)", c:"turkish", ing:"Tomato, onion, garlic, broth, butter, rice, basil"},
      {name:"D\u00fc\u011f\u00fcn \u00e7orbas\u0131 (wedding soup)", c:"turkish", ing:"Lamb, flour, egg yolk, yogurt, butter, paprika, lemon"}
    ],
    main: [
      {name:"Chicken liver with onions", c:"russian", ing:"Chicken liver, onion, butter, salt, pepper, sour cream"},
      {name:"Chicken nest", c:"russian", ing:"Mashed potato, chicken breast, onion, carrot, cheese, egg"},
      {name:"Golden roasted chicken", c:"russian", ing:"Chicken pieces, garlic, paprika, oil, salt, pepper"},
      {name:"Prague-style chicken cutlets", c:"russian", ing:"Ground chicken, butter, egg, breadcrumbs, onion"},
      {name:"KFC-style chicken legs", c:"russian", ing:"Chicken legs, buttermilk, flour, paprika, garlic powder, pepper"},
      {name:"Chicken roll with spinach", c:"russian", ing:"Chicken breast, spinach, cheese, garlic, oil"},
      {name:"Chicken wings with rice", c:"russian", ing:"Chicken wings, garlic, soy sauce, honey, rice"},
      {name:"Chicken pirzola", c:"russian", ing:"Chicken breast, lemon, garlic, olive oil, herbs"},
      {name:"Chicken saut\u00e9", c:"russian", ing:"Chicken, onion, bell pepper, oil, salt, pepper"},
      {name:"Baked chicken meatballs in tomato sauce", c:"russian", ing:"Ground chicken, onion, breadcrumbs, tomato, garlic"},
      {name:"Chicken in creamy sauce", c:"russian", ing:"Chicken, cream, garlic, mustard, butter"},
      {name:"Veal meatballs", c:"russian", ing:"Ground veal, bread, egg, onion, broth"},
      {name:"Duck breast with potatoes", c:"russian", ing:"Duck breast, potatoes, salt, pepper, thyme"},
      {name:"Veal cutlets", c:"russian", ing:"Ground veal, onion, egg, breadcrumbs"},
      {name:"Veal kofte", c:"russian", ing:"Ground veal, onion, garlic, cumin, parsley"},
      {name:"Fried sprat", c:"russian", ing:"Sprat (small fish), flour, salt, oil"},
      {name:"Uzbek plov with chicken & dried fruits", c:"russian", ing:"Chicken, rice, carrot, onion, dried apricots, raisins, oil"},
      {name:"Spaghetti Bolognese", c:"russian", ing:"Ground beef, onion, garlic, tomato, herbs, spaghetti"},
      {name:"Stuffed eggplants", c:"russian", ing:"Eggplant, ground meat, onion, tomato, rice"},
      {name:"Mini stuffed peppers", c:"russian", ing:"Bell peppers, rice, ground meat, tomato sauce"},
      {name:"Ichlekli (Turkmen meat pie)", c:"turkmen", ing:"Flour dough, lamb or beef, onion, black pepper, butter"},
      {name:"Gutap (stuffed flatbread)", c:"turkmen", ing:"Thin dough, pumpkin or greens or meat, onion, oil"},
      {name:"Manty (steamed dumplings)", c:"turkmen", ing:"Dough, ground meat, onion, black pepper, butter"},
      {name:"Govurma (pan-fried lamb)", c:"turkmen", ing:"Lamb, onion, fat tail or oil, salt, pepper"},
      {name:"Chekdirme (meat & vegetable stew)", c:"turkmen", ing:"Lamb, potato, carrot, onion, tomato, bell pepper"},
      {name:"Dograma (flatbread with meat broth)", c:"turkmen", ing:"Flatbread, lamb or beef, onion, broth, black pepper"},
      {name:"Karn\u0131yar\u0131k (stuffed eggplant with meat)", c:"turkish", ing:"Eggplant, ground beef, onion, tomato, green pepper, garlic"},
      {name:"H\u00fcnkar be\u011fendi (lamb over eggplant pur\u00e9e)", c:"turkish", ing:"Lamb stew, eggplant, milk, butter, flour, cheese"},
      {name:"Izgara k\u00f6fte (grilled meatballs)", c:"turkish", ing:"Ground beef or lamb, onion, breadcrumbs, cumin, parsley"},
      {name:"Moussaka (eggplant & meat bake)", c:"mediterranean", ing:"Eggplant, ground lamb, tomato, onion, b\u00e9chamel sauce, cheese"},
      {name:"Greek lemon chicken", c:"mediterranean", ing:"Chicken, lemon, garlic, oregano, olive oil, potatoes"},
      {name:"Baked fish plaki (tomato & herbs)", c:"mediterranean", ing:"White fish, tomato, onion, garlic, olive oil, parsley"},
      {name:"Chicken piccata (lemon caper chicken)", c:"mediterranean", ing:"Chicken breast, lemon, capers, butter, flour, white wine"},
      {name:"Shakshuka (eggs in tomato sauce)", c:"mediterranean", ing:"Eggs, tomato, onion, bell pepper, garlic, cumin, paprika"},
      {name:"Pastitsio (Greek baked pasta)", c:"mediterranean", ing:"Pasta, ground beef, tomato, b\u00e9chamel sauce, cheese"},
      {name:"Somsa (baked meat pastry)", c:"turkmen", ing:"Dough, ground meat or pumpkin, onion, black pepper"},
      {name:"Gyzyl plov (Turkmen lamb plov)", c:"turkmen", ing:"Lamb, rice, carrot, onion, garlic, cumin"},
      {name:"T\u00fcrk mant\u0131s\u0131 (dumplings with yogurt sauce)", c:"turkish", ing:"Dough, ground beef, onion, yogurt, garlic, butter, sumac"},
      {name:"Etli g\u00fcve\u00e7 (meat & vegetable stew)", c:"turkish", ing:"Beef, potato, carrot, bell pepper, tomato, garlic"},
      {name:"Kuru fasulye (white bean stew)", c:"turkish", ing:"White beans, tomato paste, onion, beef or sausage, pepper paste"}
    ],
    side: [
      {name:"Bulgur", c:"russian", ing:"Bulgur wheat, butter, broth, salt"},
      {name:"Buckwheat", c:"russian", ing:"Buckwheat groats, butter, salt, water"},
      {name:"Rice", c:"russian", ing:"Rice, butter, salt, water"},
      {name:"Vermicelli", c:"russian", ing:"Vermicelli pasta, butter, salt"},
      {name:"Mashed potatoes", c:"russian", ing:"Potatoes, butter, milk, salt"},
      {name:"Macaroni", c:"russian", ing:"Macaroni pasta, butter, salt"},
      {name:"Spaghetti", c:"russian", ing:"Spaghetti, oil or butter, salt"},
      {name:"Home-style potatoes", c:"russian", ing:"Potatoes, onion, oil, salt, pepper"},
      {name:"Navy-style macaroni", c:"russian", ing:"Macaroni, ground beef, onion"},
      {name:"Rice & mung bean porridge", c:"russian", ing:"Rice, mung beans, water, salt, butter"},
      {name:"Chorek (Turkmen flatbread)", c:"turkmen", ing:"Flour, water, yeast, salt, oil"},
      {name:"\u015eehriyeli pilav (rice with vermicelli)", c:"turkish", ing:"Rice, vermicelli, butter, broth"},
      {name:"Lemon herb rice pilaf", c:"mediterranean", ing:"Rice, lemon zest, parsley, butter, broth"},
      {name:"Orzo with herbs", c:"mediterranean", ing:"Orzo pasta, olive oil, parsley, lemon, garlic"},
      {name:"Roasted Mediterranean vegetables", c:"mediterranean", ing:"Zucchini, eggplant, bell pepper, tomato, olive oil, oregano"},
      {name:"Petir (flaky flatbread)", c:"turkmen", ing:"Flour, water, butter or oil, salt"},
      {name:"Yarma (cracked wheat porridge)", c:"turkmen", ing:"Cracked wheat, water, butter, salt"},
      {name:"Bulgur pilav\u0131 (tomato bulgur pilaf)", c:"turkish", ing:"Bulgur, tomato paste, onion, bell pepper, butter"},
      {name:"K\u00f6y ekme\u011fi (village bread)", c:"turkish", ing:"Flour, yeast, water, salt"}
    ],
    salad: [
      {name:"Green Bowl", c:"russian", ing:"Mixed greens, cucumber, cherry tomato, olive oil, lemon"},
      {name:"Salad with oil", c:"russian", ing:"Cucumber, tomato, onion, sunflower oil"},
      {name:"Salad with mayo", c:"russian", ing:"Cucumber, carrot, egg or potato, mayonnaise"},
      {name:"Achichuk (tomato & onion)", c:"turkmen", ing:"Tomato, onion, salt, black pepper"},
      {name:"Morkovcha (carrot salad)", c:"turkmen", ing:"Grated carrot, garlic, vinegar, coriander, oil"},
      {name:"Turkmen herb salad", c:"turkmen", ing:"Dill, cilantro, parsley, green onion, oil"},
      {name:"Radish salad with sour cream", c:"turkmen", ing:"Radish, sour cream, dill, salt"},
      {name:"Beetroot salad", c:"turkmen", ing:"Beetroot, garlic, mayonnaise or oil, walnuts"},
      {name:"\u00c7oban salatas\u0131 (shepherd\u2019s salad)", c:"turkish", ing:"Tomato, cucumber, onion, green pepper, olive oil, lemon"},
      {name:"Gavurda\u011f\u0131 salatas\u0131 (walnut tomato salad)", c:"turkish", ing:"Tomato, walnuts, onion, parsley, pomegranate molasses"},
      {name:"Ezme (spicy tomato salad)", c:"turkish", ing:"Tomato, onion, pepper paste, parsley, lemon, chili"},
      {name:"Cac\u0131k (yogurt & cucumber)", c:"turkish", ing:"Yogurt, cucumber, garlic, dill, olive oil"},
      {name:"Greek salad", c:"mediterranean", ing:"Tomato, cucumber, feta cheese, olives, red onion, olive oil"},
      {name:"Tabbouleh", c:"mediterranean", ing:"Parsley, bulgur, tomato, mint, lemon, olive oil"},
      {name:"Hummus with pita", c:"mediterranean", ing:"Chickpeas, tahini, lemon, garlic, olive oil, pita bread"},
      {name:"Turshy (pickled vegetable salad)", c:"turkmen", ing:"Pickled cabbage, carrot, pepper, vinegar, garlic"},
      {name:"Cucumber & dill salad", c:"turkmen", ing:"Cucumber, dill, sour cream or oil, salt"},
      {name:"Mevsim salata (seasonal salad)", c:"turkish", ing:"Lettuce, tomato, cucumber, carrot, olive oil"},
      {name:"Piyaz (white bean salad)", c:"turkish", ing:"White beans, onion, tomato, parsley, olive oil, vinegar"}
    ]
  };
  const order = ["soup","main","side","salad"];
  const icons = {soup:"\u{1F372}", main:"\u{1F357}", side:"\u{1F35A}", salad:"\u{1F957}"};
  let activeCuisine = "all";

  function getPool(cat){ return activeCuisine === "all" ? DATA[cat] : DATA[cat].filter(d => d.c === activeCuisine); }
  function populate(){
    order.forEach(cat=>{
      const sel = document.getElementById(cat);
      const prev = sel.value;
      const pool = getPool(cat);
      sel.innerHTML = pool.map(d=>`<option value="${d.name}">${d.name}</option>`).join("");
      if (pool.some(d=>d.name===prev)) sel.value = prev;
    });
  }
  function randomIndex(n){ return Math.floor(Math.random()*n); }
  function shuffleOne(cat){
    const pool = getPool(cat);
    document.getElementById(cat).selectedIndex = randomIndex(pool.length);
    updateSummary();
  }
  function shuffleAll(){ order.forEach(shuffleOne); }
  function updateSummary(){
    document.getElementById("summaryList").innerHTML = order.map(cat=>{
      const sel = document.getElementById(cat);
      const dish = DATA[cat].find(d=>d.name===sel.value);
      const ing = dish ? dish.ing : "";
      return `<li class="combo-row" tabindex="0" role="button" aria-expanded="false"><div class="combo-head"><span>${icons[cat]} ${sel.value}</span><span class="chev">&#8964;</span></div><div class="combo-ing">${ing}</div></li>`;
    }).join("");
  }
  function toggleRow(row){
    const open = row.classList.toggle("open");
    row.setAttribute("aria-expanded", open ? "true" : "false");
  }

  document.querySelectorAll(".pill").forEach(btn=>{
    btn.addEventListener("click", ()=>{
      activeCuisine = btn.dataset.cuisine;
      document.querySelectorAll(".pill").forEach(b=>b.classList.toggle("active", b===btn));
      populate();
      updateSummary();
    });
  });
  order.forEach(cat=>{
    document.getElementById(cat).addEventListener("change", updateSummary);
  });
  document.querySelectorAll(".shuffle-one").forEach(btn=>{
    btn.addEventListener("click", ()=> shuffleOne(btn.dataset.cat));
  });
  document.getElementById("surprise").addEventListener("click", shuffleAll);
  document.getElementById("summaryList").addEventListener("click", (e)=>{
    const row = e.target.closest(".combo-row");
    if(row) toggleRow(row);
  });
  document.getElementById("summaryList").addEventListener("keydown", (e)=>{
    if(e.key==="Enter" || e.key===" "){
      const row = e.target.closest(".combo-row");
      if(row){ e.preventDefault(); toggleRow(row); }
    }
  });

  populate();
  shuffleAll();

  (function(){
    try {
      const c = document.createElement("canvas");
      c.width = 180; c.height = 180;
      const ctx = c.getContext("2d");
      const r = 40;
      ctx.fillStyle = "#D98E3F";
      ctx.beginPath();
      ctx.moveTo(r,0);
      ctx.arcTo(180,0,180,180,r);
      ctx.arcTo(180,180,0,180,r);
      ctx.arcTo(0,180,0,0,r);
      ctx.arcTo(0,0,180,0,r);
      ctx.closePath();
      ctx.fill();
      ctx.font = "110px serif";
      ctx.textAlign = "center";
      ctx.textBaseline = "middle";
      ctx.fillText("\u{1F33F}", 90, 100);
      document.getElementById("appleIcon").setAttribute("href", c.toDataURL("image/png"));
    } catch(e) {}
  })();
</script>
</body>
</html>
