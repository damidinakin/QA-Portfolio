# BUG-004: Booking Status Does Not Update to "Cancelled" After Session Cancellation

## Bug Information

| Field       | Value              |
| ----------- | ------------------ |
| Bug ID      | BUG-004            |
| Module      | Booking Management |
| Severity    | High               |
| Priority    | High               |
| Environment | QA                 |
| Status      | Open               |

---

## Summary

Booking status does not update to **Cancelled** after a session has been successfully cancelled.

---

## Preconditions

* A valid booking exists.
* User has permission to cancel bookings.
* Booking is successfully cancelled.

---

## Steps to Reproduce

1. Login to the application.
2. Navigate to the **Bookings** page.
3. Cancel an existing booking/session.
4. Return to or refresh the **Bookings** page.
5. Observe the booking status.

---

## Expected Result

The booking status should immediately update to **Cancelled** after successful cancellation.

---

## Actual Result

The booking/session is successfully cancelled, but the booking status remains unchanged (e.g., Pending or Approved).

---

## Impact

Users cannot accurately determine the current state of a booking. This may lead to confusion, incorrect actions, and inconsistent booking information across the platform.

---

## Testing Type

* Functional Testing
* Negative Testing
* Regression Testing

---

## Suggested Fix

Ensure that the booking status is updated in the database and reflected consistently across all booking-related views immediately after a cancellation action is completed.
