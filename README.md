## Analysis Scenarios and Queries

### 1. Filtering Customers by Age
**Scenario:** Analyze customers who are adults (age 18 and above).
- **Query:** Load the dataset and filter out customers with `age < 18`.

-- 1. Filter customers by age (18 and above)
adults = FILTER data BY age >= 18;
dump adults;

![filtering](https://github.com/user-attachments/assets/8b754e87-6e52-4372-8a51-f03b57d6ca28)


### 2. Grouping by Customer and Calculating Total Sales
**Scenario:** Calculate the total order amount for each customer.
- **Query:** Group the data by `customer_id` and calculate the total sales (sum of `amount`) for each customer.

-- 2. Group by customer and calculate total sales
grouped_by_customer = GROUP data BY customer_id;
total_sales = FOREACH grouped_by_customer GENERATE group AS customer_id, SUM(data.amount) AS total_amount;
dump total_sales;

![grouping](https://github.com/user-attachments/assets/82d8f794-96bd-40a6-b014-d32589ab582e)


### 3. Joining Orders with Customer Information
**Scenario:** Combine customer details with order information for a detailed view.
- **Query:** Join the dataset with itself on `customer_id` to display `order_id`, `name`, `location`, and `order_date`.
  
-- 3. Join orders with customer information (simplified to generate required columns)
orders_details = FOREACH data GENERATE order_id, name, location, order_date;
dump order_details;

![joining](https://github.com/user-attachments/assets/4ae69dd5-fc45-4eed-9dd7-36fd25a85a02)

### 4. Removing Duplicate Orders
**Scenario:** Remove duplicate records due to potential system errors.
- **Query:** Load the dataset and remove any duplicate entries based on `order_id`.
  
-- 4. Remove duplicate orders based on order_id
unique_orders = DISTINCT data;
dump unique_orders;

![duplicate_removal](https://github.com/user-attachments/assets/c3eaddd1-26d4-4bf2-8c08-10ccc4fa772c)


### 5. Sorting Orders by Amount
**Scenario:** Identify the highest value orders.
- **Query:** Load the dataset, sort by `amount` in descending order, and display the top 3 highest orders.

-- 5. Sort orders by amount (Top 3 highest orders)
sorted_orders = ORDER data BY amount DESC;
top_3_orders = LIMIT sorted_orders 3;
dump top_3_orders;

  ![sorting](https://github.com/user-attachments/assets/1ee216fb-74b2-4614-9963-f29c2b077800)



### 6. Aggregating and Filtering Data (Total Purchases Above $500)
**Scenario:** Identify customers whose total purchases exceed $500.
- **Query:** Group orders by `customer_id`, calculate the total purchase amount, and filter for customers who spent more than $500.

-- 6. Aggregating and filtering data (Total purchases above $500)
customer_total_purchases = FOREACH grouped_by_customer GENERATE group AS customer_id, SUM(data.amount) AS total_amount;
high_spenders = FILTER customer_total_purchases BY total_amount > 500;
dump high spenders;

![aggregating](https://github.com/user-attachments/assets/fcefae5e-2db4-444b-b9a1-b1d726ee5cfa)

