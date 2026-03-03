# Eligibility Response — Key Fields

This document explains important fields returned by the Optum Eligibility API, especially coverage information like copay, coinsurance, deductible, insurance type, etc.

---

## 🩺 Copay & Copayment

A **copay/copayment** is a fixed amount the patient must pay for a service or prescription before insurance covers the remainder.

According to the Optum docs:
- Copay amounts can be included in the eligibility response.
- Copay details include the amount, type of service it applies to, and time period (e.g., per visit, per day).  
👉 See official doc:  
https://developer.optum.com/eligibilityandclaims/docs/find-deductible-and-co-pay-in-eligibility-response  
https://developer.optum.com/eligibilityandclaims/docs/co-payment

---

## 🔁 Coinsurance

- **Coinsurance** is the percentage of the allowed amount the patient pays after meeting the deductible.  
Example: If coinsurance is 20%, the insurer covers 80% after deductible.

Official reference:  
https://developer.optum.com/eligibilityandclaims/docs/co-insurance

---

## 🛡 Insurance Type Codes

Insurance type codes indicate the type of coverage the subscriber has.

Example types:
- Group Health
- HMO
- PPO
- Medicare
- Medicaid

Official list:  
https://developer.optum.com/eligibilityandclaims/docs/possible-insurancetypecodes

---

## 🚫 Subscriber without Active Coverage

If a subscriber has **no active medical coverage**, the API returns specific codes and messages indicating coverage is absent.

Official doc:  
https://developer.optum.com/eligibilityandclaims/docs/subscriber-without-an-active-medical-coverage
