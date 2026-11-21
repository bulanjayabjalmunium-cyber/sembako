SMART SEMBAKO — Paket awal Website + Dashboard Admin
===================================================

ISI FOLDER
- index.html          Website pelanggan
- admin.html          Dashboard admin terpisah
- firebase-config.js  Konfigurasi Firebase bersama
- firestore.rules    Aturan keamanan Firestore

PENTING: Website ini belum terhubung ke Firebase sampai konfigurasi diisi.

LANGKAH SETUP FIREBASE (GRATIS UNTUK MEMULAI)
1. Buka https://console.firebase.google.com/ dan buat project.
2. Tambahkan aplikasi Web (ikon </>) lalu salin konfigurasi SDK.
3. Buka firebase-config.js dan ganti semua nilai ISI_... dengan konfigurasi project.
4. Konfigurasi Firebase web sudah dimasukkan ke firebase-config.js. Ganti nomor WhatsApp 6281234567890 dengan nomor admin (format 62..., tanpa + atau spasi).
5. Firebase Console > Authentication > Sign-in method: aktifkan Email/Password.
6. Authentication > Users > Add user: buat akun email dan password admin. Jangan membuat form pendaftaran publik.
7. Firestore Database > Create database.
8. Firestore > Rules: salin isi file firestore.rules lalu Publish.
9. Upload semua file ini ke hosting yang sama. Jangan membuka file lewat file:// untuk pengujian Firebase; gunakan hosting/localhost.

CARA PAKAI
- Website pelanggan: index.html
- Dashboard admin: admin.html
- Login memakai email/password yang dibuat di Firebase Console.
- Tambah produk dari tombol "+ Tambah Produk".
- Edit/hapus produk dari tabel.
- Harga disimpan sebagai angka Rupiah tanpa titik, misalnya 75000.
- Produk aktif akan tampil otomatis pada katalog website setelah Firestore menerima perubahan.
- Pesanan checkout disimpan ke koleksi orders dan diarahkan ke WhatsApp toko.

CATATAN KEAMANAN
- Aturan contoh mengizinkan semua pengguna membuat dokumen pesanan, tetapi hanya pengguna login membaca/mengubah pesanan.
- Semua akun Firebase Auth yang berhasil login dapat mengelola produk/pesanan pada aturan sederhana ini. Karena itu jangan aktifkan pendaftaran publik dan jangan bagikan akun admin.
- Untuk penggunaan publik skala besar, sebaiknya aturan ditingkatkan dengan custom claims admin, validasi skema/ukuran pesanan, pembatasan spam, App Check, dan Cloud Functions.
- Nomor WhatsApp harus diganti. Nomor contoh tidak akan berfungsi.
- Produk contoh di website adalah data contoh. Setelah ada produk di Firestore, katalog website menggunakan data Firestore.
- Foto produk dapat diisi menggunakan URL gambar publik pada kolom URL foto. Upload foto langsung belum disertakan pada versi ini.
- Koneksi WhatsApp masih menggunakan link wa.me; pengiriman otomatis melalui WhatsApp Cloud API adalah tahap integrasi berikutnya.

Jika Firestore belum dibuat/konfigurasi belum diisi, website tetap menampilkan katalog contoh, tetapi dashboard admin tidak dapat login/mengelola data.
