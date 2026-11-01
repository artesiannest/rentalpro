# Rental Pro — Fleet Management | Demo GitHub Pages

Demo baru berdasarkan referensi Rental Pro pada portfolio Nestiara. Halaman login interaktif menggunakan tema navy–biru, ilustrasi mobil SVG bergerak, animasi kartu informasi, tombol isi akun, lihat/sembunyikan password, dan layout responsif. Sidebar gelap dan kartu statistik berwarna mengikuti ciri screenshot portfolio.

## Akun demo publik
Username: demo@dapurkreatif.com
Password: dapurkreatifSCODERS26!

Kredensial tercantum di login. Klik Isi akun demo, lalu Masuk ke Rental Pro. Kolom username/password memiliki ukuran yang sama.

## Upload GitHub Pages
1. Ekstrak ZIP ini.
2. Buat repository PUBLIC bernama rental-pro-demo di GitHub.
3. Add file > Upload files. Unggah ISI folder RentalPro-Demo, termasuk folder assets. index.html harus langsung di root, sejajar dengan app.js dan style.css. Jangan hanya upload ZIP-nya.
4. Commit changes.
5. Settings > Pages > Deploy from a branch > main > / (root) > Save.
6. Tunggu deployment selesai. Buka URL yang ditampilkan GitHub Pages.
7. Pola alamat untuk akun artesiannest dan repository rental-pro-demo adalah https://artesiannest.github.io/rental-pro-demo/. Paket ini belum dipublikasikan; gunakan URL deployment aktual.
8. Untuk menghubungkan portfolio, isi properti demoUrl pada kartu id rental-pro di js/data.js atau kolom URL demo pada CMS portfolio dengan URL yang sudah berhasil dibuka.

Tidak membutuhkan Node.js, npm, backend, Supabase ataupun build. Semua aset dan modul export Excel disertakan lokal.

## Fitur demo
- Login interaktif: isi akun otomatis, lihat/sembunyikan password, indikator tombol, animasi ilustrasi mobil dan jalan. Animasi dinonaktifkan otomatis jika perangkat memilih reduced motion.
- Dashboard: jumlah armada, ketersediaan hari ini, pemesanan aktif, total penerimaan, nilai kontrak per bulan dan transaksi terbaru.
- Kendaraan: tambah/edit kendaraan, pelat unik, kategori, transmisi, tahun, tarif per hari dan status aktif. Tarif kontrak yang sudah dibuat tidak berubah ketika tarif kendaraan diperbarui.
- Pelanggan: tambah/edit profil dan kontak fiktif, pencarian dan jumlah penyewaan.
- Penyewaan: pilih pelanggan/kendaraan, tanggal mulai/kembali, estimasi tarif, pembayaran awal, validasi bentrok, detail, mulai sewa, pengembalian dan tambahan pembayaran.
- Pembatalan hanya untuk pesanan belum berjalan yang belum memiliki pembayaran. Refund tidak disimulasikan. Kendaraan dapat dikembalikan walaupun masih ada sisa pembayaran, dan sisa tersebut tetap tercatat pada laporan.
- Maintenance: jadwal perawatan, biaya, validasi bentrok dengan sewa/maintenance lain, dan tandai selesai.
- Laporan: filter tanggal mulai kontrak; nilai kontrak, akumulasi pembayaran dan sisa pembayaran. Kontrak dibatalkan dikecualikan dari ringkasan. Export XLSX berisi Penyewaan (mengikuti filter), Armada (seluruh armada), Maintenance (seluruh catatan).
- Detail penyewaan dapat dicetak atau disimpan PDF melalui dialog cetak browser.
- Pengaturan usaha: nama, kontak, alamat, unduh JSON lengkap dan reset data contoh. Versi ini tidak menyediakan import/restore JSON.

## Aturan tanggal
- Satuan sewa adalah hari kalender, bukan per 24 jam berdasarkan jam pengambilan.
- Tanggal kembali eksklusif: mulai 1 November, kembali 3 November = 2 hari.
- Minimal 1 hari. Pemesanan baru ditolak jika berbenturan dengan pemesanan aktif atau jadwal maintenance yang belum selesai.
- Jadwal bersebelahan diperbolehkan: sewa selesai pada tanggal 3 dapat diikuti sewa baru mulai tanggal 3.
- Kendaraan dalam status Berjalan yang belum dikembalikan tetap dianggap dipakai; pemesanan setelah akhir jadwalnya juga ditolak sampai dikembalikan.
- Tombol Mulai Sewa hanya dapat dipakai setelah tanggal mulai tiba dan sebelum tanggal kembali terlewati.
- Tidak ada perhitungan denda, keterlambatan, deposit, refund, biaya sopir, pajak atau pembayaran nyata.

## Data dan penyimpanan
6 kendaraan, 4 pelanggan fiktif, 2 kontrak contoh dan 1 jadwal maintenance. Pelat dengan akhiran DEMO adalah data contoh. Tidak ada pengumpulan NIK atau dokumen identitas.
Data disimpan pada localStorage browser pengunjung, terpisah antarperangkat/pengunjung. Logout tidak menghapus data. Menghapus data browser/reset menghapus perubahan. Login publik adalah pemeriksaan frontend untuk demonstrasi alur, bukan autentikasi produksi. Semua pembayaran merupakan pencatatan simulasi.

## Pemeriksaan
Sintaks JavaScript lulus. Login, tombol isi akun/lihat password dan dashboard diuji di browser desktop. Input email/password sama-sama lebar 395 px dan tinggi 51 px pada viewport pengujian.
Pengujian logika: durasi tanggal, penolakan tanggal tidak valid, bentrok sewa/maintenance, snapshot tarif, penolakan kelebihan bayar dan jadwal bersebelahan lulus. Export Excel tiga sheet berhasil dibaca ulang. Belum diuji pada perangkat fisik atau dipublikasikan ke GitHub.

## Berkas
index.html, app.js, style.css, assets/xlsx.full.min.js, assets/LICENSE-SheetJS.txt, .nojekyll, README.md.
Modul Excel: SheetJS CE 0.20.3, lisensi Apache 2.0 disertakan.

Dapur Kreatif / SCODE · Portfolio Nestiara
