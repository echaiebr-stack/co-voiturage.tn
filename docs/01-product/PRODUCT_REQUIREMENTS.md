# co-voiturage.tn — Product Requirements v1.0
Status: FINAL • MVP

## Vision
A trusted, premium, mobile-first Tunisian carpooling marketplace connecting drivers and passengers around real journeys.

## MVP users
- Guest: search and view public trips.
- Passenger: profile, search, booking, messaging, reviews, reports.
- Driver: profile, vehicle, publish trips, manage bookings, messaging, reviews, reports.
- Moderator/Admin: trust, moderation and platform operations.
A user may be both driver and passenger.

## MVP capabilities
1. Authentication and profile
2. Trip creation, publication, search and details
3. Booking request, accept, decline and cancellation
4. Seat/capacity enforcement
5. Driver vehicle information
6. Trip-scoped messaging
7. Notifications
8. Reviews after eligible completed trips
9. Reporting and moderation
10. Basic administration and audit logging

## Marketplace loop
Publish → discover → request → accept → communicate → travel → complete → review → return.

## Core product rules
- Only published/searchable trips appear in public search.
- A driver cannot book their own trip.
- Accepted seats can never exceed available capacity.
- Booking state transitions are server-controlled.
- Reviews require an eligible completed trip.
- Trust/safety actions are server-authorized and audited.

## Localization
French, Arabic and English. Arabic is fully RTL-capable from the foundation.

## Explicitly out of MVP
Online payment marketplace, commission engine, native mobile apps, microservices, AI assistant, advanced recommendations, multi-country expansion, complex fleet management.

## Success metrics
Search success, search-to-booking conversion, completed trips, repeat users, active drivers/passengers, cancellation/report rate, time-to-publish and time-to-book.
