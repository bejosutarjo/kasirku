KASIRKU — APLIKASI KASIR WARUNG (PWA)
======================================

ISI PAKET
---------
- index.html      -> Aplikasi utama (buka file ini di browser)
- manifest.json    -> Konfigurasi PWA (nama app, ikon, warna tema)
- sw.js            -> Service worker (membuat app bisa dipasang & jalan offline)
- icons/           -> Kumpulan ikon aplikasi dari logo KasirKu (berbagai ukuran)

CARA MENJALANKAN
-----------------
1) CARA CEPAT (lokal, tanpa install jadi App)
   - Cukup buka file "index.html" langsung di browser (Chrome/Edge).
   - Semua fitur kasir, produk, transaksi, dan QRIS tetap berfungsi normal.
   - Catatan: mode "Install sebagai Aplikasi" (PWA) hanya aktif jika file
     dijalankan lewat server (lihat langkah 2), karena browser mewajibkan
     https/localhost untuk mengaktifkan Service Worker.

2) MENGAKTIFKAN MODE PWA (agar bisa di-"Install" ke HP/Laptop seperti aplikasi)
   Upload seluruh isi folder ini (index.html, manifest.json, sw.js, dan folder
   icons/) ke hosting/web server, contoh gratis:
   - Netlify Drop (drag & drop folder ke app.netlify.com/drop)
   - Vercel
   - GitHub Pages
   - Atau hosting cPanel/VPS milik sendiri

   Setelah online (https), buka alamatnya di HP Android/Chrome:
   - Akan muncul opsi "Tambahkan ke Layar Utama" / "Install App"
   - Ikon KasirKu akan muncul seperti aplikasi native
   - Aplikasi tetap bisa dibuka meski koneksi internet mati (offline shell)

   Untuk tes cepat di komputer sendiri tanpa upload, jalankan server lokal:
     python3 -m http.server 8080
   lalu buka: http://localhost:8080/index.html

CATATAN PENTING
----------------
- Semua data (produk, stok, transaksi, akun kasir) disimpan di penyimpanan
  lokal browser (IndexedDB) pada perangkat yang dipakai. Jangan hapus data
  browser/cache jika tidak ingin kehilangan data.
- Gunakan menu "Pengaturan > Keamanan Data > Unduh Backup Data JSON" secara
  rutin untuk mencadangkan data.
- Ganti kode QRIS statis warung Anda di menu Pengaturan agar fitur pembayaran
  QRIS dinamis berfungsi dengan rekening/merchant Anda sendiri.
