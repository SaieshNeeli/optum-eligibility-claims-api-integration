# Eligibility API – Request & Response (Sandbox v3)

Environment:
Sandbox

Endpoint:
POST https://sandbox-apigw.optum.com/medicalnetwork/eligibility/v3/

Headers:
Content-Type: application/json
Authorization: Bearer YOUR_ACCESS_TOKEN
Accept: application/json

---

## 📤 Sample Eligibility Request

{
  "controlNumber": "123456789",
  "tradingPartnerServiceId": "serviceId",
  "provider": {
    "organizationName": "happy_doctors_group",
    "npi": "0123456789",
    "serviceProviderNumber": "54321",
    "providerCode": "AD",
    "referenceIdentification": "54321g"
  },
  "subscriber": {
    "memberId": "123456789",
    "firstName": "johnOne",
    "lastName": "doeOne",
    "gender": "M",
    "dateOfBirth": "18800102",
    "ssn": "111111111",
    "idCard": "card123"
  },
  "encounter": {
    "beginningDateOfService": "20100101",
    "endDateOfService": "20100102",
    "serviceTypeCodes": ["30"]
  }
}

---

## 📥 Sample Eligibility Response (271 Equivalent)

Key Sections:

### 1️⃣ Meta Information
- senderId
- applicationMode
- traceId

### 2️⃣ Plan Status

"status": "Active Coverage"

Indicates subscriber has active insurance coverage.

---

### 3️⃣ Benefits Information

Example:

{
  "insuranceTypeCode": "QM",
  "insuranceType": "Qualified Medicare Beneficiary",
  "serviceTypeCodes": ["30"]
}

---

## 🛡 Insurance Types Returned

| Code | Description |
|------|------------|
| QM | Qualified Medicare Beneficiary |
| MA | Medicare Part A |
| MB | Medicare Part B |

---

## 🏥 Service Type Code Used

Service Type Code: 30

Meaning:
Health Benefit Plan Coverage

---

## 🔎 X12 271 Included

The API also returns raw X12:

ISA → GS → ST → EB → SE → IEA

EB segments indicate benefit information.

Example:
EB*1*IND*30*QM*QMB

This indicates:
Active coverage (1)
Individual (IND)
Service type 30
Insurance type QM
Plan: QMB
