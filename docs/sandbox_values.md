# Sandbox Predefined Fields & Values – Optum Eligibility API

Environment: Sandbox  
Reference: Optum Developer Portal  

⚠ IMPORTANT  
- Do NOT use real-world patient or provider data in sandbox.  
- Sandbox returns canned responses.  
- No real validation occurs in sandbox.  
- All required fields must use predefined values exactly as listed.

---

## 🧠 How Sandbox Works

The sandbox environment:

- Returns predefined (canned) responses.
- Does NOT validate real insurance data.
- Requires exact predefined values.
- Is case-sensitive (camelCase JSON required).

Example:
Correct → "firstName"
Incorrect → "FirstName"

---

## 🔐 Critical Rules

✔ Use only predefined values  
✔ Include all required (R) fields  
✔ Do not invent new values  
✔ Do not use real PMI (Personal Medical Information)

Using real data will result in errors.

---

# 📋 Predefined Eligibility Fields

Below are valid sandbox test values.

---

## 🔢 controlNumber

Allowed values:
- "000000001"
- "000000002"
- "000000003"
- "000000004"
- "123456789"

---

## 👤 Subscriber Information

### memberId
- "0000000000"
- "0000000001"
- "0000000002"
- "1234567890"
- "0000000004"
- "0000000005"
- "0000000006"
- "0000000007"
- "123456789"

---

### firstName
- "johnone"
- "johntwo"
- "janeone"
- "janetwo"

---

### lastName
- "doeone"
- "doetwo"

---

### gender
- "m"
- "f"

---

### dateOfBirth
- "18800102"
- "18800101"
- "18160421"
- "19800101"
- "19800102"
- "20000101"
- "20000102"

---

### ssn
- "000000000"
- "555443333"
- "111111111"
- "000000001"
- "891234567"
- "123456789"

---

## 🏥 Provider Information

### npi
- "1760854442"
- "1942788757"
- "0123456789"

---

### organizationName
- "happy doctors group"
- "happy doctors grouppractice"
- "extra healthy insurance"
- "regional ppo network"

---

## 📦 Additional Common Fields

### groupNumber
- "0000000000"
- "1111111111"
- "1234567891"

### employerId
- "00000"
- "12345"

### state
- "wa"
- "tn"

### postalCode
- "981010000"
- "372030000"

---

# 🧪 Example Valid Sandbox Request

{
  "controlNumber": "123456789",
  "tradingPartnerServiceId": "EXTRAHEALTHY",
  "provider": {
    "organizationName": "happy doctors group",
    "npi": "0123456789"
  },
  "subscriber": {
    "memberId": "123456789",
    "firstName": "johnone",
    "lastName": "doeone",
    "gender": "m",
    "dateOfBirth": "19800101",
    "ssn": "111111111"
  }
}

---

# 🚨 Common Sandbox Errors

| Problem | Reason |
|----------|--------|
| 400 Bad Request | Used non-predefined value |
| Empty response | Missing required field |
| Case mismatch | JSON not camelCase |

---

# 🎯 Key Takeaway

The sandbox is designed to:
- Simulate eligibility responses
- Help developers understand request/response structure
- Familiarize with API behavior

Real validation and payer-specific requirements only occur in production.

---

## 🔗 Official Documentation

Sandbox predefined values reference:
https://developer.optum.com/eligibilityandclaims/docs/sandbox-predefined-fields-and-values
