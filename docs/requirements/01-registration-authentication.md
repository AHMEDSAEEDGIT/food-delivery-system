# 🔐 User Registration & Authentication Module

## 📌 Overview

The User Registration & Authentication Module is responsible for creating and managing user accounts, handling secure login, and enforcing access control.

**Actors:**
- **Customer:** Creates account, logs in, places orders, and manages their profile.
- **Admin:** Manages restaurants, menu items, customer accounts, and system settings.

This module ensures secure access and prevents unauthorized users from reaching restricted areas.

---

## ✨ Features & Functionalities

### 1. User Registration (Customer & Admin)

**Customer Registration**
- Register with full name, email, phone number, password, and delivery address.
- Optional: social login (Google, Facebook, etc.).
- Input validation: email format, password strength, unique email/phone.
- Email/OTP verification before activation.

**Admin Registration**
- Admins are created by the system super-admin (not public signup).
- Admins receive activation links via email.

---

### 2. Login

**Customers**
- Login with email/username + password.
- Optionally via social login provider.
- Failed login attempts trigger CAPTCHA or lockout.

**Admins**
- Login with email + password.
- Restricted access to the Admin Dashboard only.
- Enforced strong password + optional Two-Factor Authentication (2FA).

---

### 3. Session Management

- Sessions created via JWT tokens / secure cookies.
- Session timeout for inactivity.
- Logout clears session and invalidates tokens.
- Support for “Remember Me” login (configurable).

---

### 4. Password Management

- Change Password (from profile).
- Forgot Password / Reset (via email or OTP link).
- Password policies enforced: minimum length, complexity, no reuse of last N passwords.

---

### 5. Role & Permission Management

**Customer:**
- Browse restaurants, view menus, manage cart, place orders, track orders.

**Admin:**
- Add/manage restaurants.
- Add/manage menu items.
- Approve/decline orders.
- Manage offers & promotions.
- Enable/disable customer accounts.

Access control ensures separation of responsibilities (Customers cannot access Admin functions).

---

### 6. Security Features

- Passwords stored securely (salted + hashed).
- Protection against brute-force attacks (account lockouts).
- Optional Two-Factor Authentication (2FA) for Admins.
- Audit logging: login attempts, failed logins, account lockouts.
- HTTPS enforced for all login/registration flows.

---

## 📌 Notes

- **Dependencies:** This module is required for all others (Order Management, Payment, Cart, Dashboard).
- **Security Considerations:** Must follow OWASP best practices for authentication and authorization.
