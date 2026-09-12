# 📖 Panduan Lengkap — Captura

Panduan penggunaan extension **Captura** — screen recorder berbasis Chromium (Chrome/Edge/Brave) dengan area rekam kustom dan blur titik sensitif, dirancang untuk kebutuhan dokumentasi kerja sehari-hari.

> Versi aplikasi mengikuti file [`VERSION`](../VERSION) di root repo. Panduan ini juga bisa dibuka langsung dari extension: **⚙️ Pengaturan → 📖 Panduan Cepat**.

---

## Daftar Isi

1. [Pengenalan](#1-pengenalan)
2. [Instalasi](#2-instalasi)
3. [Mulai Merekam](#3-mulai-merekam)
4. [Area Recording (✂️)](#4-area-recording-️)
5. [Blur Titik Tertentu (▓)](#5-blur-titik-tertentu-)
6. [Audio (🎤/🔊)](#6-audio-)
7. [Screenshot (📸)](#7-screenshot-)
8. [Menyimpan Hasil](#8-menyimpan-hasil)
9. [Halaman Pengaturan](#9-halaman-pengaturan)
10. [Update Aplikasi](#10-update-aplikasi)
11. [Shortcut & Indikator](#11-shortcut--indikator)
12. [Tips & Solusi Masalah](#12-tips--solusi-masalah)

---

## 1. Pengenalan

Captura adalah extension browser untuk merekam layar dengan tiga keunggulan:

| Fitur | Keterangan |
|---|---|
| 🪟 Pilih sumber fleksibel | Jendela / tab / layar penuh, dengan sumber default yang bisa diatur |
| ✂️ Area recording | Rekam hanya area yang digambar sendiri — bukan full screen |
| ▓ Blur titik tertentu | Sembunyikan data sensitif dengan blur/mosaik saat merekam (WYSIWYG) |

Output rekaman berupa **WebM (VP9)** yang bisa diputar di semua browser modern dan mudah di-upload ke Google Drive, YouTube, atau dilampirkan ke laporan atau tiket.

## 2. Instalasi

> Aturan Chrome: folder yang di-*Load unpacked* harus berisi `manifest.json` langsung di root-nya.

1. Unduh versi terbaru dari halaman **Releases** repo (contoh: `Captura-v0.2.0-chrome.zip`).
2. Ekstrak ke folder pilihanmu.
3. Buka `chrome://extensions` → aktifkan **Developer mode**.
4. Klik **Load unpacked** → pilih folder hasil ekstraksi (yang berisi `manifest.json`).
5. Ikon Captura (⏺ merah) muncul di toolbar — siap dipakai.

> Update versi: unduh zip terbaru, ekstrak menggantikan folder lama, lalu klik 🔄 di halaman extensions. Bagi pengembang repo: folder `extension/` di root berisi salinan build terbaru (di-update otomatis oleh `npm run build`), jadi juga bisa langsung di-*Load unpacked*.

## 3. Mulai Merekam

1. Klik ikon Captura di toolbar → **Buka Jendela Rekam** (atau tekan `Alt+Shift+R`).
2. Panel awal menampilkan ringkasan pengaturan aktif (chips). Ubah lewat **⚙️ Kelola / Pengaturan** bila perlu.
3. Klik **⏺ Pilih Sumber & Mulai** → picker Chrome muncul (langsung terbuka pada jenis sumber default: Jendela/Tab/Layar).
4. Pilih sumber → preview live tampil di jendela recorder.
5. (Opsional) Atur **area** dan **blur** — lihat bab 4 & 5.
6. Klik **⏺ Mulai Rekam**. Timer & estimasi ukuran file mulai berjalan; badge **REC** merah menyala di toolbar.
7. Selesai → **⏹ Selesai & Simpan**.

**Kontrol di tengah sesi:** ⏸ Jeda / ▶ Lanjut / ⏹ Selesai & Simpan / 🗑 Buang (buang sesi, ada konfirmasi).

## 4. Area Recording (✂️)

Cocok saat kamu hanya ingin merekam satu panel aplikasi, bukan seluruh layar.

1. Setelah preview tampil, pilih mode **✂️ Area** di toolbar editor.
2. **Drag** di preview untuk menggambar area. Di luar area akan digelapkan.
3. **Geser & ubah ukuran** — drag badan kotak merah untuk memindah, drag titik kanan-bawah untuk resize (persis seperti kotak blur).
4. Area minimal **100×100 px** — kalau terlalu kecil, muncul peringatan.
5. Ukuran output tampil di bawah preview (hasil video = ukuran area itu persis).
6. Salah gambar? Klik **Hapus area** lalu gambar ulang, atau drag di area kosong untuk menggambar ulang langsung.
7. Klik **⏺ Mulai Rekam** → hasil video hanya berisi area tersebut.

⚠️ Area **terkunci saat rekaman berjalan** (limitasi format streaming). Untuk mengubah area: stop dulu. Kotak blur tetap bisa diubah kapan pun.

## 5. Blur Titik Tertentu (▓)

Untuk menyembunyikan email, token, nomor telepon, atau data sensitif lainnya.

1. Pilih mode **▓ Blur**.
2. **Drag** di preview tepat di atas titik yang ingin disembunyikan → kotak muncul.
3. **Klik kotak** untuk memilihnya, lalu:
   - **Drag badan kotak** → pindah posisi
   - **Drag titik kanan-bawah** → ubah ukuran
   - **→ Mosaik / → Blur** → ganti efek (blur halus atau mosaik kotak-kotak)
   - **🗑 Hapus** → hilangkan kotak
4. Efek langsung terlihat di preview — **apa yang kamu lihat = hasil rekaman**.
5. Kotak bisa ditambah/diubah **selama rekaman berjalan** — berguna untuk menyensor data yang baru muncul di tengah sesi.

> Semua koordinat tersimpan relatif terhadap frame, jadi posisi blur tetap stabil selama rekaman.

## 6. Audio (🎤/🔊)

Di **⚙️ Pengaturan → Audio**:

- **🎤 Microphone** — merekam suara kamu (cocok untuk narasi demo).
- **🔊 Audio sistem/tab** — merekam suara dari aplikasi/tab yang direkam (mis. suara notifikasi, video).
- Keduanya ON → suara **dicampur otomatis** jadi satu track.

Saat memulai, pastikan checkbox **Share audio** tercentang di picker Chrome (untuk audio sistem; di Windows). Kalau mic tidak terdeteksi, cek izin mikrofon browser & aplikasi.

## 7. Screenshot (📸)

Selain merekam video, Captura bisa mengambil **screenshot** lengkap dengan anotasi. Ada **3 mode** yang bisa langsung dipilih dari popup — tanpa picker — plus mode layar/jendela:

| Mode | Cara kerja |
|---|---|
| 🖥️ **Penuh** | Langsung capture seluruh halaman tab aktif (viewport) → editor terbuka |
| 📄 **Full Page** | Capture **seluruh tinggi halaman** — di-scroll otomatis via debugger protocol, hasil satu gambar panjang → editor terbuka. Banner "debugging" muncul sesaat saat proses, lalu hilang otomatis. Halaman super panjang (>16.000px) dipotong di batas tersebut; hasil >9 MB otomatis dikompres JPEG |
| ⬚ **Area** | Halaman ditutupi frame — drag kotak di posisi yang diinginkan → editor terbuka |
| ✏️ **Bebas** | Gambar bentuk bebas (lasso) di halaman → editor terbuka dengan potongan sesuai bentuk |
| 🖼️ **Layar / Jendela** | Klik tombol di jendela screenshot → picker Chrome → pilih layar/jendela → langsung masuk editor |

Jendela editor selalu muncul **di sisi kanan layar** dan hanya tampil **setelah** screenshot diambil.

### Mengedit hasil

- **✂️ Area** — batasi hasil pada kotak yang digambar (bisa digeser/resize, klik → 🗑 Hapus)
- **▓ Blur** — sensor blur/mosaik, bisa diganti efek & dihapus
- **✏️ Coret** — gambar garis bebas; **warna & ketebalan** di panel kanan
- **🅣 Teks** — *segera hadir (sedang dikembangkan)*
- **🔍 Zoom** — tombol 🔍− / persen / 🔍+ di toolbar, atau **Ctrl + scroll** di atas gambar (default **25%**, 25%–400%) — berguna saat hasil kekecilan
- **↩ Undo** membatalkan aksi terakhir, **🧹 Bersihkan** menghapus semua anotasi
- Potongan bebas bisa dihapus lewat tautan **🗑 hapus** di bawah preview

Klik **💾 Simpan PNG** saat sudah pas, **📋 Copy** untuk menyalin hasil terkini (ikut potongan & anotasi) ke clipboard untuk di-paste, **🔁 Ambil Ulang** untuk mengulang mode yang sama, atau **↩ Kembali ke Menu**.

**🛟 Draf otomatis** — setiap perubahan otomatis tersimpan sementara. Kalau jendela tertutup tanpa sengaja, buka 📸 Screenshot berikutnya dan klik **Pulihkan** pada banner yang muncul — frame beserta semua anotasinya kembali.

**Scrollbar otomatis dibuang** — hasil screenshot tab tidak menyertakan scrollbar browser (kanan & bawah ter-crop otomatis).

## 8. Menyimpan Hasil

Setelah **⏹ Selesai & Simpan**, layar hasil menampilkan:

- **Preview video** hasil rekaman (bisa diputar dulu untuk dicek)
- Durasi, ukuran file, format
- Tiga aksi:
  - **💾 Simpan .webm** → dialog Save As Chrome → pilih lokasi. Setelah tersimpan, tombol berubah "✔ Tersimpan".
  - **↩ Kembali ke Menu** → kembali ke panel awal. Kalau belum disimpan, muncul konfirmasi dulu.
  - **🗑 Batalkan** → buang hasil rekaman (ada konfirmasi).

**Proteksi kehilangan:** selama ada sesi berjalan atau hasil yang belum disimpan, klik **X** (menutup jendela) akan memunculkan dialog konfirmasi bawaan browser terlebih dahulu.

## 9. Halaman Pengaturan

Buka lewat **⚙️** di popup, **⚙️ Kelola / Pengaturan** di jendela recorder, atau `chrome://extensions` → Captura → Details → Extension options.

| Bagian | Isi |
|---|---|
| 📖 Panduan Cepat | Ringkasan langkah penggunaan — bisa di-collapse/expand (posisinya diingat browser) |
| 🎥 Captura — Rekam Video | Sumber default, kunci jendela & tab, fps (15/24/30, default 15), kualitas (Rendah/Sedang/Tinggi, default Rendah) |
| 📸 Screenshot | Opsi **tampilkan penuh layar saat screenshot berhasil** (jendela editor otomatis maximized, kembali kecil saat kembali ke menu) |
| 🔊 Audio | Microphone, audio sistem/tab |
| 🔄 Update Otomatis | Repo GitHub untuk cek update + cek manual |
| 🐞 Debug Log | Log aktivitas & error, **tab terpisah** per fitur, checkbox rekam on/off (**default nonaktif**), tersimpan lokal (maks. 200 entri per fitur) |

Halaman pengaturan terdiri dari **tiga kolom**: kiri **rekam video** (Captura), tengah **panduan cepat**, kanan **pengaturan screenshot** — kolom tengah & kanan sticky mengikuti scroll.

> Default awal (install baru): sumber **Jendela**, **15 fps**, kualitas **Rendah** — hemat resource; naikkan bila butuh hasil lebih halus.

Semua perubahan **tersimpan otomatis** di penyimpanan lokal browser (`chrome.storage.local`) — persisten walau browser/komputer dimatikan, dan tersinkron langsung antar halaman tanpa reload.

## 10. Update Aplikasi

1. Isi repo GitHub di **⚙️ Pengaturan → Update Otomatis** (format `username/nama-repo`).
2. Extension mengecek file `VERSION` di repo **tiap 12 jam + saat browser dibuka** (atau klik *Cek Update Sekarang*).
3. Bila ada versi lebih baru: badge **NEW** oranye di toolbar + banner di jendela recorder/popup.
4. Klik **⬇ Lihat Update** → unduh dari halaman Releases → ekstrak menggantikan folder lama → reload extension.
5. Klik **✕** di banner untuk mengabaikan versi tertentu.

## 11. Shortcut & Indikator

| Item | Arti |
|---|---|
| `Alt+Shift+R` | Buka/fokus jendela recorder |
| Badge 🔴 **REC** | Sedang merekam |
| Badge 🟠 **NEW** | Update tersedia |
| Chips di panel awal | Ringkasan pengaturan aktif |

## 12. Tips & Solusi Masalah

| Masalah | Solusi |
|---|---|
| Picker tidak muncul | Pastikan klik **⏺ Pilih Sumber & Mulai** (picker butuh interaksi). Tutup picker lama yang masih terbuka. |
| Rekaman tidak bersuara | Cek toggle audio di Pengaturan & centang *Share audio* di picker. Untuk mic, cek izin mikrofon. |
| Jendela recorder ikut terekam | Gunakan mode **✂️ Area**, atau pindahkan jendela recorder keluar area yang direkam. |
| Titik blur bergeser | Blur mengikuti frame — jangan resize/move window sumber di tengah rekaman. |
| Hasil video hitam/kosong | Sumber berhenti di tengah sesi (mis. tab ditutup). Mulai sesi baru. |
| Update tidak terdeteksi | Pastikan format repo `username/nama-repo` benar & file `VERSION` ada di branch default repo. |
| Pengaturan hilang | Pastikan tidak menghapus data situs extension (chrome://extensions → Remove menghapus semuanya). |

---

🎉 Selamat merekam! Untuk laporan bug / saran fitur, buka halaman **Issues** di repo GitHub.
