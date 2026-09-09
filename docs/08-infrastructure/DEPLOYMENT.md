# co-voiturage.tn — Deployment Architecture v1.0
Status: FINAL • FROZEN

## Environments
Development, staging, production.

## Initial topology
Internet → HTTPS/reverse proxy → Frontend/API application → PostgreSQL.

Initial hosting may use OVH shared hosting only if the selected backend runtime is supported reliably. Otherwise deploy the backend on OVH VPS. Product/API contracts remain unchanged.

## Domains
co-voiturage.tn — primary web app
www.co-voiturage.tn — canonical redirect
api.co-voiturage.tn — API

## Configuration
Environment variables for database URL, auth/session secrets, allowed origins, email/provider settings, storage and observability. No secrets in Git.

## Release flow
Build → automated tests → staging → smoke tests → database migration → production → health verification.
Every release has a rollback/recovery procedure.

## Backup
GitHub is code/documentation backup. PostgreSQL backups are independent. Restore testing is mandatory before production confidence.

## Scaling
Keep application stateless. Add multiple instances behind a reverse proxy/load balancer when required. Add Redis/queues/search only from measured need.
