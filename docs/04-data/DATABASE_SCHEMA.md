# co-voiturage.tn — Database Schema v1.0
Status: FINAL • FROZEN

## Tables
users, profiles, verifications, vehicles, trips, trip_stops, bookings, conversations, conversation_participants, messages, reviews, reports, notifications, saved_routes, audit_logs.

## Common conventions
UUID primary keys; `created_at`/`updated_at` UTC timestamps; explicit foreign keys; enum/check constraints where appropriate; soft-delete/status fields only where domain lifecycle requires them.

## Key trip fields
id, driver_id, vehicle_id, origin, destination, departure_at, available_seats, price, currency, meeting_point, notes, status, created_at, updated_at.

## Key booking fields
id, trip_id, passenger_id, seats, status, requested_at, responded_at, cancelled_at, created_at, updated_at.

## Required constraints/indexes
- FK integrity for ownership and participation.
- Positive seats and non-negative price.
- Search indexes on status + departure time + route/location fields.
- Booking indexes on trip/status/passenger.
- Unique protection against duplicate active booking per passenger/trip.
- Transactional capacity enforcement when accepting bookings.

## Data rules
Passwords are never stored plaintext. Sensitive tokens are hashed or otherwise safely stored. Logs must not contain secrets.

## Migration policy
Every schema change is versioned, reviewed, reversible where practical, tested against staging, then applied to production with a documented rollback/recovery plan.
