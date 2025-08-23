# 💳 Checkout & Payment Module

## 📌 Overview

The **Checkout & Payment Module** manages the final stage of a customer’s shopping journey.  
It allows the Customer to confirm their order, provide delivery details, and pay securely.  
It coordinates with the Payment Gateway and Inventory System to ensure payment success and item availability.

**Actors:**
- **Customer:** Reviews and confirms order, selects delivery & payment method
- **Payment Gateway:** Validates and processes transactions
- **Inventory System:** Reserves stock before order confirmation

---

## ✨ Features & Functionalities

### 1. Delivery Details (Customer)
- View current delivery location
- Change delivery address:
  - Choose from saved addresses
  - Add a new address (home, office, etc.)
- Delivery options:
  - Standard Delivery (default)
  - Priority Delivery (extra fee)

---

### 2. Order Review (Customer)
- Review cart items with quantity, notes, and applied vouchers/discounts
- View payment summary:
  - Subtotal
  - Delivery fee
  - Service fee
  - Discounts
  - Final total

---

### 3. Payment Method Selection (Customer)
- Available options:
  - Cash on Delivery
  - Credit/Debit Card (saved card or new card)
  - Wallet/Balance

---

### 4. Payment Processing Workflow

**a. Payment Request (System → Payment Gateway)**
- After order confirmation, system sends:
  - Order ID
  - Final total amount
  - Payment method details

**b. Authorization (Payment Gateway)**
- Gateway validates credentials & funds
- Returns approval (transaction ID) or rejection (failure reason)

**c. Inventory Reservation (System → Inventory System)**
- If payment authorized → reserve items in inventory
- If stock unavailable → trigger rollback/refund flow

**d. Capture (Payment Gateway)**
- On successful reservation → capture payment
- Funds transferred to merchant’s account

---

### 5. Order Confirmation (Customer)
- If success:
  - Show confirmation page with:
    - Order ID
    - Estimated delivery time
    - Delivery address
  - Notify via email/SMS/in-app
- If failure:
  - Show reason (invalid card, insufficient funds, stock unavailable)
  - Allow retry with another method

---

### 6. Refunds & Rollbacks
- If payment captured but stock fails → automatic refund requested
- Gateway processes and confirms refund

---

## 📌 Notes

**Security:**
- No sensitive payment data stored
- Only transaction IDs saved
- PCI compliance enforced

**Dependencies:**
- Relies on Cart Module for order items
