# MongoDB Queries

This repository contains MongoDB queries for various tasks based on a sample product dataset. The data includes information about products such as their name, price, material, and color.

## Project Overview

The purpose of this project is to demonstrate basic MongoDB queries for filtering, retrieving, and deleting data using MongoDB Compass. The queries cover a variety of use cases such as finding specific product details, filtering based on price ranges, and deleting certain records.

## Dataset

The dataset used is a collection of product information stored in a JSON file. Each document in the dataset represents a product with the following fields:

- `id`: Product identifier
- `product_name`: Name of the product
- `product_price`: Price of the product
- `product_material`: Material of the product
- `product_color`: Color of the product

## MongoDB Queries

The following queries are included in this project:

1. **Find all the information about each product:**
- {}
  This query retrieves all documents in the collection.

2. **Find the product prices between 400 to 800:**

- { "product_price": { "$gte": 400, "$lte": 800 } }

3. **Find the product prices not between 400 to 600:**

- { "product_price": { "$not": { "$gte": 400, "$lte": 600 } } }

4. **List the four products with a price greater than 500:**

- { "product_price": { "$gt": 500 } }
- Limit to 4 results:
   { "$limit": 4 }

5. **Find the product name and product material of each product:**
   
- {}
- Projection: { "product_name": 1, "product_material": 1 }

6. **Find the product with an id of 10:**

- { "id": "10" }

7. **Find only the product name and product material:**

- Projection: { "product_name": 1, "product_material": 1, "_id": 0 }

8. **Find all products containing the value "soft" in product_material:**

- { "product_material": { "$regex": "soft", "$options": "i" } }
  
9. **Find products with product_color as "indigo" and product_price as 492:**

- { "product_color": "indigo", "product_price": 492 }

10. **Delete products where product_price is 28:**

- { "product_price": 28 }
