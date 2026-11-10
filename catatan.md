# Catatan Tugas: Halaman Web Statis "Kopi Sudut"

## 1. Tag HTML yang dipakai dan fungsinya

| Tag | Fungsi |
|---|---|
| `<!DOCTYPE html>` | Memberi tahu browser bahwa dokumen ini HTML5 |
| `<html lang="id">` | Elemen akar; `lang` menandai bahasa halaman |
| `<head>` | Berisi informasi dokumen yang tidak tampil di halaman |
| `<meta charset>` / `<meta viewport>` | Pengkodean karakter dan penyesuaian tampilan di layar HP |
| `<title>` | Judul yang muncul di tab browser |
| `<link rel="stylesheet">` | Menghubungkan file `style.css` |
| `<body>` | Seluruh isi yang tampil di halaman |
| `<header>` | Bagian kepala halaman (logo dan menu) |
| `<nav>` | Kelompok tautan navigasi utama |
| `<ul>`, `<li>` | Daftar tak berurutan; dipakai untuk item menu navigasi |
| `<a href>` | Tautan; `href="#menu"` meloncat ke elemen ber-id `menu` |
| `<main>` | Isi utama halaman (hanya satu per halaman) |
| `<section>` | Pengelompokan isi berdasarkan topik, tiap section punya judul |
| `<article>` | Konten mandiri; dipakai untuk tiap kartu menu minuman |
| `<h1>`, `<h2>`, `<h3>` | Judul bertingkat; `h1` hanya satu |
| `<p>` | Paragraf |
| `<span>` | Pembungkus teks sebaris; dipakai untuk harga |
| `<svg>` | Gambar vektor; dipakai untuk logo |
| `<footer>` | Bagian kaki halaman |
| `<address>` | Informasi kontak |
| `<div>` | Pembungkus umum tanpa makna; dipakai untuk kolom footer dan grid kartu |

## 2. Properti CSS untuk header dan footer

**Header**
- `display: flex`: header jadi flex container, anak-anaknya (logo dan nav) berjajar horizontal.
- `justify-content: space-between`: logo terdorong ke kiri, nav ke kanan.
- `align-items: center`: keduanya sejajar di tengah secara vertikal.
- `position: sticky; top: 0`: header tetap terlihat saat halaman digulir.
- Pada `.menu`: `display: flex` + `gap` agar item menu berjajar dengan jarak.

**Footer**
- `display: flex` + `justify-content: space-between`: tiga bagian tersusun kiri, tengah, kanan.
- `.footer-col { flex: 1 }`: ketiga kolom berbagi lebar sama, sehingga bagian tengah benar-benar di tengah.
- `text-align: center` (tengah) dan `text-align: right` (kanan): perataan teks tiap kolom.
- `gap`: jarak antar kolom.

**Pendukung**
- `.container { max-width: 960px; margin: 0 auto }`: isi dibatasi lebarnya dan diletakkan di tengah, sementara latar `<section>` tetap selebar layar.
- `display: grid` + `grid-template-columns: repeat(3, 1fr)`: kartu menu jadi tiga kolom.
- `.card` memakai `display: flex; flex-direction: column` dan `p { flex: 1 }` agar harga selalu sejajar di dasar kartu.
- `@media (max-width: 720px)`: di layar kecil, `flex-direction: column` membuat susunan menumpuk ke bawah.
- `box-sizing: border-box`: padding tidak menambah lebar elemen.

## 3. Kesulitan dan cara mengatasinya

(Isi dengan pengalamanmu sendiri. Contoh kesulitan umum yang bisa kamu jadikan acuan kalau memang kamu alami:)

- **Bagian tengah footer tidak benar-benar di tengah.** Penyebab: lebar tiap kolom mengikuti isinya. Solusi: beri `flex: 1` pada semua kolom.
- **Menu tidak berjajar ke samping.** Penyebab: `<li>` bawaannya tampil vertikal. Solusi: `display: flex` pada `<ul>`.
- **Harga di tiap kartu tidak sejajar.** Penyebab: tinggi paragraf berbeda-beda. Solusi: kartu dibuat flex kolom, paragraf diberi `flex: 1`.
- **Titik-titik daftar masih muncul.** Solusi: `list-style: none`.
- **Tampilan berantakan di HP.** Solusi: tambahkan `<meta name="viewport">` dan `@media`.
