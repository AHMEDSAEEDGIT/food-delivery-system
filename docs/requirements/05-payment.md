# 💰 Payment Module

## 📌 Overview
The **Payment Module** is responsible for securely processing customer payments after checkout.  
It ensures that funds are transferred successfully and that the ordered items are reserved in the inventory.  

**Actors**:  
- **Payment Gateway**: External service that validates and processes the monetary transaction.  
- **Inventory System**: Internal or external system that manages product stock and confirms item availability.  

---

## ✨ Features & Functionalities

### 1. Payment Request (System → Payment Gateway)
- After customer confirms checkout:  
  - System prepares a **payment request** including:  
    - Order ID  
    - Total amount (including discounts, delivery fee, service fee)  
    - Selected payment method (card, wallet, etc.)  
- Request is sent securely to **Payment Gateway**.  

### 2. Payment Authorization (Payment Gateway)
- Gateway validates:  
  - Payment credentials (card number, CVV, expiry).  
  - Customer balance or wallet funds.  
- Gateway either:  
  - **Approves payment** → returns a transaction ID and confirmation.  
  - **Rejects payment** → returns failure code and reason.  

### 3. Inventory Reservation (System → Inventory System)
- On successful payment authorization:  
  - System sends **reserve items request** to Inventory System.  
  - Inventory system checks stock availability.  
- If stock is available → items are reserved for this order.  
- If stock is not available →  
  - Payment may be rolled back/refunded.  
  - Customer notified of unavailability.  

### 4. Payment Capture (Payment Gateway)
- Once inventory confirms reservation:  
  - System requests **final capture** of the payment from Payment Gateway.  
  - Gateway charges the customer’s account.  
  - Funds are transferred to merchant’s account.  

### 5. Response Handling
- If payment success:  
  - System marks order as **“Paid & Confirmed”**.  
  - Triggers order preparation workflow.  
- If payment fails (at any stage):  
  - System updates order as **“Payment Failed”**.  
  - Customer is notified and given option to retry with another method.  

### 6. Refunds & Rollbacks
- If payment was captured but inventory failed → system must request **automatic refund**.  
- Refund request sent to gateway with transaction ID.  
- Gateway processes and returns refund confirmation.  


---

## 📌 Notes
- **Actors**:  
  - **Payment Gateway**: External actor for transaction authorization & capture.  
  - **Inventory System**: Internal/external actor ensuring stock availability.  
- **Dependencies**:  
  - Relies on **Checkout Module** for order confirmation.  
  - Supports **Delivery Module** by ensuring order is paid before dispatch.  
- **Security considerations**:  
  - Sensitive payment details never stored in system database.  
  - Only **transaction IDs** from gateway are stored for reference.  
