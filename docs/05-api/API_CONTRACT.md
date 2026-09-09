# co-voiturage.tn — API Contract v1.0
Status: FINAL • FROZEN

Base path: `/api/v1` • HTTPS • JSON

## Auth
POST /auth/register
POST /auth/login
POST /auth/logout
POST /auth/verify
POST /auth/forgot-password
POST /auth/reset-password
GET /auth/me

## Profile
GET /me
PATCH /me
GET /users/:id
PATCH /me/preferences

## Trips
GET /trips
POST /trips
GET /trips/:id
PATCH /trips/:id
POST /trips/:id/cancel
POST /trips/:id/complete

Search: origin, destination, date, timeFrom, timeTo, passengers, minPrice, maxPrice, page, limit, sort.

## Bookings
POST /trips/:id/bookings
GET /bookings
GET /bookings/:id
POST /bookings/:id/accept
POST /bookings/:id/decline
POST /bookings/:id/cancel

## Messaging
GET /conversations
GET /conversations/:id/messages
POST /conversations/:id/messages
POST /conversations/:id/read

## Other resources
GET/POST /reviews
GET/POST /saved-routes
GET /notifications
POST /reports

## Response rules
Success responses use predictable resource envelopes. Errors use stable codes, human-safe messages and `requestId`. Never expose stack traces, SQL errors or internal implementation details.

## Contract rule
Frontend and backend must implement the same documented contract. Any breaking or semantic API change requires an Architecture Change Request before implementation.
