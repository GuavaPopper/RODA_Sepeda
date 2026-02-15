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
- **Biaya**: Rp 150.000 - 300.000/tahun
- **Provider**: Niagahoster, Rumahweb, atau Cloudflare

#### Hosting
**Option 1 - Shared Hosting** (Budget rendah)
- Provider: Niagahoster, Hostinger
- Biaya: ~Rp 20.000 - 50.000/bulan
- Cocok untuk: Traffic rendah-medium

**Option 2 - VPS** (Rekomendasi)
- Provider: DigitalOcean, Vultr, AWS Lightsail
- Biaya: ~$5-10/bulan (Rp 75.000 - 150.000)
- Cocok untuk: Full control, scalable

**Option 3 - Cloud Platform**
- Vercel/Netlify (frontend) + Railway/Render (backend)
- Biaya: Free tier atau $5-20/bulan
- Cocok untuk: Modern deployment, auto-scaling

#### SSL Certificate
- Let's Encrypt (GRATIS)
- Auto-renew dengan Certbot

#### CDN (Optional tapi recommended)
- Cloudflare (Free tier cukup bagus)
- Speed up loading, DDoS protection

### 3. Third-Party Services

#### Payment Gateway
- **Midtrans** (lokal, populer)
  - QRIS, transfer bank, e-wallet, kartu kredit
  - Fee: ~0.5-3% per transaksi
- **Xendit** (alternatif)
- **PayPal** (untuk international, jika perlu)

#### Notifikasi
- **Email**: SendGrid, Mailgun (free tier available)
- **WhatsApp**: WA Business API atau Fonnte
- **SMS**: Twilio, Zenziva

#### Storage (untuk foto sepeda)
- **Option 1**: Local server storage
- **Option 2**: Cloud storage (AWS S3, Cloudinary)
  - Rekomendasi: Cloudinary (image optimization otomatis)

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
- Domain: Rp 15.000 - 25.000/bulan (jika dibagi per bulan)
- Hosting VPS: Rp 75.000 - 150.000
- SSL: Gratis (Let's Encrypt)
- Email service: Gratis (free tier) - Rp 50.000
- **Total/bulan**: Rp 90.000 - 225.000

#### Per Transaksi
- Payment gateway fee: 0.5-3% dari total transaksi
  - Contoh: Rental Rp 50.000 → fee Rp 250 - 1.500

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
