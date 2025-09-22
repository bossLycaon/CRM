# Lycaon CRM – Product Requirements Document

## 1. Product Overview

### 1.1 Core Problem
Broker CFD memerlukan CRM yang integrasi rapat dengan platform dagangan, tetapi mereka menghadapi cabaran berikut:

- Proses onboarding pelanggan (KYC/AML) yang perlahan dan berpecah.
- Data pelanggan dan akaun dagangan terpisah antara platform dan sistem back-office.
- Pengalaman pengguna mudah alih yang tidak lancar.
- Pelaporan pematuhan seperti AML, P&L dan pendedahan risiko mengambil masa yang lama.

### 1.2 Solution Overview
Lycaon CRM ialah hab serba lengkap yang menyediakan:

- Onboarding digital lengkap dengan OCR, eKYC dan saringan AML.
- Penyegerakan perdagangan masa nyata melalui API cTrader.
- Pengurusan rakan kongsi dan IB termasuk komisen dan sub-IB.
- Papan pemuka risiko dan pematuhan dengan pelaporan sedia regulatori.
- Portal pelanggan untuk deposit, pengeluaran, penyata dan sokongan langsung.

## 2. Business Context

### 2.1 Business Goals
- Meningkatkan kadar pertukaran daripada lead kepada akaun yang dibiayai.
- Mengurangkan kos operasi sokongan melalui portal layan diri.
- Mengukuhkan automasi AML/pematuhan dengan jejak audit penuh.
- Menambah lapisan penglibatan melalui notifikasi, push dan integrasi WhatsApp API.

**Keutamaan Strategik:** Tinggi — CRM menjadi enjin teras untuk pertumbuhan dan keperluan pelesenan.

### 2.2 Market Opportunity
- Pasaran global broker CFD dijangka berkembang ~7% CAGR (2025–2030).
- Trend pedagang runcit memihak kepada pengalaman mudah alih terlebih dahulu.
- Regulator memberi penekanan pada AML dan ketelusan data.

### 2.3 Competitive Landscape
- Pesaing: Tools4Brokers, Skale, Leverate.
- Keunikan Lycaon: pengalaman mudah alih ringan, pengoptimuman terus untuk cTrader dan penyesuaian untuk pasaran Asia Tenggara.

### 2.4 Constraints
- Belanja capex permulaan < RM500k.
- Tempoh ke pasaran: 6 bulan.
- Pematuhan wajib: Labuan FSA, MAS, FCA.

## 3. Key Features & Requirements

### 3.1 Client Lifecycle Management
- Onboarding digital dengan eKYC (OCR MyKad/pasport, liveness check).
- Sokongan multi-akaun: satu pelanggan boleh memiliki banyak akaun dagangan.
- Sistem dompet dalaman untuk deposit dan pengeluaran.
- Pemeriksaan KYC/AML termasuk saringan senarai sekatan, PEP dan media negatif.

### 3.2 Trading Integration (cTrader Open API / FIX API)
- Penyegerakan masa nyata untuk baki, margin, ekuiti dan posisi terbuka.
- Pelaporan P&L di peringkat pelanggan dan kumpulan.
- Penciptaan akaun automatik daripada CRM ke cTrader.
- Papan pemuka pendedahan risiko berdasarkan simbol, pelanggan dan kumpulan.

### 3.3 Partner / IB Management
- Penjejakan IB pelbagai peringkat.
- Enjin rebat yang fleksibel (per lot, % spread, model komisen).
- Pelaporan masa nyata untuk IB dan sub-IB.
- Portal rakan kongsi untuk menjejak pelanggan, komisen dan pengeluaran.

### 3.4 Client Portal (Mobile-first Web App)
- Pembiayaan: deposit, pengeluaran (payment gateway, kripto, FPX).
- Sejarah transaksi penuh.
- Muat turun penyata (harian, bulanan).
- Ticketing dan live chat.
- Notifikasi tolak (MTM call, status kelulusan, promosi).

### 3.5 Compliance & Risk
- Log audit lengkap yang bersedia untuk regulator.
- Pemantauan transaksi dengan pencetus bendera merah.
- Menjana laporan Suspicious Activity Report dan laporan AML bulanan.
- Survelan dagangan untuk mengesan wash trading dan leverage berisiko tinggi.

### 3.6 Internal Ops Tools
- Papan pemuka untuk jualan, sokongan dan pematuhan.
- Pengurusan lead dengan auto assignment.
- Kawalan akses berasaskan peranan (admin, pematuhan, jualan, pengurus IB).
- Hook API untuk alat BI/pelaporan.

## 4. Technical Requirements

### 4.1 Architecture
- Berasaskan awan dan multi-tenant.
- Frontend: PWA responsif dioptimumkan untuk mudah alih.
- Backend: mikrosistem menggunakan Node.js atau .NET Core.
- Pangkalan data: PostgreSQL untuk data pelanggan dan Redis untuk cache masa nyata.

### 4.2 Integrations
- cTrader Open API.
- Payment gateways (Stripe, PayPal, FPX, crypto).
- WhatsApp API (Twilio).
- Pembekal saringan AML (Refinitiv atau Dow Jones).

### 4.3 Security & Compliance
- Penyulitan at rest dan in transit (AES-256, TLS 1.3).
- Log masuk dengan 2FA.
- Kawalan akses berasaskan peranan.
- Pematuhan data: GDPR, PDPA Malaysia, FCA.

## 5. Success Metrics
- Masa onboarding < 10 minit (KYC ke akaun siap).
- Kadar pertukaran: +20% daripada lead ke akaun dibiayai.
- Penggunaan IB: 70% IB aktif menggunakan portal setiap bulan.
- Kecekapan pematuhan: laporan AML dihasilkan 50% lebih pantas.
- Waktu operasi sistem: 99.9% SLA awan.
- Penggunaan mudah alih: >75% sesi pada mudah alih tanpa penurunan prestasi.

## 6. Roadmap

### Phase 1 (0–3 bulan)
- CRM teras: onboarding pelanggan, KYC, penyegerakan akaun dagangan.
- Portal pelanggan asas: pembiayaan, profil, penyata.

### Phase 2 (3–6 bulan)
- Modul pengurusan IB/rakan kongsi.
- Papan pemuka pematuhan dan risiko.
- Integrasi payment gateway dan kripto.

### Phase 3 (6–9 bulan)
- Pelaporan lanjutan dan integrasi BI.
- Automasi pemasaran (emel, push WhatsApp).
- Skor risiko dan segmentasi pelanggan didorong AI.

## 7. Risks & Mitigation
- **Kebergantungan API cTrader:** gunakan middleware dengan failover sync.
- **Perubahan regulatori:** bina modul pematuhan yang fleksibel.
- **Kebocoran data:** laksanakan penyulitan awan dan matlamat SOC 2.
- **Adopsi pengguna rendah di mudah alih:** optimakan PWA dan UI ringan.
