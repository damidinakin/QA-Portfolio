# BUG-005: User Can Cancel an Already Cancelled Booking

## Bug Information

| Field       | Value              |
| ----------- | ------------------ |
| Bug ID      | BUG-005            |
| Module      | Booking Management |
| Severity    | High               |
| Priority    | High               |
| Environment | QA                 |
| Status      | Open               |

---

## Summary

The system allows a user to cancel a booking that has already been cancelled.

---

## Preconditions

* A booking exists with a status of Cancelled.
* User has access to the Bookings page.

---

## Steps to Reproduce

1. Login to the application.
2. Navigate to the Bookings page.
3. Open a booking with a status of Cancelled.
4. Attempt to cancel the booking again.

---

## Expected Result

The system should prevent repeated cancellation of an already cancelled booking and display an appropriate validation message.

---

## Actual Result

The user is able to cancel an already cancelled booking. The system does not prevent repeated cancellation.

---

## Impact

Repeated cancellation actions may lead to data inconsistencies, duplicate notifications, inaccurate audit logs, and user confusion.

---

## Testing Type

* Negative Testing
* Functional Testing
* Business Logic Validation

---

## Suggested Fix

Disable or hide the Cancel action for bookings with a status of Cancelled, or display a validation message informing the user that the booking has already been cancelled.
