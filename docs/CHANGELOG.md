# 📋 Changelog — Captura

Semua perubahan penting pada aplikasi didokumentasikan di file ini.
Format mengikuti [Keep a Changelog](https://keepachangelog.com/).

## [0.2.0] — 2026-09-12

### ✨ Added
- **Screenshot 4 mode** untuk tab aktif (langsung tanpa picker): Penuh, Area (drag kotak), Bebas (gambar bentuk bebas), dan **Full Page** (seluruh tinggi halaman via debugger protocol + pre-scroll otomatis untuk lazy-load).
- **Editor screenshot** — potong area, blur/mosaik, coretan multi-warna, teks, zoom 25%–400% (Ctrl+scroll), undo/clear, **📋 Copy ke clipboard**, dan **💾 Simpan PNG**.
- **Draf otomatis** — perubahan tersimpan sementara; jendela tertutup tanpa sengaja tetap bisa dipulihkan.
- **Debug Log** — dua tab terpisah (ScreenRecord & Screenshot), checkbox rekam on/off (default nonaktif), maks. 200 entri per fitur.
- **Halaman Pengaturan 3 kolom** — Rekam Video, Panduan Cepat (collapsible), Pengaturan Screenshot (opsi maximize jendela editor).
- **Area recording** bisa digeser & di-resize (termasuk handle resize), konsisten dengan kotak blur.
- **Kursor custom** untuk mode menggambar (terlihat jelas di background terang/gelap).
- Opsi **"kunci ke Jendela & Tab saja"** pada pemilihan sumber.
- Shortcut **Alt+Shift+R** untuk membuka jendela rekam.

### 🔄 Changed
- Nama aplikasi resmi: **Captura** (versi mengikuti file `VERSION`).
- Dialog konfirmasi tutup kini juga aktif di layar hasil yang belum disimpan.
- Scrollbar halaman otomatis dibuang dari hasil screenshot tab.
- Layout halaman pengaturan dua kolom → tiga kolom (rekam video / panduan / screenshot).

### 🐛 Fixed
- Scroll halaman "stuck" setelah full page capture (ganti teknik ke emulasi metrik + clear override).
- Warning `modulepreload` cross-world di console Chrome 130+.
- Retake screenshot kini selalu menargetkan tab sumber yang sama.

## [0.1.0] — 2026-09-11

### ✨ Added
- Rekam layar dasar: pilih sumber (jendela/tab/layar) dengan default **Jendela**, pause/resume, output WebM (VP9).
- **Area recording** dan **blur/mosaik titik tertentu** saat merekam (WYSIWYG).
- Audio opsional: microphone, audio sistem/tab, atau keduanya.
- Badge REC, timer, dan penyimpanan melalui dialog Save As.
- Halaman pengaturan dengan penyimpanan lokal (chrome.storage.local).
