# Papan Latihan — Perancang Sesi (Garuda Soccer Academy)

Aplikasi web satu halaman untuk merancang sesi latihan sepak bola: lapangan 2D berskala, zoom penuh/setengah/sepertiga, elemen (pemain, kerucut, gawang, garis, area), library sesi, dan ekspor PDF.
Tidak butuh server, akun, atau instalasi. Semua berjalan di browser.

## Cara pasang di GitHub Pages (tanpa perintah terminal)

1. Buat akun GitHub (jika belum), lalu klik **New repository**. Beri nama, misalnya `papan-latihan`. Pilih **Public** (GitHub Pages gratis hanya untuk repo publik; untuk repo privat perlu paket berbayar).
2. Di halaman repo, klik **Add file → Upload files**. Unggah **semua isi folder ini**: `index.html`, `.nojekyll`, `README.md`, dan folder `lib` (berisi `jspdf.umd.min.js`). Klik **Commit changes**.
3. Buka **Settings → Pages**. Pada *Build and deployment*, pilih **Deploy from a branch**, branch **main**, folder **/ (root)**, lalu **Save**.
4. Tunggu 1–2 menit. Alamat aplikasi: `https://NAMA-AKUN.github.io/papan-latihan/`
5. Bagikan alamat itu ke rekan pelatih. Di HP, buka alamatnya lalu pilih *Tambahkan ke layar utama* agar terasa seperti aplikasi.

## Cara kerja penyimpanan (penting)

- Sesi disimpan **otomatis di browser** masing-masing orang (localStorage). Tidak ada server bersama.
- Artinya: sesi yang Anda buat **tidak otomatis muncul** di perangkat rekan, dan data terikat pada satu browser. Menghapus data browser akan menghapus sesi.
- Untuk memindahkan atau berbagi sesi, gunakan tombol di **Library**:
  - **Cadangan**: mengunduh semua sesi menjadi satu berkas `.json`. Lakukan ini berkala.
  - **Bagikan** (di kartu sesi): mengunduh satu sesi sebagai `.json` untuk dikirim lewat WhatsApp/email.
  - **Impor**: memasukkan berkas `.json`. Sesi baru ditambahkan; sesi dengan ID sama hanya diperbarui jika berkas lebih baru.
- Ekspor PDF: tombol **⬇ PDF** (sesi yang sedang dibuka), **PDF** di kartu sesi, atau **PDF semua** di Library.

## Memperbarui aplikasi

Ganti `index.html` di repo (Add file → Upload files, timpa berkas lama). Data pelatih di browser tidak terhapus.

## Catatan teknis

- File utama: `index.html` (HTML, CSS, dan JavaScript dalam satu berkas). Pustaka PDF: `lib/jspdf.umd.min.js` (jsPDF, lisensi MIT).
- Font memakai Google Fonts; jika offline, aplikasi memakai font bawaan perangkat.
- Jika kelak butuh sinkron otomatis antar pelatih, perlu layanan basis data (misalnya Supabase atau Firebase). Itu pekerjaan tambahan.
