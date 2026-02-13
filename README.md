# SPLOG - Sistem Pengelolaan Logistik OJK Jawa Timur

![Status](https://img.shields.io/badge/Status-Development_Phase-orange)
![Version](https://img.shields.io/badge/Version-1.2.0-blue)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google_Sheets-34A853?style=for-the-badge&logo=google-sheets&logoColor=white)
![Google Apps Script](https://img.shields.io/badge/Google_Apps_Script-4285F4?style=for-the-badge&logo=google-apps-script&logoColor=white)

## 1. Deskripsi Projek 📝
**SPLOG** (Sistem Pengelolaan Logistik) adalah platform manajemen logistik terintegrasi yang dikembangkan khusus untuk mengoptimalkan operasional di Kantor Otoritas Jasa Keuangan (OJK) Provinsi Jawa Timur. Website ini mendigitalisasi seluruh rantai pengadaan barang internal—mulai dari eksplorasi katalog elektronik hingga verifikasi stok otomatis—guna menciptakan ekosistem kerja yang lebih transparan, efisien, dan terukur.

## 2. Manfaat Website 🚀
* **Digitalisasi Inventaris**: Menghilangkan ketergantungan pada pencatatan manual yang rentan terhadap *human error* dan kehilangan data.
* **Real-Time Monitoring**: Menjamin data stok di gudang selalu sinkron dengan tampilan di website melalui metode *background polling*.
* **Integritas & Keamanan Data**: Mencegah anomali stok (seperti stok minus) melalui validasi input otomatis *Zero-Floor Logic*.
* **Optimalisasi UX**: Memberikan kemudahan bagi pegawai dalam mengajukan kebutuhan kantor melalui antarmuka yang responsif dan modern.

## 3. Fitur Utama ✨

### 👤 Fitur Pegawai (User)
* **Katalog Interaktif**: Eksplorasi kebutuhan logistik berdasarkan kategori dengan navigasi *sticky* yang stabil.
* **Smart Shopping Cart**: Sistem keranjang belanja yang mendukung input manual hingga 3 digit dengan logika penghapusan angka yang cerdas.
* **Lacak Pengajuan**: Fasilitas pelacakan status pengajuan secara *real-time* mulai dari tahap *pending* hingga disetujui.
* **Search Engine**: Pencarian cepat item berdasarkan nama atau kode barang menggunakan mesin pencari internal.

### 🔑 Fitur Pengelola (Admin)
* **Dashboard Analytics**: Ringkasan visual terkait total inventaris, status pengajuan, dan peringatan stok kritis.
* **Manajemen Stok**: Kendali penuh untuk menambah, mengubah, atau menghapus item dengan proteksi stok otomatis.
* **Approval System**: Mekanisme verifikasi pengajuan pegawai yang terhubung langsung dengan basis data pusat.
* **Manajemen Akun**: Pembuatan akun baru untuk Pegawai atau Admin tambahan dengan sistem hak akses (*Role-Based Access*).

---

## 4. Arsitektur Sistem & Aliran Data 🏗️

Sistem dibangun dengan pola *Three-Tier Architecture* berbasis layanan *Cloud Serverless* untuk menjamin efisiensi dan skalabilitas.

### 🛠️ Komponen Teknologi
| Lapisan | Teknologi | Peran & Tanggung Jawab |
| :--- | :---: | :--- |
| **Frontend** | ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) | Mengelola antarmuka (UI), *State Management*, dan logika navigasi responsif menggunakan komponen fungsional. |
| **Styling** | ![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white) | Framework CSS *Utility-first* untuk membangun tata letak grid dan elemen visual yang konsisten dengan *brand identity* OJK. |
| **API/Middleware** | ![Google Apps Script](https://img.shields.io/badge/Google_Apps_Script-4285F4?style=flat-square&logo=google-apps-script&logoColor=white) | Menjadi jembatan (Restful API Gateway) yang memproses permintaan HTTPS (GET/POST) dan memvalidasi logika bisnis. |
| **Database** | ![Google Sheets](https://img.shields.io/badge/Google_Sheets-34A853?style=flat-square&logo=google-sheets&logoColor=white) | Penyimpanan data utama (NoSQL-like) yang menyimpan tabel Inventaris, User, dan Riwayat Transaksi secara terstruktur. |



### 📡 Aliran Sinkronisasi Data
1. **Initial Fetch**: Saat aplikasi dibuka, React mengirimkan permintaan HTTPS ke URL Web App Google Apps Script.
2. **JSON Transformation**: Apps Script mengekstraksi data dari Spreadsheet, mengonversinya menjadi format JSON, dan mengirimkannya kembali ke Frontend.
3. **Background Polling**: Sistem menjalankan sinkronisasi otomatis setiap **30 detik** di latar belakang menggunakan `setInterval` untuk menjaga pembaruan data stok tanpa mengganggu interaksi pengguna.
4. **Data Integrity**: Setiap aksi perubahan stok oleh Admin divalidasi secara *real-time* di sisi klien sebelum dikirimkan ke database.

---
**Developed by:** [Dimas Wahyu Saputra](https://github.com/DimsWhyu) - Sains Data ITS 2023.