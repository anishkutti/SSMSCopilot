# Sql Server Management Studio 21 (SSMS) Integration with Copilot for Sql Developers

SQL Server Management Studio (SSMS) Copilot is a powerful AI assistant that significantly enhances the productivity and capabilities of SQL Server developers.

<img width="250" height="250" alt="sqldev" src="https://github.com/user-attachments/assets/29efd10d-ee62-4af6-af6b-74a26f5ca1fe" />

## Document Table Purpose
* Add extended property named TableInfo to all tables. Populate it with meaniful table purpose

 ## Assist New Joinners
* Explain me the database tables
* Is any tables connected to each other
* Show queries from query store which is the slowest
* Explain me the database tables. Include tableInfo extended property
* Show me the frequently executed stored procs
* 	
* Is any table having confidential fields like social

# Tunning and Re-writing
* Add comments in the  stored proc dbo.GetCustomerOrders. Also re-write it
* Before:
  CREATE PROCEDURE GetCustomerOrders
    @CustomerID INT
   AS
   BEGIN
       SELECT *
       FROM dbo.sales_demo
       WHERE Customer_ID = @CustomerID
         AND sales_date IN (
             SELECT MAX(sales_date)
             FROM sales_demo
             WHERE Customer_ID = @CustomerID
         );
   END;
  
   After
     Changes Made:
   1.	Explicit Column Selection: Replaced SELECT * with specific column names (Customer_ID, sales_date, sales_amount) to improve clarity and performance.
   2.	Simplified Subquery Logic: Used = instead of IN for matching the latest sales date, as MAX returns a single value.
   3.	Added Comments: Documented each part of the procedure for better readability and maintainability.
      
     -- Created by Copilot in SSMS - review carefully before executing
     /*
     Purpose:
     This stored procedure retrieves the most recent sales record(s) for a specific customer from the `dbo.sales_demo` table. 
     It uses the `@CustomerID` parameter to filter the data and ensures only the latest sales date is considered.
     */
     
     -- Declare the stored procedure and its parameter
     CREATE PROCEDURE dbo.GetCustomerOrders
         @CustomerID INT -- Input parameter for filtering by customer ID
     AS
     BEGIN
         -- Retrieve the most recent sales record(s) for the specified customer
         SELECT Customer_ID, sales_date, sales_amount -- Explicitly list required columns
         FROM dbo.sales_demo
         WHERE Customer_ID = @CustomerID -- Filter by customer ID
           AND sales_date = ( -- Match the latest sales date for the customer
               SELECT MAX(sales_date) -- Get the latest sales date
               FROM dbo.sales_demo
               WHERE Customer_ID = @CustomerID -- Filter by customer ID
           );
     END;
