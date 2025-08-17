# 🍴 Food Delivery System

## 📌 Overview
This repository documents and develops a **Restaurant Browsing and Food Delivery System**.  
The project simulates how modern food delivery applications (like Talabat, Uber Eats, or Deliveroo) work — from **browsing restaurants** to **adding items to cart**, **checkout**, **payment**, and **delivery tracking**.  

The goal is to extract **requirements, features, and functionalities** for each module, then gradually build **use case diagrams, sequence diagrams, and system design**, and finally move toward implementation.

---

## 📂 Repository Structure
restaurant-ordering-system/
│
├── README.md
│
├── docs/
│ ├── requirements/ # Features & functionalities of each module
│ ├── diagrams/ # Use case, sequence, and class diagrams
│ └── srs/ # System Requirement Specification (optional)
│
└── src/ # Source code (later in the project)
└── backend

---
## 📦 Modules & Features Overview

![online shopping system use case](/docs/requirements/images/use-case.png)

### 1. 🔐 [User Registration & Login](/docs/requirements/01-login-registeration.md)
- User registration with email/phone verification.  
- Secure login with password hashing.  
- Password reset and account recovery.  
- Role-based access (customer vs admin).  
- Session/token-based authentication.  

### 2. 🍴 [Browsing Restaurants & Items](/docs/requirements/02-browsing.md)
- Global search (food, groceries, snacks, restaurants).  
- Browse categories (food, health & beauty, gifts, etc.).  
- Location-based recommendations (best sellers near you).  
- Restaurant pages with menu, ratings, delivery time, and fees.  
- Special offers, flash sales, and rewards section.  

### 3. 🛒 [Add to Cart](/docs/requirements/03-add-to-cart.md)
- Add items to cart with quantity and special notes.  
- Edit/remove items from cart.  
- Apply vouchers and discounts.  
- View payment summary (subtotal, delivery fee, service fee, total).  
- Persistent cart (saved even if app closes).  

### 4. 💳 [Checkout](/docs/requirements/04-checkout.md)
- Select/change delivery location.  
- Choose delivery priority (standard or express).  
- Review order before final confirmation.  

### 5. 💰 [Payment](/docs/requirements/05-payment.md)
- Multiple payment options: cash, saved cards, new card, wallet.  
- Integration with payment gateways for secure transactions.  
- Inventory system updates upon successful payment.  
- Refund and cancellation handling.  

### 6. 🛵 [Order & Delivery Tracking](/docs/requirements/06-delivery-tracking.md)
- Real-time order status (accepted, preparing, out for delivery).  
- Estimated delivery time updates.  
- Integration with delivery system for live tracking.  
- Customer can see driver’s live location.  



---

## 🎯 Project Goals
- Document system features in a structured way.  
- Model the system using UML diagrams.  
- Define functional and non-functional requirements.  
- Build a prototype implementation.  



