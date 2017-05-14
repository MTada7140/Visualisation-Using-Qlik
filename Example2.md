# 2.Visualisation example of manufacturing

## 2-1.Data model
###   I'd present the data model for this example as follows.
![Manu Data model1](/images/dataForManu1.bmp)
### The first one is the quite simple one with only one 'observation' data and an index in it. I'll show you the 'SPC chart' using this one ont the following section. For creating this data, you can use the 'Autogeneration' capability of data in Qlik. The load script I created is as follows.
![Manu Data model2](/images/manuDataGenerate.bmp) 
### In this script I used rand function in order to create random data of normal distribution. In order to create data series looks like natural, I combined two random functions in this formula. With this capability, you can create as many row of data as you like.
![Autogenerate script](/images/dataForManu2.bmp) 
### The second one is the data model of project scheduling. Just like the model of retail, I created original data in MySql database and extract the data from it using ODBC connection. With this model, I'd like to show an example of 'gantt chart' in the following section.
## 1-2.Sample of 'SPC(statistics process control) chart'
### In this section, I would show you the sample of SPC control charts(also known as Shewhart cgarts) based on the data model explained in the previous sections.
 ![control chart Sample](/images/controlChart.bmp)
### In the sample above, you can see how associative model of Qlik works. In the sample, you can see values highlighted with green colour on the data items "Year" and "Region". This means that you selected these values. In accordance with your selection, the white values are hit as in the six values in "StoreCity" data item; "Auckland", "Bay of Plenty", "Hawkes Bay", "Taranaki & Wanganui", "Waikato" and "Wellington". Also you can see the greyed 3 values including "Canterbury" in the same item, which means "not hit" values of this pattern of selection. In Qlik, you just click on the value(s) you want to select and the result is shown in three colours; green, white and grey. This is quite simple but quite powerful because in the case of "ordinary" BI tools, you can easily see the values which are selected with your query, but usually, you can't see which were "not" hit. Which provides users with more profound insights of the data just at a glance.
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
### In the example above, dollar sign denotes the current selection(=original set). Whereas, the set to be compared is defined by the expression "<currentQuarter = {"$(=previousQuarter)"}>", which extract atothr set of records representing the sales amount of previous quarter.
    