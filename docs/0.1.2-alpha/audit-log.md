# Audit Log – Version 0.1.2-alpha

## Overview
Audit logs have been introduced to track all changes and actions performed by users in the system. This feature helps in monitoring the actions of both admins and regular users, ensuring better security and traceability.

### Key Features:
- **Track User Actions:**
  - All changes made to user settings, roles, permissions, and data are logged.
  - Each log entry includes details such as the user ID, action type, and timestamp.

- **Log Types:**
  - **Create**: New data entry (e.g., new user, new role).
  - **Update**: Changes to existing data (e.g., role updates).
  - **Delete**: Removal of data.
  - **Access**: Viewing data.

- **Log Storage**:
  - Logs are stored in a dedicated `audit_log` table.

### Sample Log Entry:
```json
{
  "user_id": 1,
  "action": "Update",
  "target": "UserConfig",
  "target_id": 123,
  "timestamp": "2025-04-17T10:00:00Z"
}

For implementation details, check the [Changelog for 0.1.2-alpha](./changelog.md).
For implementation details, see Changelog for 0.1.2-alpha.

---

> *Note:* Audit logs ensure transparency and accountability for all user actions.
