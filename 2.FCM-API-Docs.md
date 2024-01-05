# FCM-API-Docs
# Firebase Cloud Messaging (FCM) Push Notification Documentations

This Documents provides a set of requests for sending push notifications using Firebase Cloud Messaging (FCM). These notifications cover various scenarios, including force updates, flexible updates, asset-related notifications, and ticket assignments.

## Getting Started

1.**Postman Configuration**
 You should have `FCM_Push_Notification.postman_collection.json` File

2. **Import Collection:**
   - Open Postman.
   - Click on "Import" and select the `FCM_Push_Notification.postman_collection.json` file which you have downloaded.

3. **Configure Environment:**
   - Create a Postman environment or update the existing one.
   - Set the values for the environment variables:
     - `deviceToken`: The token for the target device.
     - `fcm_key`: Your Firebase Cloud Messaging API key.

## Notifications Overview

### 1. Force Update

- **Endpoint:** `POST https://fcm.googleapis.com/fcm/send`
- **Description:** Sends a push notification to force users to update the app.
- **Body Example:**
  ```json
  {
    "to": "{{deviceToken}}",
    "priority": "high",
    "data": {
      "title": "App Update Required!",
      "body": "Please Update The App",
      "type": "force_update"
    }
  }
  ```

### 2. Flexible Update

- **Endpoint:** `POST https://fcm.googleapis.com/fcm/send`
- **Description:** Sends a push notification to inform users about a flexible app update.
- **Body Example:**
  ```json
  {
    "to": "{{deviceToken}}",
    "priority": "high",
    "data": {
      "title": "New Version Available!",
      "body": "Please update the app for better user experience.",
      "type": "flexible_update"
    }
  }
  ```

### 3. Asset Added (Show Big Image)

- **Endpoint:** `POST https://fcm.googleapis.com/fcm/send`
- **Description:** Sends a push notification to show a big image when an asset is added.
- **Body Example:**
  ```json
  {
    "to": "{{deviceToken}}",
    "priority": "high",
    "data": {
      "title": "Asset added!",
      "body": "Ayush kumar added it-asset",
      "image": "https://happay.com/blog/wp-content/uploads/sites/12/2023/04/best-asset-management-software-system-solutions.webp",
      "type": "asset_added",
      "asset": {
        "asset_id": "ASSET0001",
        "cid": "117769199052525670400"
      }
    }
  }
  ```

### 4. Asset Updated (Show Small Image)

- **Endpoint:** `POST https://fcm.googleapis.com/fcm/send`
- **Description:** Sends a push notification to show a small image when an asset is updated.
- **Body Example:**
  ```json
  {
    "to": "{{deviceToken}}",
    "priority": "high",
    "data": {
      "title": "Asset Updated!",
      "body": "Ayush kumar updated the it-asset",
      "image": "https://happay.com/blog/wp-content/uploads/sites/12/2023/04/best-asset-management-software-system-solutions.webp"
    }
  }
  ```

### 5. Ticket Assigned (Show Ticket Action)

- **Endpoint:** `POST https://fcm.googleapis.com/fcm/send`
- **Description:** Sends a push notification for ticket assignment.
- **Body Example:**
  ```json
  {
    "to": "{{deviceToken}}",
    "priority": "high",
    "data": {
      "title": "Ticket Assigned!",
      "body": "Ayush Kumar Assigned! Ticket to you.",
      "image": "https://happay.com/blog/wp-content/uploads/sites/12/2023/04/best-asset-management-software-system-solutions.webp",
      "type": "ticket_action"
    }
  }
  ```

## Important Note

Ensure that you replace the placeholders (`{{deviceToken}}` and `{{fcm_key}}`) with actual values in the Postman environment before making requests.

 
