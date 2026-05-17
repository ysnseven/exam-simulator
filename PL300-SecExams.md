# PL-300 Practice Questions — SecExams.com
<!-- Source: PL300180.pdf (Q1-28), PL300153219.pdf (Q59-88), PL300342404.pdf (Q149-178) -->

## Question #1 (HOTSPOT)

You plan to create the Power BI model shown in the exhibit.

The data has the following refresh requirements:
- Customer must be refreshed daily.
- Date must be refreshed once every three years.
- Sales must be refreshed in near real time.
- SalesAggregate must be refreshed once per week.

You need to select the storage modes for the tables. The solution must meet the following requirements:
- Minimize the load times of visuals.
- Ensure that the data is loaded to the model based on the refresh requirements.

Which storage mode should you select for each table?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Customer: Dual
- Date: Dual
- Sales: DirectQuery
- SalesAggregate: Import

**Explanation:**
Customer uses Dual mode — acts as either cached or not cached depending on query context.
Date uses Dual — dimension tables use Dual to reduce limited relationships and improve performance.
Sales uses DirectQuery — data must be near real time so no caching.
SalesAggregate uses Import — cached for fast performance; refreshed weekly.

Reference: https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-storage-mode

---

## Question #2

You have a project management app that is fully hosted in Microsoft Teams. The app was developed by using Microsoft Power Apps.
You need to create a Power BI report that connects to the project management app.
Which connector should you select?

A) Microsoft Teams Personal Analytics
B) SQL Server database
C) Dataverse
D) Dataflows

**Correct Answer: C**

**Explanation:**
The Power Platform category provides: Power BI datasets, Power BI dataflows, Common Data Service (Legacy), Dataverse. Microsoft Dataverse for Teams is a built-in low-code data platform that stores data for Power Apps on Microsoft Teams.

Reference: https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-data-sources

---

## Question #3

For the sales department at your company, you publish a Power BI report that imports data from a Microsoft Excel file located in a Microsoft SharePoint folder. The data model contains several measures.
You need to create a Power BI report from the existing data. The solution must minimize download effort.
Which type of data source should you use?

A) Power BI dataset
B) A SharePoint folder
C) Power BI dataflows
D) An Excel workbook

**Correct Answer: B**

**Explanation:**
Connect to a SharePoint folder: From Get Data, select SharePoint folder → paste site URL → authenticate → select Combine & Load. This connects directly to the SharePoint-hosted file without downloading.

Reference: https://docs.microsoft.com/en-us/power-query/connectors/sharepointfolder

---

## Question #4

You import two Microsoft Excel tables named Customer and Address into Power Query. Customer contains: Customer ID, Customer Name, Phone, Email Address, Address ID. Address contains: Address ID, Address Line 1, Address Line 2, City, State/Region, Country, Postal Code.
Each Customer ID represents a unique customer. Each Address ID represents a unique address.
You need to create a query that has one row per customer. Each row must contain City, State/Region, and Country for each customer.
What should you do?

A) Merge the Customer and Address tables.
B) Group the Customer and Address tables by the Address ID column.
C) Transpose the Customer and Address tables.
D) Append the Customer and Address tables.

**Correct Answer: A**

**Explanation:**
A merge queries operation joins two existing tables together based on matching values from one or multiple columns. Merge Customer and Address on the Address ID column to produce one row per customer with address fields.

Reference: https://docs.microsoft.com/en-us/power-query/merge-queries-overview

---

## Question #5 (HOTSPOT)

You have two Azure SQL databases that contain the same tables and columns. For each database, you create a query that retrieves data from a table named Customer.
You need to combine the Customer tables into a single table. The solution must minimize the size of the data model and support scheduled refresh in powerbi.com.
What should you do?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Option to use to combine the Customer tables: Append Queries as New
- Action to perform on the original two SQL database queries: Disable loading the query to the data model

**Explanation:**
Append Queries as New creates a new combined query without modifying the originals. Disabling load on the original queries prevents them from being loaded into the data model, minimizing model size.

---

## Question #6 (DRAG DROP)

In Power Query Editor, you have three queries named ProductCategory, ProductSubCategory, and Product.
Every Product has a ProductSubCategory.
Not every ProductSubCategory has a parent ProductCategory.
You need to merge the three queries into a single query. The solution must ensure the best performance in Power Query.
How should you merge the tables?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- ProductSubCategory merged with Product: Inner join
- ProductSubCategory merged with ProductCategory: Left outer join

**Explanation:**
Inner join: Every Product has a ProductSubCategory, so inner join returns only matching rows from both tables.
Left outer join: Not every ProductSubCategory has a parent ProductCategory, so use left outer join to keep all ProductSubCategory rows.

Reference: https://docs.microsoft.com/en-us/power-query/merge-queries-inner

---

## Question #7

You are building a Power BI report that uses data from an Azure SQL database. You import the following tables: Products (product catalog), Orders (high-level order information), Order Line Items (ID, quantity, price details).
You need to perform the following analyses:
- Orders sold over time that include a measure of the total order value
- Orders by attributes of products sold
The solution must minimize update times when interacting with visuals.
What should you do first?

A) From Power Query, merge the Order Line Items query and the Products query.
B) From Power Query, merge the Orders query and the Order Line Items query.
C) Calculate the count of orders per product by using a DAX function.
D) From Power Query, merge the Order Line Items query and the Products query.

**Correct Answer: B**

**Explanation:**
Merge the Orders and Order Line Items tables first to enable total order value calculation. This creates a fact table that supports time-based analysis and reduces model complexity.

Reference: https://docs.microsoft.com/en-us/power-query/merge-queries-overview

---

## Question #8

You have a Microsoft SharePoint Online site that contains several document libraries. One library contains manufacturing reports saved as Microsoft Excel files. All reports have the same data structure.
You need to use Power BI Desktop to load only the manufacturing reports to a table for analysis.
What should you do?

A) Get data from a SharePoint folder, enter the site URL, select Transform, then filter by folder path to the manufacturing reports library.
B) Get data from a SharePoint folder, enter the site URL, and then select Combine & Load.
C) Get data from a SharePoint list, enter the site URL, and then select Combine & Load.
D) Get data from a SharePoint list, enter the site URL, and then select Combine & Load.

**Correct Answer: A**

**Explanation:**
Use Get Data → SharePoint folder, then Transform to filter by folder path to include only the manufacturing reports library before combining.

Reference: https://docs.microsoft.com/en-us/power-query/connectors/sharepointfolder

---

## Question #9 (DRAG DROP)

You have a Microsoft Excel workbook with Sheet1 (Table1: abc, def, ghi, jkl, mno) and Sheet2 (Table2: abc, xyz, tuv, mno, pqr, stu).
You need to combine the products into a single table with no duplicate values.
Which three actions should you perform in sequence?

**Correct Answer:**
1. Import both tables from Excel
2. Append Table2 to Table1
3. Remove Duplicates

**Explanation:**
Append adds rows from Table2 to Table1. Remove Duplicates then eliminates duplicate entries, producing a unique combined list.

---

## Question #10

You have a CSV file that contains user complaints. The Logged column stores date and time in the format: 2018-12-31 at 08:59.
You need to analyze the complaints by the logged date and use a built-in date hierarchy.
What should you do?

A) Apply a transformation to extract the last 11 characters of the Logged column and set the data type to Date.
B) Change the data type of the Logged column to Date.
C) Split the Logged column by using "at" as the delimiter.
D) Apply a transformation to extract the first 11 characters of the Logged column.

**Correct Answer: C**

**Explanation:**
Split by "at" delimiter separates the date part from the time part. The left column (date) can then be typed as Date to enable the built-in date hierarchy.

---

## Question #11

You have a Microsoft Excel file in a Microsoft OneDrive folder. The file must be imported to a Power BI dataset.
You need to ensure that the dataset can be refreshed in powerbi.com.
Which two connectors can you use to connect to the file? Each correct answer presents a complete solution.
NOTE: Each correct selection is worth one point.

A) Excel Workbook
B) Text/CSV
C) Folder
D) SharePoint folder
E) Web

**Correct Answer: A and C**

**Explanation:**
The Excel Workbook and Folder connectors both support scheduled refresh for files stored in OneDrive/SharePoint when connected using the proper cloud path.

---

## Question #12 (HOTSPOT)

You are profiling data by using Power Query Editor. The State column shows: Valid 96%, Error 0%, Empty 4%, with 69 distinct values and 4 unique values.
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- There are [answer choice] different values in State including nulls: 69
- There are [answer choice] non-null values that occur only once in State: 4

**Explanation:**
Distinct = total number of different values (69). Unique = values that appear exactly once (4).

---

## Question #13 (HOTSPOT)

You have two CSV files: Products (ProductID, ProductName, SupplierID, CategoryID) and Categories (CategoryID, CategoryName, CategoryDescription).
You need to create a single table named Product containing all columns from both files.
How should you combine the queries, and what should you do on the Categories query?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Combine the queries by performing a: Merge
- On the Categories query: Disable the query load

**Explanation:**
Merge joins the two queries on CategoryID to produce the combined Product table. Disabling load on the Categories query prevents it from being loaded as a separate table in the model.

---

## Question #14

You have an Azure SQL database that contains sales transactions updated frequently. You need to generate reports to detect fraudulent transactions. Data must be visible within five minutes of an update.
How should you configure the data connection?

A) Add a SQL statement.
B) Set the Command timeout in minutes setting.
C) Set Data Connectivity mode to Import.
D) Set Data Connectivity mode to DirectQuery.

**Correct Answer: D**

**Explanation:**
DirectQuery queries the underlying data source live — no data is cached in Power BI Desktop. This ensures data is always current, meeting the five-minute visibility requirement.

Reference: https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-use-directquery

---

## Question #15 (DRAG DROP)

You have a folder that contains 100 CSV files. You need to make the file metadata available as a single dataset. The solution must NOT store the data of the CSV files.
Which three actions should you perform in sequence?

**Correct Answer:**
1. From Power BI Desktop, select Get Data, and then select Folder
2. From Power Query Editor, expand the Attributes column
3. From Power Query Editor, remove the Content column (do not combine it)

**Explanation:**
Selecting Folder in Get Data loads file metadata. Expanding Attributes exposes metadata columns. Removing the Content column ensures the actual file data is not loaded.

---

## Question #16

A BI developer creates a dataflow in Power BI using DirectQuery to access an on-premises SQL server. The Enhanced Dataflows Compute Engine is on.
You need to use the dataflow in a report. Requirements: minimize online processing, minimize calculation and render times, include data from the current year up to and including the previous day.
What should you do?

A) Create a dataflows connection with DirectQuery mode selected.
B) Create a dataflows connection with DirectQuery mode and configure a gateway connection.
C) Create a dataflows connection with Import mode and schedule a daily refresh.
D) Create a dataflows connection with Import mode and create a Power Automate solution to refresh hourly.

**Correct Answer: C**

**Explanation:**
Import mode caches data locally, minimizing calculation and render times. A daily refresh ensures data from the current year up to the previous day is available.

---

## Question #17

You are creating a report. You have a table with a free text field named col1. You need to analyze the distribution of string lengths without affecting the size of the model.
What should you do?

A) In the report, add a DAX calculated column that calculates the length of col1.
B) From Model view, set the distribution for the Column profile to group by length.
C) From Power Query Editor, add a column that calculates the length of col1.
D) From Power Query Editor, change the distribution for the Column profile to group by length.

**Correct Answer: A**

**Explanation:**
A DAX calculated column using LEN() calculates string length at query time and does not add data to the model. Power Query columns add data permanently.

---

## Question #18

You have reports for the HR department with row-level security (RLS). The company has multiple sales regions, each with an HR manager.
You need to ensure HR managers can interact with data from their region only and cannot change report layout.
How should you provide access?

A) Publish the reports in an app and grant the HR managers access permission.
B) Create a new workspace, copy datasets and reports, and add HR managers as members.
C) Publish the reports to a different workspace than the one hosting the datasets.
D) Add the HR managers as members of the existing workspace.

**Correct Answer: A**

**Explanation:**
Publishing as an app lets you assign viewing permissions that prevent layout changes. Combined with RLS, managers see only their region's data.

---

## Question #19

You need to provide a user with the ability to add members to a workspace. The solution must use the principle of least privilege.
Which role should you assign?

A) Viewer
B) Admin
C) Contributor
D) Member

**Correct Answer: D**

**Explanation:**
The Member role can add members or others with lower permissions. Admin can also do this but has more permissions than needed (principle of least privilege).

Reference: https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-roles-new-workspaces

---

## Question #20

You have a Power BI query named Sales with columns: ID, Sales_Date, Customer_ID, Delivery_Time, Status (Finished/Cancelled), Cancelled_Date. Only Finished rows and the date part of Sales_Date are used.
You need to reduce load times without affecting analysis. The solution must minimize the number of steps.
Which two actions achieve this goal? Each correct answer presents a complete solution.
NOTE: Each correct selection is worth one point.

A) Remove the rows where Sales[Status] = Cancelled.
B) Change the data type of Sales[Date] to DateTime.
C) Split Sales[Date] into separate date and time columns.
D) Remove Sales[Cancelled_Date].
E) Remove Sales[Customer_ID].

**Correct Answer: A and D**

**Explanation:**
A: Only finished records are used — removing cancelled rows reduces row count.
D: Cancelled_Date is only relevant for cancelled records, which are removed. Dropping this column reduces model size.

---

## Question #21

You build a report to analyze customer transactions from a Customer table (CustomerID, Name, State, Email) and a Transaction table (TransactionID, CustomerID, Date, Amount).
Which relationship should you use to link the tables?

A) one-to-many from Transaction to Customer
B) one-to-one between Customer and Transaction
C) many-to-many between Customer and Transaction
D) one-to-many from Customer to Transaction

**Correct Answer: D**

**Explanation:**
One Customer can have many Transactions. The one side is the primary key (Customer), the many side is the foreign key (Transaction).

---

## Question #22

You have a custom connector returning ID, From, To, Subject, Body, and Has Attachments for every email sent in the past year (10+ million records).
You build a report analyzing internal networks based on email recipients. You need to prevent report recipients from reading the emails. The solution must minimize model size.
What should you do?

A) From Model view, set Subject and Body columns to Hidden.
B) Remove the Subject and Body columns during import.
C) Implement RLS so recipients only see emails they sent.

**Correct Answer: B**

**Explanation:**
Removing columns during import reduces model size and prevents the data from ever entering the model, eliminating security risk at the source.

---

## Question #23 (HOTSPOT)

You create a Power BI dataset with a Business Unit table containing: Cost Center, Headcount, ID, Name.
You need to make the table available as an organizational data type in Microsoft Excel.
How should you configure the table properties?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Row label: Cost Center
- Key column: ID
- Is featured table: Yes

**Explanation:**
Row label appears as the cell value in Excel linked cells. Key column provides the unique row identifier. Setting Is Featured Table = Yes makes it available in Excel's Data Types Gallery.

Reference: https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-create-excel-featured-tables

---

## Question #24

You have a Power BI model. A manager can represent only a single country.
You need to set up RLS so managers only see their country's data. The number of RLS roles must be minimized.
Which two actions should you perform? Each correct answer presents a complete solution.
NOTE: Each correct selection is worth one point.

A) Create a single role that filters Country[Manager_Email] by using the USERNAME() DAX function.
B) Change the data type of Sales[Date] to DateTime.
C) For the relationship between Purchase Detail and Purchase, select Apply security filter in both directions.
D) Create one role for each country.
E) Change the Cross filter direction to Single.

**Correct Answer: A and C**

**Explanation:**
A: Using USERNAME() or USERPRINCIPALNAME() in a single role dynamically filters data by the logged-in manager, eliminating the need for one role per country.
C: Applying security filter in both directions ensures RLS propagates through all related tables including Purchase Detail.

Reference: https://docs.microsoft.com/en-us/power-bi/enterprise/service-admin-rls

---

## Question #25 (HOTSPOT)

You have a Power BI imported dataset with a star schema data model.
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Changing the [answer choice] setting of the relationships will improve report query performance: Assume Referential Integrity
- The data model is organized into a [answer choice]: Star schema

**Explanation:**
Assume Referential Integrity enables more efficient queries for DirectQuery by assuming no NULL/unmatched values in the join columns.
Star schema: fact table at center surrounded by dimension tables.

Reference: https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-assume-referential-integrity

---

## Question #26 (HOTSPOT)

You have a Power BI model with a Sales table and a related date table. Sales has a measure named Total Sales.
You need to create a measure that calculates total sales from the equivalent month of the previous year.
How should you complete the calculation?
NOTE: Each correct selection is worth one point.

Sales Previous Year =

**Correct Answer:**
- First dropdown: CALCULATE
- Time intelligence function: PARALLELPERIOD
- Date parameter: 'Date'[Month]

**Explanation:**
CALCULATE evaluates an expression in a modified filter context. PARALLELPERIOD shifts dates by a number of intervals (here -1 year) to return the parallel period of the previous year. Use 'Date'[Month] as the date column.

Reference: https://docs.microsoft.com/en-us/dax/parallelperiod-function-dax

---

## Question #27 (DRAG DROP)

You plan to create a report displaying sales data from the last year for multiple regions.
You need to restrict access to individual rows of data on a per-region basis using roles. The solution must use the principle of least privilege.
Which four actions should you perform in sequence?

**Correct Answer:**
1. Import data into the Power BI Desktop report
2. From the Modeling tab, select Manage Roles
3. Create a new role definition with a DAX filter expression
4. Assign users to the role in the Power BI service

**Explanation:**
RLS is defined in Power BI Desktop under Modeling → Manage Roles. Users are assigned in the Power BI service after publishing. Dynamic RLS using USERNAME()/USERPRINCIPALNAME() minimizes the number of roles needed.

Reference: https://docs.microsoft.com/en-us/power-bi/enterprise/service-admin-rls

---

## Question #28 (DRAG DROP)

You create a data model with tables: Sales_Region, Region_Manager, Sales_Manager, Manager.
Relationships: one-to-one between Sales_Region and Region_Manager; every Region_Manager record has a corresponding Manager; every Sales_Region has a corresponding Sales_Manager.
You need to denormalize the model to exclude the Manager table. Only managers associated to a sales region must be included.
Which three actions should you perform in sequence?

**Correct Answer:**
1. Merge [Sales_Region] and [Sales_Manager] by using an inner join
2. Merge [Region_Manager] and [Manager] by using an inner join
3. Merge the results into a new query named [Sales_region_and_Region_Manager]

**Explanation:**
Inner join between Region_Manager and Manager keeps only managers tied to a region (not all managers). This eliminates the separate Manager table while retaining only relevant managers.

Reference: https://docs.microsoft.com/en-us/power-query/merge-queries-inner

---

## Question #59 (HOTSPOT)

You have a Power BI report that contains a measure named Total Sales.
You need to create a new measure that will return the sum of Total Sales for a year up to a selected date.
How should you complete the DAX expression?
Measure = _____ ( [Total Sales], _____ )
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Box 1 (function): TOTALYTD
- Box 2 (date parameter): 'Date'[Date]

**Explanation:**
TOTALYTD evaluates the expression from the first day of the year to the last date in the specified dates column: TOTALYTD( [Sales Amount], 'Date'[Date] )

Reference: https://dax.guide/totalytd/

---

## Question #60 (DRAG DROP)

You have a Sales table (Transaction ID, Customer Key, Sales Date Key, Sales Amount) and a Transaction Size table (Transaction Size ID, Transaction Size, Min, Max — Small 0–10K, Medium 10K–100K, Large 100K–999M).
You need to create a calculated column to classify each transaction as small, medium, or large based on Sales Amount.
How should you complete the code?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Box 1: CALCULATE
- Box 2: AND
- Box 3: FILTER

**Explanation:**
Use CALCULATE with FILTER and AND conditions to classify transactions against the Transaction Size table ranges.

Reference: https://docs.microsoft.com/en-us/dax/calculate-function-dax

---

## Question #61

You have a report for the procurement department with a Suppliers table (100K rows) and a LineItems table (1 billion rows). There is a one-to-many relationship from Suppliers to LineItems.
You need to minimize the size of the dataset without affecting the visuals.
What should you do?

A) Merge Suppliers and LineItems.
B) Remove the LineItems[Description] column.
C) Remove rows from LineItems where Invoice Date is before last month.
D) Group LineItems by Invoice ID and Invoice Date with a sum of Price.

**Correct Answer: B**

**Explanation:**
LineItems[Description] is not used in any of the visuals. Removing unused columns reduces dataset size without affecting analysis.

---

## Question #62

You have a report for the marketing department with a Posts table and a Traffic table. The dataset takes a long time to refresh. You need to modify Posts and Traffic queries to reduce load times.
Which two actions should you perform? Each correct answer presents part of the solution.
NOTE: Each correct selection is worth one point.

A) Remove rows in Posts where Publish Date is in the last seven days.
B) Remove rows in Traffic where URL Visited does not contain "blog".
C) Remove Traffic[IP Address], Traffic[Browser Agent], and Traffic[Referring URL].
D) Remove Posts[Full Text] and Posts[Summary].

**Correct Answer: B and D**

**Explanation:**
B: Only blog traffic rows are useful — removing non-blog rows reduces Traffic table size.
D: Posts[Full Text] and Posts[Summary] are not used in any visual — removing these columns reduces Posts table size.

---

## Question #63 (DRAG DROP)

You have Excel data with columns: Department, Stage, School1, School2, School3, School4. You need to reshape it to: Department, School, Avg Score.
Which three actions should you perform in sequence in Power Query Editor?

**Correct Answer:**
1. Select the [Department] and [Stage] columns and unpivot the other columns
2. Rename the [Attribute] column as [School] and the [Value] column as [Score]
3. Group by [Department] and [School] with an average of [Score] as [Avg Score]

**Explanation:**
Unpivoting the School columns creates rows per school per department. Renaming gives meaningful column names. Grouping with average computes Avg Score per Department/School combination.

---

## Question #64

You have a report with a bar chart (customer count by segment) and a column chart (sales by month).
You need to ensure that when a segment is selected in the bar chart, you can see which portion of total monthly sales belongs to that segment.
How should the visual interactions be set on the column chart?

A) highlight
B) filter
C) no impact

**Correct Answer: A**

**Explanation:**
Highlight dims unrelated data but keeps it visible, showing the selected segment's portion within the overall monthly totals. Filter would remove unrelated data entirely.

Reference: https://docs.microsoft.com/en-us/power-bi/create-reports/power-bi-reports-filters-and-highlighting

---

## Question #65

A user creates a Power BI report named ReportA with a custom theme. You create a dashboard named DashboardA. You need DashboardA to use the custom theme with minimal effort.
Which two actions should you perform? Each correct answer presents part of the solution.
NOTE: Each correct selection is worth one point.

A) Publish ReportA to Power BI.
B) From ReportA, save the current theme.
C) Publish ReportA to the Power BI Community theme gallery.
D) From DashboardA, create a custom theme.
E) From DashboardA, upload a JSON theme.

**Correct Answer: A and E**

**Explanation:**
A: Publish ReportA to make it available in the Power BI service.
E: Save the theme from ReportA as JSON, then upload it to DashboardA via the JSON theme upload option.

Reference: https://docs.microsoft.com/en-us/power-bi/create-reports/service-dashboard-themes

---

## Question #66

You need to create a visualization that compares revenue and cost over time.
Which type of visualization should you use?

A) waterfall chart
B) stacked area chart
C) line chart
D) donut chart

**Correct Answer: C**

**Explanation:**
Line charts support multiple lines (revenue and cost) plotted over a shared time axis, making comparison easy.

---

## Question #67 (HOTSPOT)

You add a key influencers visual to a report.
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Identifying additional factors that increase attrition can be achieved by: adding more fields to Expand by
- Employee attrition is [answer choice] times greater when employees work overtime: 3

**Explanation:**
Adding fields to Expand by allows the visual to analyze additional factors without removing existing influencers.
The visual shows attrition is 3x more likely when employees work overtime.

Reference: https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-influencers

---

## Question #68

You build a report to help the sales team understand performance and drivers of sales. The team needs a single visualization to identify which factors affect success.
Which type of visualization should you use?

A) Key influencers
B) Line and clustered column chart
C) Q&A
D) Funnel chart

**Correct Answer: A**

**Explanation:**
The key influencers visual analyzes data, ranks contributing factors, and displays them as influencers — ideal for understanding what drives a metric.

Reference: https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-influencers

---

## Question #69 (HOTSPOT)

You have a table with columns: City, Total Sales, Occupation.
You need to create a key influencers visualization showing "What influences Total Sales to Increase."
How should you configure the visualization?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Analyze: Total Sales
- Explain by: Occupation

**Explanation:**
The Analyze field is the metric you want to understand (Total Sales). The Explain by field contains the factors to analyze (Occupation).

Reference: https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-influencers

---

## Question #70 (DRAG DROP)

You publish a dataset using data from an on-premises SQL Server database. The dataset must be refreshed daily.
You need to ensure Power BI service can connect and refresh the dataset.
Which four actions should you perform in sequence?

**Correct Answer:**
1. Configure an on-premises data gateway
2. Add a data source
3. Add the dataset owner to the data source
4. Configure a scheduled refresh

**Explanation:**
The gateway bridges on-premises SQL Server and the Power BI service. A data source is added under gateway configuration. The dataset owner must be added to access the data source. Finally, scheduled refresh is configured.

---

## Question #71

You attempt to connect Power BI Desktop to a Cassandra database. There is no specific connector for Cassandra in Get Data.
Which type of connector should you choose?

A) Microsoft SQL Server database
B) ODBC
C) OLE DB
D) OData

**Correct Answer: B**

**Explanation:**
The ODBC connector connects to any third-party ODBC driver by specifying a DSN or connection string, enabling connectivity to databases without a dedicated Power BI connector.

Reference: https://learn.microsoft.com/en-us/power-bi/connect-data/desktop-connect-generic-interfaces

---

## Question #72 (DRAG DROP)

You receive annual sales data in Excel with columns: Month, MonthNumber, 2019, 2020, 2021.
You need a report that: visualizes Sales over years and months, adds a slicer for month, adds a slicer for year.
Which three actions should you perform in sequence?

**Correct Answer:**
1. Select the Month and MonthNumber columns
2. Select Unpivot other columns
3. Rename the Attribute column as Year and the Value column as Sales

**Explanation:**
Selecting Month/MonthNumber and unpivoting the rest transforms year columns into rows. Renaming Attribute→Year and Value→Sales creates the structure needed for year and month slicers.

---

## Question #73 (HOTSPOT)

You connect Power BI Desktop to an Azure SQL database with: Server = mydb.database.windows.net, Database = db1, Data Connectivity mode = Import, Navigate using full hierarchy = unchecked.
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- The default timeout will be: 10 minutes
- The Navigator will display: only tables that contain data

**Explanation:**
Default connection timeout is 10 minutes. With "Navigate using full hierarchy" unchecked, only tables containing data are displayed.

Reference: https://learn.microsoft.com/en-us/power-query/connectors/azuresqldatabase

---

## Question #74 (HOTSPOT)

You are creating a quick measure using: Calculation = Rolling average, Period = Days.
You need a monthly rolling average measure for Sales over time.
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Base value: Total Sales
- Date: Date
- Period: Months

**Explanation:**
Total Sales is the measure to average. Date is the date column. Period = Months calculates a monthly rolling average.

---

## Question #75

You have a Sales table with daily records for 5 years linked to a dimDate table. You plan to create a measure returning total sales for March 2021 when March 2022 is selected.
Which DAX expression should you use?

A) CALCULATE(SUM(Sales[Sales]), PREVIOUSYEAR(dimDate[Date]))
B) TOTALYTD(SUM(Sales[Sales]), dimDate[Date])
C) CALCULATE(SUM(Sales[Sales]), SAMEPERIODLASTYEAR(dimDate[Date]))
D) SUM(Sales[Sales])

**Correct Answer: C**

**Explanation:**
SAMEPERIODLASTYEAR returns the same date range from the previous year. When March 2022 is selected, it returns March 2021 data. PREVIOUSYEAR would return the entire previous year (Jan–Dec 2021), not just March.

---

## Question #76

You use Power BI Desktop to load data from SQL Server and receive: ERROR [08001] timeout expired.
What are two ways to resolve the error? Each correct answer presents a complete solution.
NOTE: Each correct selection is worth one point.

A) Reduce the number of rows and columns returned by each query.
B) Split long-running queries into subsets of columns and use Power Query to merge the queries.
C) Use Power Query to combine long-running queries into one query.
D) Disable query folding on long-running queries.

**Correct Answer: A and B**

**Explanation:**
A reduces the result set size, reducing query time. B achieves the same by splitting the query into smaller parts that each complete within the timeout, then merging results in Power Query.

---

## Question #77

From Power Query Editor, you profile IoT data with columns: IoT GUID, IoT DateTime, IoT ID (both GUID and ID are unique per row).
You need to analyze IoT events by hour and day. The solution must improve dataset performance.
Solution: Split IoT DateTime into Date and Time columns.

Does this meet the goal?

A) Yes
B) No

**Correct Answer: B**

**Explanation:**
Splitting DateTime does not improve performance. The GUID column is also unique per row (high cardinality) and should be removed to improve performance.

---

## Question #78

Same IoT scenario as Q#77.
Solution: Remove the IoT GUID column and retain the IoT ID column.

Does this meet the goal?

A) Yes
B) No

**Correct Answer: A**

**Explanation:**
Removing the high-cardinality GUID column reduces dataset size and improves performance. IoT ID (also unique) still enables the required analysis.

---

## Question #79

Same IoT scenario as Q#77.
Solution: Change the IoT DateTime column to the Date data type.

Does this meet the goal?

A) Yes
B) No

**Correct Answer: B**

**Explanation:**
Changing to Date type loses the time portion, preventing hour-based analysis. The goal requires analyzing by both hour and day.

---

## Question #80

You have a Power BI report (550 MB PBIX, 12M rows, 15 AppSource + 10 default visuals, refreshed twice daily). Users say visuals load slowly.
What should you recommend?

A) Change DAX measures to use iterator functions.
B) Remove unused columns from tables in the data model.
C) Replace default visuals with AppSource visuals.
D) Increase the number of dataset refreshes.

**Correct Answer: B**

**Explanation:**
Removing unnecessary columns reduces the data model size, improving query and refresh performance.

---

## Question #81 (DRAG DROP)

You have Products and Sales tables with a one-to-many relationship. A report-level filter for Products is in place.
You need a measure returning the percent of total sales for each product that respects the report-level filter.

```
Percent of Product Sales =
VAR ProductSales = SUM('Sales'[Sales])
VAR AllSales =
  _____ (
    SUM('Sales'[Sales]),
    _____ ('Products'[Product])
  )
RETURN
DIVIDE(ProductSales, AllSales)
```

NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Box 1: CALCULATE
- Box 2: ALLSELECTED

**Explanation:**
ALLSELECTED removes visual-level filters but respects report-level filters, so the total denominator reflects the report filter. CALCULATE modifies the filter context to apply ALLSELECTED.

---

## Question #82

You have a data model with Product (Product ID, Product Name, Product Category) and Sales (Product ID, Order Date, Ship Date, Delivered Date, Invoice Date, Quantity, Sales Amount) tables. The auto date/time option is enabled.
You need to reduce the data model size while maintaining the ability to analyze by month and quarter.
Which two actions should you perform? Each correct answer presents part of the solution.
NOTE: Each correct selection is worth one point.

A) Create a relationship between the Date table and the Sales table.
B) Disable the auto date/time option.
C) Create a Date table and select Mark as Date Table.
D) Disable the load on the Date table.
E) Remove the relationship between the Product and Sales tables.

**Correct Answer: B and C**

**Explanation:**
Disabling auto date/time removes automatically generated hidden date tables (one per date column), significantly reducing model size. Creating a single shared Date table and marking it as a Date Table provides the month/quarter analysis capability.

---

## Question #83

Same large report scenario as Q#80 (550 MB, 12M rows, slow visuals).
What should you recommend?

A) Implement row-level security (RLS).
B) Remove unused columns from tables in the data model.
C) Replace default visuals with AppSource visuals.
D) Enable visual interactions.

**Correct Answer: B**

**Explanation:**
Removing unused columns reduces model size and improves performance. This is the primary optimization for large slow models.

---

## Question #84 (HOTSPOT)

You have a Stores table with columns: Store Name, Open Date, Status, State, City.
You need a calculated column named Active Store Name:
- When Status = "A": return Store Name
- When Status ≠ "A": return "Inactive - " & Store Name

Active Store Name = _____ ( [Status] = "A", [Store Name], "Inactive - " _____ [Store Name] )
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Box 1: IF
- Box 2: &

**Explanation:**
IF evaluates the condition. & is the DAX string concatenation operator used to prefix "Inactive - " to the Store Name.

---

## Question #85

You have a CSV file with a Logged column in format: 2018-12-31 at 08:59.
You need to analyze complaints by logged date using a built-in date hierarchy.
What should you do?

A) Apply a transformation to extract the first 11 characters and set data type to Date.
B) Add a conditional column outputting the year and set the data type to Whole Number.
C) Create a column by example starting with 2018-12-31 and set data type to Date.
D) Apply a transformation to extract the last 11 characters.

**Correct Answer: C**

**Explanation:**
Column by example recognizes the date pattern and extracts it automatically. Setting data type to Date enables the built-in date hierarchy.

---

## Question #86

Same IoT scenario as Q#77.
Solution: Create a custom column that concatenates IoT GUID and IoT ID, then delete both original columns.

Does this meet the goal?

A) Yes
B) No

**Correct Answer: B**

**Explanation:**
Concatenating columns does not extract hour/day from DateTime. This does not address the analysis requirement and does not improve performance.

---

## Question #87

You have an Employee table: Name, EmployeeID, ParentEmployeeID. All paths lead to the CEO (EmployeeID = ParentEmployeeID = 100).
You need a calculated column returning the count of levels from each employee to the CEO.
Which DAX expression should you use?

A) PATHLENGTH(PATH(Employee[EmployeeID], Employee[ParentEmployeeID]))
B) PATH(ITEM(Employee[EmployeeID], Employee[ParentEmployeeID], 1), Employee[ParentEmployeeID])
C) PATHCONTAINS(PATH(Employee[EmployeeID], Employee[ParentEmployeeID]), 1)
D) PATH(Employee[EmployeeID], Employee[ParentEmployeeID])

**Correct Answer: A**

**Explanation:**
PATH returns a string of all parent identifiers. PATHLENGTH counts the number of items in that path, which equals the number of levels from the employee to the CEO.

Reference: https://learn.microsoft.com/en-us/dax/path-function-dax

---

## Question #88

Same large report scenario as Q#80 (550 MB, 12M rows, slow visuals).
What should you recommend?

A) Replace default visuals with AppSource visuals.
B) Remove unused columns from tables in the data model.
C) Change the imported dataset to DirectQuery.
D) Increase the number of dataset refreshes.

**Correct Answer: B**

**Explanation:**
Removing unused columns reduces model size and improves performance. This is consistent with Q#80 and Q#83.

---

## Question #149

You need to create a visual that enables the adhoc exploration of data as shown in the following exhibit. (The exhibit shows a decomposition tree with Product Category, Supplier, and Customer Country dimensions.)
Which type of visual should you use?

A) smart narrative
B) decomposition tree
C) Q&A
D) key influencers

**Correct Answer: B**

**Explanation:**
The decomposition tree visual lets you visualize data across multiple dimensions, automatically aggregates data, and enables drilling down in any order. It is an AI visualization ideal for ad hoc exploration and root cause analysis.

Reference: https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-decomposition-tree

---

## Question #150

Your company associates each of 10 states to one of three regions (East, West, North). Your data model has employee info by state but no region info. You need to view employees by region as quickly as possible.
What should you do?

A) Create a new aggregation that summarizes by state.
B) Create a new aggregation that summarizes by employee.
C) Create a new group on the state column and set the Group type to List.
D) Create a new group on the state column and set the Group type to Bin.

**Correct Answer: C**

**Explanation:**
A List group in Power BI Desktop lets you manually assign states to named groups (regions). This is the fastest way to create region groupings without modifying the data source.

Reference: https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-grouping-and-binning

---

## Question #151

You need a visualization for the HR department showing historical employee counts and predicting trends for the next six months.
Which type of visualization should you use?

A) ribbon chart
B) scatter chart
C) line chart
D) key influencers

**Correct Answer: C**

**Explanation:**
Line charts support forecasting in Power BI. The best data for forecasting is a single time series line. Power BI can add forecast lines to line charts showing predicted trends.

---

## Question #152

You have a Power BI dashboard using an imported SQL Server dataset. The dashboard timestamp shows 12:03:06 PM.
What occurred at 12:03:06 PM?

A) A new transaction was added to the data source.
B) The dashboard tile cache refreshed.
C) A user added a comment to a tile.
D) A user pressed F5.

**Correct Answer: D**

**Explanation:**
Pressing F5 or the browser refresh button updates the dashboard charts with cached data and shows the refresh timestamp.

Reference: https://docs.microsoft.com/en-us/power-bi/connect-data/refresh-data

---

## Question #153 (HOTSPOT)

You need to create a Power BI report page with two views: Sales By Postal Code (map visual) and Sales By Month (column chart). Both must have a Chain slicer. Users switch views with buttons and the Chain selection must be maintained.
What is the minimum number of bookmarks required, and which property should you apply?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Minimum number of bookmarks: 2
- Property: Display

**Explanation:**
Two bookmarks — one per view. The Display property controls visual visibility (show/hide). The Chain slicer selection is preserved because bookmarks without the Data property checked don't capture filter state.

Reference: https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-bookmarks

---

## Question #154

You have a scatter chart showing Total Cost vs Total Sales over years by country. You need to show the relationship between Total Cost and Total Sales over time.
What should you do?

A) Add a play axis.
B) From the Analytics pane, add an Average line.
C) Add a slicer for the year.
D) Create a DAX measure that calculates year-over-year growth.

**Correct Answer: A**

**Explanation:**
A play axis animates scatter chart data points over time, showing how the relationship between Total Cost and Total Sales evolves year by year.

---

## Question #155 (HOTSPOT)

You have a Power BI dashboard. You need to ensure that on mobile devices the dashboard shows only: Total Sales, Total Quantity, and Total Sales by Parent Category — with reduced tile sizes.
What should you do?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Update the layout in: Report mobile layout
- Resize and move: The Total Sales by Parent Category tile

**Explanation:**
Report mobile layout lets you drag and drop tiles onto a phone canvas to create a mobile-optimized view. Resizing the bar chart tile makes it fit the mobile layout requirement.

Reference: https://docs.microsoft.com/en-us/power-bi/create-reports/power-bi-create-mobile-optimized-report-about

---

## Question #156

You are building a report to analyze customer segments dynamically based on Bounce Rate across source, geography, and demographics. The solution must minimize analysis effort.
Which type of visualization should you use?

A) decomposition tree
B) funnel chart
C) Q&A
D) key influencers

**Correct Answer: A**

**Explanation:**
The decomposition tree automatically aggregates data and enables drilling into dimensions in any order with AI assistance — ideal for dynamic multi-dimensional analysis with minimal effort.

Reference: https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-decomposition-tree

---

## Question #157

You have a table with approximately 1,000 rows of sales data. You need to identify outliers in the data.
Which type of visualization should you use?

A) area chart
B) scatter plot
C) pie chart
D) donut chart

**Correct Answer: B**

**Explanation:**
Scatter plots show the distribution of data points and make outliers (points far from the overall pattern) visually obvious.

---

## Question #158

You have a report with three pages. One page contains a KPI visualization. You need to filter all visualizations except the KPI.
Which two actions should you perform? Each correct answer presents part of the solution.
NOTE: Each correct selection is worth one point.

A) Edit the interactions of the KPI visualization.
B) Add the same slicer to each page and configure Sync slicers.
C) Edit the interactions of the slicer on the same page as the KPI visualization.
D) Configure a page-level filter.
E) Configure a report-level filter.

**Correct Answer: B and C**

**Explanation:**
B: Sync slicers across pages ensures the same filter applies to all pages.
C: Edit interactions on the slicer that is on the KPI page — set the KPI visual's interaction to None so it is excluded from filtering.

---

## Question #159 (HOTSPOT)

You have a line chart "Revenue by Date" with upward arrow indicators on data points showing values out of range.
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- The visual type is: a line chart
- The out-of-range indicators are created by using: anomaly detection

**Explanation:**
Anomaly detection automatically detects anomalies in time series data on line charts and marks them with indicators. This is different from a line and clustered column chart.

Reference: https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-anomaly-detection

---

## Question #160

You are creating a Power BI report from a Transactions table with a numeric field named Spend. You need a visual that identifies which fields have the greatest impact on Spend.
Which type of visual should you use?

A) Q&A
B) smart narrative
C) decomposition tree
D) key influencers

**Correct Answer: D**

**Explanation:**
The key influencers visual analyzes data and ranks factors by their impact on the target metric (Spend), making it ideal for understanding what drives a specific value.

Reference: https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-influencers

---

## Question #161 (HOTSPOT)

You have a line chart "Prior Year Employee Count By Month" with a dashed reference line and monthly data points.
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- The dashed line was created by using: an average reference line
- To enable users to drill down to weeks or days, add Weeks and Days fields to: Values

**Explanation:**
Average reference lines are added via the Analytics pane. Adding date fields (Weeks, Days) to the Values well of a line chart enables drill-down through the date hierarchy.

Reference: https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-analytics-pane

---

## Question #162

You have a dashboard with tiles pinned from a single report. You need to modify the dashboard to use a different color theme.
What should you do?

A) Change the report theme.
B) Change the dashboard theme.
C) Edit the details of each tile.
D) Create a custom CSS file.

**Correct Answer: B**

**Explanation:**
Dashboard themes apply a color theme to all visuals on the dashboard. Report themes apply to the report, not the dashboard.

Reference: https://docs.microsoft.com/en-us/power-bi/create-reports/service-dashboard-themes

---

## Question #163

You have a Power BI report with anomaly detection enabled on a gross sales by date visual. You need to increase the likelihood that anomalies will be identified.
What should you do?

A) Increase the Expected range transparency setting.
B) Add a data field to the Legend field well.
C) Increase the Sensitivity setting.
D) Add a data field to the Values field well.

**Correct Answer: C**

**Explanation:**
The Sensitivity setting for anomaly detection controls how sensitive the algorithm is. Higher sensitivity means more data points are flagged as anomalies.

Reference: https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-anomaly-detection

---

## Question #164

You have a supplier quality dashboard mobile layout showing 5 tiles. You need to modify it to show only single-value visuals and minimize scrolling.
What should you do?

A) Decrease the size of the card visuals. Remove the map and bar chart visuals.
B) Decrease the size of map and bar chart visuals. Move card visuals to the top.
C) Remove card visuals. Increase map and bar chart sizes.
D) Move bar charts to the top. Remove map visuals. Decrease card sizes.

**Correct Answer: A**

**Explanation:**
Single-value visuals are card visuals. Removing the map and bar chart leaves only card visuals, and decreasing their size minimizes scrolling.

---

## Question #165

You have a report with a Data1 table (10M rows): card (record count), bar chart (total transaction amount by territory), scatter plot (transaction amount vs profit by territory).
You need to modify the scatter plot to make it easier to identify meaningful patterns without affecting other visuals.
What should you do?

A) Add a count field to the size bucket of the scatter plot.
B) Add a trend line to the scatter plot.
C) Enable high-density sampling on the scatter plot.
D) Apply a row filter to the Data1 query.

**Correct Answer: B**

**Explanation:**
A trend line on a scatter plot visually represents the overall pattern/direction in the data, making patterns easier to identify without modifying the underlying data.

---

## Question #166

You have a Power BI workspace (Inventory) with a dataset, report, and dashboard. You need to add a tile showing inventory by location. This is NOT in the existing report. The solution must minimize impact on the report.
Which two actions should you perform? Each correct answer presents part of the solution.
NOTE: Each correct selection is worth one point.

A) Ask a question by using Q&A.
B) Hide the report page.
C) Pin the visual to the dashboard.
D) Use quick insights on the dataset.
E) Add the visual to the report.

**Correct Answer: A and C**

**Explanation:**
Q&A lets you create a visualization from a natural language question without modifying the report. Pinning the Q&A result to the dashboard adds the tile.

Reference: https://docs.microsoft.com/en-us/power-bi/create-reports/power-bi-tutorial-q-and-a

---

## Question #167 (HOTSPOT)

You have a dataset named Pens with columns: Item, Unit Price, Quantity Ordered.
You need a visualization showing the relationship between Unit Price and Quantity Ordered that highlights orders with similar values.
Which visualization and feature should you use?
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- Visualization: A scatter plot of Quantity Ordered and Unit Price by item
- Feature: Automatically find clusters

**Explanation:**
A scatter plot maps two numeric variables (Unit Price vs Quantity Ordered). The "Automatically find clusters" feature in scatter charts groups similar data points, highlighting items with similar price/quantity combinations.

---

## Question #168

You have a report with three pages (Page1, Page2, Page3) with the same slicers.
You need filters applied to Page1 to also apply to Page3 only.
What should you do?

A) On each page, modify the interactions of the slicer.
B) Enable visibility of the slicer on Page2. Disable visibility on Page2.
C) Sync the slicers on Page1 and Page3.
D) Configure a page-level filter.
E) Configure a report-level filter.

**Correct Answer: C**

**Explanation:**
Sync slicers lets you specify exactly which pages a slicer applies to. Syncing Page1 and Page3 means filtering on Page1 affects Page3 only, not Page2.

Reference: https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-slicers

---

## Question #169 (HOTSPOT)

You have three datasets: Sales (sales targets, employee salary), Operations (sensor data), Finance (transaction data).
Requirements: prevent export of reports with PII; data used for financial decisions must be reviewed before use.
For each statement, select Yes or No:
NOTE: Each correct selection is worth one point.

**Correct Answer:**
- The Sales dataset requires a sensitivity label: Yes
- The Operations dataset requires a sensitivity label and must be certified: No
- The Finance dataset requires a sensitivity label and must be certified: Yes

**Explanation:**
Sales contains employee salary data (PII) — requires a sensitivity label to prevent export.
Operations contains sensor readings with no PII and no financial decisions — no label or certification needed.
Finance contains financial transaction data used for financial decisions — requires a sensitivity label AND certification.

Reference: https://docs.microsoft.com/en-us/power-bi/enterprise/service-security-sensitivity-label-overview

---

## Question #170

You have reports using financial datasets exported as PDF files. You need to ensure the reports are encrypted.
What should you implement?

A) Microsoft Intune policies
B) row-level security (RLS)
C) sensitivity labels
D) dataset certifications

**Correct Answer: C**

**Explanation:**
Sensitivity labels with encryption settings ensure that exported PDFs are encrypted and can only be decrypted by authorized users.

Reference: https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels

---

## Question #171

You have a Microsoft Excel file on a file server. You create a Power BI report from it and publish it. You need to ensure data refreshes every four hours.
What should you do first?

A) Upload the Excel file to a Power BI workspace.
B) Create a subscription to the report.
C) Deploy an on-premises data gateway.
D) Edit the data source credentials.

**Correct Answer: C**

**Explanation:**
An on-premises data gateway is required to allow the Power BI service to connect to files stored on local file servers. It must be deployed before configuring scheduled refresh.

Reference: https://docs.microsoft.com/en-us/power-bi/connect-data/refresh-scheduled-refresh

---

## Question #172

You have a dataset that refreshes every hour but is used infrequently. You receive a notification that refresh was disabled due to inactivity.
Which two actions will resume the scheduled refresh? Each correct answer presents a complete solution.
NOTE: Each correct selection is worth one point.

A) Enable query caching for the dataset.
B) Import the dataset to Microsoft Excel.
C) From the Power BI service, open a dashboard that uses the dataset.
D) From the Power BI service, open a report that uses the dataset.
E) From PowerShell, run the get-powerbireport cmdlet.

**Correct Answer: C and D**

**Explanation:**
After two months of inactivity, scheduled refresh is paused. Simply visiting any dashboard or report built on the dataset is considered activity and resumes the refresh schedule.

Reference: https://docs.microsoft.com/en-us/power-bi/connect-data/refresh-scheduled-refresh#scheduled-refresh

---

## Question #173

You have a Power BI workspace with external users, managers, and employees. You need all users (including external) to be able to tag workspace administrators when they identify dashboard issues. Other users must see the issues raised.
What should you do?

A) comments
B) chat in Microsoft Teams
C) alerts
D) subscriptions

**Correct Answer: A**

**Explanation:**
Dashboard comments support @mentions, are visible to all users with access, and work for external users. Alerts are personal and not shared; subscriptions are for scheduled emails.

Reference: https://docs.microsoft.com/en-us/power-bi/consumer/end-user-comment

---

## Question #174

You have a PBIX file importing tables from an Azure SQL database. The data will be migrated to another Azure SQL database.
You need to change connections in the PBIX file. The solution must minimize administrative effort.
What should you do?

A) From Power Query Editor, create new queries.
B) From Power Query Editor, modify the source of each query.
C) Create a PBIT file and change data sources when prompted.
D) Modify the Data source settings.

**Correct Answer: D**

**Explanation:**
Data source settings (File → Options → Data source settings) lets you update the server/database for all queries at once, minimizing the effort compared to modifying each query individually.

---

## Question #175

You have a Power BI workspace with several reports. You need to provide a user with the ability to create a dashboard using visuals from the reports.
What should you do?

A) Create an RLS role and add the user to the role.
B) Share the reports with the user.
C) Grant Read permission for the datasets to the user.
D) Add the user as a Member of the workspace.
E) Add the user as a Viewer of the workspace.

**Correct Answer: D**

**Explanation:**
The Member role in a workspace allows users to create dashboards from report visuals. Viewer role only allows viewing; it does not grant the ability to pin visuals to create dashboards.

Reference: https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-roles-new-workspaces

---

## Question #176 (DRAG DROP)

You have a single-page report named Sales in a Power BI workspace. You need to add all visuals from the page to a dashboard. Additional visuals added to the page must be added automatically to the dashboard.
Which three actions should you perform in sequence?

**Correct Answer:**
1. Open powerbi.com
2. Open the Sales report
3. Pin the page (as a live tile)

**Explanation:**
Pin live page pins the entire report page as a live tile. Unlike pinning individual visuals, a live tile automatically reflects new visuals added to the report page.

Reference: https://docs.microsoft.com/en-us/power-bi/create-reports/service-dashboard-pin-live-tile-from-report

---

## Question #177

You have a report named "report" based on a shared dataset. You need to minimize risk of data exfiltration for this report without affecting other reports.
What should you do?

A) Clear Allow recipients to share and Allow users to build new content for the dataset.
B) Add row-level security to the shared dataset.
C) Select the "Don't allow end users to export any data" option for the report.
D) From Power BI service, open a report that uses the dataset.
E) From Power BI service, open a dashboard that uses the dataset.

**Correct Answer: C**

**Explanation:**
Setting the export option to prevent data export on the specific report prevents data exfiltration for that report without affecting other reports that share the same dataset.

Reference: https://data-marc.com/2021/04/13/power-bi-governance-why-you-should-consider-to-disable-export-to-excel/

---

## Question #178

In Power BI Desktop, you are creating visualizations based on an imported dataset. You need to allow Power BI users to export summarized data from visuals but prevent exporting the underlying data.
What should you do?

A) From the Power BI service, configure the dataset permissions.
B) From Power BI Desktop, configure the Data Load settings for the current file.
C) From Power BI Desktop, modify the data source permissions.
D) From Power BI Desktop, configure the Report settings for the current file.

**Correct Answer: A**

**Explanation:**
Dataset permissions in the Power BI service control the level of access users have — including whether they can export summarized data (from visuals) vs. the underlying raw data.

Reference: https://docs.microsoft.com/en-us/power-bi/connect-data/service-datasets-permissions
