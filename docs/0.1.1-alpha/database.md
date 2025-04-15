# Database Schema – Version 0.1.1-alpha

## Overview
In this version, the database schema was created with the following key tables and relationships:

### Key Tables:
- **Users**
  - Stores user information (e.g., email, name, password hash, etc.)
  - **Fields**: `id`, `email`, `first_name`, `last_name`, `password_hash`, `is_locked`, `failed_login_attempts`, etc.
  
- **Roles**
  - Stores user roles for access control (e.g., admin, user).
  - **Fields**: `id`, `name`, `permissions`.

- **Permissions**
  - Manages permissions for different roles.
  - **Fields**: `id`, `role_id`, `permission_code`, `description`.

- **User Configuration**
  - Stores user-specific configuration settings (e.g., preferences, settings).
  - **Fields**: `user_id`, `setting_code`, `setting_value`.

### Schema Relationships:
- One-to-many relationship between **Users** and **Roles**.
- One-to-many relationship between **Roles** and **Permissions**.

For more details, see the [Changelog for 0.1.1-alpha](./changelog.md) and [Permissions Documentation](./permissions.md).

---

> *Note:* The database schema is designed to support user management, roles, permissions, and configurations for personalized settings.
