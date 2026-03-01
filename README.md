# 🧪 PetStore Performance Testing using Apache JMeter

## 📌 Project Overview

This project demonstrates performance testing of the PetStore web application using **Apache JMeter**.

The objective of this test is to simulate real user behavior for:

- User Registration
- User Login

The test includes parameterization, correlation, assertions, and structured execution to mimic real-world usage.

---

## 🎯 Objective

- Validate the Registration and Login workflow under load
- Ensure dynamic values are properly handled using correlation
- Simulate multiple virtual users
- Measure response time and error rate
- Verify successful transactions using assertions

---

## 🛠️ Tools Used

- Apache JMeter
- CSV Data Set Config (for parameterization)
- Regular Expression Extractor (for correlation)
- Response Assertion
- HTML Report Generator

---

## 🔁 Test Scenario (User Flow)

Each virtual user performs the following steps:

1. GET Home Page
2. GET Register Page
3. POST Register (new user)
4. GET Login Page
5. POST Login (using registered credentials)



---

## ⚙️ Test Configuration

| Parameter        | Value        |
|------------------|-------------|
| Number of Threads | 5 Users     |
| Ramp-Up Period   | 10 Seconds  |
| Loop Count       | 1           |
| Protocol         | HTTPS       |

---
## 🔗 Correlation

During recording, the application generated dynamic hidden fields:

- `_sourcePage`
- `__fp`

These values change for every session.

### Solution:

Used **Regular Expression Extractor** to extract values from:

GET Register Page response



Extracted Variables:

- `${sourcePage}`
- `${fp}`

Passed dynamically in:

POST Register request

This ensures successful execution under multiple users.

---

