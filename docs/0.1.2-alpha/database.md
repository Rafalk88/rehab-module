# Database Schema – Version 0.1.2-alpha

## Overview

This version includes a refined and expanded schema to support user configuration, modular permissions, and full audit logging.

---

## Key Updates

### 🧑‍💻 User Configuration
- New `UserConfiguration` and `SystemConfiguration` tables added
- Tracks user-specific settings like theme, notifications, language
- Changes are logged in `UserConfigurationLog`

**Key Fields:**
- `user_id`
- `configuration_id`
- `value`
- `assigned_by`
- `assigned_at`

---

### 🔐 Permissions Model

- Roles are defined in the `Role` table
- Users are assigned roles via `UserRole`
- Permissions are defined in-code and linked to roles
- Permissions include actions like `view`, `update`, `delete`

---

### 📜 Audit Logging

- `OperationLog` records all sensitive or impactful actions
- Tracks:
  - `user_id`
  - `action`
  - `entity_type`
  - `entity_id`
  - `timestamp`

---

## 🔗 Schema Relationships

| Relationship                     | Description                                      |
|----------------------------------|--------------------------------------------------|
| User → UserRole                  | One-to-many: user can have multiple roles       |
| Role → Permissions (in code)     | One-to-many: role maps to multiple permissions  |
| User → UserConfiguration         | One-to-many: stores personalized settings       |
| UserConfiguration → SystemConfiguration | One-to-one: defines config type           |
| User → OperationLog              | One-to-many: tracks user actions and changes    |

---

## 🗺️ Full Entity Relationship Diagram

You can view the complete schema in an interactive diagram:

👉 [Open dbdiagram.io ERD](https://dbdiagram.io/d/rehabModule-67fd4aab9cea640381aea3ac)

---

## Related Documentation

- [Permissions System](./permissions.md)  
- [User Configuration Module](./user-configurations.md)  
- [Audit Log Details](./audit-log.md)  
- [Changelog for 0.1.2-alpha](./changelog.md)

---

> _Note: This schema provides a strong foundation for modular, auditable, and configurable enterprise systems._
