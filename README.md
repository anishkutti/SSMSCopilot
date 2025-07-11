# Sql Server Management Studio 21 (SSMS) Integration with Copilot

SQL Server Management Studio (SSMS) 21 Integration with Copilot marks a significant leap forward in developer productivity and intelligent database management.

<kbd> 
<img width="572" height="350" alt="ssmsCopilotBanner"  src="https://github.com/user-attachments/assets/ff91bc58-f859-49fe-89e0-2d1489b630eb" style="border: 2px solid grey;border-radius: 20px;"/>
</kbd> 


With Copilot embedded directly into SSMS, SQL developers can now leverage natural language prompts to generate T-SQL queries, optimize performance, and troubleshoot issues—all within their familiar development environment. 

This integration brings AI-assisted coding, context-aware suggestions, and real-time insights into query plans and schema design, streamlining complex tasks and accelerating development cycles. 

Whether you're writing stored procedures, analyzing execution plans, or exploring data, Copilot in SSMS 21 transforms how developers interact with SQL Server.


## Examples by Database Persona's

| Role                        | Copilot Scenarios & Examples                                                                                   |
|-----------------------------|--------------------------------------------------------------------------------------------|
| Database Administrator (DBA)| [DBA Examples](./1_DBA/README.md)                                                            |
| SQL Developer               | [SQL Developer Examples](./2_SQL_Developer/README.md)                                         |
| Data Analyst                | [Data Analyst Examples](./3_Data_Analyst/README.md)                                           |
| Application Developer       | [App Developer Examples](./ApplicationDeveloper/README.md)                                 |
| DevOps                      | [DevOps Examples](./4_DevOps/README.md)                                                      |
| End User                    | [End User Examples](./EndUser/README.md)



## Automation 
	* Creating tables and populating it
		Create a table having automobile parts. Include 50 columns. Add sample records which looks real. execute it

	* Create realtional tables and populate it
		"Create customer_demo, product_demo, sales_demo  tables
		Link all together
		Add atleast 5 columns in customer_demo and sales_demo
		Add 50 sample records which has real product names and customer names in each table
		Use tech company names"
	* Add 100 more sample data in dbo.sales_demo for year 2023. use customer_id between 1 to 5

	* Add 10 new columns in product_demo. make column names look real


## Data Transform & Curate
	* Write a stored proc which will create a flat table and populate it with customer, product and sales info by month

## New Feature Exploration
	* Show new t-sql enhancements in sql 2025	
	
	* Give example of JSON_ARRAYAGG
