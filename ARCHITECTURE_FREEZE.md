# co-voiturage.tn — Architecture Freeze v1.0
Status: FROZEN

The v1.0 architecture is approved for implementation.

Frozen areas:
- product MVP boundaries
- core user journeys
- modular-monolith architecture
- domain model
- PostgreSQL data model
- REST API boundary `/api/v1`
- authentication and RBAC
- security/rate-limit baseline
- frontend design system
- deployment/scaling path

Implementation may optimize code structure and UX details without changing these contracts. Architectural changes require explicit change control.
