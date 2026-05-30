# 🏗️ Architecture – Rehabilitacja Web App

## 1. System Context (C4 – Level 1)

The Rehabilitacja Web App is a browser-based system for managing rehabilitation and outpatient clinics. It interacts with clinic staff (doctors, therapists, receptionists) and stores all data in a PostgreSQL database.

### External Actors:
- **Clinic Staff** — manage patients, schedules, visits, and records
- **Patient** — receives appointment notifications _(planned)_
- **Email/SMS Services** — sends notifications _(planned)_

---

## 2. Container Diagram (C4 – Level 2)

[Browser (Next.js Frontend)]
|
v
[API (NestJS Backend)] ---> [PostgreSQL Database (Prisma)]

### Description:
- **Frontend:** Next.js with React, Ant Design, TypeScript. Role-based views, JWT auth via cookies.
- **Backend:** NestJS modular API. Handles auth, RBAC, patient data, audit logging.
- **Database:** PostgreSQL with Prisma ORM. Migrations versioned and tracked.

### Planned:
- AI Speech Module for visit dictation
- Notification service (Web Push, Email, SMS)

---

## 3. Component Diagram (C4 – Level 3)

### Frontend
- `AuthProvider` — JWT session management, token refresh via axios interceptor
- `AppLayout` — role-based sidebar navigation
- `Login` — authentication form

### Backend (NestJS Modules)
- `AuthModule` — login, logout, refresh token, password management
- `PatientsModule` — patient CRUD with encrypted PESEL
- `PermissionsModule` — RBAC with permission caching
- `PermissionsAdminModule` — role and permission assignment
- `PrismaModule` — database access, audit extension, session middleware
- `LoggerModule` — Winston structured logging

### Cross-cutting
- `RequestContextService` — AsyncLocalStorage per request (userId, ipAddress)
- `AuthorizationGuard` — permission enforcement on routes
- `JwtAuthGuard` — JWT token verification
- `HttpExceptionFilter` — centralized error responses
- `ZodValidationPipe` — input validation

---

## 4. Security Architecture

- JWT access tokens (15 min) + refresh tokens (7 days) with DB persistence
- Refresh token rotation and blacklist on logout
- AES-256-GCM encryption for sensitive fields (PESEL, login, email)
- HMAC-SHA256 search index for encrypted fields
- Key versioning for future key rotation without data loss
- RBAC with explicit per-user permission overrides
- Automatic audit logging via Prisma extension
- Sensitive field redaction in audit logs (`[REDACTED]`)
- Rate limiting, Helmet, CORS

---

## 5. Deployment

- **Local:** Docker Compose (PostgreSQL) + NestJS dev server
- **Production:** _(planned)_ Docker + CI/CD pipeline

---

## 6. Logging & Monitoring

- **Backend:** Winston structured logging with daily log rotation
- **Audit:** OperationLog table — all CRUD operations with old/new values, IP, retention policy
- **Error Monitoring:** _(planned)_ Sentry

---

## 7. Future Notes

- AI speech-to-text for visit dictation
- Notification service (Web Push, Email, SMS)
- Document generation and approval workflow
- Load testing with k6 under 200-300 concurrent users
- E2E tests with real database
