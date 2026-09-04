---
name: slide-emas-web
description: >
  Hasilkan deck carousel 7 slaid gaya perbualan WhatsApp (Slide Emas By Taufik) sebagai SATU fail
  HTML yang di-host — boleh di-screenshot untuk Instagram dan dihantar sebagai pautan hidup. Guna
  skill ini bila Taufik sebut "buat slide emas", "carousel emas", "deck emas", "slide web", "slide
  emas web", "buat carousel untuk repo", atau bila dia paste pautan YouTube, artikel, atau idea
  mentah dan mahu ia jadi Q&A carousel emas. Skill ini TIADA fungsi muat naik gambar/thumbnail, dan
  slaid CTA terakhirnya mengandungi tiga pautan hidup (WhatsApp, simpanemasfizikal.com,
  pg2u.my/taufikmusa). BERBEZA daripada slide-chat-gold (ada thumbnail gambar), slide-chat (tiada
  CTA pautan), emas-slide-style (kad putih rata Montserrat), colourfull-slide-style (gradient), dan
  html-doodle (sticker doodle) — jangan campur token atau layout antara skill-skill ini.
---


# Slide Emas Web

Deck carousel 7 slaid gaya perbualan WhatsApp untuk Taufik Bin Musa, Dealer Public Gold G100 Network (PG00359605). Satu fail HTML, di-host atas GitHub Pages, boleh di-screenshot untuk Instagram **dan** dihantar sebagai pautan hidup.

Beza dengan versi Gems lama: **tiada muat naik gambar** (dibuang sepenuhnya), dan slaid CTA ada **tiga pautan boleh klik**.

---

## Langkah 1 — Kenal pasti sumber

Taufik akan bagi salah satu:

| Input | Cara proses |
|---|---|
| Pautan YouTube | Tonton/analisis. Cabut SATU fakta atau pengajaran paling kuat berkaitan wang. |
| Artikel (pautan atau teks) | Baca. Cabut hujah teras atau satu titik kesakitan penonton. |
| Idea mentah / transkrip voice note | Guna terus. Titik utama jadi hook. |

**Langkah dalaman pertama sentiasa sama:** kenal pasti SATU titik kesakitan, kemudian tulis semula segalanya jadi dialog dua hala (Pengikut lawan Anda). Jangan sesekali terus bina slaid tanpa langkah tulis semula ini.

Kalau ada fakta, sejarah, harga atau angka — sahkan dahulu. Jangan reka statistik.

---

## Langkah 2 — Struktur deck (SENTIASA 7 SLAID)

1. **Hook / Tajuk** — 1 slaid
2. **Dialog / Deep Dive** — 5 slaid
3. **CTA / Penutup** — 1 slaid, salinan tetap (lihat Lampiran A)

Jangan hasilkan lebih atau kurang daripada 7 melainkan Taufik minta jumlah lain. Kalau satu jawapan terlalu panjang, pecah kepada dua slaid — jangan biar teks terpotong.

---

## Langkah 3 — Bina

Mula daripada template dalam **Lampiran A**. Jangan tulis dari kosong.

Yang boleh ditukar: teks dalam `.headline`, `.sub-text`, `.bubble-q`, `.bubble-a`, dan `{{DECK_TITLE}}`.

Yang **tidak boleh** disentuh:
- Semua token warna, `background-image` grid putih, font Poppins
- Struktur `.slide` / `.slide-content` / `.slide-footer`
- Seluruh slaid CTA — termasuk petikan, tiga pautan, dan baris FOLLOW · LIKE · SHARE
- Handle `@taufik.pg` pada setiap slaid
- `scale: 4` dalam html2canvas

Slaid 2–6 = ulang blok dialog lima kali dengan kandungan berbeza. Blok Deep Dive boleh guna satu `.bubble-a` besar sahaja tanpa `.bubble-q`.

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
4. Beritahu URL live: `https://<user>.github.io/<repo>/slides/<slug>/`

`<slug>` = kebab-case deskriptif: `duit-habis-hujung-bulan`, `emas-vs-asb`.

Pastikan `.nojekyll` wujud di root repo.

**Dalam chat:** tulis fail ke `/mnt/user-data/outputs/` dan panggil `present_files`. Jangan paste HTML penuh dalam chat.

---

## Caption listicle (WAJIB, setiap kali)

Selepas HTML, sentiasa hasilkan caption berasaskan 7 slaid tadi. Dalam Claude Code, simpan sebagai `caption.md` dalam folder deck yang sama.

- Bahasa Melayu Malaysia santai-profesional
- ✅ untuk setiap poin utama, emoji yang sesuai, baris kosong antara poin
- Tutup dengan CTA daftar dan lihat butiran di **https://simpanemasfizikal.com/**

---

## Senarai semak sebelum hantar

- [ ] Tepat 7 slaid
- [ ] Slaid CTA salinan tetap, tiga pautan utuh
- [ ] `@taufik.pg` pada setiap slaid
- [ ] Tiada nama dalam mana-mana bubble
- [ ] Tiada sisa kod thumbnail (`.thumb-container`, `FileReader`, file input)
- [ ] Bahasa Melayu Malaysia, bukan Indonesia
- [ ] `caption.md` disertakan
- [ ] Entry hub ditambah

---

# Lampiran A — Template Deck

Salin bulat-bulat. Slaid 2–6 diulang lima kali. Jangan ubah slaid CTA.

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
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
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
}
*{box-sizing:border-box}
html,body{margin:0;padding:0;height:100%;font-family:'Poppins',sans-serif;background:#1a1a1a;overflow:hidden}
.deck{display:flex;flex-direction:row;height:100dvh;overflow-x:scroll;overflow-y:hidden;scroll-snap-type:x mandatory;-webkit-overflow-scrolling:touch;scroll-behavior:smooth}
.deck::-webkit-scrollbar{display:none}
.slide-wrap{flex:0 0 100vw;height:100dvh;display:flex;align-items:center;justify-content:center;scroll-snap-align:start}
.slide{
  width:min(94vw, calc(94dvh * 4 / 5));
  aspect-ratio:4/5;max-width:94vw;max-height:94dvh;
  display:flex;flex-direction:column;padding:2rem 1.5rem;box-sizing:border-box;overflow:hidden;position:relative;
  background-color:var(--bg-base);
  background-image:linear-gradient(var(--grid-line) 1.5px, transparent 1.5px),linear-gradient(90deg, var(--grid-line) 1.5px, transparent 1.5px);
  background-size:35px 35px;background-position:center center;
  border-radius:14px;
}
.slide-content{flex:1;display:flex;flex-direction:column;justify-content:center;gap:1rem;width:100%;min-height:0;position:relative;z-index:1}
.slide-footer{flex-shrink:0;display:flex;flex-direction:column;align-items:center;justify-content:flex-end;gap:.6rem;padding-top:1rem;margin-top:auto;z-index:20}
.headline{font-weight:800;color:var(--text-dark);font-size:clamp(1.8rem,7vw,2.6rem);line-height:1.2;letter-spacing:-.02em;margin:0 0 1rem;text-align:left}
.headline .accent{background-color:var(--brand-lime);color:var(--text-dark);padding:0 8px;border-radius:6px;display:inline-block;line-height:1.1;margin-top:5px}
.sub-text{color:var(--text-muted);font-size:.95rem;line-height:1.5;margin:0}
.bubble-q{align-self:flex-start;background:var(--card-white);border-radius:0 18px 18px 18px;padding:1.2rem 1.5rem;color:var(--text-dark);font-weight:600;font-size:1.1rem;line-height:1.4;max-width:88%;box-shadow:0 3px 10px rgba(0,0,0,.04)}
.bubble-a{align-self:flex-end;background:var(--brand-purple);border-radius:18px 0 18px 18px;padding:1.2rem 1.5rem;color:#fff;font-weight:400;font-size:1.05rem;line-height:1.5;max-width:88%;box-shadow:0 4px 15px rgba(90,62,224,.2)}
.counter-pill{background:var(--card-white);border:1px solid rgba(0,0,0,.05);color:var(--text-dark);font-weight:700;padding:.3rem .9rem;border-radius:999px;font-size:.75rem;box-shadow:0 2px 10px rgba(0,0,0,.02)}
.swipe-pill{display:inline-flex;align-items:center;gap:.4rem;background:var(--brand-lime);color:var(--text-dark);font-weight:800;font-size:.65rem;padding:.3rem .9rem;border-radius:999px;text-transform:uppercase}
.card-handle{display:inline-block;font-weight:600;font-size:.7rem;color:var(--text-muted)}
.cta-quote{font-style:italic;color:var(--text-dark);font-size:1rem;line-height:1.6;margin:.5rem 0 1.2rem;padding-left:.9rem;border-left:3px solid var(--brand-lime)}
.cta-links{display:flex;flex-direction:column;gap:.6rem;width:100%}
.cta-btn{display:flex;align-items:center;justify-content:center;gap:.5rem;text-decoration:none;font-weight:700;font-size:.9rem;padding:.85rem 1rem;border-radius:12px;transition:transform .1s}
.cta-btn:active{transform:scale(.98)}
.cta-wa{background:#25D366;color:#fff;box-shadow:0 4px 14px rgba(37,211,102,.3)}
.cta-web{background:var(--brand-purple);color:#fff;box-shadow:0 4px 14px rgba(90,62,224,.25)}
.cta-alt{background:var(--card-white);color:var(--text-dark);border:1.5px solid rgba(0,0,0,.08)}
.cta-follow{font-weight:800;color:var(--brand-purple);font-size:.85rem;letter-spacing:.04em;text-align:center;margin-top:.9rem}
.fab-save{position:fixed;bottom:24px;right:24px;background:var(--brand-purple);color:#fff;border:none;border-radius:999px;padding:12px 20px;font-family:'Poppins',sans-serif;font-weight:700;font-size:.9rem;box-shadow:0 4px 15px rgba(90,62,224,.4);cursor:pointer;z-index:9999;display:flex;align-items:center;gap:8px;transition:transform .1s ease}
.fab-save:active{transform:scale(.95)}
body.is-capturing .fab-save{opacity:0}
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

<button id="save-btn" class="fab-save" onclick="simpanSlideSemasa()">📸 <span id="save-text">Save PNG</span></button>

<script>
document.addEventListener("DOMContentLoaded", () => {
  const wraps = document.querySelectorAll('.slide-wrap');
  const total = wraps.length;
  wraps.forEach((w, i) => {
    const cur = w.querySelector('.counter-current');
    const tot = w.querySelector('.counter-total');
    if (cur) cur.textContent = i + 1;
    if (tot) tot.textContent = total;
    if (i === total - 1) {
      const sp = w.querySelector('.swipe-pill');
      if (sp) sp.style.display = 'none';
    }
  });
  document.addEventListener('keydown', (e) => {
    const deck = document.getElementById('deck');
    const idx = Math.round(deck.scrollLeft / wraps[0].offsetWidth);
    if (e.key === 'ArrowRight' && idx < total - 1) wraps[idx + 1].scrollIntoView({behavior:'smooth'});
    if (e.key === 'ArrowLeft' && idx > 0) wraps[idx - 1].scrollIntoView({behavior:'smooth'});
  });
});

async function simpanSlideSemasa() {
  const deck = document.getElementById('deck');
  const wraps = document.querySelectorAll('.slide-wrap');
  const slideWidth = wraps[0].offsetWidth;
  const currentIndex = Math.round(deck.scrollLeft / slideWidth);
  const slideAktif = wraps[currentIndex].querySelector('.slide');
  const btn = document.getElementById("save-btn");
  const btnText = document.getElementById("save-text");
  const originalText = btnText.innerText;
  btnText.innerText = "Saving...";
  btn.style.pointerEvents = "none";
  document.body.classList.add('is-capturing');
  const reset = () => {
    document.body.classList.remove('is-capturing');
    btnText.innerText = originalText;
    btn.style.pointerEvents = "auto";
  };
  try {
    const canvas = await html2canvas(slideAktif, {
      scale: 4,
      backgroundColor: null,
      useCORS: true,
      allowTaint: true,
      width: slideAktif.offsetWidth,
      height: slideAktif.offsetHeight
    });
    canvas.toBlob(function(blob) {
      if (!blob) { alert("Ops, gagal save."); reset(); return; }
      const url = window.URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.style.display = 'none';
      a.href = url;
      a.download = 'Slide-Emas-' + (currentIndex + 1) + '.png';
      document.body.appendChild(a);
      a.click();
      setTimeout(() => {
        document.body.removeChild(a);
        window.URL.revokeObjectURL(url);
      }, 200);
      reset();
    }, 'image/png');
  } catch (err) {
    console.error(err);
    alert("Ops, gagal save.");
    reset();
  }
}
</script>
</body>
</html>
```
