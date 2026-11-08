# Rideradian Motor Website

## Update hero & navbar (Oktober 2026)

**Hero (index.html)** — dikendalikan penuh oleh scroll, kode ada di `js/hero-preserved.js` dan `css/hero-preserved.css`:
1. 120 frame motor dimainkan saat scroll (gelap → lampu menyala → studio abu).
2. Foto motor silver (studio abu yang sama dengan frame terakhir) menyatu di layar penuh dan melayang pelan.
3. Layar mengecil menjadi kartu di kanan; judul "Rideradian EXR" + daftar fitur muncul di kiri.
4. Scroll lanjut: daftar bergeser, gambar di kartu berganti (silver → detail → dst; semua foto motor kini silver).

**Teks hero** ("RIDE BEYOND LIMITS", spesifikasi, "Teknologi yang bergerak bersama kamu"):
- tidak ada saat halaman baru dibuka,
- hilang selama scroll,
- muncul lagi saat scroll berhenti.

**Navbar**
- Desktop: pill mengambang di atas (seperti sebelumnya).
- HP/tablet (≤ 900px): dock di bagian bawah layar dengan ikon + label, tab aktif berwarna kuning, aman untuk notch (safe-area).

## Mengubah isi
- Daftar fitur & gambar kartu: bagian `.sc-list` dan `.sc-card` di `index.html`; caption ada di array `captions` di `js/hero-preserved.js`.
- Panjang animasi: `height` pada `.hero-scroll` di `css/hero-preserved.css` (makin tinggi = makin lambat).
- Nama, harga, spesifikasi katalog: `js/data.js`.

## Menjalankan
Buka `index.html` langsung, atau `python3 -m http.server 8080` lalu buka `http://localhost:8080`.
Upload seluruh isi folder (termasuk 120 frame di `assets/images/hero-sequence/`) saat hosting.

## Update halaman Produk (Oktober 2026)
Halaman `produk.html` dirombak jadi gaya aplikasi gelap: banner produk unggulan, tombol filter ikon (Semua / Motor / Helm), dan kartu produk kecil dengan tombol favorit. Klik kartu untuk membuka detail. Gaya ada di bagian akhir `css/style.css`, render kartu di `js/script.js` (bagian `data-render="products"`).

## Update bagian "Kami percaya motor yang hebat…" (Oktober 2026)
Bagian teks besar di beranda diganti jadi section scroll bergaya video:
1. Tulisan **RIDERADIAN** berisi video (video mengintip lewat huruf).
2. Scroll → tulisan zoom masuk ke huruf "D" sampai video memenuhi layar.
3. Video penuh sebentar, lalu naik ke atas; di bawahnya muncul teks keyakinan, kata demi kata menyala.

File: `css/manifesto.css`, `js/manifesto.js`, bagian `#manifesto` di `index.html`.
Ganti video: timpa `assets/video/manifesto.mp4` (+ `manifesto-poster.jpg`). Panjang animasi: `height` pada `.mf` di `css/manifesto.css`.
Jika perangkat memakai "reduce motion", bagian ini tampil sebagai video biasa + teks.

## Update v8 (Oktober 2026) — logo, gelombang, isi beranda
- **Logo baru**: `assets/images/logo-word.png` (navbar), `logo-circle.png` (loader & footer), `favicon.ico`, `apple-touch-icon.png`, `og.jpg`. Ganti gambar-gambar ini untuk mengubah logo.
- **Gelombang baru**: `js/waves.js` + `css/v9.css`. Semua gelombang lama (SVG, zigzag, lengkung, canvas lama) diganti satu sistem canvas yang halus, tajam di layar retina, berhenti saat tidak terlihat, dan statis jika "reduce motion". Pakai: `<div class="wv" data-to="#f3f1ea" data-back="..." data-mid="..."></div>`; garis detak: `<div class="wv-ecg"></div>`.
- **Beranda**: bagian "Kenapa Rideradian" jadi bento, strip spesifikasi di Teknologi, section baru "Dari sketsa ke jalur", testimoni dengan kutipan utama, CTA dua tombol.
- **Tidak diubah**: animasi hero paling atas (`hero-preserved.*`) dan section video "Kami percaya…" (`manifesto.*`).

## Update v8.1 — halaman Produk
Panel "Pilih Motor Kamu" memakai satu palet (hitam arang + kuning volt). Blok abu-abu miring dihapus, semua kartu sewarna, teks tidak lagi miring. Gaya ada di bagian akhir `css/v9.css`.


## Update v8.4 — semua motor jadi silver
- Seluruh foto motor kuning (gallery 01/03/04/05/07/08, products r1/rs, articles 03) diwarnai ulang menjadi silver titanium; fork emas dan lampu tetap.
- Slide "Tenaga instan" di showcase EXR memakai gambar baru `assets/images/exr-tenaga-instan.webp`.
- Produk "EXR Volt" (kuning) tetap ada di menu produk bersama EXR Titanium dan 2 helm Airoh.
- Warna aksen kuning pada UI (tombol, garis) dan helm kuning tidak diubah.

## Update v8.6 — Artikel
- Gambar artikel memakai 3 desain baru (`assets/images/articles/<id>.webp` + versi `-sm`).
- Tombol "Baca selengkapnya" diganti gaya baru (pill + ikon panah, isi hitam menyapu naik saat hover); gayanya ada di akhir `css/v9.css`.
