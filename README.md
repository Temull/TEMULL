
<!DOCTYPE html>

<html lang="mn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TEMULL — PRE ORDER</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–pink: #f472b6;
–hot: #ec4899;
–bg: #080808;
–white: #ffffff;
}

body {
background: var(–bg);
color: var(–white);
font-family: ‘Space Mono’, monospace;
min-height: 100vh;
overflow-x: hidden;
}

body::before {
content: ‘’;
position: fixed;
inset: 0;
background-image: url(“data:image/svg+xml,%3Csvg viewBox=‘0 0 200 200’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cfilter id=‘n’%3E%3CfeTurbulence type=‘fractalNoise’ baseFrequency=‘0.9’ numOctaves=‘4’ stitchTiles=‘stitch’/%3E%3C/filter%3E%3Crect width=‘100%25’ height=‘100%25’ filter=‘url(%23n)’ opacity=‘0.04’/%3E%3C/svg%3E”);
pointer-events: none;
z-index: 0;
opacity: 0.5;
}

header {
text-align: center;
padding: 48px 20px 24px;
position: relative;
z-index: 1;
}

.brand {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(64px, 18vw, 160px);
letter-spacing: 0.08em;
background: linear-gradient(160deg, #fff 0%, #c0c0c0 40%, #fff 60%, #888 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
animation: shimmer 3s ease-in-out infinite alternate;
line-height: 1;
}

@keyframes shimmer {
0% { filter: drop-shadow(0 0 20px rgba(244,114,182,0.2)); }
100% { filter: drop-shadow(0 0 60px rgba(244,114,182,0.5)); }
}

.tagline {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(12px, 3vw, 18px);
letter-spacing: 0.4em;
color: var(–pink);
margin-top: 8px;
}

main {
position: relative;
z-index: 1;
max-width: 960px;
margin: 0 auto;
padding: 20px 16px 80px;
}

.drop-label {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 13px;
letter-spacing: 0.35em;
color: #444;
text-align: center;
margin-bottom: 20px;
text-transform: uppercase;
}

/* 2x2 grid */
.cards {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 14px;
margin-bottom: 48px;
}

@media (max-width: 560px) {
.cards { gap: 8px; }
}

.card {
background: #111;
border: 1px solid #222;
border-radius: 2px;
overflow: hidden;
position: relative;
transition: transform 0.3s ease, border-color 0.3s ease;
}

.card:hover { transform: translateY(-4px); border-color: var(–pink); }

.card-badge {
position: absolute;
top: 10px;
left: 10px;
z-index: 2;
font-family: ‘Bebas Neue’, sans-serif;
font-size: 10px;
letter-spacing: 0.2em;
padding: 3px 8px;
border-radius: 1px;
}

.badge-sold { background: #222; color: #555; }
.badge-pre  { background: var(–hot); color: #fff; animation: pulse 2s infinite; }

@keyframes pulse {
0%,100% { opacity: 1; }
50%      { opacity: 0.65; }
}

.card-img {
width: 100%;
aspect-ratio: 3/4;
object-fit: cover;
display: block;
}

.card.sold-out .card-img {
filter: grayscale(60%) brightness(0.45);
}

.card-body { padding: 12px 14px 14px; }

.card-title {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 20px;
letter-spacing: 0.08em;
margin-bottom: 2px;
}

.card-sub {
font-size: 9px;
letter-spacing: 0.2em;
color: #555;
margin-bottom: 10px;
text-transform: uppercase;
}

.sold-label {
display: block;
text-align: center;
font-family: ‘Bebas Neue’, sans-serif;
font-size: 14px;
letter-spacing: 0.25em;
color: #444;
padding: 9px;
border: 1px solid #2a2a2a;
}

.btn-pre {
display: block;
width: 100%;
background: var(–hot);
color: #fff;
font-family: ‘Bebas Neue’, sans-serif;
font-size: 16px;
letter-spacing: 0.2em;
padding: 10px;
border: none;
cursor: pointer;
border-radius: 1px;
text-align: center;
text-decoration: none;
transition: background 0.2s, transform 0.1s;
}

.btn-pre:hover { background: #be185d; transform: scale(0.98); }

/* ROW SEPARATOR */
.row-sep {
grid-column: 1 / -1;
display: flex;
align-items: center;
gap: 12px;
padding: 4px 0;
}

.row-sep::before, .row-sep::after {
content: ‘’;
flex: 1;
height: 1px;
background: #1e1e1e;
}

.row-sep span {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 11px;
letter-spacing: 0.35em;
color: var(–hot);
white-space: nowrap;
}

/* INFO */
.info-strip {
display: flex;
justify-content: center;
gap: 32px;
flex-wrap: wrap;
margin-bottom: 40px;
padding: 24px 0;
border-top: 1px solid #1a1a1a;
border-bottom: 1px solid #1a1a1a;
}

.info-item { text-align: center; }
.info-item .val {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 26px;
color: var(–pink);
letter-spacing: 0.1em;
display: block;
}
.info-item .lbl {
font-size: 9px;
letter-spacing: 0.22em;
color: #555;
text-transform: uppercase;
}

.divider {
text-align: center;
margin: 0 0 28px;
position: relative;
}
.divider::before {
content: ‘’;
position: absolute;
top: 50%; left: 0; right: 0;
height: 1px;
background: #1e1e1e;
}
.divider span {
position: relative;
background: var(–bg);
padding: 0 16px;
font-family: ‘Bebas Neue’, sans-serif;
font-size: 11px;
letter-spacing: 0.4em;
color: #444;
}

/* FORM */
.section-title {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(28px, 8vw, 56px);
letter-spacing: 0.12em;
text-align: center;
margin-bottom: 6px;
background: linear-gradient(90deg, var(–white) 0%, var(–pink) 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
}

.section-desc {
text-align: center;
color: #555;
font-size: 10px;
letter-spacing: 0.15em;
margin-bottom: 28px;
text-transform: uppercase;
}

.form-wrap {
background: #0f0f0f;
border: 1px solid #1e1e1e;
border-radius: 2px;
padding: 28px 22px;
max-width: 500px;
margin: 0 auto;
}

.form-row { margin-bottom: 18px; }

label {
display: block;
font-size: 9px;
letter-spacing: 0.25em;
color: #777;
margin-bottom: 6px;
text-transform: uppercase;
}

input, select, textarea {
width: 100%;
background: #161616;
border: 1px solid #2a2a2a;
color: var(–white);
font-family: ‘Space Mono’, monospace;
font-size: 13px;
padding: 10px 14px;
border-radius: 1px;
outline: none;
transition: border-color 0.2s;
-webkit-appearance: none;
}

input:focus, select:focus, textarea:focus { border-color: var(–pink); }
select option { background: #161616; }
textarea { resize: vertical; min-height: 72px; }

.size-grid {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 7px;
}

.size-btn {
background: #161616;
border: 1px solid #2a2a2a;
color: #777;
font-family: ‘Bebas Neue’, sans-serif;
font-size: 15px;
letter-spacing: 0.08em;
padding: 9px 4px;
cursor: pointer;
transition: all 0.18s;
border-radius: 1px;
}

.size-btn:hover { border-color: var(–pink); color: var(–pink); }
.size-btn.active { background: var(–hot); border-color: var(–hot); color: #fff; }

.submit-btn {
width: 100%;
background: transparent;
border: 2px solid var(–hot);
color: var(–hot);
font-family: ‘Bebas Neue’, sans-serif;
font-size: 20px;
letter-spacing: 0.3em;
padding: 13px;
cursor: pointer;
margin-top: 6px;
transition: all 0.22s;
border-radius: 1px;
}

.submit-btn:hover {
background: var(–hot);
color: #fff;
box-shadow: 0 0 30px rgba(236,72,153,0.3);
}

.success-box { display: none; text-align: center; padding: 40px 20px; }
.success-box.show { display: block; }
.success-icon { font-size: 44px; margin-bottom: 14px; }
.success-box h2 {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 32px;
letter-spacing: 0.2em;
color: var(–pink);
margin-bottom: 8px;
}
.success-box p { color: #555; font-size: 11px; letter-spacing: 0.1em; }

footer {
text-align: center;
padding: 28px 16px;
border-top: 1px solid #111;
color: #2a2a2a;
font-size: 9px;
letter-spacing: 0.2em;
position: relative;
z-index: 1;
}
</style>

</head>
<body>

<header>
  <div class="brand">TEMULL</div>
  <div class="tagline">Mongolian Streetwear — Limited Drops</div>
</header>

<main>

  <div class="drop-label">Drop 001 — Pink Woke Hoodie</div>

  <div class="cards">

```
<!-- SOLD OUT row -->
<div class="card sold-out">
  <div class="card-badge badge-sold">SOLD OUT</div>
  <img class="card-img" src="/mnt/user-data/uploads/45413DC8-36E0-4801-9190-55C11572A75A.jpeg" alt="Hoodie Drop 01 Front">
  <div class="card-body">
    <div class="card-title">WOKE HOODIE</div>
    <div class="card-sub">Front view — Drop 01</div>
    <span class="sold-label">ДУУССАН / SOLD OUT</span>
  </div>
</div>

<div class="card sold-out">
  <div class="card-badge badge-sold">SOLD OUT</div>
  <img class="card-img" src="/mnt/user-data/uploads/619BCC19-4417-4D7D-A1F1-38F91E42D790.jpeg" alt="Hoodie Drop 01 Back">
  <div class="card-body">
    <div class="card-title">WOKE HOODIE</div>
    <div class="card-sub">Back view — Drop 01</div>
    <span class="sold-label">ДУУССАН / SOLD OUT</span>
  </div>
</div>

<!-- separator -->
<div class="row-sep"><span>✦ PRE ORDER NOW OPEN ✦</span></div>

<!-- PRE ORDER row -->
<div class="card">
  <div class="card-badge badge-pre">PRE ORDER</div>
  <img class="card-img" src="/mnt/user-data/uploads/3E23189B-9283-41D9-8E31-B8057E7B6020.jpeg" alt="Hoodie Drop 02 Front">
  <div class="card-body">
    <div class="card-title">WOKE HOODIE</div>
    <div class="card-sub">Front view — Drop 02</div>
    <a href="#preorder" class="btn-pre">PRE ORDER →</a>
  </div>
</div>

<div class="card">
  <div class="card-badge badge-pre">PRE ORDER</div>
  <img class="card-img" src="/mnt/user-data/uploads/8F7A78B6-B6D5-443E-AADA-F7CDAA655E79.jpeg" alt="Hoodie Drop 02 Back">
  <div class="card-body">
    <div class="card-title">WOKE HOODIE</div>
    <div class="card-sub">Back view — Drop 02</div>
    <a href="#preorder" class="btn-pre">PRE ORDER →</a>
  </div>
</div>
```

  </div>

  <div class="info-strip">
    <div class="info-item">
      <span class="val">LIMITED</span>
      <span class="lbl">Хязгаарлагдмал тоо</span>
    </div>
    <div class="info-item">
      <span class="val">2–3 WK</span>
      <span class="lbl">Хүргэлтийн хугацаа</span>
    </div>
    <div class="info-item">
      <span class="val">100%</span>
      <span class="lbl">Монгол брэнд</span>
    </div>
  </div>

  <div class="divider"><span>PRE ORDER МАЯГТ</span></div>

  <div id="preorder">
    <div class="section-title">PRE ORDER</div>
    <div class="section-desc">Доорх маягтыг бөглөж илгээнэ үү — бид тантай холбогдоно</div>

```
<div class="form-wrap">
  <div id="form-content">

    <div class="form-row">
      <label>Нэр / Name</label>
      <input type="text" id="fname" placeholder="Таны нэр" />
    </div>

    <div class="form-row">
      <label>Утасны дугаар</label>
      <input type="tel" id="phone" placeholder="99xxxxxx" />
    </div>

    <div class="form-row">
      <label>Instagram (заавал биш)</label>
      <input type="text" id="insta" placeholder="@username" />
    </div>

    <div class="form-row">
      <label>Хэмжээ / Size</label>
      <div class="size-grid">
        <button class="size-btn" onclick="selectSize(this)">XS</button>
        <button class="size-btn" onclick="selectSize(this)">S</button>
        <button class="size-btn" onclick="selectSize(this)">M</button>
        <button class="size-btn" onclick="selectSize(this)">L</button>
        <button class="size-btn" onclick="selectSize(this)">XL</button>
        <button class="size-btn" onclick="selectSize(this)">XXL</button>
        <button class="size-btn" onclick="selectSize(this)">3XL</button>
        <button class="size-btn" onclick="selectSize(this)">OS</button>
      </div>
    </div>

    <div class="form-row">
      <label>Хаяг / Хүргэлтийн мэдээлэл</label>
      <textarea id="address" placeholder="Дүүрэг, хороо, байр..."></textarea>
    </div>

    <button class="submit-btn" onclick="submitForm()">PRE ORDER ИЛГЭЭХ</button>

  </div>

  <div class="success-box" id="success">
    <div class="success-icon">🖤</div>
    <h2>БАЯРЛАЛАА!</h2>
    <p>Таны pre-order хүлээн авагдлаа.<br>Бид удахгүй тантай холбогдоно.</p>
  </div>
</div>
```

  </div>

</main>

<footer>© 2026 TEMULL — ALL RIGHTS RESERVED</footer>

<script>
  let selectedSize = '';

  function selectSize(btn) {
    document.querySelectorAll('.size-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    selectedSize = btn.textContent.trim();
  }

  function submitForm() {
    const name  = document.getElementById('fname').value.trim();
    const phone = document.getElementById('phone').value.trim();
    if (!name)         { alert('Нэрээ оруулна уу.');           return; }
    if (!phone)        { alert('Утасны дугаараа оруулна уу.'); return; }
    if (!selectedSize) { alert('Хэмжээгээ сонгоно уу.');       return; }

    document.getElementById('form-content').style.display = 'none';
    document.getElementById('success').classList.add('show');
    document.getElementById('preorder').scrollIntoView({ behavior: 'smooth' });
  }
</script>

</body>
</html>
