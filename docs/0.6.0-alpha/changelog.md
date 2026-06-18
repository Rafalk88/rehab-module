# Changelog – Version 0.6.0-alpha
**[0.6.0-alpha] – 2026-06-18**

---

## 🆕 Added

### 🧩 Frontend Progress
- **Office module** — visit list with filtering by status and date range
- `useVisits` hook — React Query with cache per orgId/dateFrom/dateTo/status
- `useUpdateVisitStatus` hook — PATCH status with automatic cache invalidation
- `useUser` Zustand store — global organizational unit selection
- `ApiConnectionIcon` — server health check indicator in navigation
- `Checkbox` component — read-only EWUŚ and billing status indicators
- `useAutoLogout` hook — auto logout after inactivity with countdown timer
- Jest + React Testing Library — unit and integration test setup with Husky

### 🧩 Backend Progress
- **Visit module** — full CRUD with status management
- `VisitStatus` enum: `PLANNED`, `IN_PROGRESS`, `COMPLETED`, `CANCELLED`
- Three lifecycle dates: `plannedDate`, `registerDate`, `completionDate`
- `ewusVerifiedAt` — insurance verification timestamp
- `billed` — billing status flag
- PESEL decryption included in visit responses (no N+1 queries)
- `UserIdInterceptor` — fixes userId propagation to RequestContext after JwtAuthGuard

### 📚 Documentation
- Added Decision 016 — Visit module data model
- Added Decision 017 — Visit filtering strategy
- Updated `DATABASE.md` with Visit and VisitStatus
- Updated `CHANGELOG.md` in backend with version 0.8.0
- Updated `CHANGELOG.md` in frontend with version 0.4.0-alpha

---

## 🔄 Changed

- Visit filtering replaced single `date` with `dateFrom`/`dateTo` range
- `IN_PROGRESS` status uses `dateFrom = 2000-01-01` to show all active visits
- `UnitSelector` now fetches from API instead of hardcoded list
- Login error handling uses `form.setFields` instead of toast

---

## 📝 Note

Version `0.6.0-alpha` focuses on the Office module MVP — visit list, status management, and filtering.  
First end-to-end feature connecting frontend filters → Zustand store → React Query cache → backend → PostgreSQL.
