# 2.Visualisation example of financial analysis(under construction)

## 2-1.Data model
###   The data model for this example is shown as follows.
![Fin Data model](/images/finDataModel.bmp)
### Just like the example of retail one, first I created database on MySql and extracted the date from it. Again, the same as the retail model, this data model is formed with purely a 'Star schema' data model design. The transaction(=fact) table holds only measures and external keys to the dimension tables. Whereas each dimension table holds surrogate key and descriptive/attribute values of each entity(product, customer, section etc.).
## 2-2.Sample of Sales dashboard
### In this ection, I would show you the sample of sales dashboard as the first example of financial analysis.
 ![sales dashboard Sample](/images/finDashboard1.bmp)
### In the sample above, you can see five charts created from financial data model shown on the previous section. As the nature of the "associative" database of Qlik, you can click on all the values shown on the charts in order to issue query. For example, if you click on the "Sales 1" section name on the left hand soide chart named "Monthly sales achievement", all the charts limit the data records which are used for creating the charts. I'd show the example of 'selected' charts as below. 
 ![sales dashboard Sample](/images/finDashboard1selected.bmp) 
### This functionality of Qlik is quite easy for every user because we don't have to issue any command to select the data. Only to click on the values make the 'selection(s)' of data.
## 2-3.Sample of profitability analysis dashboard
### In this section, I'd show you an example of profitability analysis dashboard as below. 
 ![Gantt example](/images/finDashboard2.bmp)
### Above is the a simple sample of gantt chart. In this chart you can see the quarterly scheduling of some tasks in the projects chlonologically. The time pitch of time span can be set automatically in accordance with the data selected. Also you can see the duration of tasks indicated on the end of bars.
