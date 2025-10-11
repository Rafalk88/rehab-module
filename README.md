# Rehabilitacja – Rehabilitation Module Web App
![doc version](https://img.shields.io/badge/docs-0.2.0--alpha-blue)

## 📋 Overview

This is a web application designed for rehabilitation clinics and medical offices. It allows staff to manage patient schedules, handle rehabilitation treatments, assist doctors with visit notes using AI-powered speech-to-text and smart redaction, and includes features for document handling and approval processes.

## 🧰 Tech Stack

- **Frontend:** Next.js
- **Backend/API:** Node.js (NestJS-based modular API)
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

## 👥 User Roles

- Administrator
- Receptionist
- Rehabilitant (Therapist)
- Physician

## 🧪 Testing

The system includes a comprehensive testing strategy across both frontend and backend:

- **Unit tests** – cover core logic, validation, and UI components
- **Integration tests** – verify API endpoints, data flow, and module interactions
- **End-to-End (E2E) tests** – simulate real user flows and critical system scenarios

Each subproject (frontend, backend) defines its own testing framework and configuration.

## 🚀 CI/CD

- GitHub Actions for testing and linting
- Dockerized development and production environments
- Automatic deployment via Vercel

## 🔐 Security

- JWT authentication + RBAC
- `.env` environment variables with Vercel Secrets
- CSRF/XSS protection
- GDPR-compliant data storage

## 📁 Subprojects
- [Frontend – rehab-frontend](https://github.com/rafalk88/rehab-frontend)
- [Backend – rehab-backend](https://github.com/rafalk88/rehab-backend)

## 📘 Internal Documentation

Full technical documentation is stored in the /docs directory and versioned by release:

- [/docs/architecture.md](./docs/0.1.2-alpha/architecture.md) – C4 Architecture
- [/docs/permissions.md](./docs/0.1.2-alpha/permissions.md) – Roles and permissions system
- [/docs/database.md](https://github.com/Rafalk88/rehab-backend/blob/main/DATABASE.md) – ERD and schema decisions
- [/docs/changelog.md](./docs/) – Version history of documentation

## 📝 Changelog

You can follow the documentation and system changes in the [Changelog](./docs/).

---

> **Version:** `0.3.0-alpha`  
> 📅 Last updated: *2025-10-11*
