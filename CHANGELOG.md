# 📋 Changelog — Captura

Semua perubahan penting pada aplikasi didokumentasikan di file ini.
Format mengikuti [Keep a Changelog](https://keepachangelog.com/).

## [0.4.0] — 2026-09-12

### ✨ Added
- **Lokasi penyimpanan** — pilih folder tujuan lewat ⚙️ Pengaturan → Lokasi Penyimpanan. File video & screenshot bisa ditulis langsung ke folder pilihan tanpa dialog Save As (File System Access API, handle tersimpan di IndexedDB; otomatis fallback ke dialog bila izin tidak berlaku).
- **Backup & pulihkan pengaturan** — Export semua preferensi ke file JSON dan Import untuk memulihkannya (⚙️ Pengaturan → Backup Pengaturan).
- **Sembunyikan kursor di hasil rekaman video** — toggle di ⚙️ Pengaturan → Rekam Video (default **aktif**), memakai constraint `cursor: 'never'` Screen Capture API; otomatis diabaikan bila browser/OS tidak mendukung.

## [0.3.2] — 2026-09-12

### 🔄 Changed
- **Screenshot mode Area kini langsung terpotong di editor** — editor terbuka sudah menampilkan hasil area terpilih saja (bukan gambar penuh dengan kotak area lagi). Kotak area yang tampak di 0.3.1 diganti: potongan diterapkan langsung ke kanvas sebelum masuk editor. Crop manual dengan ✂️ tetap tersedia.

## [0.3.1] — 2026-09-12

### 🐛 Fixed
- **Screenshot mode Area menampilkan gambar penuh di editor** — seleksi rect dari overlay tidak pernah diteruskan ke editor (`region` selalu null), sehingga hasil tampil/simpan penuh alih-alih sesuai area yang dipilih. Kini seleksi area menjadi potongan awal di editor (tetap bisa digeser/di-resize), termasuk penyesuaian koordinat saat scrollbar halaman dibuang dari hasil.

## [0.3.0] — 2026-09-12

### ✨ Added
- **Toggle aktif/nonaktif cek update otomatis** di ⚙️ Pengaturan → Update Otomatis (default **nonaktif**):
  - Nonaktif → alarm periodik dibersihkan, badge NEW & banner update tidak tampil (cek manual tetap tersedia).
  - Aktif → cek berjalan tiap 12 jam + saat browser dibuka.
  - Perubahan toggle langsung berefek tanpa restart browser (sinkron via `chrome.storage.onChanged`).

### 🔄 Changed
- Status update kini memperhitungkan toggle — bila fitur dimatikan, badge NEW, banner recorder, dan indikator popup tidak tampil meski ada hasil cek lama.

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
