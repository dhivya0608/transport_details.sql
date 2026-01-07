# transport_details.sql
Transport_Details SQL dataset containing logistics, route, fuel usage, and cost information for SQL practice and analysis.
# Transport Details SQL Dataset 

## Overview
The **Transport_Details** dataset represents real-world transportation and logistics operations.  
It includes information about vehicles, drivers, routes, distance traveled, fuel usage, transport dates, and cost details.
## SQL Concepts Covered
This dataset is useful for practicing:

- `SELECT`, `WHERE`
- `ORDER BY`
- `GROUP BY`, `HAVING`
- Aggregate functions (`SUM`, `AVG`, `MIN`, `MAX`, `COUNT`)
- Date filtering
- Cost and fuel efficiency analysis

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
-- Create the table
CREATE TABLE Transport (
    Transport_ID INT PRIMARY KEY,
    Vehicle_No VARCHAR(20),
    Driver_Name VARCHAR(50),
    Route_From VARCHAR(50),
    Destination VARCHAR(50),
    Distance_km INT,
    Fuel_Used_L INT,
    Transport_Date DATE,
    Freight_Charge DECIMAL(10,2),
    Total_Price DECIMAL(10,2)
);

-- Insert data
INSERT INTO Transport VALUES
(101, 'MH12AB1234', 'Ramesh', 'Pune', 'Mumbai', 150, 25, '2025-11-01', 3000.00, 2250.00),
(102, 'MH14CD5678', 'Suresh', 'Mumbai', 'Nashik', 180, 28, '2025-11-02', 3500.00, 2520.00),
(103, 'MH12XY9999', 'Mahesh', 'Pune', 'Nagpur', 700, 100, '2025-11-03', 9000.00, 9000.00),
(104, 'MH13PQ3333', 'Ramesh', 'Mumbai', 'Pune', 150, 24, '2025-11-04', 2800.00, 2160.00),
(105, 'MH15AA5555', 'Dinesh', 'Nashik', 'Mumbai', 180, 30, '2025-11-05', 3600.00, 2700.00),
(106, 'MH16BB4444', 'Mahesh', 'Nagpur', 'Pune', 700, 95, '2025-11-06', 8800.00, 8550.00),
(107, 'MH18CC2222', 'Ravi', 'Pune', 'Solapur', 250, 40, '2025-11-07', 4200.00, 3600.00),
(108, 'MH19DD7777', 'Vikas', 'Mumbai', 'Kolhapur', 400, 60, '2025-11-08', 6500.00, 5400.00),
(109, 'MH17EE1111', 'Ramesh', 'Pune', 'Nashik', 200, 32, '2025-11-09', 3700.00, 2880.00),
(110, 'MH12FF2222', 'Suresh', 'Nashik', 'Aurangabad', 210, 33, '2025-11-10', 3800.00, 2970.00),
(111, 'MH13GG3333', 'Vikas', 'Kolhapur', 'Pune', 400, 62, '2025-11-11', 6600.00, 5580.00),
(112, 'MH14HH4444', 'Dinesh', 'Mumbai', 'Nagpur', 700, 98, '2025-11-12', 9100.00, 8820.00),
(113, 'MH15JJ5555', 'Mahesh', 'Pune', 'Mumbai', 150, 26, '2025-11-13', 3100.00, 2340.00),
(114, 'MH16KK6666', 'Ravi', 'Aurangabad', 'Pune', 230, 38, '2025-11-14', 4000.00, 3420.00),
(115, 'MH17LL7777', 'Suresh', 'Nashik', 'Mumbai', 180, 29, '2025-11-15', 3550.00, 2610.00);

  | Transport_ID | Vehicle_No   | Driver_Name | Route_From  | Destination | Distance_km | Fuel_Used_L | Transport_Date | Freight_Charge | Total_Price |
|--------------|-------------|------------|------------|------------|-------------|-------------|----------------|----------------|-------------|
| 101          | MH12AB1234  | Ramesh     | Pune       | Mumbai     | 150         | 25          | 2025-11-01     | 3000.00        | 2250.00     |
| 102          | MH14CD5678  | Suresh     | Mumbai     | Nashik     | 180         | 28          | 2025-11-02     | 3500.00        | 2520.00     |
| 103          | MH12XY9999  | Mahesh     | Pune       | Nagpur     | 700         | 100         | 2025-11-03     | 9000.00        | 9000.00     |
| 104          | MH13PQ3333  | Ramesh     | Mumbai     | Pune       | 150         | 24          | 2025-11-04     | 2800.00        | 2160.00     |
| 105          | MH15AA5555  | Dinesh     | Nashik     | Mumbai     | 180         | 30          | 2025-11-05     | 3600.00        | 2700.00     |
| 106          | MH16BB4444  | Mahesh     | Nagpur     | Pune       | 700         | 95          | 2025-11-06     | 8800.00        | 8550.00     |
| 107          | MH18CC2222  | Ravi       | Pune       | Solapur    | 250         | 40          | 2025-11-07     | 4200.00        | 3600.00     |
| 108          | MH19DD7777  | Vikas      | Mumbai     | Kolhapur   | 400         | 60          | 2025-11-08     | 6500.00        | 5400.00     |
| 109          | MH17EE1111  | Ramesh     | Pune       | Nashik     | 200         | 32          | 2025-11-09     | 3700.00        | 2880.00     |
| 110          | MH12FF2222  | Suresh     | Nashik     | Aurangabad | 210         | 33          | 2025-11-10     | 3800.00        | 2970.00     |
| 111          | MH13GG3333  | Vikas      | Kolhapur   | Pune       | 400         | 62          | 2025-11-11     | 6600.00        | 5580.00     |
| 112          | MH14HH4444  | Dinesh     | Mumbai     | Nagpur     | 700         | 98          | 2025-11-12     | 9100.00        | 8820.00     |
| 113          | MH15JJ5555  | Mahesh     | Pune       | Mumbai     | 150         | 26          | 2025-11-13     | 3100.00        | 2340.00     |
| 114          | MH16KK6666  | Ravi       | Aurangabad | Pune       | 230         | 38          | 2025-11-14     | 4000.00        | 3420.00     |
| 115          | MH17LL7777  | Suresh     | Nashik     | Mumbai     | 180         | 29          | 2025-11-15     | 3550.00        | 2610.00     |





