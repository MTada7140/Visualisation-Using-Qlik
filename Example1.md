# 1.Visualisation using retail data

## 1-1.Data model
###   I'd present the data model for this example as follows.
![Data model](/images/dataModel.bmp)
### Unlike "ordinary" Business Intelligence software, Qlik employs the unique and proprietary data format called assosiative model. It stores all the data records into main memory when Qlik is running. And the "Document file" of Qlik contains everything needed for analysis including load script (script language used for data loading), all the data records and visualisation components.
## 1-2.Load script
### In this section, I'd like to explain a little bit about load script of Qlik. With load script of Qlik, you can extract data from wide variety of sources including RDBMS, CSV/text file, Excel Spreadsheet and business systems(SAP, SFDC). 
### In this example, I used MySql as the datasource. I'd present part of script I created as follows.
 ![Load script](/images/loadScript1.bmp)