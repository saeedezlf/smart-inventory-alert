# Smart Inventory Alert 

A low-code automation solution that monitors inventory levels using SQL Server and Power Automate, and automatically sends alert emails when stock falls below threshold.

## Project Overview

This project integrates Microsoft SQL Server Express with Power Automate to build an automated inventory alert system. The flow checks a product table in SQL Server for low-stock items and sends customized email alerts, ensuring timely restocking and proactive inventory management.

## Features

* Automated inventory monitoring via Power Automate
* SQL Server Express as the central database
* Email alerts for items with `is_available = false`
* Reusable, low-code workflow
* Ideal for small business or internal IT teams

## Tech Stack

* **SQL Server 2019 Express**
* **Power Automate (Cloud Flow)**
* **Outlook Email Connector**
* **SharePoint (optional for UI or integration)**

## Database Schema

The database contains a single table `Devices` with fields:

| Field Name        | Type    | Description                      |
| ----------------- | ------- | -------------------------------- |
| `id`              | INT     | Primary key                      |
| `device_name`     | VARCHAR | Name of the device               |
| `category`        | VARCHAR | Type (e.g., Smartphone, Laptop)  |
| `serial_number`   | VARCHAR | Unique device identifier         |
| `purchase_date`   | DATE    | Date of purchase                 |
| `warranty_expiry` | DATE    | Warranty expiration date         |
| `is_available`    | BOOLEAN | Availability status (true/false) |

## Flow Logic

1. A scheduled cloud flow connects to SQL Server via on-premises gateway.
2. Executes a query to fetch unavailable items (`is_available = false`)
3. If any results exist, it sends an email summarizing the unavailable inventory.
4. The flow runs daily (or based on your schedule).

## Screenshots

## Files Included

* `schema.sql` – SQL table definition
* `sample_data.sql` – Sample insert statements
* `flow_overview.png` – Power Automate diagram

## Future Improvements

* Add UI for editing inventory (via SharePoint or Power Apps)
* Integrate approval system for restock
* Expand to multi-table product database

---

Feel free to fork, clone, or modify this solution for your own internal automation needs.
