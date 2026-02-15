# 4. Analisis Risiko

## A. Kategori Risiko

### 1. Risiko Teknis

#### 1.1 Server/Hosting Down
**Level**: 🔴 HIGH
- **Dampak**: 
  - Website tidak bisa diakses
  - Customer tidak bisa booking
  - Loss of revenue
  - Reputasi buruk
  
- **Probability**: Medium (5-10% per tahun dengan hosting standar)

- **Mitigation**:
  - ✅ Pilih hosting dengan SLA 99.5%+ (VPS lebih reliable dari shared)
  - ✅ Setup monitoring (UptimeRobot, free)
  - ✅ Auto-restart service jika crash
  - ✅ Backup server/failover (untuk bisnis critical)
  
- **Contingency Plan**:
  - Siapkan landing page backup di hosting berbeda
  - Komunikasi via WhatsApp/social media jika website down
  - Sistem manual fallback (terima booking via WA)

---

#### 1.2 Database Corruption/Data Loss
**Level**: 🔴 CRITICAL
- **Dampak**:
  - Hilang data customer, transaksi, inventory
  - Bisnis bisa lumpuh total
  - Legal issue (kehilangan data customer)

- **Probability**: Low tapi impact sangat besar

- **Mitigation**:
  - ✅ Auto backup database HARIAN
  - ✅ Backup ke multiple location (local + cloud)
  - ✅ Test restore backup secara berkala (monthly)
  - ✅ Replication database (master-slave) untuk production
  
- **Contingency Plan**:
  - Recovery procedure terdokumentasi
  - Maximum data loss: 24 jam (daily backup)
  - Bisa downgrade ke sistem manual sementara

---

#### 1.3 Security Breach (Hacking/Data Breach)
**Level**: 🔴 HIGH
- **Dampak**:
  - Data customer bocor (nama, no HP, email)
  - Website di-deface
  - Malware injection
  - Kehilangan kepercayaan customer

- **Probability**: Medium (website adalah target umum hacker)

- **Mitigation**:
  - ✅ SSL/HTTPS wajib (enkripsi komunikasi)
  - ✅ Input validation & sanitization (cegah SQL injection, XSS)
  - ✅ Password hashing dengan bcrypt (never plain text)
  - ✅ Rate limiting untuk API (cegah brute force)
  - ✅ Update dependencies secara berkala (patch security issues)
  - ✅ Principle of least privilege (user hanya akses yang mereka butuh)
  - ✅ Security headers (CSP, X-Frame-Options, dll)
  
- **Contingency Plan**:
  - Incident response plan
  - Notifikasi user jika terjadi breach
  - Reset password semua user jika perlu

---

#### 1.4 Bug/Error Kritis di Production
**Level**: 🟡 MEDIUM
- **Dampak**:
  - Fitur tidak berfungsi (misal: payment gagal terus)
  - Customer frustasi
  - Loss of revenue

- **Probability**: Medium (apalagi di early launch)

- **Mitigation**:
  - ✅ Thorough testing sebelum deploy (unit test, integration test)
  - ✅ Staging environment untuk test sebelum production
  - ✅ Error logging & monitoring (Sentry, LogRocket)
  - ✅ Feature flag (bisa matikan fitur bermasalah tanpa full deploy)
  
- **Contingency Plan**:
  - Hotfix procedure (deploy critical fix cepat)
  - Rollback ke versi sebelumnya jika perlu
  - Communication plan ke user (info maintenance)

---

### 2. Risiko Bisnis

#### 2.1 Customer Tidak Adopsi Platform Digital
**Level**: 🟡 MEDIUM
- **Dampak**:
  - Low traffic/usage
  - ROI tidak tercapai
  - Proyek dianggap gagal

- **Probability**: Medium (bisa terjadi jika target market tidak tech-savvy)

- **Mitigation**:
  - ✅ User research & testing sebelum launch
  - ✅ UI/UX yang SANGAT mudah dipakai (even for pemula)
  - ✅ Tutorial/guide untuk first-time user
  - ✅ Customer support responsive (WA, chat)
  - ✅ Promo early adopter (diskon untuk pengguna awal)
  - ✅ Tetap terima booking offline (transisi bertahap)
  
- **Contingency Plan**:
  - Gather feedback intensif di bulan pertama
  - Iterasi cepat berdasarkan feedback
  - Marketing & edukasi customer tentang benefit platform

---

#### 2.2 Kompetitor Meluncurkan Platform Serupa
**Level**: 🟡 MEDIUM
- **Dampak**:
  - Market share terbagi
  - Pressure untuk harga lebih murah
  - Butuh differentiation

- **Probability**: Medium-High (barrier to entry tidak terlalu tinggi)

- **Mitigation**:
  - ✅ Unique value proposition (misalnya: reward points, best customer service)
  - ✅ First-mover advantage (launch cepat)
  - ✅ Loyalty program untuk retain customer
  - ✅ Quality > quantity (sepeda terawat, service excellent)
  - ✅ Local SEO optimization (rank tinggi di Google)
  
- **Contingency Plan**:
  - Monitor kompetitor pricing & features
  - Continuous improvement & innovation
  - Build brand loyalty

---

#### 2.3 Payment Gateway Gagal/Issue
**Level**: 🟡 MEDIUM
- **Dampak**:
  - Customer tidak bisa bayar
  - Abandoned bookings
  - Revenue loss

- **Probability**: Low-Medium (payment provider bisa down)

- **Mitigation**:
  - ✅ Multiple payment options (Midtrans, transfer manual, cash)
  - ✅ Fallback ke payment manual jika gateway error
  - ✅ Clear error message & alternative payment instruction
  
- **Contingency Plan**:
  - Manual confirmation system
  - Customer service handle payment issue case-by-case

---

### 3. Risiko Operasional

#### 3.1 Sepeda Rusak/Hilang Saat Rental
**Level**: 🟡 MEDIUM
- **Dampak**:
  - Loss of asset
  - Customer dispute
  - Inventory berkurang

- **Probability**: Medium (bisa terjadi)

- **Mitigation**:
  - ✅ Sistem deposit/jaminan (KTP/SKCK scan, deposit uang)
  - ✅ Foto kondisi sepeda sebelum & sesudah rental
  - ✅ Terms & conditions jelas (tanggung jawab customer)
  - ✅ Asuransi sepeda (untuk high-value bikes)
  - ✅ GPS tracker (untuk sepeda mahal) - future enhancement
  
- **Contingency Plan**:
  - Dispute resolution procedure
  - Blacklist customer bermasalah
  - Claim deposit untuk kerusakan

---

#### 3.2 Overboking (Double Booking)
**Level**: 🟡 MEDIUM
- **Dampak**:
  - Customer datang tapi sepeda tidak available
  - Refund/komplain
  - Bad review

- **Probability**: Low (jika sistem dirancang baik)

- **Mitigation**:
  - ✅ Real-time inventory update (database lock/transaction)
  - ✅ Booking confirmation hanya setelah payment
  - ✅ Buffer time antar booking (30 min untuk cleaning/checking)
  - ✅ Notification ke admin jika inventory < threshold
  
- **Contingency Plan**:
  - Upgrade customer ke sepeda lebih bagus (gratis)
  - Refund + voucher kompensasi
  - Partner dengan rental lain untuk backup bike

---

#### 3.3 Staff/Owner Tidak Familiar dengan Admin Panel
**Level**: 🟢 LOW
- **Dampak**:
  - Salah input data
  - Tidak maksimal pakai fitur
  - Butuh training berkali-kali

- **Probability**: Medium (umum terjadi)

- **Mitigation**:
  - ✅ UI admin panel yang intuitif & simple
  - ✅ User manual/documentation lengkap (Bahasa Indonesia)
  - ✅ Video tutorial step-by-step
  - ✅ Training session sebelum go-live
  - ✅ In-app tooltips & help text
  
- **Contingency Plan**:
  - Support hotline/WA untuk admin issues
  - Remote assistance (TeamViewer/AnyDesk)

---

### 4. Risiko Proyek (Development Phase)

#### 4.1 Timeline Delay
**Level**: 🟡 MEDIUM
- **Dampak**:
  - Launch tertunda
  - Budget overrun (jika bayar developer per bulan)
  - Missed market opportunity (misal target launch sebelum peak season)

- **Probability**: High (80% proyek IT delay)

- **Mitigation**:
  - ✅ Realistic timeline dengan buffer 20%
  - ✅ Weekly sprint review (early warning)
  - ✅ Clear scope & requirements (no scope creep)
  - ✅ Prioritize MVP (launch minimal dulu, iterate later)
  - ✅ Daily standup meeting (untuk tim)
  
- **Contingency Plan**:
  - Cut non-critical features
  - Soft launch (limited users) dulu
  - Add resources (temporary contractor) jika perlu

---

#### 4.2 Developer Resign/Sakit/Unavailable
**Level**: 🔴 HIGH
- **Dampak**:
  - Project stuck
  - Knowledge loss
  - Cari replacement butuh waktu

- **Probability**: Medium

- **Mitigation**:
  - ✅ Code documentation yang baik
  - ✅ Version control (Git) dengan commit messages jelas
  - ✅ Code review (minimal 2 orang paham codebase)
  - ✅ Pair programming untuk critical features
  - ✅ Knowledge transfer session
  - ✅ Contract yang jelas (notice period, knowledge transfer obligation)
  
- **Contingency Plan**:
  - Backup developer (freelancer on-call)
  - Extend timeline
  - Hire replacement ASAP

---

#### 4.3 Budget Overrun
**Level**: 🟡 MEDIUM
- **Dampak**:
  - Proyek terhenti di tengah jalan
  - Features dipotong
  - Quality compromise

- **Probability**: Medium

- **Mitigation**:
  - ✅ Detailed budget breakdown di awal
  - ✅ Buffer 20% dari total budget
  - ✅ Fixed-price contract (jika outsource)
  - ✅ Phased payment (milestone-based)
  - ✅ Regular budget tracking
  
- **Contingency Plan**:
  - Launch MVP dengan limited features
  - Cari funding tambahan
  - Self-funding untuk critical features

---

#### 4.4 Requirement Berubah di Tengah Jalan (Scope Creep)
**Level**: 🟡 MEDIUM
- **Dampak**:
  - Timeline delay
  - Budget overrun
  - Developer frustasi

- **Probability**: High (sangat umum)

- **Mitigation**:
  - ✅ Documented & approved requirements di awal
  - ✅ Change request procedure (formal, ada timeline & cost impact)
  - ✅ Stakeholder alignment (owner setuju dengan scope awal)
  - ✅ Phase-based development (new features di phase 2/3)
  
- **Contingency Plan**:
  - Re-negotiate timeline & budget
  - Prioritize changes (critical vs nice-to-have)

---

## B. Risk Matrix

| Risiko | Level | Probability | Impact | Priority |
|--------|-------|-------------|--------|----------|
| Server down | 🔴 HIGH | Medium | High | 🔥 P1 |
| Data loss | 🔴 CRITICAL | Low | Critical | 🔥 P1 |
| Security breach | 🔴 HIGH | Medium | High | 🔥 P1 |
| Developer resign | 🔴 HIGH | Medium | High | 🔥 P1 |
| Bug kritis | 🟡 MEDIUM | Medium | Medium | ⚠️ P2 |
| Low adoption | 🟡 MEDIUM | Medium | High | ⚠️ P2 |
| Kompetitor | 🟡 MEDIUM | Medium | Medium | ⚠️ P2 |
| Payment issue | 🟡 MEDIUM | Low | Medium | ⚠️ P2 |
| Sepeda rusak/hilang | 🟡 MEDIUM | Medium | Medium | ⚠️ P2 |
| Overbooking | 🟡 MEDIUM | Low | Medium | ⚠️ P2 |
| Timeline delay | 🟡 MEDIUM | High | Medium | ⚠️ P2 |
| Budget overrun | 🟡 MEDIUM | Medium | Medium | ⚠️ P2 |
| Scope creep | 🟡 MEDIUM | High | Medium | ⚠️ P2 |
| Staff tidak familiar | 🟢 LOW | Medium | Low | ✅ P3 |

---

## C. Risk Response Plan (Quick Reference)

### Prevention (Sebelum terjadi):
1. ✅ Auto backup harian
2. ✅ Security best practices
3. ✅ Thorough testing
4. ✅ Clear documentation
5. ✅ Monitoring & alerting
6. ✅ Realistic timeline & buffer
7. ✅ Good contract & agreement

### Detection (Deteksi cepat):
1. ✅ Uptime monitoring
2. ✅ Error logging (Sentry)
3. ✅ Weekly project review
4. ✅ User feedback channel

### Response (Kalau terjadi):
1. ✅ Incident response plan terdokumentasi
2. ✅ Escalation path jelas (siapa yang handle apa)
3. ✅ Backup & rollback procedure ready
4. ✅ Communication template (info ke user)

---

*Review risk analysis ini setiap 3 bulan atau saat ada perubahan major*

**Last updated**: 15 Februari 2026
