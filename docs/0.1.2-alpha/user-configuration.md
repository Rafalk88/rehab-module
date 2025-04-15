# User Configurations – Version 0.1.2-alpha

## Overview
User configurations allow for the personalization of the application by enabling users to control their settings and preferences. In version `0.1.2-alpha`, these configurations have been extended to provide more options for customization.

### Available Configuration Options:
- **Theme**: Choose between light and dark mode for the UI.
- **Notification Preferences**: Set up whether the user will receive email and SMS notifications for specific events.
- **Language**: Choose the preferred language for the user interface (e.g., English, Polish).
- **Reminder Time**: Set the time for appointment reminders.

### Example Configuration (JSON Format):
Here’s an example of how user configurations could be stored in the database:

```json
{
  "user_id": 1,
  "settings": [
    {
      "setting_code": "theme",
      "setting_value": "dark"
    },
    {
      "setting_code": "notification_email",
      "setting_value": "true"
    },
    {
      "setting_code": "language",
      "setting_value": "en"
    },
    {
      "setting_code": "reminder_time",
      "setting_value": "30"  // 30 minutes before the appointment
    }
  ]
}
```

### Available Configuration Options:
- **theme**: Choose the appearance of the application (e.g., dark, light).
- **notification_email**: Controls whether email notifications are enabled (true/false).
- **language**: The language setting for the application (e.g., en, pl).
- **reminder_time**: The time in minutes before a reminder notification is sent to the user.

### How User Configurations Work:
1. **Storage**: User configurations are stored in the `user_configurations` table in the database. Each setting is associated with a specific `user_id`.
2. **Editable Settings**: Users can modify their own settings, such as changing the theme or adjusting notification preferences.
3. **Admin Access**: Admin users can also update configurations for other users. However, some settings (such as theme and language) can only be modified by the user themselves.

### Example User Settings Table:

| user_id | setting_code       | setting_value |
|---------|--------------------|---------------|
| 1       | theme              | dark          |
| 1       | notification_email | true          |
| 1       | language           | en            |
| 1       | reminder_time      | 30            |

### Configuration Management:
- Users can update their own settings via the user interface.
- Admins can manage and adjust configurations for individual users, enabling flexibility in system customization.
- All changes to user settings are logged in the system for auditing purposes.

### Configuration Workflow:
- When a user modifies their settings, the changes are immediately reflected in the database.
- Admin modifications will be applied to the target user's configuration and will be communicated accordingly.

### User Preferences System:
- The user preferences system helps provide a personalized experience.
- The configuration settings are stored in a centralized table (`user_configurations`), which links each setting to a specific user.

> **Note:** For more information on the database schema and where the configurations are stored, please refer to the [Database Documentation](./database.md).
> 
