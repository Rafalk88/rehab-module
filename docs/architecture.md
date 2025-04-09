# 🏗️ Architecture – Rehabilitacja Web App

## 1. System Context (C4 – Level 1)

The Rehabilitacja Web App is a browser-based system for managing rehabilitation and outpatient clinics. It interacts with users (doctors, therapists, receptionists), and external services (email, SMS). All data is stored in a PostgreSQL database.

### External Actors:
- **Patient** – receives appointment notifications
- **Clinic Staff** – manage schedules, visits, and records
- **Email/SMS Services** – sends appointment messages

---

## 2. Container Diagram (C4 – Level 2)

[Browser (Next.js Frontend)] | v [API (Next.js API Routes / Express)] ---> [PostgreSQL Database (Prisma)] | v [AI Speech Module (Browser-based Worker / Web Speech API)] | v [Web Push, Email (Nodemailer), SMS (Twilio)]


### Description:
- **Frontend:** Built in Next.js, supports role-based views and dynamic forms.
- **Backend/API:** Next.js API Routes or Express endpoints handle logic, auth, notifications.
- **Database:** PostgreSQL using Prisma ORM to manage data models and migrations.
- **AI Module:** Local browser-based AI using Web Workers + Speech API for dictation.
- **Notifications:** In-app (Web Push), email via Nodemailer, SMS via Twilio.

---

## 3. Component Diagram (C4 – Level 3)

### Frontend
- `AuthProvider` – session and JWT role management
- `Dashboard` – per-role interfaces
- `Scheduler` – calendar view with appointment logic
- `SpeechToText` – AI dictation module using Web APIs

### Backend
- `auth.ts` – login, register, JWT
- `appointments.ts` – scheduling logic
- `notifications.ts` – email/SMS triggers
- `ai.ts` – handles dictation parsing, formatting
- `db.ts` – Prisma client and queries

---

## 4. Deployment

- Hosted on **Vercel** (frontend + backend API)
- PostgreSQL hosted via **Railway / Supabase / Render**
- CI/CD via **GitHub Actions**
- Containerized with **Docker**

---

## 5. Error Monitoring

- **Frontend:** React Error Boundaries catch UI crashes
- **Monitoring:** Sentry for full-stack tracing
- **Logging:** Server logs for backend events and errors

---

## 6. Security Practices

- JWT + RBAC (Role-Based Access Control)
- Environment secrets managed via `.env` and Vercel Secrets
- CSRF protection (Next.js default + HTTP-only cookies)
- Input validation (Zod or custom validators)
- GDPR-ready data handling

---

## 7. Future Notes

- Optional external AI service for advanced analysis (reports, summaries)
- Microservices split if project scales beyond monorepo
