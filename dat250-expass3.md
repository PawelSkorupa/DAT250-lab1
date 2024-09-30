# DAT250-Lab5 Report

## Overview
Objective of assignment: get familiar with MongoDB by following its official tutorial.

## Step 1: Installation
I downloaded the official MongoDB 8.0.0 installer for Windows and created a SHA256 file with the checksum taken from official MongoDB website.
Then, I ran a Powershell script to check SHA256 values of both files:

![obraz](https://github.com/user-attachments/assets/281ae6ce-984a-46cf-a287-98545c2ccaf8)

The values of both checksums were identical.

## Step 2: CRUD operations
I followed the official tutorials for each type of CRUD operation in MongoDB. Below, I provided some screenshots confirming the successful outcome of those operations.

### Insert documents
![obraz](https://github.com/user-attachments/assets/c50853ed-e7e9-425a-a41d-b3fab47db938)

### Query documents
![obraz](https://github.com/user-attachments/assets/68eaca5a-591d-4fd6-9c40-cdf0fc6397e7)

### Update documents
![obraz](https://github.com/user-attachments/assets/e479d391-6422-4473-9200-741a1dc094ee)

### Remove documents
![obraz](https://github.com/user-attachments/assets/276ffb17-1dd2-46a5-a3ad-f7f1e925d3b6)

### Bulk write operations
![obraz](https://github.com/user-attachments/assets/6a10e1f9-5928-4778-a923-46de50994f31)

## Step 3: Aggregation
I followed the official tutorial for map-reduce and aggregation pipeline. The screenshot below shows the execution of calculating order and total quantity with average quantity per item:

![obraz](https://github.com/user-attachments/assets/e2696e65-e15e-4bbd-8332-8d7ffb949797)

I also developed my own map-reduce function for calculating total revenue and total quantity sold per product:

![obraz](https://github.com/user-attachments/assets/487ee849-50d6-4112-917b-34bb538b3071)

Explanation of the map-reduce function:
1. The map function emits each product SKU as the key, with a value that includes the quantity and revenue for that item.
2. The reduce function aggregates the quantity and revenue for each product.

The results of this query can be useful for business purposes (which product generates the most revenue, which product has the highest demand among customers).

## Technical difficulties
During this exercise, I didn't encounter any technical difficulties.
