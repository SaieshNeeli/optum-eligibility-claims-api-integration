# Optum Healthcare API Integration

## 📌 Overview

This project demonstrates enterprise-level integration with Optum Healthcare APIs including:

- Eligibility Inquiry (270/271)
- Institutional Claims Submission (837i)
- Claim Validation Workflow
- Secure Bearer Token Authentication
- X12 ↔ JSON Mapping
- Sandbox Environment Testing

⚠ This project is built for educational and sandbox integration purposes. No real patient data or production credentials are used.

---

## 🏥 Business Workflow

Eligibility Flow:
Provider → 270 Request → Optum API → 271 Response

Claims Flow:
Provider → 837i Submission → Validation Endpoint → Processing

---

## 🔐 Authentication

- OAuth2 Bearer Token
- Secure header handling
- Environment variable based credential storage

---

## 📡 APIs Covered

- Eligibility API (270/271)
- Institutional Claims API (837i)
- Claim Validation Endpoint

---

## 🛠 Technical Highlights

✔ Secure authentication  
✔ Request validation before submission  
✔ X12 EDI structure understanding (ISA, GS, ST segments)  
✔ Error handling from payer responses  
✔ Sandbox vs Production architecture awareness  

---

## 🧠 Key Concepts Implemented

- Healthcare EDI (ASC X12)
- JSON to X12 Mapping
- Trading Partner Configuration
- Control Numbers & Trace IDs
- API Response Debugging

---

## 🏗 Architecture

Client → Backend Service → Optum API Gateway → Payer
