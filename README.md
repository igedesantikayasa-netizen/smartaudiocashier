# SmartAudioCashier — Aplikasi Kasir Digital Modern & Inklusif (Audio First)

**SmartAudioCashier** adalah aplikasi kasir (Point of Sale / POS) modern yang dirancang inklusif dan ramah bagi penyandang disabilitas, khususnya pengguna tunanetra dan *low vision*, dengan pendekatan **Audio-First** dan kepatuhan penuh terhadap standar aksesibilitas internasional **WCAG 2.2 Level AA**.

Aplikasi ini dapat dioperasikan secara penuh tanpa menggunakan mouse (100% Keyboard Navigable), mendukung interaksi suara dua arah (Text-to-Speech bahasa Indonesia alami dan Perintah Suara / Voice Command), serta terintegrasi mulus dengan pembaca layar (*screen reader*) seperti NVDA, JAWS, dan TalkBack.

---

## 🌟 Karakteristik & Keunggulan Utama

1. **Modern Accessible POS Dashboard:**
   - Desain profesional, bersih, dan berhierarki jelas setara aplikasi kasir komersial modern.
   - Sistem desain dengan rasio kontras tinggi (>14:1 pada teks utama) sesuai rekomendasi WCAG 2.2 AA.
   - Palet warna: Navy Blue (`#173B57`), Teal (`#087F8C`), Accent Amber/Orange (`#F59E0B`), Neutral Soft (`#F5F7FA`), Surface (`#FFFFFF`), Success Green (`#167D45`), Danger Red (`#B42318`).
   - Tersedia pilihan tema kontras ekstrem: **Modern Navy**, **High-Contrast Gelap (Hitam-Kuning WCAG AAA)**, dan **High-Contrast Terang (Putih-Hitam WCAG AAA)**.
   - Skala tipografi fleksibel: Kecil (90%), Normal (100%), Besar (115%), dan Sangat Besar (130%).
   - **Mode Tampilan Sederhana (Simple View):** Menyederhanakan elemen visual, memperbesar tombol, dan menghilangkan dekorasi non-esensial bagi pengguna yang membutuhkan fokus tinggi.

2. **Audio First & Smart Audio Assistant (TTS Indonesia):**
   - Menggunakan Web Speech API dengan sintesis suara Bahasa Indonesia (`id-ID`).
   - Konverter angka Rupiah ke kata bahasa Indonesia alami (*"Enam puluh delapan ribu rupiah"*, *"Satu lembar sepuluh ribu rupiah dan satu lembar lima ribu rupiah"*).
   - Membacakan sapaan pembuka, perpindahan halaman, penambahan barang ke keranjang, perubahan kuantitas, total belanja, uang kembalian beserta rincian pecahan, notifikasi kesalahan, dan petunjuk navigasi.
   - Dilengkapi bilah *Live Caption Banner* di bagian atas layar agar pengguna *low vision* atau teman tuli dapat membaca teks ucapan secara langsung.
   - Tombol Ulangi Suara (`R` / `Alt+U`) dan Hentikan Suara (`Esc`).

3. **Perintah Suara (Voice Command 100% Hands-Free):**
   - Mendukung Speech Recognition berbasis Web Speech API bahasa Indonesia alami.
   - Indikator status mikrofon visual (animasi denyut) dan audio (chime naik/turun) yang transparan; mikrofon tidak pernah aktif diam-diam.
   - Konfirmasi suara dua tahap sebelum mengeksekusi tindakan krusial (misal: konfirmasi pembatalan keranjang atau penghapusan data).

4. **Sintesis Audio Web Audio API (Tanpa File MP3 Eksternal):**
   - Sensor barcode kasir *BEEP* tajam 1200Hz.
   - Suara koin & uang kertas masuk (Harmonik E5 -> B5).
   - Nada lonceng laci kasir *cha-ching* (1568Hz).
   - Melodi *fanfare* kemenangan arpeggio saat transaksi sukses.
   - Nada peringatan lembut saat uang kurang atau terjadi kekeliruan.
   - Umpan balik klik sentuh eksplorasi.

5. **100% Mandiri, Offline & Portabel:**
   - Tidak memerlukan koneksi internet, tidak memerlukan instalasi Node.js/npm, dan tidak memerlukan server database eksternal.
   - Menggunakan penyimpanan browser `localStorage` dengan penanganan *graceful fallback*.

---

## 📋 Fitur Utama Aplikasi

### A. Dashboard Ringkasan POS
- Kartu metrik eksekutif: Total Pendapatan Hari Ini, Jumlah Transaksi Hari Ini, Jumlah Produk Aktif, dan Status Audio/Sistem.
- Tabel aktivitas transaksi terakhir secara real-time.
- Pintasan cepat untuk memulai transaksi baru, menambah produk, atau melihat laporan.

### B. Transaksi Kasir (Point of Sale)
- Pencarian produk cepat dengan filter kategori: Sembako, Minuman, Makanan, Alat Tulis, Kebutuhan Rumah.
- Simulasi pemindai barcode (*barcode scanner*) dengan bunyi sensor BEEP.
- Keranjang belanja interaktif: ubah jumlah barang (+/-), subtotal otomatis, dan hapus barang.
- Kalkulasi pembayaran tunai instan dengan tombol uang cepat (*Uang Pas*, *+Rp5.000*, *+Rp10.000*, *+Rp20.000*, *+Rp50.000*, *+Rp100.000*).
- Penghitungan uang kembalian otomatis disertai **rincian lembaran uang Rupiah** (misal: 1 lembar Rp50.000, 1 lembar Rp10.000).
- Penyelesaian transaksi dengan pencetakan struk belanja kasir profesional.

### C. Manajemen Produk & Stok (CRUD)
- Tambah, edit, dan hapus produk.
- Input kode barcode / SKU, nama barang, kategori, harga satuan, dan persediaan stok.
- Indikator status persediaan: *Aman*, *Menipis* (<=5 unit), atau *Habis*.
- Muat ulang data sampel default kapan saja.

### D. Riwayat Transaksi & Struk
- Log lengkap seluruh transaksi dengan nomor faktur resmi (`TRX-YYYYMMDD-XXXX`), tanggal, jam, rincian barang, total belanja, uang diterima, dan kembalian.
- Penampil struk kasir (*modal receipt viewer*) dengan tombol cetak struk (*Print Dialog*).
- Ekspor riwayat ke format **CSV** untuk pembukuan Excel/Spreadsheet.

### E. Laporan Penjualan & Analisis
- Metrik omset keseluruhan, rata-rata nilai belanja per transaksi, dan produk terlaris.
- Grafik pendapatan 7 hari terakhir (Visual Bar Chart) yang dilengkapi **Tabel Rincian Data Harian untuk Screen Reader**.
- Tabel peringkat 5 produk paling laris (*Top Selling Products*).

### F. Mode Latihan Belajar & Pemilah Anggaran (Fitur Edukasi Asli Dilestarikan)
- **Modul 1 (Pemilah Skala Prioritas):** 4 skenario interaktif melatih membedakan Kebutuhan Pokok sekolah dan Keinginan dengan uang saku terbatas.
- **Modul 2 (Simulasi Meja Kasir):** Simulasi pemindaian barcode belanjaan dan penyusunan uang pecahan Rupiah.

### G. Pengaturan Aksesibilitas
- Pengaturan tema kontras, ukuran font, mode sederhana, kecepatan bicara TTS (0.7x - 1.5x), pilihan suara sistem browser, dan aktivasi pengenalan suara.
- Tersimpan permanen di perangkat pengguna.

---

## ⌨️ Daftar Pintasan Keyboard Lengkap (Global Shortcuts)

| Tombol Pintasan | Fungsi |
|---|---|
| `Alt + D` | Buka Halaman **Dashboard** |
| `Alt + K` | Buka Halaman **Transaksi Kasir (POS)** |
| `Alt + P` | Buka Halaman **Manajemen Produk** |
| `Alt + R` | Buka Halaman **Riwayat Transaksi** |
| `Alt + L` | Buka Halaman **Laporan Penjualan** |
| `Alt + E` | Buka **Mode Latihan Belajar Edukasi** |
| `Alt + S` | Buka **Pengaturan Aksesibilitas** |
| `Alt + H` | Buka **Pusat Bantuan & Panduan** |
| `Alt + V` atau `Spasi` | **Aktifkan Perintah Suara (Voice Command)** *(saat tidak mengetik teks)* |
| `F2` | Buka Jendela **Pemindai Barcode Kasir** |
| `F4` | **Selesaikan Transaksi & Bayar Sekarang** di kasir |
| `R` atau `Alt + U` | **Ulangi Narasi Suara Terakhir** |
| `Esc` | **Hentikan Suara Asisten** atau Tutup Jendela Dialog Modal |
| `Alt + T` | Beralih Cepat Tema Kontras (Standar / Gelap / Terang) |
| `Alt + 0` / `Tab` pertama | **Lompat ke Konten Utama (Skip to Main Content)** |

---

## 🎙️ Kamus Perintah Suara (Voice Commands)

Katakan perintah berikut dalam Bahasa Indonesia alami setelah menekan tombol mikrofon atau tombol `Spasi`:

- *"Buka dashboard"* &rarr; Berpindah ke tampilan Dashboard.
- *"Buka kasir"* atau *"Buka transaksi"* &rarr; Membuka meja kasir POS.
- *"Cari produk [nama barang]"* (contoh: *"Cari produk beras"*) &rarr; Memfilter katalog kasir.
- *"Tambahkan [nama barang]"* (contoh: *"Tambahkan minyak goreng"*) &rarr; Memasukkan barang ke keranjang.
- *"Berapa total belanja?"* &rarr; Asisten membacakan nominal total belanja saat ini.
- *"Lihat keranjang"* &rarr; Asisten mengumumkan jumlah jenis barang di keranjang.
- *"Bayar uang pas"* &rarr; Mengisi nilai uang tunai dengan total belanja persis.
- *"Bayar sekarang"* atau *"Selesaikan transaksi"* &rarr; Memproses pembayaran dan mencetak struk.
- *"Batalkan transaksi"* &rarr; Meminta konfirmasi suara ("Katakan Ya") sebelum mengosongkan keranjang.
- *"Buka laporan"* &rarr; Membuka halaman analisis dan laporan omset.
- *"Ulangi"* &rarr; Mengulang ucapan asisten terakhir.
- *"Hentikan suara"* atau *"Diam"* &rarr; Mematikan pembacaan suara seketika.

---

## ♿ Kepatuhan Standar Aksesibilitas WCAG 2.2 Level AA

1. **Perceivable (Dapat Dipersepsi):**
   - Rasio kontras teks normal minimal 4.5:1 (warna teks `#17212B` di atas `#FFFFFF` memiliki rasio > 14:1).
   - Rasio kontras komponen antarmuka dan border aktif minimal 3:1.
   - Tema *High-Contrast Dark* mencapai rasio 17.8:1 (WCAG AAA).
   - Seluruh grafik visual dilengkapi tabel data semantik (`<caption>`, `<th>`, `<td>`) untuk pengguna pembaca layar.
   - Bilah teks takarir langsung (*live subtitles*) mendampingi seluruh keluaran audio.

2. **Operable (Dapat Dioperasikan):**
   - Bebas jebakan keyboard (*no keyboard trap*).
   - Fokus keyboard terlihat mencolok melalui *focus ring* tebal 3px solid dengan jarak offset 2px.
   - Tautan *Skip to Main Content* tersedia di awal dokumen (`Alt + 0`).
   - Ukuran target interaktif (*touch target size*) minimal 44 x 44 CSS pixel, jauh melampaui ketentuan WCAG 2.2 Success Criterion 2.5.8 (minimal 24 x 24px).
   - Seluruh modal dialog mengimplementasikan *focus trapping*, penutupan via tombol `Escape`, dan pengembalian fokus ke elemen pemicu.

3. **Understandable (Dapat Dipahami):**
   - Deklarasi bahasa dokumen `lang="id"`.
   - Seluruh form memiliki elemen `<label for="...">` eksplisit, teks petunjuk, dan validasi yang jelas.
   - Konfirmasi dua langkah untuk tindakan penghapusan dan pembatalan data penting.

4. **Robust (Kokoh):**
   - Struktur HTML semantik murni (`<header>`, `<nav>`, `<aside>`, `<main>`, `<section>`, `<article>`).
   - Pemanfaatan ARIA Live Regions secara disiplin (`role="status"` dengan `aria-live="polite"` dan `role="alert"` dengan `aria-live="assertive"`).
   - Integrasi cerdas antara Text-to-Speech Web Speech API dan Screen Reader asli agar tidak menimbulkan pengumuman ganda (*no duplicate speech*).

---

## 🚀 Cara Menjalankan Aplikasi

Aplikasi ini dapat dijalankan dengan dua cara mudah:

### Cara 1: Buka Langsung File (Tanpa Server)
Cukup klik ganda (*double-click*) file `index.html` pada peramban modern (Google Chrome, Microsoft Edge, Mozilla Firefox, atau Safari). Aplikasi akan langsung terbuka 100% berfungsi secara offline.

### Cara 2: Menjalankan via Server Lokal (Opsional)
Jika ingin menjalankan melalui protokol `http://localhost`:
1. Buka PowerShell di folder project.
2. Jalankan perintah:
   ```powershell
   powershell -ExecutionPolicy Bypass -File .\serve.ps1
   ```
3. Buka peramban pada alamat `http://localhost:8080/`.

---

&copy; 2026 SmartAudioCashier Team. Dikembangkan dengan prinsip Inklusivitas, Aksesibilitas, dan Audio First.
