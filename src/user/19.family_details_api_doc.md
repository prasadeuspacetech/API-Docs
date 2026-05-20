# API Documentation: User Family Details API

This documentation details the GET, POST, PUT, and DELETE endpoints for managing user family details.

## Base URL
`/api/auth/profile/family`

## Required Request Headers
All endpoints require the following headers for authorization, context, and localization:
* `Authorization`: `Bearer <jwt_token>`
* `x-app-type`: `user`
* `accept-language`: `en-US` | `hi` | `mr`

---

## 1. Retrieve Family Details (GET)

Fetches active family details for a specific user.

### Request
* **Method**: `GET`
* **URL**: `/api/auth/profile/family/{userId}`
* **Path Parameters**:
  * `userId` (string, required): The target user ID.

### Response (200 OK)
Returns a direct flat JSON response.
```json
{
  "fatherStatusCategory": "Retired",
  "motherStatusCategory": "Homemaker",
  "numberOfBrothers": 1,
  "numberOfMarriedBrothers": 0,
  "numberOfSisters": 1,
  "numberOfMarriedSisters": 1,
  "familyAffluenceCategory": "Middle Class",
  "placeOfFamily": "Pune"
}
```

---

## 2. Create Family Details (POST)

Creates a new active family details record for the logged-in user. Prevents duplicates if an active record already exists.

### Request
* **Method**: `POST`
* **URL**: `/api/auth/profile/family`
* **Body** (application/json):
```json
{
  "fatherStatusCategory": "Retired",
  "motherStatusCategory": "Homemaker",
  "numberOfBrothers": 1,
  "numberOfMarriedBrothers": 0,
  "numberOfSisters": 1,
  "numberOfMarriedSisters": 1,
  "familyAffluenceCategory": "Middle Class",
  "placeOfFamily": "Pune"
}
```

### Responses
#### 200 OK (Success)
```json
{
  "statusCode": 200,
  "messageCode": "success.FAMILY_DETAILS_CREATED",
  "message": "Family details created successfully"
}
```

#### 409 Conflict (Record Already Exists)
```json
{
  "statusCode": 409,
  "messageCode": "error.familyDetailsExists",
  "message": "Family details already exist."
}
```

---

## 3. Update Family Details (PUT)

Updates the existing active family details record for the logged-in user.

### Request
* **Method**: `PUT`
* **URL**: `/api/auth/profile/family`
* **Body** (application/json):
```json
{
  "fatherStatusCategory": "Retired",
  "motherStatusCategory": "Homemaker",
  "numberOfBrothers": 1,
  "numberOfMarriedBrothers": 0,
  "numberOfSisters": 1,
  "numberOfMarriedSisters": 1,
  "familyAffluenceCategory": "Middle Class",
  "placeOfFamily": "Pune"
}
```

### Responses
#### 200 OK (Success)
```json
{
  "statusCode": 200,
  "messageCode": "success.FAMILY_DETAILS_UPDATED",
  "message": "Family details updated successfully"
}
```

#### 404 Not Found (No Active Row)
```json
{
  "statusCode": 404,
  "messageCode": "error.familyDetailsNotFound",
  "message": "Family details not found."
}
```

---

## 4. Delete Family Details (DELETE)

Soft deletes the active family details record for the logged-in user (sets `deleted = TRUE` in the database).

### Request
* **Method**: `DELETE`
* **URL**: `/api/auth/profile/family`

### Responses
#### 200 OK (Success)
```json
{
  "statusCode": 200,
  "messageCode": "success.FAMILY_DETAILS_DELETED",
  "message": "Family details deleted successfully"
}
```

#### 404 Not Found (No Active Row)
```json
{
  "statusCode": 404,
  "messageCode": "error.familyDetailsNotFound",
  "message": "Family details not found."
}
```
