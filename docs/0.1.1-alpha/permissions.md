# Permissions System – Version 0.1.1-alpha

## Overview
In this version, a role-based access control (RBAC) system was implemented. It defines various roles and their associated permissions.

### Roles:
- **Admin**: Full access to all features and data.
- **User**: Limited access to specific features (e.g., view only).
  
### Permissions:
- **View Data**: Allows a user to view specific data.
- **Edit Data**: Allows a user to modify data.
- **Admin Actions**: Allows an admin to perform administrative tasks (e.g., user management, role assignment).

Each role is associated with one or more permissions. The system ensures that users can only perform actions that their role allows.

For more details on user roles and permissions, refer to the [Database Documentation](./database.md).

---

> *Note:* Permissions can be dynamically assigned to roles and are part of the system's security model.
