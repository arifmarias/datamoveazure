# Create destination table in Azure Data warehouse
This file contains text you can copy and paste for the Data Flow _Using Azure Data Lake Storage Gen2_ , _Azure Storage_, _Azure Synapse Analytics_  

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

### Verify number of rows
```
SELECT count(1) FROM [prod].[vGetAllCategories]
```



### verify the data was loaded into the 60 distributions
###  Find data skew for a distributed table
```
DBCC PDW_SHOWSPACEUSED('prod.vGetAllCategories');
```

