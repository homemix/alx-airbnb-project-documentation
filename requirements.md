# Airbnb Clone Backend – Feature Summary

## 1.  User Authentication
Handles user registration, login, and profile access.
- **Endpoints**:
  - `POST /api/auth/register/` – Create account
  - `POST /api/auth/login/` – Authenticate user
  - `GET /api/auth/profile/` – View profile (auth required)
- **Validation**: Unique email, secure password, valid input
- **Performance**: Fast response (<300ms), rate-limited

---

## 2. Property Management
Enables hosts to list, update, and manage properties, and guests to browse available listings.
- **Endpoints**:
  - `POST /api/properties/` – Add new property
  - `GET /api/properties/` – View all listings
  - `PUT /api/properties/:id/` – Update property
  - `DELETE /api/properties/:id/` – Delete property
- **Validation**: Title, location required; price > 0; valid image URLs
- **Performance**: Retrieval under 500ms; host listing limit

---

## 3.  Booking System
Lets guests book available properties and manage their bookings.
- **Endpoints**:
  - `POST /api/bookings/` – Make a booking
  - `GET /api/bookings/my/` – View user's bookings
  - `DELETE /api/bookings/:id/` – Cancel booking
- **Validation**: No date overlap, check-in < check-out, one active booking per property/date
- **Performance**: Availability check <200ms; concurrency-safe

---

 **Security Note**: All endpoints are protected by JWT-based authentication.

 **Design Goal**: Scalable REST API, consistent naming, and validation logic for a real-world booking system.
