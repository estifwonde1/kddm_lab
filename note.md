# Assignment 1: Note

(a) `customer_id` is different on every row (99,441 distinct in 99,441 rows) because a new one is created for each order, but `customer_unique_id` stays the same when the same person buys again (96,096 distinct). So to count customers I would use `count(DISTINCT customer_unique_id)`, not `customer_id`.

(b) `order_items` is the junction table because it sits between `orders`, `products` and `sellers`, and it solves the many-to-many between orders and products (one order can have many products, and one product can be in many orders), and the same for orders and sellers.

(c) The data is stricter than my diagram for `products` and `sellers`: every one of them has at least one item (minimum 1), but I still drew the circle since a product can be listed or a seller can join before the first sale. The circle between `orders` and `order_items` is justified, because 775 orders have no items at all, mostly `unavailable` and `canceled` ones.