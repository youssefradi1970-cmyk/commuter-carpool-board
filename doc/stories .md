# Commuter Carpool Board — User Stories

**Course:** Agile Software Engineering (SET 312) · **Team:** Group 1
**Product Backlog — Sprint 0 / Week 4**

**MVP total: 57 points (15 User Stories)**
**Stretch total: 16 points (3 User Stories)**
**Backlog total: 73 points (18 User Stories)**

---

## 1. Product Vision

For students and staff who commute to campus, the **Commuter Carpool Board** is a web application that connects drivers with free seats to passengers travelling the same way. Unlike scattered WhatsApp groups, it lets users offer, search, book and cancel rides in one place, and it protects privacy by revealing phone numbers only after a booking is confirmed.

## 2. User Roles

| Role | Description |
|------|-------------|
| **Driver** | Offers rides, and confirms or rejects booking requests. |
| **Passenger** | Searches rides, requests seats and cancels bookings. |
| **Admin** | Moderates rides and users. |
| **User** | Any registered person (Driver or Passenger). |

## 3. Backlog Overview

### Key business rules
1. Free seats can never drop below zero.
2. A driver cannot book their own ride.
3. Phone numbers are visible only after a booking is confirmed.

### Epics and priorities

| Epic | Stories | Points | Priority |
|------|---------|--------|----------|
| Account | US-01, US-02 | 8 | Must (MVP) |
| Offer a Ride | US-03, US-04, US-05 | 11 | Must (MVP) |
| Search and Book | US-06 – US-11 | 22 | Must (MVP) |
| Cancel and Notifications | US-12 – US-15 | 16 | Must (MVP) |
| Stretch | US-16, US-17, US-18 | 16 | Could |
| **Total** | **18** | **73** | |

---

## 4. Epic: Account

### US-01 — Register and Log In (5 pts)

As a **user**, I want to register and log in so that I can offer or book rides under my own identity.

**Acceptance Criteria**

AC1 – Successful Registration
- Given a user is not registered in the system.
- When the user enters a valid name, email, phone number, password, and role, and clicks Register.
- Then the system creates a new account and displays a success confirmation.

AC2 – Duplicate Email
- Given an account already exists with the same email address.
- When the user attempts to register using that email address.
- Then the system rejects the registration and displays an error message indicating that the email is already registered.

AC3 – Required Fields Validation
- Given a user is on the registration page.
- When the user submits the registration form with one or more required fields empty.
- Then the system prevents registration and displays validation messages for the missing fields.

AC4 – Invalid Email Format
- Given a user is on the registration page.
- When the user enters an invalid email format.
- Then the system rejects the input and displays an appropriate validation message.

AC5 – Successful Login
- Given a user has an existing registered account.
- When the user enters the correct email and password and clicks Login.
- Then the system authenticates the user and redirects them to their dashboard.

AC6 – Invalid Credentials
- Given a user is on the login page.
- When the user enters an incorrect email or password.
- Then the system denies access and displays an error message without revealing which field was wrong.

### US-02 — Manage Profile (3 pts)

As a **user**, I want to view and update my profile so that other users see correct information about me.

**Acceptance Criteria**

AC1 – View Profile
- Given a user is logged in.
- When the user opens the profile page.
- Then the system displays their name, email, phone number, and role.

AC2 – Update Profile
- Given a user is on the profile page.
- When the user changes their name or phone number and clicks Save.
- Then the system stores the changes and displays a success confirmation.

AC3 – Phone Number Privacy
- Given another user views this user's public profile.
- When the viewer has no confirmed booking with this user.
- Then the system does not display the phone number.

---

## 5. Epic: Offer a Ride

### US-03 — Offer a Ride (5 pts)

As a **driver**, I want to offer a ride with an area, departure time and number of free seats so that passengers can find and book it.

**Acceptance Criteria**

AC1 – Successful Offer
- Given a driver is logged in.
- When the driver enters a valid area, departure time, and number of free seats, and clicks Post Ride.
- Then the system creates the ride and displays it in the driver's list of offered rides.

AC2 – Required Fields Validation
- Given a driver is on the Offer Ride page.
- When the driver submits the form with one or more required fields empty.
- Then the system prevents the ride from being created and displays validation messages.

AC3 – Departure Time in the Past
- Given a driver is on the Offer Ride page.
- When the driver enters a departure time that is in the past.
- Then the system rejects the ride and displays an error message.

AC4 – Invalid Seat Count
- Given a driver is on the Offer Ride page.
- When the driver enters zero or a negative number of free seats.
- Then the system rejects the ride and displays an error message.

### US-04 — View and Edit My Offered Rides (3 pts)

As a **driver**, I want to view and edit the rides I have offered so that I can keep the details accurate.

**Acceptance Criteria**

AC1 – View Offered Rides
- Given a driver has offered one or more rides.
- When the driver opens "My Rides".
- Then the system lists their rides with area, departure time, free seats, and status.

AC2 – Edit Ride
- Given a driver is viewing one of their upcoming rides.
- When the driver changes the departure time or area and clicks Save.
- Then the system updates the ride and notifies passengers with confirmed bookings.

AC3 – Seats Cannot Drop Below Confirmed Bookings
- Given a ride has confirmed bookings.
- When the driver reduces the total seats below the number of confirmed bookings.
- Then the system rejects the change and displays an error message.

### US-05 — See Bookings on My Ride (3 pts)

As a **driver**, I want to see who has booked seats on my ride so that I know whom to pick up.

**Acceptance Criteria**

AC1 – List Bookings
- Given a driver has a ride with booking requests.
- When the driver opens the ride's details.
- Then the system lists each passenger's name and booking status (pending, confirmed, rejected, cancelled).

AC2 – Pending Requests Highlighted
- Given a ride has pending booking requests.
- When the driver opens the ride's details.
- Then the system highlights the pending requests as requiring action.

AC3 – Contact Details Hidden for Pending Requests
- Given a booking is still pending.
- When the driver views the booking.
- Then the system does not display the passenger's phone number.

---

## 6. Epic: Search and Book

### US-06 — Search Rides by Area and Time (5 pts)

As a **passenger**, I want to search rides by area and arrival or departure time so that I can find one that fits my schedule.

**Acceptance Criteria**

AC1 – Search by Area and Time
- Given rides exist in the system.
- When the passenger enters an area and a time window and clicks Search.
- Then the system displays only rides that match both criteria.

AC2 – No Results
- Given no ride matches the search criteria.
- When the passenger searches.
- Then the system displays a "no rides found" message.

AC3 – Unavailable Rides Excluded
- Given a ride is full, cancelled, or already departed.
- When the passenger searches.
- Then the system does not include that ride in the results.

AC4 – Result Ordering
- Given several rides match the search criteria.
- When the results are displayed.
- Then the system orders them by departure time, earliest first.

### US-07 — View Ride Details (2 pts)

As a **passenger**, I want to open a ride to see its details so that I can decide whether to book it.

**Acceptance Criteria**

AC1 – Display Details
- Given a passenger selects a ride from the search results.
- When the ride details page opens.
- Then the system displays the area, departure time, free seats, and the driver's name.

AC2 – Phone Number Hidden
- Given a passenger has no confirmed booking on the ride.
- When the passenger views the details.
- Then the system does not display the driver's phone number.

### US-08 — Request a Seat (5 pts)

As a **passenger**, I want to request a seat on a ride so that the driver can confirm it for me.

**Acceptance Criteria**

AC1 – Successful Request
- Given a ride has at least one free seat.
- When the passenger clicks Request Seat.
- Then the system creates a booking with status "pending" and notifies the driver.

AC2 – No Free Seats
- Given a ride has zero free seats.
- When the passenger attempts to request a seat.
- Then the system rejects the request and displays a "ride is full" message.

AC3 – Own Ride
- Given a driver views their own ride.
- When the driver attempts to book a seat on it.
- Then the system rejects the action and displays an error message.

AC4 – Duplicate Request
- Given a passenger already has an active booking on the ride.
- When the passenger requests another seat on the same ride.
- Then the system rejects the request and displays an error message.

### US-09 — Confirm or Reject a Booking (5 pts)

As a **driver**, I want to confirm or reject booking requests so that I control who rides with me.

**Acceptance Criteria**

AC1 – Confirm Booking
- Given a booking is pending and the ride has at least one free seat.
- When the driver clicks Confirm.
- Then the system sets the booking to "confirmed", reduces the free seats by one, and notifies the passenger.

AC2 – Reject Booking
- Given a booking is pending.
- When the driver clicks Reject.
- Then the system sets the booking to "rejected", leaves the free seats unchanged, and notifies the passenger.

AC3 – No Seats Left (Seat Rule)
- Given a ride has zero free seats.
- When the driver attempts to confirm another pending booking.
- Then the system rejects the confirmation and free seats remain at zero.

### US-10 — View My Bookings (2 pts)

As a **passenger**, I want to see all my bookings so that I can track their status.

**Acceptance Criteria**

AC1 – List Bookings
- Given a passenger has made bookings.
- When the passenger opens "My Bookings".
- Then the system lists each booking with ride details and status.

AC2 – Empty State
- Given a passenger has no bookings.
- When the passenger opens "My Bookings".
- Then the system displays a message that no bookings exist yet.

### US-11 — Reveal Contact Details After Confirmation (3 pts)

As a **passenger**, I want to see the driver's phone number once my booking is confirmed so that we can coordinate the pickup.

**Acceptance Criteria**

AC1 – Visible After Confirmation
- Given a booking has status "confirmed".
- When the passenger or the driver views the booking.
- Then the system displays the other party's phone number.

AC2 – Hidden Before Confirmation
- Given a booking is pending, rejected, or cancelled.
- When either party views the booking.
- Then the system does not display the other party's phone number.

---

## 7. Epic: Cancel and Notifications

### US-12 — Cancel a Booking (3 pts)

As a **passenger**, I want to cancel my booking so that the seat becomes available to others.

**Acceptance Criteria**

AC1 – Cancel Confirmed Booking
- Given a passenger has a confirmed booking on an upcoming ride.
- When the passenger clicks Cancel.
- Then the system sets the booking to "cancelled", increases the free seats by one, and notifies the driver.

AC2 – Cancel Pending Booking
- Given a passenger has a pending booking.
- When the passenger clicks Cancel.
- Then the system sets the booking to "cancelled" without changing the free seats.

AC3 – Ride Already Departed
- Given the ride's departure time has passed.
- When the passenger attempts to cancel the booking.
- Then the system rejects the cancellation and displays an error message.

### US-13 — Cancel a Ride (5 pts)

As a **driver**, I want to cancel a ride so that passengers know it will not take place.

**Acceptance Criteria**

AC1 – Successful Cancellation
- Given a driver has an upcoming ride.
- When the driver clicks Cancel Ride and confirms.
- Then the system marks the ride as "cancelled" and removes it from search results.

AC2 – Bookings Cancelled and Passengers Notified
- Given the ride has pending or confirmed bookings.
- When the driver cancels the ride.
- Then the system cancels all its bookings and notifies every affected passenger.

AC3 – Past Ride
- Given the ride's departure time has passed.
- When the driver attempts to cancel it.
- Then the system rejects the action and displays an error message.

### US-14 — In-App Notifications (5 pts)

As a **user**, I want to receive in-app notifications about my rides and bookings so that I stay informed of changes.

**Acceptance Criteria**

AC1 – Notification Created
- Given a booking is requested, confirmed, rejected, or cancelled, or a ride is edited or cancelled.
- When the event occurs.
- Then the system creates a notification for each affected user.

AC2 – Unread Counter
- Given a user has unread notifications.
- When the user opens any page.
- Then the system displays the number of unread notifications.

AC3 – Mark as Read
- Given a user opens the notifications page.
- When the user views or dismisses a notification.
- Then the system marks it as read and updates the unread counter.

### US-15 — Moderate Rides (3 pts)

As an **admin**, I want to remove inappropriate rides so that the platform stays safe and trustworthy.

**Acceptance Criteria**

AC1 – View All Rides
- Given an admin is logged in.
- When the admin opens the moderation page.
- Then the system lists all rides regardless of the driver.

AC2 – Remove Ride
- Given an admin selects a ride.
- When the admin clicks Remove and confirms.
- Then the system removes the ride, cancels its bookings, and notifies the driver and the passengers.

AC3 – Access Control
- Given a user who is not an admin.
- When the user attempts to open the moderation page.
- Then the system denies access.

---

## 8. Epic: Stretch

### US-16 — Rate a Ride (5 pts)

As a **passenger**, I want to rate my driver after a ride so that other users can judge reliability.

**Acceptance Criteria**

AC1 – Submit Rating
- Given a passenger had a confirmed booking on a ride that has departed.
- When the passenger submits a rating from 1 to 5.
- Then the system stores the rating and updates the driver's average.

AC2 – Eligibility
- Given a passenger has no confirmed booking on the ride.
- When the passenger attempts to rate the driver.
- Then the system rejects the rating.

AC3 – One Rating per Ride
- Given a passenger has already rated a ride.
- When the passenger tries to rate it again.
- Then the system rejects the second rating.

### US-17 — Recurring Weekly Rides (8 pts)

As a **driver**, I want to offer a ride that repeats weekly so that I do not have to post it every week.

**Acceptance Criteria**

AC1 – Create Recurring Ride
- Given a driver is on the Offer Ride page.
- When the driver selects weekdays and an end date and clicks Post Ride.
- Then the system creates one ride for each selected date.

AC2 – Cancel Single Occurrence
- Given a recurring ride exists.
- When the driver cancels one occurrence.
- Then the system cancels only that occurrence and leaves the others unchanged.

AC3 – Seats Reset per Occurrence
- Given a recurring ride has several occurrences.
- When passengers book one occurrence.
- Then the system updates the free seats of that occurrence only.

### US-18 — Preference Filters (3 pts)

As a **passenger**, I want to filter rides by preferences so that I find rides that suit me.

**Acceptance Criteria**

AC1 – Apply Filter
- Given search results are displayed.
- When the passenger selects a preference filter (for example, same-gender rides).
- Then the system shows only rides that satisfy the filter.

AC2 – Clear Filter
- Given a filter is applied.
- When the passenger clears it.
- Then the system shows all matching rides again.
