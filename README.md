# Rehabilitacja – Rehabilitation Module Web App

## 📋 Overview

This is a web application designed for rehabilitation clinics and medical offices. It allows staff to manage patient schedules, handle rehabilitation treatments, and assist doctors with visit notes using AI-powered speech-to-text and smart redaction.

## 🧰 Tech Stack

- **Frontend:** Next.js
- **Backend/API:** Next.js API Routes / Express
- **Database:** PostgreSQL + Prisma ORM
- **Notifications:** Web Push API, Email (Nodemailer), SMS (Twilio)
- **AI:** Dictation and text processing (Web Speech API)
- **CI/CD:** Docker + GitHub Actions + Vercel
- **Error Monitoring:** Sentry
- **Error Handling:** React Error Boundaries

## 🧩 App Modules

### Cabinet
- Patient schedule management
- Rehabilitation treatment workflow
- Daily planned patients

### Outpatient Clinic
- Medical appointments
- Dictation of visit content (AI)
- Logical redaction of notes

### Notifications
- In-app (Web Push)
- Email notifications
- SMS reminders for patients

### Error Handling
- React Error Boundaries for UI
- Centralized error logging/monitoring

## 🧪 Testing

- Unit Testing – Vitest
- Integration Testing – API endpoints
- E2E Testing – Cypress

## 🚀 CI/CD

- GitHub Actions for testing and linting
- Dockerized development and production environments
- Automatic deployment via Vercel

## 🔐 Security

- JWT authentication + role-based access control
- `.env` environment variables with Vercel Secrets
- CSRF/XSS protection
- GDPR-compliant data storage

## 📘 Documentation

Located in the `/docs` folder or project Wiki.

- Architecture (C4 Model)
- API Documentation (Swagger / Postman / Redoc)
- Database schema (ERD)
- CI/CD setup and deployment guide
- Error handling strategy and monitoring
- Recovery & backup procedures
