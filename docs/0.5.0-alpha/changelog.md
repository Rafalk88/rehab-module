# Changelog – Version 0.5.0-alpha

**[0.5.0-alpha] – 2026-05-30**

---

## 🆕 Added

### 🧩 Backend Progress
- Implemented **Patient module** with encrypted PESEL storage
- Added `GET /api/v1/patients`, `GET /api/v1/patients/:id`, `POST /api/v1/patients`
- Added `PeselStatus` enum covering Polish and foreign patient cases
- Implemented automatic audit logging for all patient operations
- Added conflict detection (409) for duplicate PESEL

### 🔐 Security
- AES-256-GCM encryption with key versioning for sensitive fields
- HMAC-based search index for encrypted fields
- Sensitive field redaction in audit logs (`[REDACTED]`)
- Fixed `AuthorizationGuard` to correctly read JWT payload

### 📚 Documentation
- Rewrote main `README.md` — honest status with implemented vs planned features
- Added `DECISIONS.md` link to main docs
- Added Decision 015 — Patient data encryption and PESEL handling
- Updated `DATABASE.md` with Patient model and PeselStatus enum
- Updated `CHANGELOG.md` in backend with version 0.7.0

---

## 🔄 Changed

- README now clearly separates **implemented** from **planned** features
- Tech stack updated to reflect actual current state
- Version badge updated to `0.5.0-alpha`
- Documentation links updated to point to correct versioned folders

---

## 🧹 Removed

- Removed misleading references to Twilio, Sentry, GitHub Actions, Vercel from tech stack
- Removed unimplemented features from active modules description

---

## 📝 Note

Version `0.5.0-alpha` focuses on documentation accuracy and patient module implementation.  
The project now clearly communicates what is built vs planned — a more honest and professional presentation for portfolio purposes.
