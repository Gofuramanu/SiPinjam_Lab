# 🔬 Sistem Informasi Manajemen Peminjaman Alat Laboratorium (SIPINJAM LAB)

Aplikasi web berbasis **Laravel 12 (PHP MVC)** yang dirancang untuk mengelola peminjaman dan inventarisasi alat laboratorium secara efisien, transparan, dan terstruktur dengan sistem **Multi-Role (Admin Petugas Lab & User Mahasiswa)**.

---

## 👥 Pengembang (Kelompok 6)
Proyek Tugas Manajemen Sistem Informasi:
* **Lian Rosyid Alamzah** (24051130084)
* **Aditya Danu Marizta** (24051130094)
* **Muhammad Ghafur Amanu Putra Warnada** (24051130103)

---

## 🚀 Fitur Utama

### 1. 🛡️ Portal Admin (Petugas Laboratorium)
* **Dashboard Statistik & Analitik**: Monitoring total barang, kategori, mahasiswa terdaftar, transaksi aktif, serta rekapitulasi denda.
* **Manajemen Barang (CRUD)**: Pengelolaan kode alat, nama, spesifikasi, kategori, total stok, dan ketersediaan stok fisik.
* **Manajemen Kategori**: Pengelompokan alat lab berdasarkan kategori/jenis.
* **Verifikasi & Pengembalian Transaksi**:
  * Pengecekan kondisi fisik barang saat kembali (Baik / Rusak).
  * Perhitungan denda otomatis jika melewati batas toleransi pengembalian.
  * Penambahan biaya servis/perbaikan jika alat rusak.
  * Pengembalian stok barang secara otomatis.

### 2. 🎓 Portal User (Mahasiswa)
* **Katalog Alat Lab**: Pencarian alat berdasarkan nama/kode dan filter kategori dengan informasi ketersediaan stok *real-time*.
* **Pengajuan Pinjaman Mandiri**: Formulir peminjaman dengan data peminjam otomatis terhubung ke akun mahasiswa yang aktif.
* **Dashboard & Riwayat Pinjaman**: Memantau status pengajuan, batas waktu peminjaman, serta rincian biaya denda/servis jika ada.

---

## ⚖️ Aturan Bisnis (Business Rules)
1. **Denda Keterlambatan**: Keterlambatan pengembalian lebih dari 3 hari dari tanggal rencana kembali dikenakan denda sebesar **Rp2.000 / hari**.
2. **Biaya Kerusakan**: Pengembalian alat dalam kondisi rusak dikenakan biaya perbaikan tetap sebesar **Rp10.000**.
3. **Kalkulasi Otomatis**: Seluruh kalkulasi denda dihitung otomatis oleh sistem pada controller sehingga meminimalkan *human error*.
4. **Validasi Stok Real-time**: Stok alat otomatis berkurang saat dipinjam dan bertambah kembali ketika proses pengembalian selesai diverifikasi admin.

---

## 🛠️ Teknologi yang Digunakan
* **Backend**: Laravel 12 (PHP MVC Framework)
* **Database**: MySQL / MariaDB
* **Frontend**: Blade Templating, Bootstrap 5, Custom Responsive Dark UI
* **Tools**: Composer, Git

---

## 💻 Panduan Instalasi & Menjalankan Proyek

### 1. Clone Repositori
```bash
git clone https://github.com/<username>/<repo-name>.git
cd Project-Pinjaman-Alat-Laboratorium-main
```

### 2. Install Dependensi
```bash
composer install
npm install && npm run build
```

### 3. Konfigurasi Lingkungan (.env)
Salin `.env.example` menjadi `.env`:
```bash
cp .env.example .env
```
Sesuaikan konfigurasi database Anda di file `.env`:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db_peminjaman_lab
DB_USERNAME=root
DB_PASSWORD=
```

Generate application key:
```bash
php artisan key:generate
```

### 4. Migrasi & Seeder Database
Jalankan migrasi beserta data awal (termasuk akun uji coba):
```bash
php artisan migrate:fresh --seed
```

### 5. Jalankan Server
```bash
php artisan serve
```
Akses aplikasi melalui browser di: `http://127.0.0.1:8000`

---

## 🔑 Akun Demo Pengujian

| Peran | Username / NIM | Password | Keterangan |
|---|---|---|---|
| **Admin** | `admin` | `admin123` | Petugas Lab (Akses Penuh) |
| **Mahasiswa** | `24051130084` / `24051130094` / `24051130103` | `123456` | Akun Mahasiswa |
