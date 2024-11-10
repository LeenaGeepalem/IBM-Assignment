## Analysis Scenarios and Queries

### 1. Filtering Customers by Age
**Scenario:** Analyze customers who are adults (age 18 and above).
- **Query:** Load the dataset and filter out customers with `age < 18`.


![filtering](https://github.com/user-attachments/assets/8b754e87-6e52-4372-8a51-f03b57d6ca28)


### 2. Grouping by Customer and Calculating Total Sales
**Scenario:** Calculate the total order amount for each customer.
- **Query:** Group the data by `customer_id` and calculate the total sales (sum of `amount`) for each customer.


![grouping](https://github.com/user-attachments/assets/82d8f794-96bd-40a6-b014-d32589ab582e)


### 3. Joining Orders with Customer Information
**Scenario:** Combine customer details with order information for a detailed view.
- **Query:** Join the dataset with itself on `customer_id` to display `order_id`, `name`, `location`, and `order_date`.
  
![joining](https://github.com/user-attachments/assets/4ae69dd5-fc45-4eed-9dd7-36fd25a85a02)

### 4. Removing Duplicate Orders
**Scenario:** Remove duplicate records due to potential system errors.
- **Query:** Load the dataset and remove any duplicate entries based on `order_id`.

![duplicate_removal](https://github.com/user-attachments/assets/c3eaddd1-26d4-4bf2-8c08-10ccc4fa772c)


### 5. Sorting Orders by Amount
**Scenario:** Identify the highest value orders.
- **Query:** Load the dataset, sort by `amount` in descending order, and display the top 3 highest orders.

  ![sorting](https://github.com/user-attachments/assets/1ee216fb-74b2-4614-9963-f29c2b077800)



### 6. Aggregating and Filtering Data (Total Purchases Above $500)
**Scenario:** Identify customers whose total purchases exceed $500.
- **Query:** Group orders by `customer_id`, calculate the total purchase amount, and filter for customers who spent more than $500.

![aggregating](https://github.com/user-attachments/assets/fcefae5e-2db4-444b-b9a1-b1d726ee5cfa)

