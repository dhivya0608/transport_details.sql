# transport_details.sql
Transport_Details SQL dataset containing logistics, route, fuel usage, and cost information for SQL practice and analysis.
# Transport Details SQL Dataset 🚚

## Overview
The **Transport_Details** dataset represents real-world transportation and logistics operations.  
It includes information about vehicles, drivers, routes, distance traveled, fuel usage, transport dates, and cost details.

This dataset is designed for **SQL practice**, **data analysis**, and **interview preparation**.

---

## Table Structure

### Table Name: `Transport_Details`

| Column Name       | Data Type        | Description |
|------------------|------------------|-------------|
| Transport_ID     | INT (PK)         | Unique identifier for each transport record |
| Vehicle_No       | VARCHAR(15)      | Vehicle registration number |
| Driver_Name      | VARCHAR(50)      | Name of the driver |
| Route_From       | VARCHAR(50)      | Starting city |
| Route_To         | VARCHAR(50)      | Destination city |
| Distance_km      | INT              | Distance traveled (in kilometers) |
| Fuel_Used_L      | INT              | Fuel consumed (in liters) |
| Transport_Date   | DATE             | Date of transport |
| Freight_Charge   | DECIMAL(10,2)    | Freight charge amount |
| Total_Price      | DECIMAL(10,2)    | Fuel cost (Fuel_Used_L × Fuel price) |

---

## Dataset Highlights
- Multiple drivers and vehicles
- Various routes across cities
- Short and long-distance transport records
- Fuel usage and cost-based calculations
- Date-based transport analysis

Fuel price is assumed as **₹90 per liter** for calculating `Total_Price`.

---

## SQL Concepts Covered
This dataset is useful for practicing:

- `SELECT`, `WHERE`
- `ORDER BY`
- `GROUP BY`, `HAVING`
- Aggregate functions (`SUM`, `AVG`, `MIN`, `MAX`, `COUNT`)
- Date filtering
- Cost and fuel efficiency analysis
- Interview-style SQL problems (without JOINs)

---

## Sample Use Cases
- Total freight charge by driver
- Average fuel consumption per route
- Most expensive transport route
- Driver-wise total distance covered
- Monthly transport cost analysis

---

## File Information
- **File Name:** `transport_details.sql`
- **Database Type:** MySQL (compatible with most SQL databases)

---

## Who Can Use This?
- SQL beginners
- Data Analyst aspirants
- Interview preparation candidates
- Students practicing real-world datasets

---

## Author
Created as part of a **SQL practice and data analytics portfolio**.

---

⭐ *If you find this useful, feel free to star the repository!*  
