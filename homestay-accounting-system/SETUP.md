# Panduan Setup

1. **Extract ZIP** lalu **buka folder di VS Code**.
2. Buat project di https://supabase.com (New project).
3. Buka **SQL Editor** > New query. Copy isi `supabase/supabase_setup.sql`, paste, **Run**.
4. Ulangi untuk `supabase/seed.sql` (data contoh, jalankan sekali).
5. **Authentication > Users > Add user**: isi email + password, centang *Auto Confirm User*.
6. **Project Settings > API**: salin *Project URL* dan *Publishable/anon key*.
7. Buka `config/supabase-config.js`, ganti dua nilai, simpan.
8. Jalankan lokal: klik kanan `index.html` > **Open with Live Server** (ekstensi VS Code).
9. **Test login** dengan user langkah 5.
10. **Test transaksi**: Invoice baru, 3 malam Standard Room = Rp1.500.000. Cek Jurnal Umum (D Piutang, K Pendapatan).
11. **Test pembayaran**: Rp1.000.000 > sisa Rp500.000, status Sebagian. Bayar Rp500.000 > Rp0, status Lunas.
12. Cek Jurnal, Buku Besar, Dashboard, dan Laporan ikut berubah.
13. Buat repository kosong di GitHub, lalu di terminal VS Code:
```bash
git init
git branch -M main
git add .
git commit -m "Initial commit - Homestay Accounting System"
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```
14. GitHub: **Settings > Pages > Source: GitHub Actions**. Situs aktif di `https://USERNAME.github.io/REPOSITORY/`.

Catatan: publishable/anon key memang aman ada di frontend karena data dilindungi RLS. Jangan pernah memakai service_role key.
