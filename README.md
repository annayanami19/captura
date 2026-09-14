# 🎥 Captura

Extension browser (Chrome / Edge / Brave — berbasis Chromium) untuk **merekam layar** dengan fitur andalan untuk kebutuhan dokumentasi kerja: **rekam area tertentu** dan **blur titik sensitif** langsung saat merekam.

**Versi:** lihat file [`VERSION`](./VERSION) · **Update:** extension memeriksa repo GitHub secara otomatis (tiap 12 jam + saat browser dibuka) · **📖 Panduan lengkap:** [docs/PANDUAN.md](docs/PANDUAN.md) (juga tersedia di dalam extension: *⚙️ Pengaturan → Panduan Cepat*)

## 🗂️ Struktur Repo

| Folder / File | Isi |
|---|---|
| `extension/` | **Hasil build siap install** — folder inilah yang di-*Load unpacked* (manifest.json di root) |
| `entrypoints/`, `lib/`, `components/` | Source code aplikasi |
| `docs/PANDUAN.md` | Panduan penggunaan lengkap |
| `TESTING.md` | Checklist uji manual |
| `VERSION` | Nomor versi aplikasi (sumber kebenaran versi) |

---

## ✨ Fitur

- 🪟 **Pilih sumber fleksibel** — jendela, tab, atau layar penuh. Picker Chrome terbuka langsung pada jenis sumber default pilihanmu (default: *Jendela*). Bisa juga dikunci agar picker hanya menampilkan jendela & tab.
- ✂️ **Area recording** — rekam hanya area yang kamu gambar sendiri di preview (minimum 100×100 px). Hasil video hanya berisi area tersebut.
- ▓ **Blur titik tertentu** — pasang kotak blur/mosaik di titik sensitif (email, token, data pribadi). Bisa ditambah, dipindah, di-resize, dan diubah **di tengah rekaman** — apa yang terlihat di preview = hasil rekaman (WYSIWYG).
- 🎥 **Webcam (camera bubble)** — wajahmu ikut terekam bersama layar: bubble kamera di atas video dan **ter-bake permanen** ke hasil. Bentuk **Bubble/Kotak** + mode **pratinjau penuh** di panel awal, mirror, ring, dan bebas digeser & di-resize langsung di preview — bahkan saat merekam. Izin kamera ditolak? Rekaman tetap jalan normal.
- 🏷️ **Watermark** — teks atau gambar penanda untuk hasil kerjamu. Watermark **video** khusus **teks**, diatur *sebelum* mulai merekam dengan **pratinjau langsung** lalu ter-bake permanen ke hasil (tidak bisa diubah saat/sesudah merekam); watermark **screenshot** muncul di editor *setelah* capture — begitu diaktifkan langsung tampil di preview dan bebas diedit (teks atau gambar). Mode teks punya gaya standar esensial (B/I/U, warna teks & background, opasitas, ukuran persen, 9 posisi); mode gambar cukup atur letak & ukuran persen.
- ⏺ **Kontrol lengkap** — mulai / jeda / lanjut / selesai, timer + estimasi ukuran file, badge REC di toolbar, dan konfirmasi sebelum jendela tertutup saat ada sesi berjalan.
- 📸 **Screenshot 4 mode** — langsung dari popup **atau dari jendela screenshot** (tanpa picker) untuk tab aktif: **Penuh** 🖥️, **Full Page** 📄 (seluruh tinggi halaman — di-scroll otomatis per layar lalu dijahit jadi satu gambar, tanpa debugger; lazy-load ikut termuat), **Area** ⬚ (drag kotak di halaman), **Bebas** ✏️ (gambar bentuk bebas); plus layar/jendela via picker. Tiap capture bisa membuka **sesi editornya sendiri** (pengaturan: *timpa sesi aktif* / *sesi baru*, opsional konfirmasi sebelum menimpa).
- 🖌️ **Editor screenshot** — potong area, blur/mosaik ▓, coretan ✏️ multi-warna, **🅣 teks** (ukuran persen per-teks, pindah/resize/skala bebas dua sumbu), **◇ shapes ala Snipping Tool** (emoji, persegi, elips, garis, panah + opsi isi; ujung garis/panah bisa ditarik untuk memutar arah), **🏷️ watermark** bebas diedit, **zoom 25%–400%** (Ctrl+scroll), **📋 Copy ke clipboard** (ikut semua editan), **🛟 draf otomatis** yang bisa dipulihkan, dan scrollbar halaman otomatis dibuang dari hasil.
- ⏺ **Kontrol lengkap** — mulai / jeda / lanjut / selesai, timer + estimasi ukuran file, badge REC di toolbar, dan konfirmasi sebelum jendela tertutup saat ada sesi berjalan.
- 🔊 **Audio opsional** — rekam suara microphone, audio sistem/tab, atau keduanya (dicampur otomatis).

- ⚙️ **Halaman Pengaturan 3 kolom** — *Rekam Video* (kiri), *Panduan Cepat* (tengah — bisa di-collapse & posisinya diingat), *Screenshot* (kanan — opsi "tampilkan penuh layar saat screenshot berhasil" + **perilaku sesi screenshot**: timpa sesi aktif / sesi baru, langsung timpa / tanya dulu). Semua preferensi tersimpan otomatis di penyimpanan lokal browser dan tersinkron langsung antar jendela.
- 🐞 **Debug Log** — dua tab terpisah (🎥 Captura & 📸 Screenshot); **error & warning selalu terekam** apa pun settingnya, toggle = mode verbose (mencatat pula langkah sukses), maks. **500 entri** per fitur, tersimpan lokal di browser.
- 🔄 **Cek update otomatis** — notifikasi halus saat versi baru tersedia di repo GitHub, lengkap dengan tombol menuju halaman download.
- 💾 **Output WebM (VP9)** untuk video dan **PNG** untuk screenshot — kualitas rendah/sedang/tinggi, 15/24/30 fps.

## 📥 Instalasi

> Aturan Chrome: folder yang di-*Load unpacked* **harus berisi `manifest.json` langsung di root-nya** — jangan pilih folder source atau subfolder di dalamnya.

**Cara A — dari ZIP (untuk pengguna lain):**
1. Unduh versi terbaru dari halaman **Releases** repo (contoh: `Captura-v0.2.0-chrome.zip` — manifest sudah ada di root zip).
2. Ekstrak zip-nya ke folder pilihanmu.
3. Buka `chrome://extensions` → aktifkan **Developer mode** → **Load unpacked** → pilih folder hasil ekstraksi.

**Cara B — dari repo ini:**
1. Clone/unduh repo → **Load unpacked** → pilih folder **`extension/`** (salinan build terbaru, manifest di root-nya).

5. Ikon Captura muncul di toolbar — siap dipakai! 🎉

## 🚀 Cara Pakai

1. Klik ikon Captura di toolbar → **Buka Jendela Rekam** (atau tekan `Alt+Shift+R`).
2. Atur kebutuhanmu lewat **⚙️ Kelola / Pengaturan** — sumber default, audio, fps, kualitas.
3. Klik **⏺ Pilih Sumber & Mulai**, lalu pilih jendela/tab/layar di picker Chrome.
4. (Opsional) Gunakan mode **✂️ Area** untuk membatasi area rekam, dan mode **▓ Blur** untuk menyembunyikan titik sensitif.
5. Klik **⏺ Mulai Rekam**. Kontrol jeda/lanjut/selesai ada di bawah preview.
6. Selesai? Klik **⏹ Selesai & Simpan** → preview hasil → **💾 Simpan .webm**.
   Bisa juga **🗑 Batalkan** (buang) atau **↩ Kembali ke Menu**.

### 📸 Mengambil Screenshot

1. **Tab aktif** — dari popup atau jendela screenshot, pilih **🖥️ Penuh**, **📄 Full Page** (seluruh halaman di-scroll otomatis), **⬚ Area** (drag kotak), atau **✏️ Bebas** (gambar bentuk bebas) → editor langsung terbuka.
2. **Layar / Jendela** — klik tombol di jendela screenshot → pilih sumber di picker Chrome → langsung masuk editor.
3. Edit hasilnya: ✂️ potong area, ▓ blur/mosaik, ✏️ coretan, zoom dengan 🔍± atau Ctrl+scroll.
4. **💾 Simpan PNG**, **📋 Copy** ke clipboard, **↩ Kembali ke Menu** — atau pulihkan draf kalau jendela sempat tertutup.



## 🔄 Update Aplikasi

- Saat versi baru dirilis di repo GitHub, extension menampilkan badge **NEW** di toolbar dan banner di jendela recorder/popup dengan tombol menuju halaman download.
- Pastikan **repo GitHub sudah diisi** di *⚙️ Pengaturan → Update Otomatis* (format: `username/nama-repo`).
- Karena aplikasi ini terdistribusi via GitHub (bukan Chrome Web Store), pembaruan dilakukan dengan mengunduh versi terbaru lalu mengganti folder extension — cukup satu kali per versi.

## ⚠️ Catatan

- Mode **Layar Penuh** dapat ikut merekam jendela recorder — gunakan mode **Area** atau pindahkan jendelanya keluar area rekam.
- Area rekam terkunci selama rekaman berjalan (kotak blur tetap bisa diubah kapan pun).
- Rekaman berformat **WebM** — bisa diputar di semua browser modern dan di-upload ke Google Drive/YouTube.
