# Database Schema – Version 0.1.2-alpha

## Overview
In this version, we refined the database schema to include additional user configuration details and improved relationships between users, roles, and permissions.

### Key Updates:
- **User Configurations Table:**
  - **Fields**: `user_id`, `setting_code`, `setting_value`, `updated_at`
  - Additional fields added to store more granular user preferences.

- **Permissions Table:**
  - Extended to cover more actions like **View**, **Edit**, **Delete**.
  - Granular control over permissions per role.

### Schema Relationships:
- **Users to Roles**: One-to-many relationship.
- **Roles to Permissions**: One-to-many relationship.
- **Users to User Configurations**: One-to-many relationship.

For more details, check the [Changelog for 0.1.2-alpha](./changelog.md) and [Permissions System Documentation](./permissions.md).

---

> *Note:* The database schema is now more flexible with added configurations and permissions.
