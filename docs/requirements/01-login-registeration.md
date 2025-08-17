# 🔐 User Registration & Authentication Module

## 📌 Overview
The **User Registration & Authentication Module** allows customers to securely create accounts, log in, and manage their sessions.  
It ensures that only authenticated users can access certain features (checkout, order history, tracking, etc.).  

**Actors**:  
- **Customer**: Registers, logs in, and manages their account.  
- **System**: Handles authentication, session management, and security.  

---

## ✨ Features & Functionalities

### 1. User Registration
- Customer can register with:
  - Full name, email, password, phone number, address.  
  - Optional: social login (Google, Facebook, etc.).  
- System validates input (email format, password strength, unique email/phone).  
- Email/phone verification (OTP or confirmation link).  

### 2. User Login
- Login with:
  - Email/username + password.  
  - Or via social login provider (if supported).  
- System verifies credentials securely (hashed passwords, salted storage).  
- Invalid attempts trigger security measures (lockout, CAPTCHA, etc.).  

### 3. Session Management
- Successful login creates a session (via cookie, JWT token, etc.).  
- User stays logged in until logout or session timeout.  
- Secure logout clears session and tokens.  

### 4. Password Management
- Customers can:
  - Change password from profile.  
  - Reset forgotten password (via email/OTP link).  
- Enforce strong password policies.  

### 5. Role & Permission Management
- **Customer** role: Access browsing, cart, checkout, payment, and delivery tracking.  
- **Admin/Support** role (future expansion): Manage products, view orders, handle customer issues.  
- Access control ensures customers cannot access admin features.  

### 6. Security Features
- Passwords encrypted and never stored in plain text.  
- Brute-force protection (account lockout after failed attempts).  
- Optional two-factor authentication (2FA).  
- Audit logging for login attempts.  


---

## 📌 Notes
- **Dependencies**:  
  - This module is required for most other modules (Checkout, Payment, Delivery Tracking).  
- **Security considerations**:  
  - Follow OWASP best practices for authentication.  
  - Ensure HTTPS for all authentication flows.  
  - Store tokens securely and avoid long-lived sessions.  
