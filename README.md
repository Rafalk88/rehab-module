# Rehabilitacja – Rehabilitation Module Web App

![doc version](https://img.shields.io/badge/docs-0.6.0--alpha-blue)
![status](https://img.shields.io/badge/status-active%20development-green)

## 📋 Overview

A web application designed for rehabilitation clinics and medical offices. Built to support staff in managing patients, rehabilitation workflows, and clinical documentation — with a focus on **minimum clicks, maximum value**.

The system is inspired by real clinical workflows observed in a rehabilitation department, with domain knowledge embedded into architecture decisions.

> ⚠️ This project is in active development. Features marked as **[planned]** are not yet implemented.

---

## 🧰 Tech Stack

### Implemented
- **Frontend:** Next.js, React, Ant Design, TypeScript
- **Backend:** NestJS (modular architecture), TypeScript
- **Database:** PostgreSQL + Prisma ORM
- **Auth:** JWT (access + refresh tokens), RBAC with permission overrides
- **Security:** AES-256-GCM encryption, HMAC search index, key versioning
- **Validation:** Zod schemas
- **Logging:** Winston
- **Testing:** Jest (unit + integration), ~71% coverage
- **Dev tools:** Docker, Husky, ESLint, Prettier

### Planned
- Notifications: Web Push, Email, SMS
- AI: Speech-to-text dictation for visit notes
- CI/CD: GitHub Actions + deployment pipeline
- Error monitoring: Sentry

---

## 🧩 App Modules

### ✅ Implemented
- **Authentication** — login, logout, refresh token, password management
- **Authorization** — RBAC with per-user permission overrides
- **Cabinet** — visit list with status filtering, date range, EWUŚ and billing indicators, status change
- **Patients** — encrypted PESEL storage, paginated list, create patient
- **Audit** — automatic operation logging for all CRUD operations
- **Visits** — create, status management, date tracking (planned/register/completion)

### 🔄 In Progress
-

### 📋 Planned
- **Outpatient Clinic** — medical appointments, AI dictation
- **Notifications** — in-app, email, SMS
- **Document Management** — generation, scanning, approval workflow
- **Statistics & Billing**

---

## 👥 User Roles

- Administrator
- Receptionist
- Rehabilitant (Therapist)
- Physician

---

## 🔐 Security Highlights

- JWT authentication with access (15m) + refresh (7d) tokens
- Refresh token rotation and blacklist on logout
- AES-256-GCM encryption for sensitive fields (PESEL, login, email)
- HMAC-based search index for encrypted fields
- Key versioning for future key rotation
- RBAC with explicit per-user permission overrides
- Automatic audit logging with sensitive field redaction (`[REDACTED]`)
- Rate limiting, Helmet, CORS
- GDPR-aware data retention policies

---

## 🧪 Testing

- Unit tests for business logic, validation, guards
- Integration tests for API endpoints
- Pre-commit hooks via Husky
- Current coverage: ~71%

---

## 📁 Subprojects

- [Frontend – rehab-frontend](https://github.com/rafalk88/rehab-frontend)
- [Backend – rehab-backend](https://github.com/rafalk88/rehab-backend)

---

## 📘 Documentation

- [Architecture](./docs/0.5.0-alpha/architecture.md) – C4 Architecture overview
- [Permissions](./docs/0.1.2-alpha/permissions.md) – Roles and permissions system
- [Database](https://github.com/Rafalk88/rehab-backend/blob/main/DATABASE.md) – Schema and model decisions
- [Technical Decisions](https://github.com/Rafalk88/rehab-backend/blob/main/DECISSIONS.md) – Architecture decision records
- [Changelog](./docs/) – Version history

---

> **Version:** `0.6.0-alpha`  
> 📅 Last updated: *2026-06-18*
