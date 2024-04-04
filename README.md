# PowerBi-Power-Queries
WS PowerBi Tips and Power Queries 
𝗗𝗮𝘁𝗮 𝘁𝗿𝗮𝗻𝘀𝗳𝗼𝗿𝗺𝗮𝘁𝗶𝗼𝗻 is the process of cleaning, shaping, and enriching raw data from various sources to make it suitable for analysis and reporting.

𝗨𝘀𝗶𝗻𝗴 𝗣𝗼𝘄𝗲𝗿 𝗤𝘂𝗲𝗿𝘆 𝗶𝗻 𝗱𝗮𝘁𝗮 𝘁𝗿𝗮𝗻𝘀𝗳𝗼𝗿𝗺𝗮𝘁𝗶𝗼𝗻 𝘄𝗶𝘁𝗵𝗶𝗻 𝗣𝗼𝘄𝗲𝗿 𝗕𝗜 𝗵𝗮𝘀 𝘀𝗲𝘃𝗲𝗿𝗮𝗹 𝗶𝗺𝗽𝗼𝗿𝘁𝗮𝗻𝘁 𝗯𝗲𝗻𝗲𝗳𝗶𝘁𝘀 𝗮𝗻𝗱 𝗮𝗱𝘃𝗮𝗻𝘁𝗮𝗴𝗲𝘀:

1️⃣ Power Query is tightly integrated with Power BI, enabling seamless data transformation within the Power BI environment.
2️⃣ Power Query includes data profiling capabilities that allow users to quickly analyze the structure and quality of their data.
3️⃣ Power Query supports the creation of reusable data transformation steps, known as queries, which can be applied to multiple datasets.
4️⃣ Power Query includes optimizations for performance, such as query folding and data load settings.

This covers various aspects of data transformation using Power Query in Power BI, including connecting to data sources, data cleansing, data transformation, date and time operations, aggregation and grouping, filtering and sorting, joins and merges, conditional columns and rows, text operations, number operations, and more.

**Data Import Transformation**

1. Import data from a CSV file: Csv.Document(File.Contents("C:\data.csv"))

2. Import data from an Excel file: Excel.Workbook(File.Contents("C:\data.xlsx"))

3. Import data from a JSON file: Json.Document(File.Contents("C:\data.json"))

4. Import data from a SQL Server database: Sql.Database("server", "database", [Query="SELECT * FROM table"]) 

5. Import data from a web API: Web.Contents("https://api.example.com/data")

6. Import data from a folder: Folder.Files("C:\data") 

7. Import data from a SharePoint list: SharePoint.Tables("https://contoso.sharepoint.com/sites/mysite", "ListName") 

8. Import data from an OData feed: OData.Feed("https://services.odata.org/V4/Northwind/Northwind.svc") 

9. Import data from an ODBC source: Odbc.Query("dsn=MyDSN", "SELECT * FROM table") 

10. Import data from a text file: Text.FromBinary(File.Contents("C:\data.txt"))
