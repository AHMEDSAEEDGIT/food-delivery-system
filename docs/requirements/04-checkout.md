# 💳 Checkout Module

## 📌 Overview
The **Checkout Module** finalizes the customer’s shopping process by confirming the order, selecting delivery details, and processing payments.  
It involves two actors:  
- **Customer**: Reviews order, provides delivery & payment details.  
- **Payment Gateway**: Handles payment authorization and processing.  

---

## ✨ Features & Functionalities

### 1. Delivery Details (Customer)
- View current delivery location.  
- Option to **change delivery address**:  
  - Select from saved addresses.  
  - Add a new address (home, office, etc.).  
- Delivery options:  
  - **Standard Delivery** (default).  
  - **Priority Delivery** (e.g., + extra fee for faster delivery).  

### 2. Order Review (Customer)
- Review all cart items with quantity and notes.  
- See **general order note** (if provided).  
- Check applied vouchers/discounts.  
- Payment summary includes:  
  - Subtotal  
  - Delivery fee  
  - Service fee  
  - Discounts  
  - Final total amount  

### 3. Payment Method Selection (Customer)
- Choose a payment method:  
  - **Cash on Delivery**  
  - **Credit/Debit Card** (saved card or add new card).  
  - **Wallet/Balance** (if available in the system).  

### 4. Payment Processing (Payment Gateway)
- If card/wallet selected → system redirects/communicates with **Payment Gateway**.  
- Gateway responsibilities:  
  - Validate payment details (card number, CVV, expiry).  
  - Authorize transaction.  
  - Return **success/failure response**.  

### 5. Order Confirmation (Customer)
- If payment successful → system generates:  
  - Order confirmation screen with:  
    - Order ID  
    - Estimated delivery time  
    - Delivery address  
  - Notification (email/SMS/in-app).  
- If payment fails → system displays:  
  - Failure reason (invalid card, insufficient funds, gateway error).  
  - Option to retry with another payment method.  

### 6. Navigation
- **Back button** → return to cart without confirming order.  
- **Place Order button** → confirm and initiate payment process.  

---

## 📌 Notes
- **Actors**:  
  - **Customer**: Interacts with the system UI to finalize order.  
  - **Payment Gateway**: External service for handling card/wallet payments.  
- **Security considerations**:  
  - Sensitive payment details must not be stored directly (PCI compliance).  
  - Use encrypted communication with payment gateway.  
- **Dependencies**:  
  - Relies on **Add to Cart Module** for order details.  
  - Relies on **Browsing Module** indirectly (to select items).  
