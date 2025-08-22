# 🧑 Customer Management Module

## 📌 Overview

The **Customer Management** module provides customers with tools to manage their personal profile, delivery preferences, and account settings.  
It also connects with other modules (Orders, Payments, Delivery) to give a personalized and seamless experience.

---

## ✨ Features & Functionalities

### 1. Order History (Reference to Order Management)
- Customers can view their order history (linked from Order Management).
- Includes:
  - Completed, cancelled, and refunded orders
  - Quick re-order option
- *Note: Detailed order processing & tracking is managed by the Order Management Module.*

---

### 2. Current Order Status Tracking (Reference to Order Management)
- Customers can check the live status of active orders (e.g., preparing, out for delivery).
- *Note: The actual status update workflow is part of Order Management.*

---

### 3. Preferred Payment Settings
- Customers can save default payment preferences:
  - Credit/Debit card (e.g., VISA/MasterCard)
  - Cash on Delivery
  - Wallet/loyalty balance (optional, future scope)
- Customers can add, remove, or set a default method.
- Works with the Payment Module during checkout.

---

### 4. Address Management
- Customers can store multiple delivery addresses (Home, Work, etc.).
- Ability to:
  - Add new addresses
  - Update existing addresses
  - Set a default delivery address
- Integrated with Delivery Module for accurate order delivery.

---

### 5. Account Deactivation
- Customers can temporarily or permanently deactivate their account.
- Data handling:
  - Orders in progress must finish before deactivation
  - Customer data may be anonymized after permanent deletion (GDPR compliance optional)

---

### 6. Ratings & Comments
- Customers can provide feedback after an order:
  - Rate food quality, delivery time, and overall experience
  - Add comments for restaurant/delivery person
- Feedback stored for restaurants and visible in Admin Management Module.

---

## 📌 Notes

- Customer Management Module focuses on user profile & personalization.
- It integrates with:
  - **Order Management** → history + tracking
  - **Payment Module** → preferred payment settings
  - **Delivery Module** → address management
 
- Avoids duplication by referencing, not re-