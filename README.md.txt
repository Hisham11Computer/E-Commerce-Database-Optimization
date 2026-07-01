📌 Project Title:
E-Commerce Database Performance Optimization & Index Engineering

💻 Tech Stack:
MySQL, Python (Faker, MySQL-Connector), Execution Plan Analysis (Visual Explain).

🛠️ What I Did (Description):
Simulated a production-grade E-Commerce environment by generating and seeding a massive dataset (200K+ orders & 400K+ order items) using a custom Python script.

Identified and diagnosed bottleneck queries causing Full Table Scans during heavy aggregate reporting operations.

Analyzed MySQL Execution Plans (Visual Explain) to locate cost-heavy operations and sub-optimal join paths.

Engineered strategic Single-Column & Composite Indexes (idx_orders_status) that successfully shifted database behavior from resource-intensive Scans to instantaneous Index Seeks/Lookups.

Documented performance benchmarks and query execution path alterations (Before vs. After optimization states).


### 📊 Performance Benchmarks & Execution Plans

#### ❌ Before Optimization (Full Table Scan)
As shown below, querying the unindexed `orders` table forced a **Full Table Scan**, reading over 199K rows sequentially, leading to high I/O cost and degraded performance:

![Before Optimization](Before%20optimization%20states.png)

####  After Optimization (Index Lookup)
After implementing the strategic `idx_orders_status` index, the execution path successfully shifted to a highly efficient **Non-Unique Key Lookup**, eliminating the full table scan entirely:

![After Optimization](After%20optimization%20states.png)