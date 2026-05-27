# Set Password API Documentation

Allows standard authenticated users (e.g. logged in via OTP) to set their initial account password.

* **Endpoint**: `POST /api/auth/user/set-password`
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
  "password": "yourSecurePassword123"
}
```

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `password` | `string` | **Yes** | The password to set for the account (minimum 6 characters). |

---

### Responses

#### 1. Success Response (200 OK)
Returned when the password has been successfully set.

```json
{
  "message": "Password set successfully.",
  "statusCode": 200,
  "messageCode": "success.passwordSet"
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

* **400 Bad Request (Missing `password` Field)**
  ```json
  {
    "message": "password is required.",
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

* **400 Bad Request (Database Set Password Failed)**
  ```json
  {
    "message": "Failed to set password. Please try again.",
    "statusCode": 400,
    "messageCode": "error.passwordSetFailed"
  }
  ```
