# 💬 WhatsCRM — WhatsApp CRM SaaS System

Full-featured WhatsApp CRM SaaS platform with chatbot flow builder, real-time messaging,
broadcasting, AI calling, REST API, webhooks, and multi-tenant architecture.

## 🚀 Quick Start

### Backend
```bash
cd backend
cp .env.example .env     # Configure MongoDB, JWT, WhatsApp
npm install
npm run dev              # Starts on :5000
```

### Frontend
```bash
cd frontend
npm install
npm run dev              # Starts on :3000 (Vite)
npm run build            # Production build
```

## 🏗️ Tech Stack

- **Frontend**: React 18, Vite, Recharts, Zustand, React Router
- **Backend**: Node.js, Express, MongoDB, Socket.IO, BullMQ
- **WhatsApp**: Meta WhatsApp Cloud API
- **Theme**: Custom dark theme (matching WhatsCRM design)

## 📄 All Pages (30+ Routes)

### Main
- ✅ Dashboard — Stats, charts, user growth, agent performance
- ✅ Inbox — Real-time WhatsApp chat interface

### WhatsApp QR Plugin
- ✅ Add WhatsApp by QR — QR code session linking
- ✅ WhatsApp Warmer — Number warming system

### REST API
- ✅ Rest API — Full API documentation with parameters, examples, responses

### WA Meta Connect
- ✅ Link Meta WhatsApp — Embed Login / Manual Setup with webhook URL

###  AI WHATSAPP CALLING
- ✅ AI Voice Calling
- ✅ Create Call Flow
- ✅ WA Call Logs
- ✅ Setup WA Calls

### Automation & Bots
- ✅ Automation Flows — Visual flow builder with nodes
- ✅ WA Chatbot — Bot configuration with flow linking

### Broadcasting
- ✅ Create Meta Template — 6-step wizard with phone preview
- ✅ Send Campaign — Template selection and bulk send
- ✅ Campaign Dashboard — Performance tracking
- ✅ Phonebook — Contact management with variables

### AI WhatsApp Calling
- ✅ Create Call Flow — AI call builder with OpenAI, voice config, recording
- ✅ WA Call Logs — Call history with transcriptions
- ✅ Setup WA Calls — Incoming bot & outgoing campaign config

### Meta REST API
- ✅ Conversational API — Full API docs with message types
- ✅ Template API — Template message API
- ✅ API Dashboard — Usage monitoring

### Webhook Automation
- ✅ Manage Webhooks — Endpoint configuration
- ✅ Webhook Automation — Event-driven workflows
- ✅ Webhook Logs — Activity logging

### More
- ✅ Telegram Sessions
- ✅ Web Notification
- ✅ Agent Login
- ✅ Agent Task
- ✅ Chat Widget


### CATALOG & ORDERS
- ✅ Product Catalog
- ✅ Appointments
- ✅ Coupons & Offers

## 🎨 Design System

Dark theme with:
- Background: `#1a1d23` / Surface: `#22262e` / Card: `#282c34`
- Primary: `#25d366` (WhatsApp Green)
- Font: DM Sans + JetBrains Mono
- Consistent card/border styling across all pages

## 📡 Backend API Endpoints

Auth, Contacts, Conversations, Flows, Webhooks, External API (API key auth)
— See `backend/routes/` for full details.

## 📋 License
MIT

###  For More Detail Email: ametvaid@gmail.com
