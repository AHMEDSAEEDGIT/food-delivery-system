# 📊 Dashboard Module

## 📌 Overview

The **Dashboard Module** provides real-time insights and reports for both restaurants and system administrators.  
It helps track performance, monitor orders, and make data-driven decisions.

**Actors:**
- **Restaurant Owners/Managers:** Monitor their restaurant activity
- **System Admin:** Monitor the overall platform performance

---

## ✨ Features

### 1. Restaurant Dashboard (For Restaurant Owners)
- **Orders Overview**
  - Daily/weekly/monthly sales
  - Pending, completed, and cancelled orders
- **Revenue Tracking**
  - Total earnings (with applied commissions)
  - Payout summary (amount credited to restaurant)
- **Menu Insights**
  - Best-selling items
  - Low-performing items
- **Customer Feedback**
  - Ratings and reviews summary
  - Average rating score

---

### 2. System Dashboard (For Admin)
- **Platform Performance**
  - Total number of active restaurants
  - Total number of customers
  - Total number of orders (daily/weekly/monthly)
- **Revenue Overview**
  - Platform revenue from commissions
  - Breakdown by restaurants
- **Operational Monitoring**
  - Active orders in progress
  - Failed/cancelled orders statistics
- **Restaurant Performance**
  - Top-performing restaurants
  - Restaurants with issues (low rating, high cancellations)

---

## 📌 Notes

- Dashboards are read-only analytics, not management tools
- They rely on Order, Payment, Customer modules for data
