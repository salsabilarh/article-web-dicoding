# 🧠 Berpikir Out of The Box — Artikel Pengembangan Diri

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![Responsive](https://img.shields.io/badge/Responsive-Design-brightgreen?style=for-the-badge)
![Dicoding](https://img.shields.io/badge/Dicoding-Submission-4285F4?style=for-the-badge)
![Score](https://img.shields.io/badge/Score-5%2F5_%E2%98%85-FFD700?style=for-the-badge)
![Learning Path](https://img.shields.io/badge/Frontend_Web-Learning_Path_Stage_1-orange?style=for-the-badge&logo=dicoding)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

> ⭐ **Submission akhir kursus "Belajar Dasar Pemrograman Web"** — tahap pertama dari *Frontend Web Learning Path* Dicoding.  
> Halaman artikel yang terstruktur secara semantik, responsif penuh, dan siap diperluas dengan JavaScript. **Skor sempurna 5/5** dari tim reviewer.

---

## 📖 Daftar Isi

- [Ringkasan Eksekutif](#ringkasan-eksekutif)
- [✨ Fitur Utama](#-fitur-utama)
- [🛠️ Tech Stack](#️-tech-stack)
- [🏗️ Arsitektur & Pendekatan Teknis](#️-arsitektur--pendekatan-teknis)
- [🚀 Cara Instalasi & Penggunaan](#-cara-instalasi--penggunaan-lokal)
- [📚 Pelajaran Teknis — What I Learned](#-pelajaran-teknis--what-i-learned)
- [📄 Lisensi](#-lisensi)

---

## Ringkasan Eksekutif

Proyek ini adalah halaman artikel bertema *self-development* yang dibangun **dari nol** menggunakan **HTML5 dan CSS3 murni** — tanpa framework, tanpa library, tanpa *shortcut*.

> 🎯 **Tujuan utama:** Bukan sekadar membuat halaman yang "jadi", melainkan membuktikan pemahaman mendalam atas **fondasi web yang benar**:
> - Hierarki elemen semantik yang dapat dibaca mesin
> - Sistem tata letak yang stabil di semua ukuran layar 📱💻🖥️
> - Kode terorganisasi agar mudah diperluas di iterasi berikutnya 🔁

---

## Fitur Utama

### Kegunaan (Usability)

| Fitur | Deskripsi |
|-------|------------|
| 🔝 **Navigasi Sticky** | `nav` tetap terlihat saat scroll — pengguna selalu punya akses navigasi tanpa harus scroll ke atas |
| 🔗 **In-Page Anchor Links** | Daftar isi yang dapat diklik langsung membawa ke section terkait (`#cara1` s/d `#cara7`) |
| 📰 **Layout Dua Kolom** | Konten artikel (3 bagian) + sidebar profil penulis tampil berdampingan pada layar lebar, nyaman dibaca |
| 👤 **Foto Profil Circular** | Sidebar menampilkan identitas penulis lengkap dengan foto bundar dan tabel informasi terstruktur |

### Keandalan (Reliability)

| Fitur | Deskripsi |
|-------|------------|
| 📱 **Fully Responsive** | Tiga *breakpoint* terpisah: desktop (>900px), tablet (≤900px), mobile (≤600px) — menggunakan CSS Flexbox murni, bukan `float` yang rapuh |
| 🔄 **CSS Reset Universal** | `* { box-sizing: border-box; margin: 0; padding: 0; }` mencegah inkonsistensi rendering lintas browser |
| 🖼️ **Gambar Adaptif** | `width: 100%; object-fit: cover;` memastikan gambar tidak pernah keluar dari *container* di layar apapun |
| 🔤 **External Font Fallback** | `font-family: 'Source Serif Pro', Georgia, serif;` — jika Google Fonts gagal dimuat, halaman tetap terbaca dengan degradasi elegan |


---

## Tech Stack

```
📁 Teknologi
├── HTML5          — Struktur & konten semantik
└── CSS3
    ├── Flexbox    — Sistem layout utama (bukan Float)
    ├── Media Query — Responsivitas 2 breakpoint
    ├── Position Sticky — Navigasi persisten
    └── Transition  — Micro-interaction hover pada card
```

**Ketergantungan Eksternal:**
- [Google Fonts](https://fonts.google.com/) — `Source Serif Pro` (editorial serif typeface)
- Tidak ada npm package, tidak ada build tool — dapat dibuka langsung di browser

---

## Arsitektur & Pendekatan Teknis

### Struktur Semantik HTML5

Halaman ini menggunakan elemen semantik HTML5 secara konsisten, bukan hanya `<div>` generik. Setiap elemen dipilih berdasarkan *maknanya*, bukan penampilannya:

```
<body>
├── <header>              ← Area branding & navigasi
│   ├── .jumbotron        ← Hero section
│   └── <nav>             ← Menu navigasi (sticky)
├── <main>                ← Flex container utama
│   ├── <div #content>    ← Area konten primer (flex: 3)
│   │   └── <article>     ← Setiap poin artikel berdiri sendiri
│   └── <aside>           ← Informasi sekunder/profil (flex: 1)
│       └── <figure>      ← Gambar + caption yang terikat semantik
└── <footer>              ← Informasi hak cipta
```

Struktur yang semantik adalah prasyarat agar **DOM Manipulation** dengan JavaScript di masa depan dapat dilakukan secara efisien. Selektor seperti `document.querySelector('article#cara3')` jauh lebih andal daripada mengandalkan urutan `div` yang tidak bermakna.

### Sistem Layout: Flexbox (bukan Float)

Layout dua kolom dibangun murni dengan CSS Flexbox:

```css
/* Flex container — main layout */
main {
    display: flex;
    flex-wrap: wrap;   /* Bungkus otomatis di layar kecil */
    gap: 30px;
}

#content { flex: 3; min-width: 260px; }  /* Artikel: 75% ruang */
aside    { flex: 1; min-width: 250px; }  /* Sidebar: 25% ruang */
```

`flex-wrap: wrap` dengan `min-width` adalah mekanisme responsif yang bekerja tanpa `if-else` di media query — layout otomatis berkolom satu saat ruang tidak cukup. Media query hanya digunakan untuk fine-tuning tipografi dan spacing spesifik per breakpoint.

---

## Cara Instalasi & Penggunaan Lokal

Proyek ini tidak memerlukan build tool, server lokal, atau instalasi apapun.

**Opsi 1 — Buka Langsung:**
```bash
# Clone repositori
git clone https://github.com/salsabilarh/article-web-dicoding.git

# Masuk ke folder
cd article-web-dicoding

# Buka index.html di browser
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

**Opsi 2 — Via VS Code Live Server:**
1. Install ekstensi [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) di VS Code
2. Klik kanan `index.html` → **"Open with Live Server"**
3. Browser akan membuka `http://127.0.0.1:5500`

**Struktur Folder:**
```
submission-web-dicoding/
├── index.html          ← Entry point utama
├── style.css           ← Semua styling (satu file, terorganisir per section)
└── assets/
    ├── profile.jpg     ← Foto profil penulis
    ├── books.jpg
    ├── alone.jpg
    ├── do.png
    ├── world.png
    ├── kreatif.jpg
    ├── critical.jpg
    └── design-thinking.png
```

---

## Pelajaran Teknis — What I Learned

### 1. Penulisan Kode yang Bersih (Clean Code)

CSS terorganisasi dalam blok bernama dengan komentar yang konsisten (`/* ===== HEADER ===== */`, `/* ===== NAVIGASI ===== */`), bukan satu blok monolitik. Ini bukan sekadar estetika — ini tentang **maintainability**: developer lain (atau diri sendiri 6 bulan ke depan) dapat menemukan dan memodifikasi section tertentu dalam hitungan detik.

Hal yang sama berlaku pada HTML: atribut `alt` pada setiap `<img>` bukan formalitas, melainkan kebiasaan yang mencerminkan pemahaman bahwa kode web dikonsumsi bukan hanya oleh manusia, tetapi juga oleh screen reader, crawler, dan parser lainnya.

### 2. CSS Flexbox sebagai Fondasi Layout Modern

Memahami `flex`, `flex-wrap`, `gap`, dan `min-width` secara mendalam — bukan hanya copy-paste — mengubah cara berpikir tentang layout. Flexbox *mendeklarasikan niat* ("elemen-elemen ini berbagi ruang secara proporsional"), bukan *menginstruksikan posisi* seperti float. Pola pikir deklaratif ini sangat mirip dengan cara kerja framework modern seperti React atau Vue dalam mengelola state.

### 3. Responsivitas sebagai Perilaku, Bukan Afterthought

Menggunakan `flex-wrap` + `min-width` sebagai mekanisme responsivitas *intrinsik* sebelum media query — artinya layout yang benar di banyak kondisi tanpa menulis banyak kode. Media query hanya untuk koreksi spesifik. Ini adalah prinsip **Progressive Enhancement**: mulai dari yang paling dasar dan benar, kemudian tingkatkan.

### 4. HTML Semantik sebagai Fondasi API Consumption

Struktur DOM yang semantik adalah **kontrak implisit** yang memudahkan semua lapisan di atasnya. Ketika nanti mengonsumsi RESTful API — misalnya endpoint `/api/articles` yang mengembalikan array JSON — JavaScript hanya perlu me-*render* data ke dalam template `<article>` yang sudah ada. Pemisahan antara **struktur** (HTML), **presentasi** (CSS), dan **perilaku** (JS) yang dipraktikkan di sini adalah implementasi nyata dari prinsip Separation of Concerns yang sama-sama berlaku di arsitektur backend.

---

## Lisensi

Proyek ini dibuat sebagai submission kursus Dicoding dan bersifat open untuk keperluan pembelajaran.

---
*Submission: Belajar Dasar Pemrograman Web — Stage 1 of Frontend Web Learning Path, Dicoding 2026*
*Reviewed Score: 5/5 — Sempurna*