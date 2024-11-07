# Recyclable and Low Fat Products

This repository contains a solution to the problem of filtering products from a database where the products must meet two criteria:
1. They must be **low-fat**.
2. They must be **recyclable**.

## Problem Description

You are given a `Products` table with the following structure:

| Column Name | Type    |
|-------------|---------|
| product_id  | int     |
| low_fats    | enum    |
| recyclable  | enum    |

- **product_id**: A unique identifier for each product (Primary Key).
- **low_fats**: An ENUM column with values `'Y'` (Low Fat) and `'N'` (Not Low Fat).
- **recyclable**: An ENUM column with values `'Y'` (Recyclable) and `'N'` (Not Recyclable).

You are tasked with finding the product IDs of products that are both **low fat** and **recyclable**.

### Input Example

#### Products table:

| product_id | low_fats | recyclable |
|------------|----------|------------|
| 0          | Y        | N          |
| 1          | Y        | Y          |
| 2          | N        | Y          |
| 3          | Y        | Y          |
| 4          | N        | N          |

### Output Example

| product_id |
|------------|
| 1          |
| 3          |

#### Explanation:
- Products 1 and 3 are both low-fat and recyclable. Therefore, their product IDs are returned in the output.

## Solution

### SQL Query

The following SQL query is used to solve the problem:

```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y';
