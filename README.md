# 📦 Inventory Management System — Domain Mapping

This document describes the domain mapping for an inventory management system based on Domain-Driven Design (DDD) practices. The goal is to track products, control minimum stocks, issue alerts, view sales history, and manage purchase orders automatically with integration with suppliers.

---
## 🧩 Domain Entities

### 🏷️ Product
Represents an item controlled in the inventory.

**Attributes:**
- `id`: Unique identifier
- `name`: Product name
- `size`: Item size (if applicable)
- `color`: Item color (if applicable)
- `currentQuantity`: Current quantity in stock
- `minimumQuantity`: Minimum quantity defined
- `price`: Product value
- `historyMovements`: List of stock entries and exits

---

### 📦 Stock
Manages all registered products.

**Attributes:**
- `products`: List of products
- `movements`: Stock entries and exits
- `trends`: Historical data on stock growth or decline

---

### 💰 Sales
Records product exits to customers.

**Attributes:**
- `date`: Date of sale
- `productsSold`: List of products and quantities
- `totalValue`: Total sale value
- `profitPerProduct`: Profit obtained per item sold

---

### 🧾 Purchase Order
Represents a request to purchase products based on defined criteria.

**Attributes:**
- `id`: Order identifier
- `productsRequested`: List of products and quantities
- `dataCreated`: Date the order was generated
- `status`: Order status (pending, in progress, delivered, etc.)
- `supplier`: Associated supplier

---

### 🏭 Supplier
Represents the suppliers that serve the company.

**Attributes:**
- `name`: Supplier name
- `contact`: Contact details
- `productsSupplied`: Available items
- `deliverytime`: Estimated delivery time

---

### 🚨 Alert
Indicates a critical condition, such as low stock.

**Attributes:**
- `type`: Alert type (e.g. minimum stock)
- `product`: Related product
- `date`: Alert generation date
- `notificationMethod`: Email, system or both

---

## ✅ Use Cases

1. **Register Product**
2. **Update Product**
3. **Register Entry/Exit in Stock**
4. **Track Product by ID**
5. **Set Minimum Stock Quantity**
6. **Issue Low Stock Alerts**
7. **View Sales History**
8. **Analyze Stock Trends**
9. **Automatically Generate Purchase Orders**
10. **Manage Purchase Orders**
11. **Integrate with Suppliers**
12. **Notify Users (System/Email)**

---

## 📈 System Objectives

- Avoid stock shortages
- Automate orders based on historical data
- Reduce waste and losses due to excess inventory
- Facilitate decisions based on sales and trends

---

## 📎 Technical Notes

- **DDD**-based architecture
- Can be developed as a **modular monolith** or with a focus on **domain events** for future scalability
- Can use notifications with services such as SMTP email, WebSocket or internal push via UI

---

> This mapping is a starting point for application development. It can be refined as the domain evolves.
