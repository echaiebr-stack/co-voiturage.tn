# co-voiturage.tn — Security & Rate Limits v1.0
Status: FINAL • FROZEN

## Security baseline
- HTTPS everywhere in production.
- Strong password hashing; never plaintext.
- Strict input/schema validation.
- Parameterized queries/ORM.
- CORS allowlist.
- Secure headers.
- CSRF protection where cookie authentication requires it.
- Secrets excluded from GitHub and logs.
- Uploads, messages and external content treated as untrusted.
- Admin/moderation actions audited.
- Dependencies and production configuration reviewed before release.

## Rate-limit classes
### Strict
Login, registration, verification, password recovery/reset, report submission.

### Mutation
Trip creation/update, booking creation/decision, messaging, reviews, profile-sensitive mutations.

### Public read
Trip search and public trip/profile reads: higher limits, still protected against abuse.

### Health
Minimal limit; endpoint must remain lightweight.

## Enforcement
Return HTTP 429 with stable error code and `Retry-After`. Clients must not perform infinite retries.

For one application instance, in-process limiting is acceptable initially. For multi-instance deployment, use shared rate-limit state such as Redis only when required.

## Observability
Request IDs, structured logs, errors, latency, health/readiness, rate-limit events. Never log passwords, tokens, secrets or unnecessary personal data.
