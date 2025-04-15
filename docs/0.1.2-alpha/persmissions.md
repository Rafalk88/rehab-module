# Permissions – Rehabilitacja Web App

## Overview

The permissions system is designed to control access to various resources and actions within the application. Each user is assigned one or more roles, and these roles define what actions the user is permitted to perform. Permissions are granted or restricted based on these roles.

## Roles

### 1. **Administrator**
- **Permissions**:
  - Full access to all modules and features.
  - Ability to manage user roles and configurations.
  - Can update any user's settings and preferences.

### 2. **Rehabilitant**
- **Permissions**:
  - Access to patient schedules, rehabilitation treatments, and daily plans.
  - Cannot manage users or modify system configurations.

### 3. **Doctor**
- **Permissions**:
  - Can view and manage medical appointments and visit notes.
  - Access to the AI dictation and redaction tools.
  - Cannot manage users or modify system settings.

### 4. **Receptionist**
- **Permissions**:
  - Can manage patient appointments and schedules.
  - Cannot access sensitive medical data or user configurations.

## Role-Based Access Control (RBAC)

The system uses Role-Based Access Control (RBAC) to manage user permissions. Each role has a predefined set of permissions that determine what actions a user can perform. Admin users are responsible for assigning roles to other users.

## Dynamic Permissions

In addition to predefined roles, the system allows dynamic permissions that can be modified on a per-user basis. This ensures flexibility in managing user access and functionality, depending on their needs.

## Example of Permissions Management:

| Role        | Permissions                                                      |
|-------------|------------------------------------------------------------------|
| Admin       | Full access to all system features, user management, and settings |
| Rehabilitant| View/manage patient schedules, treatments, and plans             |
| Doctor      | View/manage appointments and medical notes                        |
| Receptionist| Manage patient appointments and schedules                         |

Note: The permissions table is stored in the `permissions` table in the database, and the roles are linked to users through the `user_roles` table.
