# Football Ticket Booking System - SQL Queries


## 📌 Project Overview
1. **Schema Initialization (DDL):** Translating structural blueprints into active tables with explicit keys, defaults, and data integrity check constraints.
2. **Data Ingestion (DML):** Seeding the database with realistic sample entities (`Users`, `Matches`, `Bookings`) to emulate a production state.
3. **Analytical Reporting:** Resolving 7 distinct operational query requirements to extract actionable insights.

---

## 🛠️ Script Architecture: `QUERY.sql`

The core script is systematically structured into clear operational blocks:

### **1. Data Definition & Integrity Layer**
* **`Users` Table:** Manages core system entity profiles, enforcing role separation (`Ticket Manager`, `Football Fan`) and unique communication links.
* **`Matches` Table:** Maps tournament categorization, fixture titles, and seat pricing metrics under strict non-negative rules.
* **`Bookings` Table:** Orchestrates the financial transaction layer, safely linking users to upcoming events through foreign key dependencies.

### **2. Mock Data Seeding**
* Ingests validated production profiles, scheduling data spanning the *Champions League*, *Premier League*, and *Serie A*, along with correlated booking receipts.

### **3. Operational Analytics (The 7 Core Solutions)**
The engine features optimized queries providing functional resolutions for the following requirements:
* **Query 1 (Inventory Tracking):** Extracts upcoming *Champions League* matches that are actively listed as *Available*.
* **Query 2 (Pattern Recognition):** Performs comprehensive user filtering with case-insensitive name matching (`ILIKE`/`LIKE`).
* **Query 3 (Data Transformation):** Utilizes `COALESCE` to identify unresolved payment states (`NULL`) and dynamically returns them as `'Action Required'`.
* **Query 4 (Relational Joins):** Merges transactional maps via `INNER JOIN` to yield user names alongside scheduled team fixtures.
* **Query 5 (Comprehensive Auditing):** Employs a `FULL JOIN` to audit platform engagement, listing all users even if they haven't purchased a ticket.
* **Query 6 (Subquery Processing):** Detects high-value transactions by filtering bookings that exceed the global average cost.
* **Query 7 (Data Window Pagination):** Leverages `ORDER BY`, `LIMIT`, and `OFFSET` parameters to safely paginate data and return the top premium pricing profiles.

---

## 📂 Repository Layout
* `QUERY.sql` — The complete standalone SQL database pipeline script.
* `README.md` — Project documentation and operational workflow overview.
