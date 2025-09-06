# 🍴 Food Delivery System

## 📌 Overview
This repository documents and develops a **Restaurant Browsing and Food Delivery System**.  
The project simulates how modern food delivery applications (like Talabat, Uber Eats, or Deliveroo) work — from **browsing restaurants** to **adding items to cart**, **checkout**, **payment**, and **delivery tracking**.  

The goal is to extract **requirements, features, and functionalities** for each module, then gradually build **use case diagrams, sequence diagrams, and system design**, and finally move toward implementation.

---

## 📑 Table of Contents

- **README.md** – Project overview & main documentation  

- **docs/** – Project documentation  
  - **requirements/** – Features & functionalities of each module  
  - **diagrams/** – Use case, sequence, and class diagrams  
  - **srs/** – System Requirement Specification (optional)  

- **src/** – Source code (future implementation)  
  - **backend/** – Server-side logic & APIs    

---

## 📦 Modules & Features Overview

### 1. 🔐 [User Registration & Authentication](/docs/requirements/01-registration-authentication.md)

   - Handles secure onboarding and account access.
   - User registration with email/phone verification.
   - Secure login with password hashing.
   - Password reset and account recovery.
   - Role-based access (customer, restaurant, admin).
   - Token/session-based authentication.
### 2. 🍴 [Restaurant & Menu Management](/docs/requirements/02-menu-management.md)

   - Enables customers to explore restaurants and their offerings.
   - Search restaurants, items, and categories.
   - Location-based recommendations (best sellers nearby).
   - Restaurant details (menu, reviews, delivery time, fees).
   - Special offers, flash sales, and rewards.
### 3. 🛒 [Cart Management](/docs/requirements/03-cart-management.md)

   - Customer shopping cart functionality.
   - Add/remove/edit items with special notes.
   - Apply discounts, vouchers, or coupons.
   - Persistent cart (saved even after logout/app close).
   - Payment summary (subtotal, delivery, service fee, total).

### 4. 📦 [Order Management](/docs/requirements/04-order-management.md)

   - Core system for handling orders.
   - Place new orders.
   - Cancel orders (by customer or restaurant).
   - Order status updates (tracking lifecycle).
   - Order summary & details.
   - Order history (for customers & restaurants).

### 5. 💳 [Checkout & Payment](/docs/requirements/05-checkout-payment.md)

   - Processes order confirmation and payment.
   - Select/change delivery address.
   - Choose delivery type (standard, express).
   - Multiple payment methods (cash, card, wallet).
   - Integration with payment gateways.
   - Refunds & cancellations handling.

### 6. 🛵 [Order & Delivery Tracking](/docs/requirements/06-delivery-tracking.md)

   - Real-time order tracking for customers and restaurants.
   - Track order status (accepted, preparing, out for delivery).
   - Estimated delivery time updates.
   - Live driver location.
   - Delivery system integration.

### 7. 🧑 [Customer Management](/docs/requirements/07-customer-management.md)
   - Manages customer accounts and preferences.
   - Order history & tracking.
   - Preferred payment settings (cash, card).
   - Address management (multiple delivery addresses).
   - Ratings & comments for restaurants/items.
   - Account deactivate/reactivation.

### 8. 🛠️  [Admin Management](/docs/requirements/08-admin.md)

   - System-level control for admins.
   - Manage restaurants & customers.
   - Monitor platform health.
   - Revenue/commission tracking.
   - Handle disputes, refunds, fraud detection.
   - User role/permissions management.

### 9. 🎁 [Offers & Promotions](/docs/requirements/09-offers.md)
   - Marketing features to improve engagement.
   - Discount coupons & promo codes.
   - Flash sales.
   - Restaurant-specific deals.
   - Loyalty & reward programs.

### 10. 📊 [Dashboards](/docs/requirements/10-dashboard.md)

   - Analytics & insights for decision-making.

   - **Restaurant Dashboard**
      - Sales & revenue summary.
      - Best/low-performing items.
      - Customer feedback overview.
   
   - **Admin Dashboard**
      - Platform performance (orders, users, revenue).
      - Restaurant performance monitoring.
  

---
# Database Schema Overview

This document outlines the core Entity-Relationship Diagram (ERD) for the Food Delivery System, detailing the main entities and their purposes.

![Food Delivery System ERD](./docs/diagrams/full-scheme/food-deliver-system-scheme.png) 



## Entity Definitions


<style>
  .module-auth { background-color: #DAE8FC; } /* Light Blue */
  .module-restaurant { background-color: #FFF2CC; } /* Light Yellow */
  .module-cart { background-color: #D5E8D4; } /* Light Orange */
  .module-order { background-color: #E1D5E7; } /* Light Green */
  .module-delivery { background-color: #E1D5E7; } /* Light Purple */
  .module-payment { background-color: #FAD9D5; } /* Light Pink */
  .module-customer { background-color: #FFE6CC; } /* Light Blue 2 */
  .module-offers { background-color: #B0E3E6; } /* Light Cyan */
</style>




| Entity | Description | Module |
| :--- | :--- | :--- |
| <span class="module-auth">`User`</span> | <span class="module-auth">Central account table for all platform users. Stores login credentials and core profile.</span> | <span class="module-auth">Authentication</span> |
| <span class="module-auth">`Role`</span> | <span class="module-auth">Lookup table for system roles (e.g., `customer`, `restaurant_owner`, `admin`, `driver`).</span> | <span class="module-auth">Authentication</span> |
| <span class="module-auth">`UserRole`</span> | <span class="module-auth">Junction table that manages the many-to-many relationship between Users and Roles.</span> | <span class="module-auth">Authentication</span> |
| <span class="module-auth">`VerificationToken`</span> | <span class="module-auth">Stores secure tokens for account verification emails and password reset requests.</span> | <span class="module-auth">Authentication</span> |
| <span class="module-restaurant">`Restaurant`</span> | <span class="module-restaurant">Contains all information about a restaurant, including status, location, and operational details.</span> | <span class="module-restaurant">Restaurant & Menu</span> |
| <span class="module-restaurant">`CuisineType`</span> | <span class="module-restaurant">Defines types of food a restaurant can serve (e.g., "Pizza", "Sushi", "Burger").</span> | <span class="module-restaurant">Restaurant & Menu</span> |
| <span class="module-restaurant">`RestaurantCuisine`</span> | <span class="module-restaurant">Junction table linking Restaurants to the CuisineTypes they serve.</span> | <span class="module-restaurant">Restaurant & Menu</span> |
| <span class="module-restaurant">`MenuCategory`</span> | <span class="module-restaurant">A section within a restaurant's menu (e.g., "Appetizers", "Main Courses").</span> | <span class="module-restaurant">Restaurant & Menu</span> |
| <span class="module-restaurant">`MenuItem`</span> | <span class="module-restaurant">The core sellable product offered by a restaurant.</span> | <span class="module-restaurant">Restaurant & Menu</span> |
| <span class="module-restaurant">`MenuItemOptionGroup`</span> | <span class="module-restaurant">Defines a set of choices for a menu item (e.g., "Choose Size").</span> | <span class="module-restaurant">Restaurant & Menu</span> |
| <span class="module-restaurant">`MenuItemOption`</span> | <span class="module-restaurant">An individual choice within an option group (e.g., "Large").</span> | <span class="module-restaurant">Restaurant & Menu</span> |
| <span class="module-cart">`Cart`</span> | <span class="module-cart">A user's temporary workspace for items before checkout. Locked to a single restaurant.</span> | <span class="module-cart">Cart Management</span> |
| <span class="module-cart">`CartItem`</span> | <span class="module-cart">An item from the menu added to the cart. Stores a snapshot of the price.</span> | <span class="module-cart">Cart Management</span> |
| <span class="module-cart">`CartItemOption`</span> | <span class="module-cart">Records the customizations chosen for a cart item. Stores a snapshot of the option details.</span> | <span class="module-cart">Cart Management</span> |
| <span class="module-order">`Order`</span> | <span class="module-order">The master record of a transaction. Tracks status, amount, and links to involved parties.</span> | <span class="module-order">Order Management</span> |
| <span class="module-order">`OrderItem`</span> | <span class="module-order">A permanent, immutable snapshot of a purchased menu item at the time of order.</span> | <span class="module-order">Order Management</span> |
| <span class="module-order">`OrderItemOption`</span> | <span class="module-order">A permanent snapshot of the customizations chosen for an order item.</span> | <span class="module-order">Order Management</span> |
| <span class="module-delivery">`Driver`</span> | <span class="module-delivery">Profile information for a user with the `driver` role (vehicle, availability).</span> | <span class="module-delivery">Delivery Tracking</span> |
| <span class="module-delivery">`DeliveryTracking`</span> | <span class="module-delivery">Tracks key timestamps and details for the delivery process.</span> | <span class="module-delivery">Delivery Tracking</span> |
| <span class="module-payment">`Payment`</span> | <span class="module-payment">Records the attempt to collect payment for an order, including method and status.</span> | <span class="module-payment">Checkout & Payment</span> |
| <span class="module-payment">`Address`</span> | <span class="module-payment">Stores delivery addresses associated with a user's account.</span> | <span class="module-payment">Checkout & Payment</span> |
| <span class="module-customer">`Review`</span> | <span class="module-customer">Allows users to leave ratings and comments for a restaurant based on an order.</span> | <span class="module-customer">Customer Management</span> |
| <span class="module-offers">`PromoCode`</span> | <span class="module-offers">Defines a discount code or promotion with its rules and validity.</span> | <span class="module-offers">Offers & Promotions</span> |
| <span class="module-offers">`OrderPromoCode`</span> | <span class="module-offers">Links an applied promo code to a specific order and records the discount given.</span> | <span class="module-offers">Offers & Promotions</span> |
---
## 📌 Use Cases

This section documents the system’s main use cases.  
Each use case includes:
- **Sequence Diagram**
- **Flowchart**
- **Pseudo Code**
- **Entity Relationship Diagram (ERD)**

### 1. Place Order
**Description:**  
A customer confirms their cart and places an order.  
The system validates item availability, delivery address, payment details, and applied vouchers.  
On success, an order is created, stored, and both customer and restaurant receive confirmation.  

**Artifacts:**  
- 💻 [Pseudo Code](docs/diagrams/use-cases/place-order/pseudo-code.md)  
- 📐 Sequence Diagram  
  ![Sequence Diagram](/docs/diagrams/use-cases/place-order/sequence-diagrams/place-order-sequence.png)  

- 🗂️ Flowchart  
  ![Flowchart](/docs/diagrams/use-cases/place-order/flowcharts/checkout-order-flowchart.png)  


- 🗄️ ERD  
  ![ERD](/docs/diagrams/use-cases/place-order/entity-diagrams/place-order-erd.png)  


---

## 🎯 Project Goals
- Document system features in a structured way.  
- Model the system using UML diagrams.  
- Define functional and non-functional requirements.  
- Build a prototype implementation.  



