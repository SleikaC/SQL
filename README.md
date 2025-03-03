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




