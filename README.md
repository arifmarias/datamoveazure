This file contains text you can copy and paste for the Data Flow _Using Azure Data Lake Storage Gen2_ , _Azure Storage_, _Azure Synapse Analytics_  and _Azure Data Factory_

#### Step 1: 
Download the .bak file and restore into your local server (using SQL Server Management Studio)

#### Step 2: 
Export table to flat file

#### Step 3: 
Upload flat file to blob storage 

#### Step 4:
Use Azure Data Factory to Move the file from _Blob Storage_ to _Azure Data Lake_

#### Step 5:
Create destination table in Azure Data warehouse
```
CREATE SCHEMA [prod];
GO
CREATE TABLE [prod].vGetAllCategories
(
    [ProductCategoryID] [nvarchar](50) NOT NULL,
	[ParentProductCategoryName] [nvarchar](50) NOT NULL,
	[ProductCategoryName] [nvarchar](50) NOT NULL
	
)
```

#### Step 6:
Use Azure Data Factory to Move the file from _Azure Data Lake_ to _Azure Synapse Analytics_

#### Step 7:
Once Done - Verify number of rows in Azure SQL Data Warehouse (Azure Synapse Analytics)
```
SELECT count(1) FROM [prod].[vGetAllCategories]
```
#### (Optional)
Verify the data was loaded into the 60 distributions
_Find data skew for a distributed table_

```
DBCC PDW_SHOWSPACEUSED('prod.vGetAllCategories');
```

