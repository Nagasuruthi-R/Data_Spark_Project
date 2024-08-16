## DataSpark: Illuminating Insights for Global Electronics
### Introduction:
Global Electronics is harnessing the power of data to stay competitive in the consumer 
electronics market. As part of Data Analytics team, I conduct an in depth Exploratory Data Analysis 
across multiple datasets. The goal is to uncover actionable insights that will enhance customer 
satisfaction, optimize operation and drive overall business growth.
### Data Preprocessing and Cleaning:
1. Imported necessary libraries: pandas and timedelta(datetime).
2. Created Functions:
#### “process customer()” Function:
 1. Loaded customers data from CSV file.
 2. Converts Birthday column into date time format, retaining only date.
 3. Drops the state_code column from the dataset.
 4. Finally saved the cleaned dataset into different excel file for backup.
#### “process stores()” Function:
1. Loaded stores data from CSV file.
2. Converts the open_date column into date time format.
3. Fills missing value in the “Square Meters” column with 0.
4. Finally saved the cleaned stores dataset into different excel file.
#### “process exchange rates()” Function:
1. Loaded exchange_rates data from CSV file.
2. Converts the date column to a date time format.
3. Saved the cleaned exchange rates file into different excel file.
#### “process products()” Function:
1. Loads products data from CSV file.
2. Converts “unit cost USD” and “unit price USD” columns from strings to float by removing any 
symbols like $, whitespace, commas.
3. Fills missing values in this column with 0.
4. Saves the cleaned data into an excel file.
#### “process sales()” Function:
1. Loaded products data from CSV file.
2. Converts the order date and delivery date column into the date time format.
3. Calculates the difference in days between order date and delivery date.
4. Fills missing delivery date values with the order date plus average delivery duration 
(calculated from the available data)
5. Drops the difference column which is used for delivery time calculations.
6. Finally saved the cleaned sales data into excel file.
#### “process all data()” Function:
1. To execute all the individual data processing functions.
2. Calls each of the above functions in sequence to process the customers, stores, products, 
exchange rates, sales functions.
## Database Creation in Mysql:
1. Mysql connection: Connects to the Mysql server using “mysql.connector()
2.  Created a new database called “global_electronics”.
## Tables Merging Using Keys:
### Created Tables:
#### Customers Table:
Customers: customer_key (primary key), Gender, Name, City, state, zip_code, country, 
continent, Birthday. 
#### Stores Table:
Stores: Store Key (primary key), state, country, square meters , open date
#### Exchange-rates Table:
Exchange_rates: Date, Currency, Exchange.
#### Products Table:
Products: product key (primary key), product name, color, brand, unit cost USD, unit price USD, 
Category, subcategory, category key, subcategory key.
#### Sales Table:
Sales: order number (primary key), line item (primary key), order date, delivery date, customer 
key (foreign key), store key (foreign key), product key (foreign key), quantity, currency code
## Inserted Data into Tables:
1. Data Loading: The code is designed to load data from excel files into pandas dataframe.
(“df_customers”, “df_products”, “df_exchange_rates”, “df_stores”, “df_sales”).
 Column Mapping: A dictionary named column mappings is used to map column name from the 
excel files to the corresponding columns in the Mysql table.
2. Insert functions: 
--->This function takes a dataframe , a table name, cursor object and insert each row in the 
DataFrame into corresponding Mysql table.
--->SQL queries are dynamically constructed and executed using the cursor.
--->This first insert data into stores, products, exchange_rates, exchange_rates and then finally 
sales table to ensure foreign key constraints linking the stores, custo,ers, products table.
3. Error Handling:
--->The code includes try-except block to handle errors that might occur during the connection 
to the database, table creation and data insertion process.
--->If an error occurs, it prints the error message and continues executing the rest of the code.
4. Execution and Output:
--->The code prints the message, if my output is correct or it prints the error message if anything 
occurs.
## Import datasets into Power BI:
I imported datasets into power bi using import icon (Mysql database) 
## Data Modelling Flowchart:
![global_electronics_flowchart](https://github.com/user-attachments/assets/0062122c-91a0-4428-9551-5838490f86c7)
## Visualization in Power BI:
### Demographic Distribution:
a) Customer analysis: Analyzed number of customers spreads across the world using female and 
male categorization , age category
b) To visualize: used “Clustered column bar chart”, “pie charts”, “slicers”, “Map”
![image](https://github.com/user-attachments/assets/3b5c4a4f-2cb2-4a1e-8dac-b111efc684dc)
### Purchase Patterns:
a) Purchase Frequencies Based on Order: Created a summary table which has order value, average 
order value, purchase frequencies, total quantity sold and used all of these measures to visualize 
purchase trends using age category and products category, subcategory.
b) To visualize: used “stacked area chart”, “Line and clustered column chart”,” pie charts”, “slicers”


