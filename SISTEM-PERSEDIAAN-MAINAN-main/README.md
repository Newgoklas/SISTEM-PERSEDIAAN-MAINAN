# Sistem Akuntansi Persediaan Toko Mainan

Aplikasi web untuk mencatat persediaan, transaksi, dan laporan akuntansi toko mainan. Frontend dibuat dengan HTML, CSS, dan JavaScript, sedangkan data disimpan di Supabase.

## Fitur

- Dashboard ringkasan persediaan dan aktivitas toko
- Pengelolaan barang, pemasok, dan pelanggan
- Transaksi pembelian, penjualan, dan penyesuaian stok
- Jurnal umum dan buku besar
- Laporan stok, pembelian, penjualan, kartu persediaan, laba rugi, dan neraca
- Pengaturan profil toko

## Struktur Proyek

```text
UTS/
  backend/
    database.sql
  frontend/
    css/style.css
    html/index.html
    js/app.js
    js/config.js
```

File pada folder utama merupakan salinan aplikasi. Untuk menjalankan aplikasi, gunakan versi di `UTS/frontend` karena path HTML, CSS, dan JavaScript-nya sudah sesuai dengan struktur folder.

## Persiapan Supabase

1. Buat atau buka proyek di [Supabase Dashboard](https://supabase.com/dashboard).
2. Buka **SQL Editor**, lalu jalankan isi file `UTS/backend/database.sql` untuk membuat tabel dan kebijakan yang disertakan.
3. Buka pengaturan API proyek dan salin **Project URL** serta **publishable/anon key**.
4. Ganti nilai `SUPABASE_URL` dan `SUPABASE_ANON_KEY` di `UTS/frontend/js/config.js` dengan nilai dari proyek Anda.

URL Supabase yang saat ini tersimpan di konfigurasi tidak dapat ditemukan oleh DNS (`DNS_PROBE_FINISHED_NXDOMAIN`). Ganti dengan Project URL yang tampil di dashboard Supabase Anda. Jangan menebak URL atau memakai `service_role` key di frontend.

Frontend menggunakan key publik, sehingga akses tabel perlu dilindungi dengan kebijakan Row Level Security (RLS) yang sesuai sebelum aplikasi digunakan dengan data sungguhan.

## Menjalankan Aplikasi

Jalankan server HTTP lokal dari folder utama proyek:

```powershell
py -m http.server 8000
```

Buka alamat berikut di browser:

```text
http://localhost:8000/UTS/frontend/html/
```

Jika perintah `py` tidak tersedia, gunakan ekstensi Live Server di VS Code dan buka `UTS/frontend/html/index.html` melalui Live Server. Jangan membuka file HTML langsung dengan skema `file://`.

## Catatan

- Browser harus terhubung ke internet untuk memuat Supabase JavaScript dari jsDelivr dan berkomunikasi dengan Supabase.
- Jika muncul `Failed to fetch` atau `DNS_PROBE_FINISHED_NXDOMAIN`, pastikan Project URL benar, proyek Supabase aktif, dan jaringan/DNS dapat mengakses domain Supabase.
- Jika muncul pesan izin atau tabel tidak ditemukan, periksa hasil eksekusi SQL serta konfigurasi akses tabel di Supabase.