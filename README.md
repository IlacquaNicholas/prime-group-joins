# prime-group-joins

### Tasks
1. Get all customers and their addresses.
    SELECT * FROM "addresses"
    JOIN "customers"
    ON "addresses"."id"="customers"."id"

2. Get all orders and their line items (orders, quantity and product).
    SELECT * FROM "orders"
    JOIN "line_items"
    ON "orders"."id"="line_items"."id"

3. Which warehouses have cheetos?
 SELECT * FROM "warehouse" 
    JOIN "warehouse_product" 
    on "warehouse"."id"="warehouse_product"."warehouse_id" 
    WHERE "product_id"=5;
  

4. Which warehouses have diet pepsi?
SELECT * FROM "warehouse" 
    JOIN "warehouse_product" 
     on "warehouse"."id"="warehouse_product"."warehouse_id" 
    WHERE "product_id"=6;

5. Get the number of orders for each customer. NOTE: It is OK if 
those without orders are not included in results.
SELECT "customers".*, COUNT(*) from "customers" 
  JOIN "addresses" 
  on "customers"."id"="addresses"."customer_id"
  JOIN "orders" 
  on "addresses"."id"="orders"."address_id" 
  GROUP BY "customers"."id" 

6.  How many customers do we have?
    SELECT count("customers") FROM "customers" 

7. How many products do we carry?
   SELECT count("products") FROM "products"

8. What is the total available on-hand quantity of diet pepsi?

  SELECT  SUM("on_hand") from "warehouse_product" 
  WHERE "product_id"=6;
  
