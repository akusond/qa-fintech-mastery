# QA Test Plan: Crypto & Utility Fintech App

## 1. Overview
This test plan outlines the quality assurance strategy for the core transaction engine, covering crypto wallet interactions and utility bill payments (Airtime/Data).

## 2. Testing Strategy
* **Functional Testing:** Verifying all "Happy Path" transactions.
* **Security Testing:** Validating API authorization and preventing IDOR vulnerabilities.
* **Resiliency Testing:** Ensuring idempotency during network failures.

## 3. Core Test Scenarios

### A. Transaction Management
| Scenario | Expected Result | Priority |
| :--- | :--- | :--- |
| Successful Airtime Purchase | `200 OK` + Transaction Receipt | High |
| Insufficient Wallet Balance | `400 Bad Request` | High |
| Duplicate Payment Request | `200 OK` (using Idempotency-Key) | High |

### B. Security & Access Control
* **Test:** Accessing Transaction History of another user.
* **Expectation:** `403 Forbidden` status code.
* **Reasoning:** Prevents Insecure Direct Object Reference (IDOR) attacks.

## 4. Tools Used
* **Postman:** API collection and environment automation.
* **Git/GitHub:** Version control for test documentation and scripts.
* **GitHub Actions:** CI/CD pipeline for automated test execution.