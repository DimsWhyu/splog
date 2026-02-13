# SPLOG - Sistem Pengelolaan Logistik OJK Jawa Timur

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google_Sheets-34A853?style=for-the-badge&logo=google-sheets&logoColor=white)

## 1. Deskripsi Projek
**SPLOG** adalah platform manajemen logistik terintegrasi yang dikembangkan untuk mengoptimalkan operasional di Kantor Otoritas Jasa Keuangan (OJK) Provinsi Jawa Timur. Website ini mendigitalisasi seluruh proses pengadaan barang, mulai dari katalog elektronik hingga verifikasi stok, guna menciptakan ekosistem kerja yang lebih efisien dan terukur.

## 2. Manfaat Website
* **Digitalisasi Inventaris**: Menghilangkan ketergantungan pada pencatatan manual yang rentan kesalahan.
* **Real-Time Monitoring**: Memastikan data stok di gudang selalu sinkron dengan tampilan di web melalui metode *polling*.
* **Keamanan Data**: Mencegah anomali stok melalui validasi input otomatis seperti *Zero-Floor Logic*.
* **User Experience**: Memberikan kenyamanan bagi pegawai dalam mengajukan kebutuhan kantor dengan UI yang responsif dan modern.

## 3. Fitur Utama

### 👤 Fitur Pegawai (User)
* **Katalog Interaktif**: Eksplorasi barang berdasarkan kategori dengan navigasi *sticky* yang *smooth*.
* **Smart Shopping Cart**: Pengaturan jumlah item yang fleksibel (mendukung 3 digit) dengan logika input manual yang cerdas.
* **Lacak Pengajuan**: Transparansi riwayat transaksi beserta status verifikasi dari Admin.
* **Search & Filter**: Pencarian cepat kebutuhan logistik menggunakan mesin pencari internal.

### 🔑 Fitur Pengelola (Admin)
* **Dashboard Analytics**: Ringkasan data inventaris dan status pengadaan barang terbaru.
* **Manajemen Inventaris**: Pengelolaan stok (Tambah/Edit/Hapus) dengan proteksi stok otomatis agar tidak bernilai negatif.
* **Manajemen User**: Pembuatan akun baru (Pegawai atau Admin tambahan) dengan sistem hak akses (*Role-Based*).
* **Real-Time Sync Control**: Sinkronisasi data otomatis dengan Google Spreadsheet setiap 30 detik.

---

## 4. Arsitektur & Peran Unsur
Sistem ini dibangun dengan arsitektur modern yang memanfaatkan layanan cloud untuk skalabilitas:

| Komponen | Teknologi | Peran & Tanggung Jawab |
| :--- | :--- | :--- |
| **Frontend** | React.js & Tailwind CSS | Mengelola antarmuka pengguna, navigasi, dan logika tampilan yang responsif. |
| **Middleware/API** | Google Apps Script (GAS) | Bertindak sebagai jembatan (API) untuk memproses permintaan data dari Web ke Spreadsheet. |
| **Database** | Google Sheets | Penyimpanan data utama untuk tabel Inventaris, User, dan Riwayat Transaksi. |
| **Data Flow** | HTTPS (JSON) | Pertukaran data antar komponen menggunakan format JSON untuk integritas data yang tinggi. |



---

## 5. Saran Pengembangan (Next Steps)
Untuk memaksimalkan potensi sistem ini, berikut adalah saran pengembangan di masa mendatang:
1. **Predictive Procurement**: Mengimplementasikan model Sains Data untuk memprediksi kapan barang akan habis berdasarkan tren historis.
2. **Export Report**: Fitur unduh laporan bulanan otomatis dalam format PDF/Excel untuk keperluan audit formal OJK.
3. **Notification System**: Integrasi dengan Gmail/WhatsApp API untuk memberikan notifikasi instan saat pengajuan disetujui.
4. **Dark Mode Support**: Penyesuaian tema visual untuk kenyamanan pengguna di berbagai kondisi cahaya.

---
**Developed by:** [Dimas Wahyu Saputra](https://github.com/dimaswahyusaputra) - Sains Data ITS 2023.