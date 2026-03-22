# stellar-school-fee
Borderless school fee payment platform for parents and institutions powered by Stellar
> A transparent, fast, and borderless school fee payment platform built on Stellar — enabling parents, schools, and students to transact with zero friction.

![Stellar](https://img.shields.io/badge/Stellar-Network-blue?logo=stellar)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-in--development-yellow)

---

## 📌 Overview

Education payments are often delayed by bank processing times, high remittance fees (especially for diaspora parents), and poor record-keeping. This platform solves all three by using Stellar's near-instant, low-cost payment infrastructure.

### Key Features
- **Instant Cross-Border Payments** — Parents abroad pay in seconds using Stellar
- **Auto-Generated Receipts** — On-chain proof of payment, forever
- **Per-Student Fee Breakdown** — Tuition, books, exam fees — itemized
- **School Admin Dashboard** — Real-time payment tracking per student
- **Payment Reminders** — Automated notifications before due dates
- **Multi-Currency Accept** — Accept USDC, XLM, or local-pegged stablecoins

---

## 🏗️ Architecture

```
┌──────────────┐    ┌──────────────┐    ┌──────────────────┐
│  Parent App  │───▶│   API Server  │───▶│  Stellar Horizon  │
└──────────────┘    └──────────────┘    └──────────────────┘
                           │
              ┌────────────┴────────────┐
              │                         │
       ┌──────┴──────┐         ┌────────┴──────┐
       │  School DB   │         │  Admin Portal  │
       └─────────────┘         └───────────────┘
```

---

## 📁 Folder Structure

```
stellar-school-fee/
├── backend/
│   ├── src/
│   │   ├── routes/
│   │   │   ├── payments.js        # Fee payment endpoints
│   │   │   ├── students.js        # Student management
│   │   │   ├── schools.js         # School onboarding
│   │   │   └── receipts.js        # Receipt generation
│   │   ├── services/
│   │   │   ├── stellarService.js  # Payment processing on Stellar
│   │   │   ├── receiptService.js  # PDF receipt generator
│   │   │   ├── smsService.js      # SMS notifications
│   │   │   └── emailService.js
│   │   ├── models/
│   │   │   ├── Student.js
│   │   │   ├── School.js
│   │   │   ├── FeeStructure.js
│   │   │   ├── Payment.js
│   │   │   └── Receipt.js
│   │   └── middleware/
│   │       ├── schoolAuth.js
│   │       └── parentAuth.js
│   └── config/
│       ├── database.js
│       └── stellar.js
│
├── frontend/                      # Parent-facing payment portal
│   └── src/
│       ├── components/
│       │   ├── FeeBreakdown/
│       │   ├── PaymentForm/
│       │   ├── ReceiptViewer/
│       │   └── StudentCard/
│       ├── pages/
│       │   ├── Login.jsx
│       │   ├── Dashboard.jsx
│       │   ├── PayFees.jsx
│       │   └── History.jsx
│       ├── hooks/
│       │   └── usePayment.js
│       └── utils/
│           └── stellar.js
│
├── admin/                         # School admin interface
│   └── src/
│       ├── components/
│       │   ├── StudentList/
│       │   ├── PaymentTracker/
│       │   └── FeeConfigurator/
│       └── pages/
│           ├── Dashboard.jsx
│           ├── Students.jsx
│           └── Reports.jsx
│
├── docs/
│   ├── ONBOARDING_SCHOOLS.md
│   ├── PARENT_GUIDE.md
│   └── API.md
│
├── scripts/
│   └── seed-school-data.js
│
├── tests/
├── .env.example
└── package.json
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js >= 18
- MongoDB or PostgreSQL
- Stellar Testnet Account

### Installation

```bash
git clone https://github.com/your-org/stellar-school-fee.git
cd stellar-school-fee && npm install
cp .env.example .env
npm run dev
```

### Environment Variables

```env
STELLAR_NETWORK=testnet
STELLAR_SCHOOL_ACCOUNT=school_public_key
DATABASE_URL=mongodb://localhost:27017/schoolfees
TWILIO_SID=your_twilio_sid
SMTP_HOST=smtp.mailtrap.io
```

---

## 🌍 Why Stellar?

Traditional bank transfers for school fees can take 3–5 business days and charge 3–8% in fees. Stellar settles in **3–5 seconds** with fees under **$0.001**.

---

## 📄 License

MIT © 2025 — Built on the Stellar Network
