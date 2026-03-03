# Raw X12 Eligibility (270/271) – Sandbox Integration

Environment: Sandbox  
Endpoint:  
POST https://sandbox-apigw.optum.com/medicalnetwork/eligibility/v3/raw-x12

Headers:
Content-Type: application/json  
Authorization: Bearer YOUR_ACCESS_TOKEN  
Accept: application/json  
x-chng-trace-id: TXN-001-TEST  

---

## 📤 Raw X12 270 Request

{
  "x12": "ISA*00*          *01*PWD         *ZZ*SENDERID      *ZZ*RECEIVERID    *260227*1000*^*00501*000000001*0*T*:~GS*HS*SENDERID*RECEIVERID*20260227*1000*1*X*005010X279A1~ST*270*0001*005010X279A1~BHT*0022*13*TXN001*20260227*1000~HL*1**20*1~NM1*PR*2*EXTRA HEALTHY INSURANCE*****PI*EXTRAHEALTHY~HL*2*1*21*1~NM1*1P*2*HAPPY DOCTORS GROUP*****XX*1234567890~HL*3*2*22*0~TRN*1*123456789~NM1*IL*1*DOEONE*JOHNONE****MI*1234567890~DMG*D8*19800101*M~DTP*291*D8*20260227~SE*13*0001~GE*1*1~IEA*1*000000001~"
}

---

## 🔎 Breakdown of Important 270 Segments

| Segment | Meaning |
|----------|----------|
| ISA | Interchange Control Header |
| GS | Functional Group Header |
| ST | Transaction Set Header (270) |
| BHT | Beginning of Hierarchical Transaction |
| HL | Hierarchical Levels |
| NM1*PR | Payer |
| NM1*1P | Provider |
| NM1*IL | Subscriber |
| DTP | Date of Service |
| SE | Transaction Trailer |

---

## 📥 Raw X12 271 Response

The API returns a 271 X12 transaction:

ST*271 → Eligibility Response

Key Segment Example:

EB*1*IND*30*QM*QMB

---

## 🔍 EB Segment Interpretation

| Element | Meaning |
|----------|----------|
| EB | Eligibility Benefit |
| 1 | Active Coverage |
| IND | Individual Coverage |
| 30 | Service Type Code |
| QM | Insurance Type Code |
| QMB | Plan Name |

---

## 🛡 Insurance Types Returned

| Code | Description |
|------|------------|
| QM | Qualified Medicare Beneficiary |
| MA | Medicare Part A |
| MB | Medicare Part B |

---

## 🔄 Flow Summary

1. Submit X12 270 request
2. Receive X12 271 response
3. Parse EB segments
4. Determine:
   - Active coverage
   - Insurance type
   - Service type coverage
   - Additional payers

---

## 🧠 Why Raw X12 Matters

- Some clearinghouses require X12 format
- Shows deep EDI understanding
- Required for legacy healthcare systems
- Demonstrates enterprise healthcare interoperability knowledge
