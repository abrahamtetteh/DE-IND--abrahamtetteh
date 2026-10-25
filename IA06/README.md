
https://youtu.be/L7gU-NsRVp8
Data Model, Query and State Walkthrough1. Database Schema Design (PostgreSQL)users: Stores staff and customer profiles, roles, and password hashes.   menu_items: Stores traditional dishes, categories, pricing, and stock thresholds.   orders: Stores customer orders, delivery fees, payment types (Cash/MoMo), and status states (PENDING -> PREPARING -> READY -> COMPLETED).   order_items: Junction table linking orders to menu items and quantities.   2. Complex SQL Query ExampleSQLSELECT 
    o.id AS order_id,
    o.customer_name,
    o.status,
    o.created_at,
    SUM(oi.quantity * mi.price) AS total_amount
FROM orders o
JOIN order_items oi ON o.id = oi.order_id
JOIN menu_items mi ON oi.menu_item_id = mi.id
WHERE o.status IN ('PENDING', 'PREPARING')
GROUP BY o.id, o.customer_name, o.status, o.created_at
ORDER BY o.created_at ASC;
