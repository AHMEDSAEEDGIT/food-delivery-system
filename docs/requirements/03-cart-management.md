
# 🛒 Cart Management Module

## 📌 Overview

The **Add to Cart** module allows customers to select items from a restaurant menu, customize them, and prepare an order before proceeding to checkout.  
It covers item selection, cart persistence, item editing, vouchers, cart management, and payment summary.

---

## ✨ Features & Functionalities

### 1. Item Selection
- User can select an item from the restaurant menu.
- Display item details:
  - Name
  - Description
  - Price
  - (Optional) Image

---

### 2. Quantity & Customization
- User can **increase/decrease quantity** before adding to cart.
- Option to **add special notes/requests** (e.g., "No onions", "Extra cheese").
- Support for **extra toppings/add-ons** with additional cost (if applicable).
- ✅ Update quantities also available directly in cart.

---

### 3. Related Products
- System displays **"You might also like"** items with their price.
- Clicking on a suggested item opens its detail page.

---

### 4. Cart Persistence
- Cart contents are **saved locally** even if the user closes the app.
- On reopening:
  - If cart exists → system asks: **“Continue with existing cart or start a new one?”**

---

### 5. Cart Editing & Management
- User can:
  - Modify items (quantity, notes, add-ons).
  - Remove an item individually.
  - Clear all cart with a single action.
  - Add new items from the restaurant.
- Cart updates **subtotal in real-time**.

---

### 6. Order-Level Notes
- Apart from per-item notes, user can leave a **general note for the whole order** (e.g., "Call when outside").

---

### 7. Voucher & Discounts
- User can submit voucher or promo codes.
- System validates and applies discount.
- Cart updates the payment summary automatically.

---

### 8. Payment Summary
- Cart displays:
  - Subtotal (items only)
  - Delivery fee
  - Service fee (if applicable)
  - **Total amount** (calculated automatically)

---

### 9. Cart Navigation
- **“View Cart”** → shows all selected items with full details.
- **“Add More Items”** → return to restaurant menu.
- **“Back” button** → return to browsing screen.

---

### 10. Checkout Transition
- User proceeds to checkout where they:
  - Confirm delivery location
  - Choose delivery priority (standard vs express)
  - Select payment method (cash, saved card, new card, wallet)
  - Review final payment summary
  - Place the order

---

## 📌 Notes

- This module is tightly linked with:
  - **Browsing Module** (to add items to cart)
  - **Checkout Module** (to place the order)
- Persistence can be implemented via **local storage/session** for prototype stage, and **database storage**