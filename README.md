# API Test Automation Project (Postman + Newman)

## Overview

This project contains automated API tests for a user management system.
The tests are built using Postman and executed via Newman with Allure reporting.

The collection covers a full user lifecycle, including positive and negative scenarios, with dynamic test data and environment-based configuration.

---

## Tech Stack

* Postman (API test design)
* Newman (CLI execution)
* JavaScript (Postman test scripts)
* Allure Reporter (test reporting)

---

## Test Coverage

### User Flow (End-to-End)

* Create user (`POST /users`)
* Login (`POST /users/login`)
* Get user profile (`GET /users/me`)
* Update user (`PATCH /users/me`)
* Logout (`POST /users/logout`)
* Delete user (`DELETE /users/me`)

### Negative Scenarios

* Login with missing required fields
* Unauthorized access with invalid or expired token

---

## Key Features

* Dynamic test data generation (random users)
* Environment variable management (token, user data)
* Token-based authentication handling
* Validation of response structure, data types, and business logic
* Safe JSON parsing to prevent test crashes
* Cleanup after execution (removal of test data and variables)

---

## Project Structure

```
postman-api-tests/
│
├── config/
│   ├── user-setup.postman_collection.json
│   └── users-contacts-api.postman_environment.json
│
├── allure-results/
├── package.json
├── .gitignore
└── README.md
```

---

## How to Run Tests

### 1. Install dependencies

```bash
npm install
```

### 2. Run tests

```bash
npm test
```

This will:

* Execute the Postman collection via Newman
* Generate Allure results in `allure-results/`

---

## Generate Allure Report

If Allure CLI is installed:

```bash
allure generate ./allure-results --clean -o ./allure-report
allure open ./allure-report
```

---

## Notes

* Environment variables are used to store dynamic data such as:

  * `auth_token`
  * `email`
  * `firstName`
* Test data is generated dynamically to avoid conflicts between runs
* Allure results are cleaned before each execution to ensure accurate reporting

---

## Purpose

This project demonstrates practical API test automation skills, including:

* Writing reusable and maintainable test scripts
* Handling authentication flows
* Covering both positive and negative scenarios
* Running tests via CLI tools
* Integrating reporting for test results

---
