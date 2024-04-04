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
------------------------------------------------------------------------
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

**Data Cleansing**
------------------------------------------------------------------------
1. Remove duplicate rows: Table.Distinct(table) 

2. Remove blank rows: Table.SelectRows(table, each not List.IsEmpty(Record.FieldValues(_))) 

3. Replace null values with a specific value: Table.ReplaceValue(table, null, 0, Replacer.ReplaceValue, {"ColumnName"}) 

4. Remove rows with errors: Table.RemoveRowsWithErrors(table) 

5. Fill down missing values: Table.FillDown(table, {"ColumnName"}) 

6. Fill up missing values: Table.FillUp(table, {"ColumnName"}) 

7. Trim whitespace from text: Table.TransformColumns(table, {{"ColumnName", Text.Trim, type text}}) 

8. Clean text by removing non-printable characters: Table.TransformColumns(table, {{"ColumnName", Text.Clean, type text}}) 

9. Capitalize text: Table.TransformColumns(table, {{"ColumnName", Text.Proper, type text}})

10. Lowercase text: Table.TransformColumns(table, {{"ColumnName", Text.Lower, type text}}) 

11. Uppercase text: Table.TransformColumns(table, {{"ColumnName", Text.Upper, type text}})

**Data Trasformation**
------------------------------------------------------------------------

1. Rename columns: Table.RenameColumns(table, {"OldColumnName", "NewColumnName"}) 

2. Reorder columns: Table.ReorderColumns(table, {"Column1", "Column2", "Column3"}) 

3. Remove columns: Table.RemoveColumns(table, {"ColumnName"}) 

4. Filter rows based on a condition: Table.SelectRows(table, each [ColumnName] > 10) 

5. Sort rows: Table.Sort(table, {{"ColumnName", Order.Ascending}}) 

6. Group rows and aggregate: Table.Group(table, {"GroupColumnName"}, {{"AggregateColumnName", each List.Sum([ColumnName]), type number}}) 

7. Pivot data: Table.Pivot(table, List.Distinct(table[PivotColumnName]), "PivotColumnName", "ValueColumnName", List.Sum) 

8. Unpivot data: Table.UnpivotOtherColumns(table, {"ColumnName"}, "AttributeColumn", "ValueColumn") 

9. Transpose a table: Table.Transpose(table) 

10. Split a column by delimiter: Table.SplitColumn(table, "ColumnName", Splitter.SplitTextByDelimiter(","), {"Column1", "Column2"}) 

11. Merge columns: Table.CombineColumns(table, {"Column1", "Column2"}, Combiner.CombineTextByDelimiter(" "), "NewColumnName") 

12. Extract text before a delimiter: Table.TransformColumns(table, {{"ColumnName", each Text.BeforeDelimiter(_, " "), type text}})

13. Extract text after a delimiter: Table.TransformColumns(table, {{"ColumnName", each Text.AfterDelimiter(_, " "), type text}}) 

14. Extract text between delimiters: Table.TransformColumns(table, {{"ColumnName", each Text.BetweenDelimiters(_, "{", "}"), type text}}) 

15. Replace text: Table.TransformColumns(table, {{"ColumnName", each Text.Replace(_, "old", "new"), type text}}) 

16. Add a custom column with a formula: Table.AddColumn(table, "NewColumnName", each [Column1] + [Column2], type number) 

