#  Login via Mobile (Send OTP)

This API is used by existing users to request an OTP for logging into the application using their registered mobile number.

**URL:**
`/api/user/login-mobile`

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
  "countryCode": "+91"
}
```

**Sample Output (Success)**

```json
{
    "message": "OTP sent successfully.",
    "statusCode": 200,
    "messageCode": "success.otpSent"
}
```

**Error Message Scenarios**

1. User Not Registered
```json
{
  "message": "User not found. Please register first.",
  "statusCode": 400,
  "messageCode": "error.userNotRegistered"
}

```

2. User Account Deactivated
```json
{
  "message": "Your account has been deactivated. Please contact support.",
  "statusCode": 400,
  "messageCode": "error.userDeactivated"
}

```

3. User Account Deleted
```json
{
  "message": "This account has been removed. Please contact support.",
  "statusCode": 400,
  "messageCode": "error.userDeleted"
}

```

4. OTP Rate Limit (Too many attempts)
```json
{
  "message": "Too many OTP requests. Please try again after 10 minutes.",
  "statusCode": 429,
  "messageCode": "error.otpRateLimit"
}

```

5. Invalid Mobile Number Format
```json
{
  "message": "Invalid mobile number.",
  "statusCode": 400,
  "messageCode": "error.mobileInvalid"
}

```
