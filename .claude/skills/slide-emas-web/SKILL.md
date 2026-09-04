---
name: slide-emas-web
description: >
  Hasilkan deck carousel 7 slaid gaya perbualan WhatsApp (Slide Emas By Taufik) sebagai SATU fail
  HTML yang di-host — bersaiz menegak 9:16 (video TikTok), diswipe seperti laman web biasa dengan
  bar navigasi di bawah, dan dihantar sebagai pautan hidup. Guna skill ini bila Taufik sebut "buat
  slide emas", "carousel emas", "deck emas", "slide web", "slide emas web", "buat carousel untuk
  repo", atau bila dia paste pautan YouTube, artikel, atau idea mentah dan mahu ia jadi Q&A carousel
  emas. Skill ini TIADA fungsi muat naik gambar/thumbnail dan TIADA butang Save PNG, dan slaid CTA
  terakhirnya mengandungi tiga pautan hidup (WhatsApp, simpanemasfizikal.com, pg2u.my/taufikmusa).
  BERBEZA daripada slide-chat-gold (ada thumbnail gambar), slide-chat (tiada CTA pautan),
  emas-slide-style (kad putih rata Montserrat), colourfull-slide-style (gradient), dan html-doodle
  (sticker doodle) — jangan campur token atau layout antara skill-skill ini.
---

# Slide Emas Web

Deck carousel 7 slaid gaya perbualan WhatsApp untuk Taufik Bin Musa, Dealer Public Gold G100 Network (PG00359605). Satu fail HTML, di-host atas GitHub Pages, dibaca sebagai laman web hidup.

Bentuknya **menegak 9:16** — nisbah yang sama dengan video TikTok/Reels. Pembaca swipe mendatar seperti laman web biasa, dan bar navigasi tetap di bawah skrin membawa butang **Home**, titik penunjuk, dan anak panah.

Beza dengan versi Gems lama: **tiada muat naik gambar** dan **tiada butang Save PNG** (kedua-duanya dibuang sepenuhnya), dan slaid CTA ada **tiga pautan boleh klik**.

---

## Langkah 1 — Kenal pasti sumber

Taufik akan bagi salah satu:

| Input | Cara proses |
|---|---|
| Pautan YouTube | Tonton/analisis. Cabut SATU fakta atau pengajaran paling kuat berkaitan wang. |
| Artikel (pautan atau teks) | Baca. Cabut hujah teras atau satu titik kesakitan penonton. |
| Idea mentah / transkrip voice note | Guna terus. Titik utama jadi hook. |

**Langkah dalaman pertama sentiasa sama:** kenal pasti SATU titik kesakitan, kemudian tulis semula segalanya jadi dialog dua hala (Pengikut lawan Anda). Jangan sesekali terus bina slaid tanpa langkah tulis semula ini.

Kalau ada fakta, sejarah, harga atau angka — sahkan dahulu. Jangan reka statistik. Kalau pautan sumber tak dapat dicapai (disekat, mati, atau perlu log masuk), jangan teka kandungan: sahkan fakta dari sumber lain dan beritahu Taufik bahagian mana yang tak dapat dibaca.

---

## Langkah 2 — Struktur deck (SENTIASA 7 SLAID)

1. **Hook / Tajuk** — 1 slaid
2. **Dialog / Deep Dive** — 5 slaid
3. **CTA / Penutup** — 1 slaid, salinan tetap (lihat Lampiran A)

Jangan hasilkan lebih atau kurang daripada 7 melainkan Taufik minta jumlah lain. Kalau satu jawapan terlalu panjang, pecah kepada dua slaid — jangan biar teks terpotong.

Ingat bentuk 9:16 lebih sempit daripada 4:5. Bubble panjang cepat penuh — kalau satu bubble melebihi kira-kira 45 patah perkataan, pecahkan.

---

## Langkah 3 — Bina

Mula daripada template dalam **Lampiran A**. Jangan tulis dari kosong.

Yang boleh ditukar: teks dalam `.headline`, `.sub-text`, `.bubble-q`, `.bubble-a`, dan `{{DECK_TITLE}}`.

Yang **tidak boleh** disentuh:
- Semua token warna, `background-image` grid putih, font Poppins
- `aspect-ratio:9/16` dan pengiraan tinggi slaid
- `container-type:inline-size` pada `.slide`, dan semua saiz font, padding serta gap dalam unit `cqw` — inilah yang buat seluruh slaid mengecut secara berkadar bersama kad
- Jangan letak lantai `rem` dalam `clamp()` untuk saiz font (guna `min(Ncqw, Xrem)` sahaja). Lantai `rem` tak mengecut bila kad jadi kecil, dan teks akan terpotong bila telefon dipusing landscape
- Struktur `.slide` / `.slide-content` / `.slide-footer`
- Seluruh bar `.deck-nav` — butang Home ke `https://slide.taufik.fyi/`, titik penunjuk, anak panah
- Seluruh slaid CTA — termasuk petikan, tiga pautan, dan baris FOLLOW · LIKE · SHARE
- Handle `@taufik.pg` pada setiap slaid

Slaid 2–6 = ulang blok dialog lima kali dengan kandungan berbeza. Blok Deep Dive boleh guna satu `.bubble-a` besar sahaja tanpa `.bubble-q`.

**Jangan tambah balik html2canvas, butang Save PNG, atau apa-apa muat naik gambar.** Deck ini dibaca sebagai laman web; kalau Taufik nak gambar untuk Instagram, dia screenshot sendiri — dan 9:16 memang sudah saiz Reels.

### Navigasi

Bar bawah dibina oleh JavaScript kecil dalam template:

- **Home** — pautan tetap ke `https://slide.taufik.fyi/` (hub)
- **Titik** — satu bagi setiap slaid, boleh diklik untuk lompat, titik aktif melebar jadi lime
- **Anak panah** — ‹ dan ›, dimatikan (disabled) di hujung deck
- Kekunci ← dan → berfungsi sama

Jangan guna `requestAnimationFrame` untuk segerakkan titik dengan kedudukan scroll. Template segerakkan UI serta-merta dalam `goTo()` bila diklik, dan guna `setTimeout` pendek pada event scroll untuk tangkap swipe jari. Ini yang buat titik bertindak balas walaupun animasi scroll masih berjalan.

---

## Peraturan kandungan

- **Jangan sebut nama.** Tiada "Taufik", "Tuan", atau nama sesiapa dalam bubble. Soalan terus, jawapan terus.
- **Bahasa Melayu Malaysia** santai-tapi-profesional. Guna "Anda" atau "Kita", bukan "Korang". Jangan sesekali Bahasa Indonesia.
- Teks dalam bubble pendek dan padat. Jawapan panjang dipecah kepada slaid tambahan.
- Tiada nasihat pelaburan, tiada janji pulangan, tiada angka keuntungan.

---

## Langkah 4 — Hantar

**Dalam Claude Code (repo carousel):**

```
slides/<slug>/index.html     ← deck
slides/<slug>/caption.md     ← caption listicle
index.html                   ← hub, senarai semua deck
```

1. Tulis deck dan caption
2. Tambah kad baru dalam hub `index.html`
3. Commit, buka PR
4. Beritahu URL live: `https://slide.taufik.fyi/slides/<slug>/`

`<slug>` = kebab-case deskriptif: `duit-habis-hujung-bulan`, `emas-vs-asb`.

Pastikan `.nojekyll` wujud di root repo.

**Dalam chat:** tulis fail ke `/mnt/user-data/outputs/` dan panggil `present_files`. Jangan paste HTML penuh dalam chat.

### Hub

Hub di root repo guna token yang sama (grid putih, Poppins, ungu/lime) dan ia adalah destinasi butang Home. Setiap deck baru dapat satu kad:

```html
<a class="card" href="slides/<slug>/">
  <span class="card-tag">Kategori</span>
  <h2 class="card-title">Tajuk Deck</h2>
  <p class="card-desc">Satu ayat pendek tentang isi deck.</p>
  <div class="card-meta"><span>7 slaid</span><span class="card-go">Buka →</span></div>
</a>
```

---

## Caption listicle (WAJIB, setiap kali)

Selepas HTML, sentiasa hasilkan caption berasaskan 7 slaid tadi. Dalam Claude Code, simpan sebagai `caption.md` dalam folder deck yang sama.

- Bahasa Melayu Malaysia santai-profesional
- ✅ untuk setiap poin utama, emoji yang sesuai, baris kosong antara poin
- Tutup dengan CTA daftar dan lihat butiran di **https://simpanemasfizikal.com/**

---

## Senarai semak sebelum hantar

- [ ] Tepat 7 slaid
- [ ] Nisbah `9/16` kekal, tiada scroll mendatar pada `<html>`
- [ ] Bar nav bawah ada: Home ke `https://slide.taufik.fyi/`, titik, anak panah
- [ ] Slaid CTA salinan tetap, tiga pautan utuh
- [ ] `@taufik.pg` pada setiap slaid
- [ ] Tiada nama dalam mana-mana bubble
- [ ] Tiada sisa kod thumbnail (`.thumb-container`, `FileReader`, file input)
- [ ] Tiada sisa html2canvas, `.fab-save`, atau `is-capturing`
- [ ] Tiada bubble yang teksnya terpotong pada telefon kecil (uji 360×640)
- [ ] Bahasa Melayu Malaysia, bukan Indonesia
- [ ] `caption.md` disertakan
- [ ] Entry hub ditambah

---

# Lampiran A — Template Deck

Salin bulat-bulat. Slaid 2–6 diulang lima kali. Jangan ubah slaid CTA dan jangan ubah bar nav.

```html
<!DOCTYPE html>
<html lang="ms">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>{{DECK_TITLE}} | Slide Emas By Taufik</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
:root{
  --brand-purple:#5A3EE0;
  --brand-lime:#CEFE1D;
  --brand-yellow:#FFCE32;
  --bg-base:#EAEDF1;
  --grid-line:#FFFFFF;
  --card-white:#FFFFFF;
  --text-dark:#111827;
  --text-muted:#6B7280;
  --nav-h:68px;
}
*{box-sizing:border-box}
html,body{margin:0;padding:0;height:100%;font-family:'Poppins',sans-serif;background:#1a1a1a;overflow:hidden}
.deck{display:flex;flex-direction:row;height:calc(100dvh - var(--nav-h));overflow-x:scroll;overflow-y:hidden;scroll-snap-type:x mandatory;-webkit-overflow-scrolling:touch;scroll-behavior:smooth}
.deck::-webkit-scrollbar{display:none}
.slide-wrap{flex:0 0 100vw;height:calc(100dvh - var(--nav-h));display:flex;align-items:center;justify-content:center;scroll-snap-align:start}
.slide{
  height:min(96%, calc(94vw * 16 / 9));
  aspect-ratio:9/16;max-width:94vw;
  container-type:inline-size;
  display:flex;flex-direction:column;padding:7cqw 6cqw;box-sizing:border-box;overflow:hidden;position:relative;
  background-color:var(--bg-base);
  background-image:linear-gradient(var(--grid-line) 1.5px, transparent 1.5px),linear-gradient(90deg, var(--grid-line) 1.5px, transparent 1.5px);
  background-size:35px 35px;background-position:center center;
  border-radius:14px;
}
.slide-content{flex:1;display:flex;flex-direction:column;justify-content:center;gap:3cqw;width:100%;min-height:0;position:relative;z-index:1}
.slide-footer{flex-shrink:0;display:flex;flex-direction:column;align-items:center;justify-content:flex-end;gap:1.6cqw;padding-top:3cqw;margin-top:auto;z-index:20}
.headline{font-weight:800;color:var(--text-dark);font-size:min(9cqw,2.8rem);line-height:1.2;letter-spacing:-.02em;margin:0 0 3cqw;text-align:left}
.headline .accent{background-color:var(--brand-lime);color:var(--text-dark);padding:0 min(2cqw,8px);border-radius:6px;display:inline-block;line-height:1.1;margin-top:5px}
.sub-text{color:var(--text-muted);font-size:min(3.6cqw,1.05rem);line-height:1.5;margin:0}
.bubble-q{align-self:flex-start;background:var(--card-white);border-radius:0 18px 18px 18px;padding:4cqw 5cqw;color:var(--text-dark);font-weight:600;font-size:min(4.4cqw,1.3rem);line-height:1.4;max-width:90%;box-shadow:0 3px 10px rgba(0,0,0,.04)}
.bubble-a{align-self:flex-end;background:var(--brand-purple);border-radius:18px 0 18px 18px;padding:4cqw 5cqw;color:#fff;font-weight:400;font-size:min(4.1cqw,1.2rem);line-height:1.5;max-width:90%;box-shadow:0 4px 15px rgba(90,62,224,.2)}
.counter-pill{background:var(--card-white);border:1px solid rgba(0,0,0,.05);color:var(--text-dark);font-weight:700;padding:.8cqw 2.4cqw;border-radius:999px;font-size:min(3cqw,.75rem);box-shadow:0 2px 10px rgba(0,0,0,.02)}
.swipe-pill{display:inline-flex;align-items:center;gap:.4rem;background:var(--brand-lime);color:var(--text-dark);font-weight:800;font-size:min(2.6cqw,.65rem);padding:.8cqw 2.4cqw;border-radius:999px;text-transform:uppercase}
.card-handle{display:inline-block;font-weight:600;font-size:min(2.8cqw,.7rem);color:var(--text-muted)}
.cta-quote{font-style:italic;color:var(--text-dark);font-size:min(3.8cqw,1.1rem);line-height:1.6;margin:1.5cqw 0 3.5cqw;padding-left:2.5cqw;border-left:3px solid var(--brand-lime)}
.cta-links{display:flex;flex-direction:column;gap:1.6cqw;width:100%}
.cta-btn{display:flex;align-items:center;justify-content:center;gap:1.4cqw;text-decoration:none;font-weight:700;font-size:min(3.6cqw,1rem);padding:2.4cqw 2.8cqw;border-radius:12px;transition:transform .1s}
.cta-btn:active{transform:scale(.98)}
.cta-wa{background:#25D366;color:#fff;box-shadow:0 4px 14px rgba(37,211,102,.3)}
.cta-web{background:var(--brand-purple);color:#fff;box-shadow:0 4px 14px rgba(90,62,224,.25)}
.cta-alt{background:var(--card-white);color:var(--text-dark);border:1.5px solid rgba(0,0,0,.08)}
.cta-follow{font-weight:800;color:var(--brand-purple);font-size:min(3.4cqw,.85rem);letter-spacing:.04em;text-align:center;margin-top:2.5cqw}

/* --- NAV BAWAH --- */
.deck-nav{position:fixed;left:0;right:0;bottom:0;height:var(--nav-h);display:flex;align-items:center;justify-content:space-between;gap:.75rem;padding:0 clamp(.75rem,3vw,1.5rem);padding-bottom:env(safe-area-inset-bottom);background:rgba(17,17,17,.92);backdrop-filter:blur(10px);border-top:1px solid rgba(255,255,255,.07);z-index:50}
.nav-home{display:inline-flex;align-items:center;gap:.4rem;flex-shrink:0;background:var(--brand-lime);color:var(--text-dark);font-family:inherit;font-weight:800;font-size:.7rem;letter-spacing:.04em;text-transform:uppercase;padding:.6rem 1rem;border-radius:999px;text-decoration:none;transition:transform .1s}
.nav-home:active{transform:scale(.96)}
.nav-dots{display:flex;align-items:center;gap:.4rem;flex:1;justify-content:center;overflow:hidden}
.nav-dot{width:8px;height:8px;flex-shrink:0;padding:0;border:none;border-radius:999px;background:rgba(255,255,255,.28);cursor:pointer;transition:width .2s,background .2s}
.nav-dot.is-active{width:24px;background:var(--brand-lime)}
.nav-arrows{display:flex;gap:.45rem;flex-shrink:0}
.nav-arrow{width:40px;height:40px;display:flex;align-items:center;justify-content:center;border:none;border-radius:999px;background:var(--brand-purple);color:#fff;font-family:inherit;font-size:1.15rem;line-height:1;cursor:pointer;transition:transform .1s,opacity .2s}
.nav-arrow:active{transform:scale(.94)}
.nav-arrow:disabled{opacity:.3;cursor:default}
@media (max-width:420px){
  .nav-home span{display:none}
  .nav-home{padding:.6rem .8rem;font-size:.9rem}
}
</style>
</head>
<body>

<div class="deck" id="deck">

  <!-- SLIDE 1 — HOOK -->
  <div class="slide-wrap"><div class="slide">
    <div class="slide-content">
      <h1 class="headline">{{HOOK_LINE}} <span class="accent">{{HOOK_ACCENT}}</span></h1>
      <p class="sub-text">{{HOOK_SUB}}</p>
    </div>
    <div class="slide-footer">
      <span class="swipe-pill">Swipe →</span>
      <span class="counter-pill"><span class="counter-current">1</span> / <span class="counter-total">7</span></span>
      <span class="card-handle">@taufik.pg</span>
    </div>
  </div></div>

  <!-- SLIDES 2-6 — DIALOG / DEEP DIVE (ulang blok ini 5 kali) -->
  <div class="slide-wrap"><div class="slide">
    <div class="slide-content">
      <div class="bubble-q">{{QUESTION}}</div>
      <div class="bubble-a">{{ANSWER}}</div>
    </div>
    <div class="slide-footer">
      <span class="swipe-pill">Swipe →</span>
      <span class="counter-pill"><span class="counter-current">2</span> / <span class="counter-total">7</span></span>
      <span class="card-handle">@taufik.pg</span>
    </div>
  </div></div>

  <!-- SLIDE 7 — CTA (SALIN BULAT-BULAT, JANGAN UBAH PAUTAN) -->
  <div class="slide-wrap"><div class="slide">
    <div class="slide-content">
      <h1 class="headline">Mula Simpan <span class="accent">Emas</span></h1>
      <p class="cta-quote">"Ingat, kekayaan bukan tentang berapa besar gaji kita, tapi tentang berapa lama kita boleh bertahan bila gaji itu tiada."</p>
      <div class="cta-links">
        <a class="cta-btn cta-wa" href="https://wa.me/60132740711?text=Salam,%20boleh%20bantu%20saya%20simpan%20emas%20di%20Public%20Gold%20-%20Dari%20Slide" target="_blank" rel="noopener">WhatsApp Saya</a>
        <a class="cta-btn cta-web" href="https://simpanemasfizikal.com/" target="_blank" rel="noopener">simpanemasfizikal.com</a>
        <a class="cta-btn cta-alt" href="https://pg2u.my/taufikmusa" target="_blank" rel="noopener">Daftar Public Gold</a>
      </div>
      <p class="cta-follow">FOLLOW · LIKE · SHARE</p>
    </div>
    <div class="slide-footer">
      <span class="counter-pill"><span class="counter-current">7</span> / <span class="counter-total">7</span></span>
      <span class="card-handle">@taufik.pg</span>
    </div>
  </div></div>

</div>

<nav class="deck-nav">
  <a class="nav-home" href="https://slide.taufik.fyi/">⌂ <span>Home</span></a>
  <div class="nav-dots" id="nav-dots"></div>
  <div class="nav-arrows">
    <button class="nav-arrow" id="nav-prev" type="button" aria-label="Slaid sebelum">‹</button>
    <button class="nav-arrow" id="nav-next" type="button" aria-label="Slaid seterusnya">›</button>
  </div>
</nav>

<script>
document.addEventListener("DOMContentLoaded", () => {
  const deck = document.getElementById('deck');
  const wraps = document.querySelectorAll('.slide-wrap');
  const dotsBox = document.getElementById('nav-dots');
  const prevBtn = document.getElementById('nav-prev');
  const nextBtn = document.getElementById('nav-next');
  const total = wraps.length;
  let index = 0;
  let settle;

  wraps.forEach((w, i) => {
    const cur = w.querySelector('.counter-current');
    const tot = w.querySelector('.counter-total');
    if (cur) cur.textContent = i + 1;
    if (tot) tot.textContent = total;
    if (i === total - 1) {
      const sp = w.querySelector('.swipe-pill');
      if (sp) sp.style.display = 'none';
    }
    const dot = document.createElement('button');
    dot.className = 'nav-dot';
    dot.type = 'button';
    dot.setAttribute('aria-label', 'Slaid ' + (i + 1));
    dot.addEventListener('click', () => goTo(i));
    dotsBox.appendChild(dot);
  });

  const dots = dotsBox.querySelectorAll('.nav-dot');

  function setUI(i) {
    index = i;
    dots.forEach((d, n) => d.classList.toggle('is-active', n === i));
    prevBtn.disabled = i === 0;
    nextBtn.disabled = i === total - 1;
  }

  function goTo(i) {
    const target = Math.max(0, Math.min(total - 1, i));
    setUI(target);
    deck.scrollTo({ left: target * wraps[0].offsetWidth, behavior: 'smooth' });
  }

  setUI(0);

  deck.addEventListener('scroll', () => {
    clearTimeout(settle);
    settle = setTimeout(() => {
      const i = Math.round(deck.scrollLeft / wraps[0].offsetWidth);
      if (i !== index) setUI(i);
    }, 90);
  }, { passive: true });

  window.addEventListener('resize', () => {
    deck.scrollTo({ left: index * wraps[0].offsetWidth, behavior: 'instant' });
  });

  prevBtn.addEventListener('click', () => goTo(index - 1));
  nextBtn.addEventListener('click', () => goTo(index + 1));
  document.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowRight') goTo(index + 1);
    if (e.key === 'ArrowLeft') goTo(index - 1);
  });
});
</script>
</body>
</html>
```
