# store database
sql portfolio

CREATE TABLE superstore (
    item_id INTEGER PRIMARY KEY,
    item_name TEXT,
    category TEXT,
    price DECIMAL(10, 2),
    stock_quantity INTEGER,
    average_rating DECIMAL(3, 2)
);

INSERT INTO superstore (item_id, item_name, category, price, stock_quantity, average_rating)
VALUES
    (1, 'Stainless Steel Cookware Set', 'Kitchen Supplies', 89.99, 50, 4.6),
    (2, 'Memory Foam Mattress', 'Furnishings', 499.99, 30, 4.8),
    (3, 'Smart LED TV', 'Electronics', 549.00, 20, 4.5),
    (4, 'Robot Vacuum Cleaner', 'Appliances', 199.50, 40, 4.3),
    (5, 'Wireless Bluetooth Speaker', 'Electronics', 39.99, 60, 4.2),
    (6, 'Non-Stick Baking Set', 'Kitchen Supplies', 29.95, 80, 4.4),
    (7, 'Cotton Bedding Set', 'Furnishings', 89.00, 25, 4.7),
    (8, 'Smart Home Security Camera', 'Electronics', 79.95, 15, 4.1),
    (9, 'Air Purifier', 'Appliances', 129.50, 35, 4.6),
    (10, 'Premium Coffee Maker', 'Kitchen Supplies', 79.99, 50, 4.9),
    (11, 'Ergonomic Office Chair', 'Furnishings', 189.00, 20, 4.5),
    (12, 'Wireless Earbuds', 'Electronics', 49.99, 75, 4.3),
    (13, 'Slow Cooker', 'Appliances', 49.95, 30, 4.7),
    (14, 'Cutlery Set', 'Kitchen Supplies', 34.50, 40, 4.4),
    (15, 'Cozy Throw Blanket', 'Furnishings', 24.99, 100, 4.2);
    
    #For this project i use sql to query the superstore database to retrieve information about the items sold and their prices

    #ordering the item by price
    SELECT item_name, price
FROM superstore;

#ordering the item from the highest to the lowest price
SELECT item_name, price
FROM superstore
ORDER BY price desc;

#show a statistic of the sum of all items
SELECT sum (price)
FROM superstore;

#show a statistic of the maximum price of item in the category of "Appliances"
SELECT max (price)
FROM superstore
WHERE category= 'Appliances';

# BANK DATABASE

CREATE TABLE bank_products (
    product_id INTEGER PRIMARY KEY,
    product_name TEXT,
    product_type TEXT,
    interest_rate DECIMAL(5, 2),
    monthly_fee DECIMAL(6, 2),
    minimum_balance DECIMAL(10, 2)
);

INSERT INTO bank_products (product_id, product_name, product_type, interest_rate, monthly_fee, minimum_balance)
VALUES
    (1, 'Savings Account', 'Savings', 0.75, 0.00, 100.00),
    (2, 'Checking Account', 'Checking', 0.25, 5.00, 50.00),
    (3, 'Business Account', 'Business', 1.50, 10.00, 500.00),
    (4, 'Credit Card', 'Credit Card', 18.99, 0.00, 0.00),
    (5, 'Mortgage Loan', 'Loan', 3.25, 0.00, 100000.00),
    (6, 'Certificate of Deposit', 'Savings', 1.50, 0.00, 1000.00),
    (7, 'Student Checking Account', 'Checking', 0.10, 0.00, 10.00),
    (8, 'Business Credit Card', 'Credit Card', 16.99, 0.00, 0.00),
    (9, 'Home Equity Loan', 'Loan', 4.50, 0.00, 50000.00),
    (10, 'IRA Account', 'Savings', 1.25, 0.00, 500.00),
    (11, 'Personal Loan', 'Loan', 8.75, 0.00, 5000.00),
    (12, 'Money Market Account', 'Savings', 1.00, 0.00, 500.00),
    (13, 'Youth Savings Account', 'Savings', 0.50, 0.00, 10.00),
    (14, 'Rewards Credit Card', 'Credit Card', 21.99, 0.00, 0.00),
    (15, 'Auto Loan', 'Loan', 4.25, 0.00, 20000.00);
    
#For this project i use sql to query the bank database so i can find the best option for certain customer

#Selecting all the product name to know my options
SELECT product_name
FROM bank_products;

#uses OR to show the product names that have a Checking OR Savings product type
SELECT product_name
FROM bank_products
WHERE product_type = "Checking"
OR product_type = "Saving";

#uses AND to show the product names that have a "Savings" product type AND have an interest_rate of at least 0.75, AND have no monthly fee
SELECT product_name,interest_rate
FROM bank_products
WHERE product_type="Saving"
AND interest_rate>=0.75
AND monthly_fee=0;

# Fortune 500 database
CREATE TABLE fortune_companies (
    company_id INTEGER PRIMARY KEY,
    company_name TEXT,
    industry TEXT,
    revenue REAL,
    employees INTEGER,
    healthcare_benefits BIT,
    paid_time_off_days INTEGER,
    maternity_leave_weeks INTEGER,
    avg_employee_tenure REAL
);

INSERT INTO fortune_companies (company_name, industry, revenue, employees, healthcare_benefits, paid_time_off_days, maternity_leave_weeks, avg_employee_tenure)
VALUES
    ('Apple Inc.', 'Technology', 365.7, 147000, 1, 20, 12, 4.5),
    ('Walmart Inc.', 'Retail', 523.96, 2200000, 1, 15, 8, 6.2),
    ('Exxon Mobil Corporation', 'Energy', 265.01, 72000, 0, 18, 6, 7.8),
    ('Amazon.com Inc.', 'Technology', 386.06, 1370000, 1, 22, 14, 5.1),
    ('JPMorgan Chase & Co.', 'Financials', 160.1, 255998, 1, 21, 12, 6.9),
    ('Verizon Communications Inc.', 'Telecommunications', 131.88, 132600, 0, 15, 6, 5.5),
    ('Company A', 'Retail', 235.4, 2000, 1, 18, 10, 5.8),
    ('Company B', 'Healthcare', 400.7, 2300, 1, 22, 13, 5.7),
    ('Company C', 'Manufacturing', 300.2, 2000, 1, 18, 10, 5.8),
    ('Company D', 'Healthcare', 150.5, 3500, 1, 20, 12, 6.5),
    ('Company E', 'Finance', 280.7, 1800, 0, 14, 8, 4.2),
    ('Company F', 'Technology', 420.1, 2500, 1, 22, 14, 7.1),
    ('Company G', 'Retail', 190.8, 1500, 1, 16, 9, 5.3),
    ('Company H', 'Energy', 280.5, 2200, 0, 15, 8, 6.8),
    ('Company I', 'Telecommunications', 110.3, 1800, 1, 19, 11, 4.9),
    ('Company J', 'Manufacturing', 390.6, 2700, 1, 21, 13, 6.2),
    ('Company K', 'Healthcare', 180.2, 3200, 1, 17, 9, 7.4),
    ('Company L', 'Finance', 230.4, 1900, 0, 13, 7, 5.6),
    ('Company M', 'Technology', 340.9, 2800, 1, 23, 15, 6.9),
    ('Company N', 'Retail', 200.6, 1600, 1, 15, 8, 4.7),
    ('Company O', 'Energy', 260.2, 2400, 0, 14, 7, 6.1),
    ('Company P', 'Telecommunications', 130.5, 2100, 1, 20, 12, 5.3),
    ('Company Q', 'Manufacturing', 360.0, 2900, 1, 22, 14, 7.8),
    ('Company R', 'Technology', 400.7, 2300, 1, 22, 13, 5.7),
    ('Company S', 'Retail', 210.8, 1600, 0, 16, 9, 4.9),
    ('Company T', 'Energy', 290.5, 2200, 1, 15, 8, 7.2),
    ('Company U', 'Telecommunications', 140.3, 1900, 1, 20, 12, 6.1),
    ('Company V', 'Manufacturing', 350.6, 2800, 1, 22, 14, 5.4),
    ('Company W', 'Healthcare', 160.2, 3300, 0, 18, 10, 4.8),
    ('Company X', 'Finance', 240.4, 2000, 1, 13, 7, 7.1),
    ('Company Y', 'Technology', 320.9, 2700, 1, 23, 15, 5.6),
    ('Company Z', 'Retail', 180.6, 1400, 0, 14, 8, 6.3),
    ('Company AA', 'Energy', 240.2, 2600, 1, 17, 9, 6.5),
    ('Company BB', 'Telecommunications', 120.5, 2100, 0, 19, 11, 4.5),
    ('Company CC', 'Manufacturing', 380.0, 3000, 1, 21, 13, 7.3),
    ('Company DD', 'Healthcare', 170.2, 3200, 1, 17, 9, 5.8),
    ('Company EE', 'Finance', 250.4, 1900, 0, 12, 6, 6.4),
    ('Company FF', 'Technology', 300.9, 2500, 1, 24, 16, 6.9),
    ('Company GG', 'Retail', 190.6, 1700, 0, 13, 7, 5.2),
    ('Company HH', 'Energy', 280.2, 2300, 1, 16, 9, 6.8),
    ('Company II', 'Telecommunications', 110.5, 2000, 1, 21, 12, 4.9),
    ('Company JJ', 'Manufacturing', 370.0, 3100, 1, 20, 12, 7.6),
    ('Company KK', 'Healthcare', 150.2, 3400, 0, 16, 8, 5.3);
    

    ~ In this SQL i'm retrieving data about customers and their order using a database that has multiple tables

    1- How many products were sold in January?
    
SELECT COUNT (orderID)
FROM JanSales
WHERE lenght (orderID)=6
 AND orderID <>'order id';

    2-How many of those orders were an iPhone?
    
SELECT COUNT(orderid)
FROM JanSales
WHERE product= iPhone
AND lenght(orderid)= 6
AND orderid <> 'orderid';

 3-Select the customer account numbers for all the orders that were placed in February.
 
SELECT distinct acctnum
FROM customers
INNER JOIN FebSales
ON customers.order_id=FebSales.orderID;

 4-Which product was the cheapest one sold in January, and what was the price?
 
SELECT distinct Product, price
FROM JanSales
WHERE price in (SELECT MIN (price) FROM JanSales);

 5-What is the total revenue for each product sold in January? 
 
SELECT SUM (Quantity)*price as revenue,product
FROM JanSales
GROUP BY Product;

 6-Which products were sold in February at 548 Lincoln St, Seattle, WA 98101, how many of each were sold, and what was the total revenue?
 
SELECT SUM (quantity),Product,SUM (quantity)*price as revenue
FROM FebSales
WHERE location = '548 Lincoln St,Seattle, WA 98191'
GROUP BY  Product;

7-How many customers ordered more than 2 products at a time in February, and what was the average amount spent for those customers?

SELECT COUNT (customers.acctnum),AVG (quantity *price)
FROM FebSales
LEFT JOIN customers
ON FebSales.orderID = customers.order_id
WHERE FebSales.Quantity>2;

8-List all the products sold in Los Angeles in February, and include how many of each were sold
SELECT Product, SUM(quantity) 
FROM FebSales
WHERE location LIKE '%Los Angeles%'
GROUP BY Product;

9- Which locations in New York received at least 3 orders in January, and how many orders did they each receive?

SELECT location, COUNT (orderID)
FROM JanSales
WHERE location LIKE '%NY%'
AND length (orderID)=6
AND orderID <> 'Order ID'
GROUP BY location 
HAVING COUNT (orderID)>2;

10- How many of each type of headphone were sold in February?

SELECT Product, SUM (Quantity) as Quantity
FROM FebSales
WHERE Product LIKE '%headphone%'
GROUP BY Product;

11- What was the average amount spent per account in February?

SELECT SUM(quantity*price)/ COUNT (customers.acctnum)
FROM FebSales
LEFT JOIN customers
ON FebSales.orderID=customers.order_id
WHERE length (orderID)=6
AND orderID<> 'Order ID';

12- What was the average quantity of products purchased per account in February? 

SELECT SUM (quantity*product)/COUNT (customers.acctnum)
FROM FebSales
LEFT JOIN customers
ON FebSales.orderID=customers.acctnum
WHERE length (orderID)=6
AND orderid<> 'Order ID';

13- Which product brought in the most revenue in January and how much revenue did it bring in total?

SELECT SUM (quantity*price), Product
FROM  JanSales
GROUP BY product
ORDER BY SUM (quantity*price) desc
LIMIT 1;  
    
    

    



