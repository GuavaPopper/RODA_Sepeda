# 2. Identifikasi Masalah dan Kebutuhan

## A. Masalah yang Dihadapi (Current Pain Points)

### Masalah Operasional
1. **Sistem manual tidak efisien**
   - Pencatatan rental masih pakai buku/excel
   - Sulit tracking sepeda mana yang sedang disewa
   - Rawan human error dalam pencatatan

2. **Kesulitan manajemen inventory**
   - Tidak tahu realtime sepeda mana yang available
   - Sulit track kondisi sepeda (maintenance schedule)
   - Inventory count manual, memakan waktu

3. **Proses transaksi lambat**
   - Customer harus datang langsung ke lokasi
   - Antrian saat peak season/weekend
   - Pembayaran cash only atau transfer manual

### Masalah Customer Experience
4. **Informasi tidak transparan**
   - Customer tidak bisa cek ketersediaan sebelum datang
   - Tidak ada info harga yang jelas di platform
   - Tidak ada review/rating sistem

5. **Booking tidak fleksibel**
   - Tidak bisa booking di muka
   - Tidak ada sistem reminder/notifikasi
   - Kalau telat return, sulit koordinasi

### Masalah Business Intelligence
6. **Tidak ada data analytics**
   - Sulit tahu peak hours/season
   - Tidak ada insights customer behavior
   - Laporan keuangan manual, tidak realtime

---

## B. Kebutuhan Sistem (System Requirements)

### Kebutuhan Fungsional

#### Untuk Customer:
- [x] **Katalog Sepeda Online**
  - Lihat semua sepeda yang tersedia dengan foto
  - Filter berdasarkan tipe, harga, lokasi
  - Detail spesifikasi sepeda

- [x] **Sistem Booking**
  - Pilih sepeda dan durasi rental
  - Pilih tanggal & waktu pengambilan/pengembalian
  - Konfirmasi booking realtime

- [x] **Pembayaran Digital**
  - Multiple payment methods (transfer, e-wallet, kartu kredit)
  - Payment gateway terintegrasi
  - Bukti pembayaran otomatis

- [x] **Tracking Rental**
  - Status rental (aktif, selesai, overdue)
  - Countdown timer durasi rental
  - Notifikasi reminder waktu pengembalian

- [x] **User Account**
  - Register & login
  - Riwayat transaksi
  - Profile management

#### Untuk Admin/Owner:
- [x] **Dashboard Admin**
  - Overview: total sepeda, yang tersewa, revenue hari ini
  - Grafik statistik rental
  - Laporan keuangan

- [x] **Manajemen Inventory**
  - CRUD sepeda (tambah, edit, hapus)
  - Update status (available, rented, maintenance)
  - Jadwal maintenance tracking

- [x] **Manajemen Booking**
  - Lihat semua booking (pending, confirmed, completed)
  - Approve/reject booking
  - Update status rental (picked up, returned)

- [x] **Manajemen Customer**
  - Database customer
  - Riwayat rental per customer
  - Blacklist customer bermasalah

- [x] **Laporan & Analytics**
  - Laporan harian/bulanan
  - Most rented bikes
  - Revenue report
  - Customer analytics

### Kebutuhan Non-Fungsional

1. **Performance**
   - Loading time < 3 detik
   - Handle 100+ concurrent users
   - Database optimized untuk query cepat

2. **Security**
   - SSL/HTTPS wajib
   - Password encryption
   - Input validation & sanitization
   - Protection dari SQL injection & XSS

3. **Usability**
   - UI responsive (mobile-friendly)
   - Navigasi intuitif
   - Bahasa Indonesia

4. **Reliability**
   - Uptime 99.5%
   - Auto backup database harian
   - Error handling yang baik

5. **Scalability**
   - Bisa tambah fitur baru
   - Support multiple lokasi rental (future)

---

## C. Prioritas Fitur (MVP vs Future)

### Phase 1 - MVP (Minimum Viable Product)
- ✅ Katalog sepeda
- ✅ Booking sederhana
- ✅ Pembayaran transfer manual (konfirmasi admin)
- ✅ Dashboard admin basic
- ✅ Inventory management

### Phase 2 - Enhancement
- Payment gateway otomatis
- Notifikasi email/WhatsApp
- Rating & review system
- Loyalty program

### Phase 3 - Advanced
- Mobile app (Android/iOS)
- GPS tracking sepeda
- AI recommendation
- Multi-branch support

---

*Update dokumen ini setelah wawancara dengan owner untuk validasi masalah & prioritas fitur*
