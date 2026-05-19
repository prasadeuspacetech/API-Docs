# Login via Password

This API is used for direct login using a registered mobile number and password.

**URL:**
`/api/user/login-password`

**Method:**
Post

**Headers:**
```
Content-Type: application/json
Accept-Language: en-US
```

**Sample Input**

```json
{
  "mobileNumber": "9000000125",
  "countryCode": "+91",
  "password": "man@123",
  "deviceInfo": {
    "deviceId": "device-001",
    "deviceType": "android",
    "os": "Android",
    "osVersion": "13",
    "appVersion": "1.0.0",
    "notificationToken": "fcm-token-001"
  }
}
```

**Sample Output (Success)**

```json
{
    "message": "Login successful.",
    "statusCode": 200,
    "messageCode": "success.login",
    "id": "b67695843eaa4f6b9caa1c2ad105006a",
    "createdAt": 1779117726,
    "updatedAt": 1779120145,
    "platformId": "M-637160",
    "firstName": "Dummy.Nitin",
    "lastName": "Mehta",
    "birthDate": "1087237800",
    "age": 21,
    "mobileNumber": 9000000125,
    "countryCode": "+91",
    "email": "nitin.mehta12@example.com",
    "gender": "Male",
    "password": null,
    "profilePicture": null,
    "roleList": null,
    "deviceDetails": {
        "id": "c886ace900bb497dbe06cd607551d524",
        "createdAt": 1779120633,
        "updatedAt": 1779120633,
        "sessionKey": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiYjY3Njk1ODQzZWFhNGY2YjljYWExYzJhZDEwNTAwNmEiLCJleHAiOjE3Nzk3MjU0MzN9.d1zD_gWaDBQ4DfY3TuYJKKJnRVY-2KxJS6k1niyaIWE",
        "userId": "b67695843eaa4f6b9caa1c2ad105006a",
        "deviceId": "device-001",
        "deviceType": "android",
        "os": "Android",
        "osVersion": "13",
        "appVersion": "1.0.0",
        "notificationToken": "fcm-token-001"
    },
    "profileCompleteness": {
        "id": "00ddbfc79419419ab3ad63b2df24a774",
        "userId": "b67695843eaa4f6b9caa1c2ad105006a",
        "createdAt": 1779117726,
        "updatedAt": 1779120633,
        "userDetails": true,
        "userBasicDetails": true,
        "professionDetails": true,
        "personalDetails": true,
        "galleryDetails": false,
        "familyDetails": false,
        "addressDetails": false,
        "partnerPreferencesDetails": true,
        "verifyMobileNumber": true
    }
}
```

**Error Message Scenarios**

1. Incorrect Password
```json
{
  "message": "Incorrect password. Please try again.",
  "statusCode": 400,
  "messageCode": "error.passwordIncorrect"
}
```

2. User Not Registered
```json
{
  "message": "User not found. Please register first.",
  "statusCode": 400,
  "messageCode": "error.userNotRegistered"
}

```

3. Password Not Set
```json
{
  "message": "Password not set. Please login using OTP.",
  "statusCode": 400,
  "messageCode": "error.passwordNotSet"
}

```

4. User Account Deactivated
```json
{
  "message": "Your account has been deactivated. Please contact support.",
  "statusCode": 400,
  "messageCode": "error.userDeactivated"
}
```
