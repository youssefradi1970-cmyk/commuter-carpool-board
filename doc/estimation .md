# Commuter Carpool Board — Estimation

**Course:** Agile Software Engineering (SET 312) · **Team:** Group 1

## 1. Method

- **Technique:** Planning Poker. Each member picks a card in private, cards are revealed together, and the team discusses the highest and lowest votes until it agrees.
- **Scale:** Modified Fibonacci: 1, 2, 3, 5, 8.
- **Unit:** Story points measure relative effort, complexity, and uncertainty. They are not hours.
- **Reference story:** **US-07 — View Ride Details = 2 points** (one read-only page, no business rules). Every other story is sized relative to it.
- **Splitting rule:** Any story larger than 8 points is split before it enters a Sprint.
- **Scope of estimate:** Each estimate covers design, implementation, unit tests (TDD), Gherkin scenarios where relevant, review, and the Definition of Done.

## 2. Estimates

| ID | Story | Epic | Points | Rationale |
|----|-------|------|--------|-----------|
| US-01 | Register and Log In | Account | 5 | Registration, validation, authentication, and sessions. Six acceptance criteria. |
| US-02 | Manage Profile | Account | 3 | Simple CRUD plus a phone privacy rule. |
| US-03 | Offer a Ride | Offer a Ride | 5 | Form with several validations (time, seats) and persistence. |
| US-04 | View and Edit My Offered Rides | Offer a Ride | 3 | List and edit, with a seat-count consistency rule. |
| US-05 | See Bookings on My Ride | Offer a Ride | 3 | Query and display with status handling. |
| US-06 | Search Rides by Area and Time | Search and Book | 5 | Filtering on two criteria, exclusions, and ordering. |
| US-07 | View Ride Details | Search and Book | 2 | Reference story: read-only page. |
| US-08 | Request a Seat | Search and Book | 5 | Core business rules: full ride, own ride, duplicates. |
| US-09 | Confirm or Reject a Booking | Search and Book | 5 | Seat counter logic. Must never drop below zero. Notification trigger. |
| US-10 | View My Bookings | Search and Book | 2 | Read-only list with an empty state. |
| US-11 | Reveal Contact Details After Confirmation | Search and Book | 3 | Conditional visibility depending on booking status. |
| US-12 | Cancel a Booking | Cancel and Notifications | 3 | State change plus seat release and time check. |
| US-13 | Cancel a Ride | Cancel and Notifications | 5 | Cascades to all bookings and notifies several users. |
| US-14 | In-App Notifications | Cancel and Notifications | 5 | New data model, event hooks, and unread counter. |
| US-15 | Moderate Rides | Cancel and Notifications | 3 | Admin view, removal cascade, and access control. |
| US-16 | Rate a Ride | Stretch | 5 | New entity, eligibility rules, and average calculation. |
| US-17 | Recurring Weekly Rides | Stretch | 8 | Date generation and per-occurrence state. High uncertainty. |
| US-18 | Preference Filters | Stretch | 3 | Extension of the existing search. |

## 3. Totals

| Scope | Stories | Points |
|-------|---------|--------|
| Account | 2 | 8 |
| Offer a Ride | 3 | 11 |
| Search and Book | 6 | 22 |
| Cancel and Notifications | 4 | 16 |
| **MVP (Must)** | **15** | **57** |
| Stretch (Could) | 3 | 16 |
| **Total backlog** | **18** | **73** |

## 4. Distribution

| Points | Number of stories |
|--------|-------------------|
| 2 | 2 |
| 3 | 7 |
| 5 | 8 |
| 8 | 1 |

## 5. Assumptions and Risks

- Estimates assume the team uses a framework the members already know. A new tool would raise the estimates of US-14 and US-17.
- US-17 (8 points) is the most uncertain story. It is part of the stretch scope for that reason.
- Seat-counter rules (US-08, US-09, US-12, US-13) are the most important to unit-test, so their points include test-writing effort.
- Estimates are re-calibrated at the end of Sprint 1 using the actual velocity.

## 6. Estimation Session Log

| Item | Detail |
|------|--------|
| Date | _fill in_ |
| Participants | _fill in_ |
| Stories re-estimated after discussion | _fill in_ |
