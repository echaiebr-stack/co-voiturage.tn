# co-voiturage.tn

> Premium carpooling platform for Tunisia.

co-voiturage.tn is a modern, trusted and scalable carpooling platform designed for passengers and drivers in Tunisia.

The platform is being rebuilt from scratch with a production-oriented architecture, premium UX/UI and an API-first backend.

---

## Project Status

**Current Phase:** Implementation

**Architecture Version:** v1.0

**Architecture Status:** Frozen for MVP

**Development Status:** Starting

---

## Product Vision

Build the trusted digital infrastructure for carpooling in Tunisia.

The platform aims to make shared mobility:

- Simple
- Safe
- Trusted
- Affordable
- Convenient
- Mobile-first
- Scalable

---

## Core Users

### Passenger

Passengers can:

- Search for trips
- View trip details
- Review driver information
- Request a booking
- Manage bookings
- Communicate with drivers
- Leave reviews

### Driver

Drivers can:

- Create a profile
- Add vehicles
- Publish trips
- Manage available seats
- Receive booking requests
- Accept or reject passengers
- Communicate with passengers
- Manage their trips

### Administration

Administrators can:

- Manage users
- Moderate trips
- Handle reports
- Manage platform activity
- Monitor operational metrics
- Apply moderation actions

---

## MVP Architecture

```text
                         co-voiturage.tn
                                |
                                v
                         React Frontend
                                |
                              HTTPS
                                |
                                v
                    Node.js / TypeScript API
                                |
             +------------------+------------------+
             |                  |                  |
             v                  v                  v
           Auth               Trips             Bookings
             |                  |                  |
             +------------------+------------------+
                                |
                                v
                           PostgreSQL