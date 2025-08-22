# 🎁 Offers Module

## 📌 Overview

The **Offers Module** allows restaurants/admins to create promotions and discounts to attract customers and increase sales.  
Customers can apply these offers during checkout to reduce the total amount.

**Actors:**
- **Admin / Restaurant:** Create and manage offers
- **Customer:** View and apply offers during checkout

---

## ✨ Features

### 1. Offer Creation (Admin/Restaurant)
- Create new offers with details:
  - Offer type (Percentage discount, Flat discount)
  - Validity period (start & end date)
  - Minimum order value (optional)
  - Applicable items/categories (optional)

---

### 2. Offer Availability (Customer)
- Customers can view available offers in the app/website
- Offers visible on:
  - Checkout page
  - Product/restaurant listing (highlighted if applicable)

---

### 3. Offer Application (System → Checkout Module)
- During checkout, customer selects an available offer
- System validates:
  - Offer is still active
  - Order meets conditions (min value, applicable items, etc.)
- Discount applied to order total

---

### 4. Offer Expiration
- Expired offers automatically removed from customer view
- System ensures no expired offers can be applied

---

### 5. Offer History (Admin)
- Admin/restaurant can view:
  - Active offers
  - Expired offers
  - Usage statistics (how many times applied)

---

## 📌 Notes

- Keep offers simple: percentage or flat discounts only
- No need for complex “loyalty points” or “bundle offers”
- Works closely with Checkout and