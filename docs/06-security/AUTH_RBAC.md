# co-voiturage.tn — Auth & RBAC v1.0
Status: FINAL • FROZEN

## Roles
Guest, Passenger, Driver, Moderator, Administrator. Passenger and Driver are capabilities; one account may hold both.

## Authentication
Registration → validation → account creation → password hashing → verification → authenticated state.
Login → rate-limit → credential verification → authenticated state.
Logout invalidates the authenticated state according to the chosen session strategy.

Password reset uses short-lived, single-use tokens and never reveals whether an account exists.
Verification tokens are short-lived and single-use.

## Authorization
Every protected mutation is authorized server-side against both role and resource ownership. Frontend guards are UX only.

## Permission summary
Guest: public search/details.
Passenger: own profile, bookings, eligible messages/reviews/reports.
Driver: own vehicles/trips, booking decisions, eligible messages/reviews/reports.
Moderator: reports, moderation actions, relevant audit information.
Administrator: platform administration and privileged configuration.

## Session security
Use secure transport. For cookie sessions: Secure, HttpOnly and appropriate SameSite policy. Session/token secrets live only in environment/secret storage.
