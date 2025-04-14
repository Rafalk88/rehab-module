# Rehabilitacja – Rehabilitation Module Web App

## 📋 Overview

This is a web application designed for rehabilitation clinics and medical offices. It allows staff to manage patient schedules, handle rehabilitation treatments, assist doctors with visit notes using AI-powered speech-to-text and smart redaction, and includes features for document handling and approval processes.

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
- Notifications for upcoming appointments and tasks

### Outpatient Clinic
- Medical appointments
- Dictation of visit content (AI-powered speech-to-text)
- Logical redaction of notes
- Notifications for pending actions (e.g., medical notes to be reviewed or submitted)

### Notifications
- In-app notifications (Web Push)
- Email notifications (via Nodemailer)
- SMS reminders for patients
- Automatic email system for document flow and approval

### Document Management & Approval
- Dynamic document generation (with AI assistance)
- **Document scanning and OCR**: Users can scan physical documents and upload them to the system. OCR technology will convert the scanned text into an editable format.
- **AI-powered document processing**: AI will help process and understand the scanned text, extracting key information and transforming it into structured documents (e.g., forms, medical reports).
- Automated document workflow for approval (e.g., supervisor/manager review before sending)
- Role-based access control for document approval
- Audit trail for document handling

### Error Handling
- React Error Boundaries for UI
- Centralized error logging/monitoring via Sentry

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

- [Architecture](./docs/architecture.md) (C4 Model)
- API Documentation (Swagger / Postman / Redoc)
- Database schema (ERD)
- CI/CD setup and deployment guide
- [Permissions System](./docs/permissions.md) - Role-based access control and dynamic permissions
