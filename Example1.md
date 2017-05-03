# 1.Visualisation using retail data

## 1-1.Data model
###   I'd present the data model for this example as follows.
![Data model](/images/dataModel.bmp)
### Unlike "ordinary" Business Intelligence software, Qlik employs the unique and proprietary data format called assosiative model. It stores all the data records into main memory when Qlik is running. And the "Document file" of Qlik contains everything needed for analysis including load script (script language used for data loading), all the data records and visualisation components.
## 1-2.Load script
### In this section, I'd like to explain a little bit about load script of Qlik. With load script of Qlik, you can extract data from wide variety of sources including RDBMS, CSV/text file, Excel Spreadsheet and business systems(SAP, SFDC). 
### In this example, I used MySql as the datasource with ODBC connection. I'd present part of script I created as follows.
 ![Load script](/images/loadScript1.bmp)
### As you can see easily, syntax of load script is quite similar to SQL language but different points are 1) you don't have to create table since Qlik creates column based data, 2) you don't have to care about indecies since Qlik employs "natural" connection of data items only with column names(you never use "join" on Qlik!!) and 3) you can add columns without define them beforehand. 