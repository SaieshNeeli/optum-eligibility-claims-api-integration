# API Testing using Insomnia

This project was tested using Insomnia REST Client against the Optum Sandbox Environment.

---

## 1️⃣ Generate Access Token

POST /apip/auth/v2/token

Headers:
Content-Type: application/x-www-form-urlencoded

Body:
client_id=YOUR_CLIENT_ID
client_secret=YOUR_CLIENT_SECRET
grant_type=client_credentials

Response:
{
  "access_token": "YOUR_ACCESS_TOKEN",
  "token_type": "Bearer",
  "expires_in": 3600
}

---

## 2️⃣ Check Eligibility (JSON Request)

POST /medicaleligibility

Headers:
Authorization: Bearer YOUR_ACCESS_TOKEN
Content-Type: application/json

Request Body:
{
  "controlNumber": "123456789",
  "tradingPartnerServiceId": "EXTRAHEALTHY",
  "provider": {
    "organizationName": "Happy Doctors Group"
  },
  "subscriber": {
    "memberId": "TEST12345"
  }
}

---

## Sample Response (271 Equivalent)

{
  "coverageStatus": "Active",
  "copay": {
    "amount": "25.00",
    "serviceTypeCode": "30"
  },
  "insuranceTypeCode": "HMO"
}
