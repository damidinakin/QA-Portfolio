# API-BUG-001: User Created Despite Missing Required Fields

## Bug Information

| Field       | Value               |
| ----------- | ------------------- |
| Bug ID      | API-BUG-001         |
| Module      | User Management API |
| Severity    | High                |
| Priority    | High                |
| Environment | QA                  |
| Status      | Open                |

---

## Summary

The API creates a user successfully even when required fields are missing.

---

## Steps to Reproduce

1. Send a POST request to /users.
2. Populate only one required field.
3. Leave other required fields empty.
4. Send the request.

---

## Expected Result

The API should reject the request and return a validation error such as:

* Status Code 400 Bad Request

No user should be created.

---

## Actual Result

The API returned:

* Status Code 201 Created
* New user ID generated

The request was accepted despite missing required fields.

---

## Impact

Invalid or incomplete user records may be created, leading to poor data quality and business rule violations.

---

## Testing Type

* Negative Testing
* Validation Testing
* API Testing
