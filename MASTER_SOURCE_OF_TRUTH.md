# co-voiturage.tn — MASTER SOURCE OF TRUTH v1.0
Status: APPROVED BASELINE / ARCHITECTURE FROZEN

## Authority order
1. Product Requirements
2. User Journeys
3. System Architecture
4. Domain Model + Database Schema
5. API Contract
6. Auth/RBAC + Security/Rate Limits
7. Frontend Design System
8. Deployment
9. Implementation code

Code never overrides an approved contract.

## Build ownership
- Lovable: frontend implementation and UI iteration inside approved boundaries.
- Claude/backend agent: backend, database, migrations, API and server-side rules.
- GitHub: source-of-truth repository and change history.

## Change control
Any change to domain entities, database semantics, API contracts, auth model, security model, deployment topology or core user journeys requires an Architecture Change Request before implementation.

## MVP build order
1. Search trips
2. Trip details
3. Authentication/profile
4. Booking request + capacity
5. Driver trip publishing
6. Booking management
7. Messaging/notifications
8. Reviews
9. Reports/moderation
10. Admin basics

## Definition of Done
A vertical slice is done only when UI, API, database behavior, authorization, validation, error states, responsive behavior and tests agree with this Source of Truth.

## Frozen decisions
Modular monolith; API-first REST; PostgreSQL; mobile-first FR/AR/EN with RTL; server-side authorization; provider-agnostic deployment; no MVP microservices/Redis/queues/payment marketplace/AI assistant.
