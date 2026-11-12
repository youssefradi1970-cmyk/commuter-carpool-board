# Commuter Carpool Board — Forecast

**Course:** Agile Software Engineering (SET 312) · **Team:** Group 1

## 1. Assumptions

| Item | Value |
|------|-------|
| Sprint length | 1 week |
| Sprints | Sprint 1 – Sprint 4 (Weeks 8–11), after Sprint 0 (setup) |
| MVP deadline | End of Sprint 3 (Week 10) |
| MVP size | 57 points (15 stories) |
| Stretch size | 16 points (3 stories) |
| Total backlog | 73 points (18 stories) |

Velocity is the number of points the team completes per Sprint. No Sprint history exists yet, so three scenarios are used. The forecast is re-calculated after each Sprint from the average of the last completed Sprints.

| Scenario | Velocity (points per Sprint) |
|----------|------------------------------|
| Pessimistic | 15 |
| Likely | 19 |
| Optimistic | 22 |

## 2. Forecast

Sprints needed = points ÷ velocity, rounded up.

| Goal | Points | Pessimistic | Likely | Optimistic |
|------|--------|-------------|--------|------------|
| MVP | 57 | 4 Sprints | 3 Sprints | 3 Sprints |
| Full backlog (MVP + Stretch) | 73 | 5 Sprints | 4 Sprints | 4 Sprints |

## 3. Sprint Plan (Likely Scenario)

| Sprint | Week | Goal | Stories | Points |
|--------|------|------|---------|--------|
| 1 | 8 | Walking skeleton: register, offer, search, view a ride end to end. CI pipeline running | US-01, US-03, US-06, US-07 | 17 |
| 2 | 9 | Booking flow and driver tools. Deployed with ≥ 5 Gherkin scenarios | US-08, US-09, US-02, US-04, US-05 | 19 |
| 3 | 10 | **MVP complete**: cancellations, contact reveal, notifications, moderation. User feedback collected | US-10, US-11, US-12, US-13, US-14, US-15 | 21 |
| 4 | 11 | Improve from feedback, plus stretch stories | US-16, US-18, US-17 | 16 |

**Cumulative progress**

| After Sprint | Points done | % of MVP | % of total |
|--------------|-------------|----------|------------|
| 1 | 17 | 30% | 23% |
| 2 | 36 | 63% | 49% |
| 3 | 57 | 100% | 78% |
| 4 | 73 | n/a | 100% |

## 4. MVP Line

The MVP line sits after **US-15**. Everything above it must work in the Week 12 demo: account, offer a ride, search and book, and cancel with notifications. US-16, US-17 and US-18 fall below the line and are delivered only if time allows.

## 5. Risks and Mitigation

| Risk | Impact | Mitigation |
|------|--------|------------|
| Velocity is below 19 | MVP slips past Sprint 3 | Re-forecast after Sprint 1. Move US-15 (3 pts) and US-14 (5 pts) to Sprint 4, using the improvement Sprint as a buffer. |
| Sprint 3 is heavy (21 pts) | Overload at the deadline | Pull small stories (US-10, US-11) forward into Sprint 2 if capacity allows. |
| Seat-counter bugs | Breaks the key rule | Write unit tests first (TDD) for US-08, US-09, US-12, and US-13. |
| Technical uncertainty in US-17 | Overrun | Keep it last in Sprint 4. Drop it first if behind. |
| Member availability (exams, other courses) | Lower velocity | Plan Sprints on actual capacity at each Sprint Planning. |

## 6. Re-Forecasting Log

| After Sprint | Actual velocity | Average velocity | Updated MVP forecast |
|--------------|-----------------|------------------|----------------------|
| 1 | _fill in_ | _fill in_ | _fill in_ |
| 2 | _fill in_ | _fill in_ | _fill in_ |
| 3 | _fill in_ | _fill in_ | _fill in_ |
