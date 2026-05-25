# Update Password API Documentation

Allows standard authenticated users to update their password.

* **Endpoint**: `PUT /api/auth/user/update-password`
* **Content-Type**: `application/json`
* **Authentication**: Requires `Authorization: Bearer <jwt_token>` header.
* **Localization**: Supports `Accept-Language` header (`en-US`, `hi`, or `mr`).

---

### Request Headers

| Header | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `Authorization` | `string` | **Yes** | Bearer token format: `Bearer <token>` |
| `Accept-Language` | `string` | No | Target locale for messages (defaults to `en-US`) |

### Request Body

```json
{
  "newPassword": "yourNewSecurePassword"
}
```

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `newPassword` | `string` | **Yes** | The new password to set (minimum 6 characters). |

---

### Responses

#### 1. Success Response (200 OK)
Returned when the password has been successfully updated.

```json
{
  "message": "Password updated successfully.",
  "statusCode": 200,
  "messageCode": "success.passwordUpdated"
}
```

#### 2. Error Responses

* **401 Unauthorized (Missing/Invalid Token)**
  ```json
  {
    "message": "Authorization token is required.",
    "statusCode": 401,
    "messageCode": "error.tokenRequired"
  }
  ```

* **400 Bad Request (Missing `newPassword` Field)**
  ```json
  {
    "message": "newPassword is required.",
    "statusCode": 400,
    "messageCode": "error.fieldRequired"
  }
  ```

* **400 Bad Request (Password Less Than 6 Characters)**
  ```json
  {
    "message": "Password must be at least 6 characters.",
    "statusCode": 400,
    "messageCode": "error.passwordMinLength"
  }
  ```

* **400 Bad Request (Attempting to update when password is not set yet)**
  ```json
  {
    "message": "Password is not set. Please set the password first.",
    "statusCode": 400,
    "messageCode": "error.passwordUpdateNotSet"
  }
  ```

* **404 Not Found (User Not Found)**
  ```json
  {
    "message": "User not found.",
    "statusCode": 404,
    "messageCode": "error.userNotFound"
  }
  ```
