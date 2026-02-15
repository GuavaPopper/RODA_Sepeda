# 3. Perencanaan Sumber Daya

## A. Sumber Daya Manusia (SDM)

### Tim Inti

#### 1. Project Manager
- **Jumlah**: 1 orang
- **Tanggung jawab**:
  - Koordinasi seluruh tim
  - Timeline & milestone tracking
  - Komunikasi dengan client/owner rental
  - Risk management
- **Estimasi waktu**: Full project duration

#### 2. UI/UX Designer
- **Jumlah**: 1 orang
- **Tanggung jawab**:
  - Wireframe & mockup
  - User flow design
  - Visual design (warna, logo, branding)
  - Prototype interaktif
- **Estimasi waktu**: 2-3 minggu

#### 3. Frontend Developer
- **Jumlah**: 1-2 orang
- **Tanggung jawab**:
  - Convert design ke HTML/CSS/JS
  - Integrasi dengan backend API
  - Responsive implementation
  - Testing frontend
- **Skill**: HTML, CSS, JavaScript, React/Vue.js
- **Estimasi waktu**: 4-6 minggu

#### 4. Backend Developer
- **Jumlah**: 1-2 orang
- **Tanggung jawab**:
  - Database design
  - API development
  - Business logic implementation
  - Security implementation
  - Payment gateway integration
- **Skill**: Node.js/PHP, MySQL/PostgreSQL, REST API
- **Estimasi waktu**: 4-6 minggu

#### 5. QA Tester (Optional tapi direkomendasikan)
- **Jumlah**: 1 orang
- **Tanggung jawab**:
  - Testing functionality
  - Bug reporting
  - User acceptance testing (UAT)
- **Estimasi waktu**: 2 minggu (parallel dengan development)

---

## B. Sumber Daya Teknologi

### 1. Tech Stack

#### Frontend
- **Framework**: React.js atau Vue.js
  - *Alasan*: Modern, component-based, banyak library pendukung
- **Styling**: Tailwind CSS atau Bootstrap
- **State Management**: Redux (React) / Vuex (Vue)
- **Build Tool**: Vite atau Webpack

#### Backend
- **Option 1 - Node.js**
  - Express.js framework
  - Fast, scalable, JavaScript full-stack
  
- **Option 2 - PHP**
  - Laravel framework
  - Mature, dokumentasi lengkap, banyak tutorial Indonesia

- **Rekomendasi**: Node.js (lebih modern, performance baik)

#### Database
- **Primary DB**: PostgreSQL atau MySQL
  - *Rekomendasi*: PostgreSQL (lebih robust untuk relational data)
- **Cache** (optional): Redis untuk session & caching

#### Authentication
- JWT (JSON Web Token) untuk stateless auth
- bcrypt untuk password hashing

### 2. Hosting & Infrastructure

#### Domain
- **Biaya**: 
  - .com: Rp 150.000/tahun (~Rp 12.500/bulan)
  - .id: Rp 300.000/2 tahun (~Rp 12.500/bulan)
- **Provider**: Niagahoster, Domainesia, Cloudflare Registrar

#### Hosting
**Option 1 - Shared Hosting** (Budget rendah, traffic rendah)
- Provider: Niagahoster, Hostinger
- Biaya: ~Rp 20.000 - 50.000/bulan
- Cocok untuk: MVP testing, traffic <1000 visit/hari
- Limitasi: Resource terbatas, tidak scalable

**Option 2 - VPS** (Rekomendasi untuk produksi)
- **DigitalOcean Basic Droplet**
  - Spec: 1 vCPU, 1GB RAM, 25GB SSD, 1TB transfer
  - Biaya: $6/bulan (~Rp 96.000/bulan)
- **Vultr Cloud Compute**
  - Spec: 1 vCPU, 1GB RAM, 25GB SSD, 1TB transfer
  - Biaya: $6/bulan (~Rp 96.000/bulan)
- Cocok untuk: Full control, scalable, production-ready
- Location: Singapore (latency rendah untuk Indonesia)

**Option 3 - Cloud Platform** (Modern deployment)
- Vercel/Netlify (frontend) + Railway/Render (backend)
- Biaya: Free tier atau $5-20/bulan (Rp 80.000 - 320.000)
- Cocok untuk: Modern stack, auto-scaling, CI/CD otomatis

**Rekomendasi**: VPS DigitalOcean/Vultr - balance antara biaya, performa, dan kontrol

#### SSL Certificate
- **Let's Encrypt** (GRATIS)
- Auto-renew dengan Certbot
- Trusted oleh semua browser modern

#### CDN (Content Delivery Network)
**Cloudflare Free Tier** (Rekomendasi)
- Biaya: GRATIS
- Features:
  - CDN global
  - DDoS protection
  - SSL/TLS encryption
  - Bandwidth unlimited
  - Cache optimization
- Speed improvement: 30-50% faster loading

### 3. Third-Party Services

#### Payment Gateway
**Midtrans** (Lokal, populer, recommended)
- **Setup Fee**: GRATIS (no monthly subscription)
- **Transaction Fees**:
  - Virtual Account/Transfer Bank: Rp 4.000/transaksi
  - QRIS: 0,7% per transaksi
  - GoPay: 2% per transaksi
  - ShopeePay: 1,5% per transaksi
  - Kartu Kredit: 2,9% + Rp 2.000 per transaksi
  - Over The Counter (Indomaret/Alfamart): Rp 5.000/transaksi
  
- **Contoh Perhitungan** (Rental Rp 50.000):
  - Via Virtual Account: Fee Rp 4.000 (8% dari nilai transaksi)
  - Via QRIS: Fee Rp 350 (0,7%)
  - Via GoPay: Fee Rp 1.000 (2%)
  - Via Kartu Kredit: Fee Rp 3.450 (2,9% + Rp 2.000)

- **Note**: Fee ditanggung merchant (owner), bisa dibebankan ke customer dengan adjust harga final

**Alternative**: Xendit, Doku (pricing serupa)

#### Email Service
**SendGrid Free Tier** (Recommended untuk MVP)
- Biaya: GRATIS
- Quota: 100 email/hari (3.000/bulan)
- Cocok untuk: Notifikasi booking, konfirmasi pembayaran
- Upgrade: $19.95/bulan untuk 40.000 email/bulan (jika perlu)

**Alternative**: 
- Mailgun Free: 5.000 email gratis untuk 3 bulan pertama
- AWS SES: $0.10 per 1.000 email (sangat murah tapi setup lebih kompleks)

#### WhatsApp Notification (Optional)
**Fonnte**
- Biaya: Rp 350.000/bulan (unlimited message)
- Cocok untuk: Reminder booking, konfirmasi, notifikasi pengembalian
- Alternative: WA Business API (lebih mahal, enterprise-level)

#### Storage Foto/Image
**Cloudinary Free Tier** (Recommended)
- Biaya: GRATIS
- Quota:
  - 25 GB storage
  - 25 GB bandwidth/bulan
  - 25.000 transformations/bulan
- Features:
  - Auto image optimization
  - Responsive image delivery
  - CDN included
- Cocok untuk: Foto sepeda, user profile pictures
- Upgrade: $89/bulan untuk 89 credits (jika perlu lebih)

**Alternative**: 
- Supabase Storage (2GB free, unlimited bandwidth)
- AWS S3 + CloudFront (lebih murah untuk traffic tinggi, tapi setup kompleks)
- Local server storage (gratis tapi butuh backup manual)

### 4. Development Tools

- **Version Control**: Git + GitHub/GitLab
- **Project Management**: Trello, Notion, atau Jira
- **Design**: Figma (gratis untuk basic)
- **API Testing**: Postman atau Insomnia
- **Code Editor**: VS Code
- **Database Client**: DBeaver, TablePlus

---

## C. Estimasi Biaya

### Biaya Development (One-time)

| Item | Harga |
|------|-------|
| UI/UX Design | Rp 2.000.000 - 5.000.000 |
| Frontend Development | Rp 5.000.000 - 10.000.000 |
| Backend Development | Rp 7.000.000 - 15.000.000 |
| Testing & QA | Rp 1.500.000 - 3.000.000 |
| **TOTAL** | **Rp 15.500.000 - 33.000.000** |

*Note: Harga bisa lebih rendah jika dikerjakan tim internal/mahasiswa*

### Biaya Operasional (Recurring)

#### Bulanan
| Item | Provider | Harga/Bulan | Keterangan |
|------|----------|-------------|------------|
| Domain .com | Domainesia/Niagahoster | Rp 12.500 | Rp 150.000/tahun ÷ 12 bulan |
| Hosting VPS | DigitalOcean Basic | Rp 96.000 | $6/bulan, 1GB RAM, 25GB SSD, 1TB transfer |
| SSL Certificate | Let's Encrypt | GRATIS | Auto-renew, trusted |
| CDN | Cloudflare Free | GRATIS | DDoS protection, unlimited bandwidth |
| Email Service | SendGrid Free | GRATIS | 100 email/hari (cukup untuk MVP) |
| Image Storage | Cloudinary Free | GRATIS | 25GB storage + bandwidth |
| **TOTAL BULANAN** | | **Rp 108.500** | **~Rp 1.300.000/tahun** |

#### Per Transaksi (Payment Gateway - Midtrans)
| Metode Pembayaran | Fee/Transaksi | Contoh (Rental Rp 50.000) |
|-------------------|---------------|---------------------------|
| Virtual Account (BCA, Mandiri, dll) | Rp 4.000 flat | Rp 4.000 (8%) |
| QRIS | 0,7% | Rp 350 |
| GoPay | 2% | Rp 1.000 |
| ShopeePay | 1,5% | Rp 750 |
| DANA | 1,5% | Rp 750 |
| Kartu Kredit | 2,9% + Rp 2.000 | Rp 3.450 |
| Indomaret/Alfamart | Rp 5.000 flat | Rp 5.000 (10%) |

**Note**: 
- Fee payment gateway ditanggung merchant (owner)
- Bisa dibebankan ke customer dengan adjust harga final
- Contoh: Harga rental Rp 50.000 → Harga final untuk customer Rp 54.000 (jika pakai VA)

**Estimasi Biaya Payment Gateway per Bulan**:
- Asumsi: 50 transaksi/bulan dengan rata-rata Rp 50.000
- Asumsi 70% pakai VA/Transfer, 20% QRIS, 10% GoPay
- Biaya: (35 × Rp 4.000) + (10 × Rp 350) + (5 × Rp 1.000) = Rp 148.500/bulan

**Total Operasional Realistis**: Rp 108.500 (infrastruktur) + Rp 148.500 (payment) = **Rp 257.000/bulan**

#### Optional Services (Jika Budget Ada)
| Item | Provider | Harga/Bulan | Benefit |
|------|----------|-------------|---------|
| WhatsApp Notifikasi | Fonnte | Rp 350.000 | Unlimited message, auto reminder |
| Backup Storage | AWS S3 | Rp 50.000 | Backup database offsite |
| Monitoring | UptimeRobot Pro | $7 (~Rp 112.000) | Advanced monitoring, SMS alert |
| Email (Upgrade) | SendGrid Essentials | $19.95 (~Rp 320.000) | 40.000 email/bulan |

**Total dengan Optional**: Rp 257.000 + Rp 350.000 (WA) = **Rp 607.000/bulan** (jika include WA notification)

### Biaya Maintenance (Optional)
- Bug fixes & minor updates: Rp 1.000.000 - 3.000.000/tahun
- Major feature additions: Sesuai scope

---

## D. Timeline Proyek

### Phase 1 - Planning & Design (2-3 minggu)
- Week 1: Requirement gathering, wawancara owner
- Week 2: Wireframe & mockup
- Week 3: Design finalization & approval

### Phase 2 - Development (6-8 minggu)
- Week 1-2: Database design & backend setup
- Week 3-4: Backend API development
- Week 5-6: Frontend development
- Week 7-8: Integration & initial testing

### Phase 3 - Testing & Launch (2-3 minggu)
- Week 1-2: Testing, bug fixing
- Week 3: User acceptance testing (UAT)
- Deployment & go-live

**Total Durasi**: 10-14 minggu (2.5 - 3.5 bulan)

---

## E. Risk & Mitigation

| Risk | Mitigation |
|------|------------|
| Developer resign/sakit | Dokumentasi kode yang baik, pair programming |
| Budget overrun | Buffer 20%, phased development (MVP first) |
| Delay timeline | Weekly sprint review, early warning system |
| Hosting down | Backup server, monitoring uptime |
| Data loss | Auto backup harian, off-site backup |

---

*Update dokumen ini setelah finalisasi tim & budget approval*
