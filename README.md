# E-Commerce Database Management

This project implements a simple e-commerce database using MySQL. It includes tables to manage customers, orders, products, and their relationships. The database is normalized for efficient storage and retrieval of data.

---

## Database Details

### Database Name
`ecommerce`

---

### Table Structures

#### 1. `customers`
| Column     | Type          | Description                           |
|------------|---------------|---------------------------------------|
| `id`       | INT           | Primary key, unique identifier for each customer (auto-increment). |
| `name`     | VARCHAR(100)  | Customer's name.                     |
| `email`    | VARCHAR(100)  | Customer's email address (unique).   |
| `address`  | TEXT          | Customer's address.                  |

#### 2. `orders`
| Column        | Type         | Description                           |
|---------------|--------------|---------------------------------------|
| `id`          | INT          | Primary key, unique identifier for each order (auto-increment). |
| `customer_id` | INT          | Foreign key referencing `customers.id`. |
| `order_date`  | DATE         | Date when the order was placed.      |
| `total_amount`| DECIMAL(10,2)| Total amount of the order.           |

#### 3. `products`
| Column       | Type          | Description                           |
|--------------|---------------|---------------------------------------|
| `id`         | INT           | Primary key, unique identifier for each product (auto-increment). |
| `name`       | VARCHAR(100)  | Name of the product.                 |
| `price`      | DECIMAL(10,2) | Product price.                       |
| `description`| TEXT          | Description of the product.          |
| `discount`   | DECIMAL(10,2) | Discount on the product.             |

#### 4. `order_items` (Normalized Table)
| Column       | Type          | Description                           |
|--------------|---------------|---------------------------------------|
| `id`         | INT           | Primary key, unique identifier for each item (auto-increment). |
| `order_id`   | INT           | Foreign key referencing `orders.id`. |
| `product_id` | INT           | Foreign key referencing `products.id`. |
| `quantity`   | INT           | Quantity of the product in the order.|

---

## SQL Queries

### Functional Queries
1. Retrieve all customers who have placed an order in the last 30 days.
2. Calculate the total amount spent by each customer.
3. Update the price of a specific product.
4. Add a new `discount` column to the `products` table.
5. Retrieve the top 3 most expensive products.
6. Get the names of customers who ordered a specific product.
7. Join `orders` and `customers` tables to get customer names and order dates.
8. Retrieve orders with a total amount greater than a specific value.
9. Normalize the database by creating an `order_items` table.
10. Calculate the average total of all orders.

---

## How to Use

1. **Set Up the Database**  
   - Run the SQL script to create the `ecommerce` database and the required tables.
   - Insert the sample data provided in the script.

2. **Run Queries**  
   - Use the functional queries listed above to interact with the database and extract insights.

3. **Normalize and Enhance**  
   - Normalize the database by utilizing the `order_items` table for better scalability.

---

## Sample Data

- **Customers**
  - John Doe, Jane Smith, Alice Johnson.
- **Products**
  - Product A, Product B, Product C.
- **Orders**
  - Orders placed by customers with relevant dates and amounts.

---

## Notes

- The database design ensures proper normalization by avoiding data redundancy.
- Sample data provided in the script is for demonstration purposes.
- MySQL syntax is used for all operations.

---
