# Authentication – Access Token Generation

Optum APIs require OAuth2 Client Credentials authentication.

Environment:
Sandbox Gateway

Endpoint:
POST https://sandbox-apigw.optum.com/apip/auth/v2/token

---

## Request Headers

Content-Type: application/json

---

## Request Body

{
  "client_id": "YOUR_CLIENT_ID",
  "client_secret": "YOUR_CLIENT_SECRET",
  "grant_type": "client_credentials"
}

---

## Sample Response

{
  "access_token": "YOUR_ACCESS_TOKEN",
  "token_type": "bearer",
  "expires_in": 3600
}

---

## Field Explanation

| Field | Description |
|-------|-------------|
| access_token | Token used in Authorization header |
| token_type | Always 'bearer' |
| expires_in | Token validity in seconds (3600 = 1 hour) |

---

## Usage in Eligibility API

Authorization: Bearer YOUR_ACCESS_TOKEN
