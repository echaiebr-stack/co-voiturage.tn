# co-voiturage.tn — System Architecture v1.0
Status: FINAL • FROZEN

## Architecture
Modular monolith, API-first, REST/JSON, PostgreSQL authoritative datastore.

Browser → HTTPS → Frontend → /api/v1 → Backend modules → PostgreSQL

## Frontend
React + TypeScript. Mobile-first responsive web application. Runtime must not depend on Lovable.

## Backend
Node.js + TypeScript modular monolith. Modules:
Identity/Auth, Users/Profiles, Vehicles, Trips/Search, Bookings, Messaging, Notifications, Reviews, Reports/Moderation, Administration, Health.

Modules communicate through application/domain boundaries, not direct cross-module database coupling.

## Data
PostgreSQL is the authoritative source for transactional data. UUID identifiers, UTC timestamps, foreign keys, constraints and targeted indexes.

## API
All application APIs live under `/api/v1`. Stable response/error contracts are mandatory.

## Architecture principles
- Simple first; scale from evidence.
- Backend owns business rules and authorization.
- Frontend never becomes the source of truth.
- No runtime dependency on AI builders.
- No microservices, Redis, message broker or search cluster in MVP.

## Scaling path
Single application + PostgreSQL → multiple stateless application instances behind reverse proxy/load balancer → introduce Redis/queue/search only when a measured requirement justifies it.

## Runtime boundaries
External providers (email, maps/geocoding, storage, future identity/payment providers) are adapters behind application interfaces so providers can change without domain rewrites.
