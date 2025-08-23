# 📦 Order Management Module

## 📌 Overview

The **Order Management** module is responsible for handling the full lifecycle of an order — from placement to completion.  
It ensures both customers and restaurants can manage, track, update, and review orders with proper status handling.

This module also maintains an order history and provides a detailed breakdown of each order.

---

## ✨ Features & Functionalities

### 1. Place Order
- Customer confirms cart → proceeds to place order.
- System validates:
  - Cart items availability (with inventory system)
  - Delivery address and payment details
  - Any applied voucher/discount validity
- On success:
  - Order ID is generated
  - Order is stored in the system
  - Confirmation is sent to customer and restaurant

---

### 2. Order Cancellation

**By Customer**
- Allowed only before preparation starts
- Customer can cancel via "Cancel Order" option
- Refund initiated (if payment made)

**By Restaurant**
- If item is unavailable or unforeseen issues occur
- Customer is notified with explanation
- Refund initiated (if payment made)
- System updates order status → “Cancelled”

---

### 3. Order Status Update & Tracking
- System maintains real-time status flow, e.g.:
  - Pending → Confirmed
  - Preparing → Ready for Delivery
  - Out for Delivery → Delivered
  - Cancelled (if applicable)
- Both Customer and Restaurant can view the current order status
- Delivery tracking (integrated with delivery system) shows estimated time of arrival (ETA)

---

### 4. Order History

**Customers:**
- View list of all past orders
- Includes completed, cancelled, and refunded orders
- Option to reorder a past meal

**Restaurants:**
- View incoming, ongoing, and completed orders
- Track cancellation reasons
- Generate performance insights (e.g., frequent orders)

---

### 5. Order Summary
- After placing an order, customer and restaurant can view:
  - Order ID
  - Date & time
  - Items with quantity and price
  - Delivery details (address, contact)
  - Applied discounts
  - Payment method & status
  - Final total

---

### 6. Order Details
- Clicking on an order (in history or active list) opens full details:
  - Item breakdown (with special notes/customizations)
  - Order timeline (placed → confirmed → preparing → delivered)
  - Payment breakdown (subtotal, delivery fee, tax, discount, total)
  - Status tracking (live progress)

---

## 📌 Notes

- This module is tightly linked with:
  - **Cart Management Module** (checkout → place order)
  - **Checkout & Payment Module** (order confirmation requires payment validation)
  - **Order & Delivery Tracking Module** (status updates & tracking)
-- - For prototype stage → can be session-based order logs
-- - For production → requires database persistence with relational schema (orders, order_items, status_updates)
