# 1.Visualisation example of retail data

## 1-1.Data model
###   I'd present the data model for this example as follows.
![Data model](/images/dataModel.bmp)
### Unlike "ordinary" Business Intelligence software, Qlik employs the unique and proprietary data format called assosiative model. It stores all the data records into main memory when Qlik is running. And the "Document file" of Qlik contains everything needed for analysis including load script (script language used for data loading), all the data records and visualisation components.
## 1-2.Load script(ETL features of Qlik)
### In this section, I'd like to explain a little bit about load script of Qlik. With load script of Qlik, you can extract data from wide variety of sources including RDBMS, CSV/text file, Excel Spreadsheet, business systems(SAP, SFDC) etc. 
### In this example, I use MySql as the datasource with ODBC connection. I'd present part of script I created as follows.
 ![Load script](/images/loadScript1.bmp)
### As you can see easily, syntax of load script is quite similar to SQL language but different points are 1) you don't have to create table since associative modelling of Qlik is based on column type data structure, 2) you don't have to care about indecies since Qlik employs "natural" connection of data items only with column names(you never use "join" on Qlik!!) and 3) you can add columns without define them beforehand. 
### For the transformation of data, Qlik has hundreds of powerful functions for data aggregation, mathematical calculation, string manipulation, statistical testing, data mapping, etc.
 ![Load script2](/images/loadScript2.bmp)
### For example, sample code above shows the using of "ApplyMap" function. This enables the conversion of code to name or name to another name.
## 1-3.Dashboard
### In this section, I would show you the sample of dashoboard based on the data model explained in the previous sections.
 ![Dashboard](/images/dashboard.bmp)
### In the dashboard above, you can see how associative model of Qlik works. In the sample, you can see values highlighted with green colour on the data items "Year" and "Region". This means that you selected these values. In accordance with your selection, the white values are hit as in the six values in "StoreCity" data item; "Auckland", "Bay of Plenty", "Hawkes Bay", "Taranaki & Wanganui", "Waikato" and "Wellington". Also you can see the greyed 3 values including "Canterbury" in the same item, which means "not hit" values of this pattern of selection. In Qlik, you just click on the value(s) you want to select and the result is shown in three colours; green, white and grey. This is quite simple but quite powerful because in the case of "ordinary" BI tools, you can easily see the values which are selected with your query, but usually, you can't see which were "not" hit. Which provides users with more profound insights of the data just at a glance.
## 1-4.Decile analysis
### In this section, I'd show you the "decile analysis" as one sample of typical retail analysis especially effective when you try to segment customers. 
 ![Decile example1](/images/decile1.bmp)
### Above is the a simple sample of decile analysis. This table was formulated segmentation of customers based on sum of sales amount in certain period of time. In Qlik, to calculate "Decile" rank on the left of the table, you can use "fractile" function in the chart hence the calculation can be done dynamically as you select any period of time(year(s),month(s),day(s)...any combinations are possible). I'd show you the function for this table below.
 ![Decile example2](/images/fractile.bmp)
### Also you can calculate cumulative sum dynamically as below.
 ![Decile example3](/images/cumulative.bmp) 
### With using these functions, you can do the decile analysis without aggregate your tables beforehand. It is another example of Qlik's powerful visualisation. 
## 1-5.Comparison of decile ranks quarter by quater
### One interesting analysis using decile is shown below. This is the comparison of decile "ranks" over quarter. With this, you can see the "shifting" of behaviour of customers over time. You can quantify the effectiveness of your sales promotions, campaigns and advertisement easily.
 ![Decile example3](/images/decile2.bmp)
### In order to do this, I created another dimension using "SET analysis" of Qlik. Set analysis enables the comaring of group of records on the fly without calculating aggregations beforehand.
 ![Decile example2](/images/fractile2.bmp)
### In the example above, dollar sign denotes the current selection(=original set). Whereas, in this case, the set to be compared is defined by the expression "<currentQuarter = {"$(=previousQuarter)"}>", which extract atothr set of records representing the sales amount of previous quarter.
    