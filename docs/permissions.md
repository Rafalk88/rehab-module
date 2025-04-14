# 🔐 Permissions System

This document describes the architecture of the permissions system in the `rehab-module` application, following enterprise-level standards.

---

## 📄 Core Concepts

| Element               | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| `Role`                | A defined function of the user (e.g., Physiotherapist, Manager)             |
| `Permission`          | A single action the user is allowed to perform (e.g., `can_create_patient`) |
| `RolePermission`      | Mapping of many permissions to roles                                        |
| `UserRoleBinding`     | Assigns a role to a user within an organizational unit context              |
| `OrganizationalUnit`  | Logical organization entity (e.g., clinic, department, cabinet)             |

---

## 🧑‍💼 Relational Schema

[User] └── has many → [UserRoleBinding] ├── belongs to → [OrganizationalUnit] └── has one → [Role] └── has many → [RolePermission] └── belongs to → [Permission]

---

## 🔄 Example Role and Permissions

### Example role: `medical_receptionist`
```json
{
  "role": "medical_receptionist",
  "permissions": [
    "can_create_patient",
    "can_schedule_appointment",
    "can_view_schedule"
  ]
}

### Example permission: `can_create_patient`
```json
{
  "id": "perm_001",
  "name": "can_create_patient",
  "description": "Allows creation of new patient records"
}
