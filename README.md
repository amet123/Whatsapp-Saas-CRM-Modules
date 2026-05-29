# 💬 WhatsCRM — AI-Powered WhatsApp CRM Platform

Full-featured WhatsApp CRM SaaS with multi-tenant architecture, AI chatbot builder, real-time inbox, bulk broadcasting, social media automation, sales & billing, voice calling, and a fully dynamic landing page with backend-controlled SEO.

---

## 🚀 Quick Start

### Backend
```bash
cd backend
cp .env.example .env     # Configure MongoDB, JWT, WhatsApp, OpenAI, Twilio
npm install
npm run dev              # Starts on :5000
```

### Frontend
```bash
cd frontend
npm install
npm run dev              # Vite dev server on :3000
npm run build            # Production build → frontend/build/
```

### Deploy (Production)
```bash
cd frontend && npm run build   # Rebuild after every code change
pm2 restart wcrm-backend       # Backend serves frontend/build/ via Express static
```

---

## 🏗️ Tech Stack

| Layer | Tech |
|---|---|
| Frontend | React 18, Vite, Zustand, React Router, Recharts |
| Backend | Node.js, Express, MongoDB (Mongoose), Socket.IO |
| WhatsApp | Meta WhatsApp Cloud API + whatsapp-web.js (QR) |
| AI | OpenAI GPT-4o (chatbot, flow generator, content) |
| Voice | Twilio + OpenAI Realtime (AI calling) |
| Payments | Razorpay / Stripe |
| Email | SMTP (Nodemailer) |
| Infra | PM2, Nginx, Let's Encrypt SSL |

---

## ✨ Full Feature List

### 📢 WhatsApp Broadcasting
- Bulk campaign sending with template messages
- Personalized variable substitution per contact
- Scheduled campaigns (date/time picker)
- Campaign dashboard — delivery, read, reply rates
- Drip sequences (multi-step timed campaigns)
- Phonebook management with CSV import/export

### 🤖 AI Chatbot & Flow Builder
- Visual drag-and-drop flow builder
- AI flow generator — describe in plain text, GPT-4o builds it
- Conditional branching, delays, loops
- Button/list/media message nodes
- Flow templates marketplace
- WA Chatbot linking flows to WhatsApp numbers

### 💬 Team Inbox & CRM
- Real-time shared inbox (Socket.IO)
- Agent assignment & routing
- Labels, tags, conversation status
- Quick reply templates
- Contact profiles, notes, custom fields
- Internal team chat / notes

### 👥 Contact Management
- Contact list with search, filter, segment
- CSV bulk import
- Segments & dynamic lists
- Contact activity timeline

### 📱 Social Media Automation
- Instagram comment-to-DM automation
- Facebook comment bot
- Telegram bot sessions
- LinkedIn, Twitter (X), YouTube, Reddit automation
- Unified social media manager dashboard

### 🛒 Commerce & Payments
- WhatsApp product catalog
- In-chat payment links (Razorpay / Stripe)
- Coupon & discount code management
- Order management
- Shopify & WooCommerce integration (webhooks)

### 📊 Analytics & Reporting
- Dashboard — messages, open rate, new leads, revenue
- Campaign performance charts
- Agent productivity metrics
- API usage monitoring

### 🧾 Sales & Billing (GST-Ready)
- Quotation builder with PDF + WhatsApp send
- Invoice builder with GST (IGST/CGST auto-detection by state)
- Customer management
- Subscription & recurring billing engine
- Sales dashboard with MRR, ARR charts
- Lead management & CRM pipeline

### 📅 Appointments & Booking
- Booking configuration per tenant
- Appointment scheduling via WhatsApp
- Calendar view

### 🔊 AI Voice Calling (Twilio + OpenAI)
- Create AI call flows with system instructions
- Outgoing campaign voice calls
- Incoming bot with voice response
- Call logs with transcription & recording
- Polly / OpenAI TTS voice selection

### 🤖 AI Tools
- AI Content Creator (captions, emails, ad copy)
- AI Image Studio (DALL·E generation)
- AI Video Studio
- AI Chatbot template marketplace

### 📡 REST API & Webhooks
- External API (API key auth) — send messages, manage contacts, trigger flows
- Webhook automation — event-driven workflows
- Webhook delivery logs
- Meta WhatsApp Cloud API integration
- Conversational API & Template API docs

### 🔗 Integrations
- OpenAI (GPT-4o, DALL·E, Whisper)
- Twilio (voice calls, SMS)
- Shopify (orders, products, webhooks)
- WooCommerce
- Razorpay & Stripe
- Dialogflow
- WebEngage / LeadSquared / Integrately
- Instagram, Facebook, Telegram, LinkedIn, Twitter, YouTube, Reddit

### 🌐 Landing Page
- Fully dynamic — plans fetched live from database
- SEO meta tags, Open Graph, Twitter Card, Schema.org — all backend-controlled
- Admin panel SEO editor (5 tabs: Basic, OG, Twitter Card, Technical, Schema.org)

### ⚙️ Admin Panel (Superadmin)
- Dashboard with live user activity feed
- Manage tenants / users
- Plan management (CRUD) — reflected live on landing page
- Landing SEO settings
- Site settings, SMTP, Theme, Social Login
- Payment gateway configuration (Razorpay / Stripe)
- FAQ, Testimonials, Partners, Legal Pages
- Flow templates, Chatbot templates marketplace
- Blue tick verification requests
- WhatsApp connection manager
- Web translation
- One-click update

### 🔒 Auth & Multi-Tenant
- JWT authentication
- Role-based access (superadmin, owner, agent)
- Per-tenant isolation (all data scoped by tenant)
- Social login (Google, GitHub)
- API key management

### 💬 Chat Widget
- Embeddable WhatsApp chat widget (widget.js)
- Per-tenant configuration (color, position, welcome message)
- Public embed token system

---

## 📁 Project Structure

```
whatscrm/
├── backend/
│   ├── models/          # Mongoose models (30+)
│   ├── routes/          # Express routes (40+)
│   ├── services/        # Business logic services
│   ├── middleware/       # Auth, validation
│   ├── utils/           # GST, helpers
│   ├── seeds/           # Default data seeders
│   └── public/          # widget.js (served at /)
├── frontend/
│   ├── src/
│   │   ├── pages/       # React pages (50+)
│   │   ├── components/  # Shared components
│   │   ├── services/    # API client, Socket.IO
│   │   ├── store/       # Zustand global state
│   │   └── utils/       # GST calculator, helpers
│   └── build/           # Production build (gitignored)
└── README.md
```

---

## 🎨 Design System

| Token | Value |
|---|---|
| Background | `#1a1d23` |
| Surface | `#22262e` |
| Card | `#282c34` |
| Border | `#2f343d` |
| Primary (WA Green) | `#25d366` |
| Font | DM Sans + JetBrains Mono |

---

## 📋 Changelog

### v6.0.0 — 2026-05-29
- **Landing page live plans**: Pricing section fetches plans from MongoDB via `GET /api/public/plans` — admin changes reflect instantly on the landing page
- **Backend SEO control**: New `LandingSeo` model + `GET /api/public/seo` endpoint; landing page dynamically injects title, meta description, keywords, Open Graph, Twitter Card, canonical URL, favicon, and Schema.org JSON-LD from the database
- **Admin SEO editor**: "Landing SEO" page in admin panel with 5 tabs — Basic SEO (Google preview), Open Graph (image preview), Twitter Card, Technical (canonical, robots, favicon), Schema.org (live JSON-LD preview)
- **Fix — stale build override**: Removed old `backend/public/index.html` and `assets/` that were blocking all frontend updates; frontend now correctly served from `frontend/build/`

### v5.0.0 — 2026-05-28
- AI Voice Calling system (Twilio + OpenAI Realtime)
- Sales & GST system — Quotations, Invoices, Subscriptions, Customers
- GST IGST/CGST auto-detection by state
- Sales dashboard with MRR/ARR charts
- Lead management & CRM pipeline
- Social media automation (Instagram, Facebook, LinkedIn, Twitter, YouTube, Reddit)
- AI Content Creator, AI Image Studio, AI Video Studio
- Click-to-WhatsApp Ads Manager
- WhatsApp In-Chat Payment Links
- Shopify & WooCommerce integration
- Chatbot templates marketplace
- Flow templates gallery
- Coupon & discount system
- Appointment & booking system
- WhatsApp forms (public embeddable)
- Legal pages manager (Privacy, Terms, Cookies)
- Admin panel — complete rebuild with live activity feed, plan manager, SEO editor, translation, update system

### v4.0.0 — Prior
- Multi-tenant architecture
- Real-time team inbox (Socket.IO)
- WhatsApp QR session manager + number warmer
- Drag-and-drop flow builder with AI generator
- Campaign broadcasting with drip sequences
- Contact management & segments
- Webhook automation & delivery logs
- External REST API (API key auth)
- Meta WhatsApp Cloud API integration
- Embeddable chat widget (widget.js)
- JWT auth + role-based access control

---

## 📄 License
MIT
