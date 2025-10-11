# Changelog – Version 0.3.0-alpha

**[0.3.0-alpha] – 2025-10-11**

---

## 🆕 Added

### 🧩 Backend Integration

- Introduced a dedicated **Rehab Backend** repository using **NestJS**  
- Implemented modular architecture with `modules/`, `common/`, and `lib/` directories  
- Added JWT authentication with access & refresh tokens  
- Integrated **Prisma ORM** with PostgreSQL  
- Introduced structured logging via **Winston** and centralized exception filters  

### 📚 Documentation Structure

- Split documentation between **main app** and **backend** repositories  
- Added links in the main README to backend docs (`architecture.md`, `database.md`, `permissions.md`, `api.md`)  
- Updated `Internal Documentation` section to avoid duplication  
- Improved clarity of README sections and hierarchy  

---

## 🔄 Changed

### 🧰 Tech Stack Overview

- Updated backend stack from *Next.js API Routes / Express* to **NestJS (TypeScript, modular)**  
- Made “Testing” section technology-neutral (no longer references specific frameworks)  
- Clarified structure for `/app`, `/docker`, and `.github` directories  
- Marked `/api` directory as deprecated (backend moved to separate repo)  

### 🚀 CI/CD and Versioning

- Maintained Docker-based development setup  
- Updated versioning metadata and changelog to reflect new multi-repo architecture  

---

## 🧹 Removed

- Duplicated internal docs (`architecture.md`, `permissions.md`, `database.md`) from main repo — now hosted in backend repo  
- Old references to Express/Next API backend  

---

## 📝 Note

Version `0.3.0-alpha` introduces a **multi-repository architecture**, separating frontend and backend responsibilities.  
The backend now uses **NestJS**, and the documentation has been reorganized to ensure maintainability and consistency across projects.
