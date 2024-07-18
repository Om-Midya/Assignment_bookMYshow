# Movie-Ticket-Booking-WebApp

## Bugs

- [x] Seat Booking Matrix is on the Left
- [x] Home Button is not redirecting to the Home page
- [x] Role-Based Access Control
- [x] Booked Seats Being Considered for Booking
- [x] Users can book from previous dates
- [ ] Email Not Comming
- [ ] OTP Not Comming
- [ ] Admin not able to see its booking
- [ ] When a new user logged in, The home page still shows the details of the previous User until we refresh the page. Probably this is a rerendering Issue.

## Bug 1: Moving the Seat Booking Matrix to the Middle.

## Bug 2: Added Hyperlinks to Home & BookMyShow Component

## Bug 3: Role-Based Access Control

### Problem:

Previously, users were able to access the `/admin` and `/partner` panels regardless of their roles. Similarly, partners could access the `/admin` panel, leading to unauthorized access to restricted areas of the application.

### Expected Behavior

Users should only be able to access panels that correspond to their roles:

- Admins should have access to the `/admin` panel.
- Partners should have access to the `/partner` panel.
- Unauthorized users should not have access to any restricted panels and should be redirected appropriately.

### Solution:

Implemented a role-based access control system to ensure that users can only access panels for which they have the appropriate roles. Unauthorized users attempting to access restricted panels will be redirected to the Unauthorized page (`/unauthorised`).

## Bug 4: Booked Seats Being Considered for Booking

### Issue Description

When a user clicks on a seat that has already been booked, the "Pay Now" button appears, and the amount of the booked seat is included in the total price and selected seats. This should not happen, as booked seats should not be available for selection.

### Expected Behavior

Users should not be able to select seats that have already been booked. If a user attempts to select a booked seat, an error message should be displayed, and the "Pay Now" button should be disabled. The user should only be able to select unbooked seats for booking.

### Solution

Implemented a check to ensure that only unbooked seats can be selected. If a user attempts to select a booked seat, an error message will be displayed, and the "Pay Now" button will be disabled. Once the user selects only unbooked seats, the "Pay Now" button will be enabled, and the user can proceed with the booking.

## Bug 5: Date Selection in Booking System

### Problem:

Users are able to book shows for past dates, which is not a valid use case. The system should restrict users from selecting past dates in the date picker input to ensure that all bookings are for upcoming shows only.

### Expected Behavior

Users should only be able to book shows for today or future dates. The system should restrict the selection of past dates in the date picker input, ensuring that all bookings are relevant and valid for upcoming shows only.

### Solution:

Modified the date selection input to disable all past dates. This was achieved by setting the `min` attribute of the date input field to the current date. Now, users cannot select a date earlier than the current day, ensuring that all bookings are for valid showtimes.
