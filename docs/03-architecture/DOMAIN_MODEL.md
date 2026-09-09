# co-voiturage.tn — Domain Model v1.0
Status: FINAL • FROZEN

## Core aggregates
- User: identity, account state, profile, preferences.
- Vehicle: driver-owned vehicle data.
- Trip: route, departure, seats, price, meeting point, vehicle, lifecycle.
- Booking: passenger request/reservation and lifecycle.
- Conversation: trip-scoped participants and messages.
- Review: post-trip reputation record.
- Report: trust/safety case and moderation state.
- Notification: user-facing event delivery record.
- AuditLog: sensitive operational action record.

## Relationships
User 1—1 Profile; User 1—N Vehicles; User 1—N Trips; Trip 1—N Bookings; User 1—N Bookings; Trip 1—N Conversations; Conversation 1—N Messages; Trip/Booking → eligible Reviews; User → Notifications; sensitive mutations → AuditLog.

## Invariants
1. Driver owns the trip and selected vehicle.
2. Driver cannot book own trip.
3. Accepted seats never exceed capacity.
4. Booking transitions are explicit and authorized.
5. Trip lifecycle transitions are explicit and authorized.
6. Duplicate booking requests are safely rejected/idempotently handled.
7. Review eligibility is derived from completed participation.
8. Users cannot review themselves.
