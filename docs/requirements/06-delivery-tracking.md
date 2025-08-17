# 🛵 Delivery & Tracking Module

## 📌 Overview
The **Delivery & Tracking Module** ensures that customer orders are shipped from inventory to the delivery partner and tracked until they reach the customer.  

It connects the **Inventory System**, **Delivery System**, and **Customer** to provide real-time updates on order status and location.  

**Actors**:  
- **Delivery System / Delivery Partner**: Manages shipping, assigns delivery staff, and provides tracking updates.  
- **Inventory System**: Confirms stock dispatch and hands over order to delivery system.  
- **Customer**: Views and tracks delivery progress until completion.  

---

## ✨ Features & Functionalities

### 1. Order Dispatch (Inventory → Delivery System)
- After successful payment and stock reservation:  
  - Inventory system confirms **dispatch request** to Delivery System.  
  - Package details sent (order ID, pickup location, delivery address, customer contact).  

### 2. Delivery Assignment (Delivery System)
- Delivery System assigns a delivery agent (rider/driver).  
- Generates a **tracking ID** for the order.  
- Updates system with **estimated delivery time (ETA)**.  

### 3. Real-Time Tracking (Delivery System → Customer)
- Customer can see current order status:  
  - **Pending Dispatch** (awaiting pickup).  
  - **Picked Up** (delivery agent collected the order).  
  - **In Transit** (on the way to destination).  
  - **Out for Delivery** (near destination).  
  - **Delivered** (successfully completed).  
- Map integration (optional) to show live location of delivery agent.  

### 4. Notifications & Alerts
- Customer receives notifications at key events:  
  - Order dispatched from inventory.  
  - Delivery agent assigned.  
  - Delivery agent picked up order.  
  - Estimated arrival updated (e.g., delays).  
  - Order delivered.  

### 5. Delivery Confirmation
- Delivery agent updates status once order is handed to customer.  
- System records:  
  - Delivery timestamp.  
  - Customer signature / OTP / photo confirmation (based on business rules).  

### 6. Exception Handling
- If delivery fails (customer not available, incorrect address, etc.):  
  - Delivery system notifies customer + support.  
  - System may reschedule delivery or return to inventory.  
- Failed deliveries recorded for audit/logs.  


---

## 📌 Notes
- **Actors**:  
  - **Inventory System**: Dispatch point for items.  
  - **Delivery System/Partner**: Responsible for actual shipping and tracking.  
  - **Customer**: Passive actor, can track status and receive notifications.  
- **Dependencies**:  
  - Relies on **Payment Module** (only paid orders are dispatched).  
  - Supports **Customer Module** (tracking UI & notifications).  
- **Security considerations**:  
  - Customer contact details shared securely only with assigned delivery agent.  
  - Tracking links should be tokenized/temporary for safety.  
