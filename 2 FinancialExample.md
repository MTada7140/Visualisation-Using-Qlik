# 2.Visualisation example of financial analysis(under construction)

## 2-1.Data model
###   The data model for this example is shown as follows.
![Fin Data model](/images/finDataModel.bmp)
### Just like the example of retail one, first I created database on MySql and extracted the date from it. Again, the same as the retail model, this data model is formed with purely a 'Star schema' data model design. The transaction(=fact) table holds only measures and external keys to the dimension tables. Whereas each dimension table holds surrogate key and descriptive/attribute values of each entity(product, customer, section etc.).
## 2-2.Sample of Sales dashboard
### In this ection, I would show you the sample of sales dashboard as the first example of financial analysis.
 ![sales dashboard Sample](/images/finDashboard1.bmp)
### In the sample above, you can see how a SPC chart works. You can grasp the behaviour of a manufacturing proces at a glance. Alongside the chart, you can see the main statistics of the data. To create SPC charts, it is essential for us to calculate and present these statistics. In order to calculate these statistices, I prepared three variables using 'Let' statements in the script shown in 2-1. These variables store the pre-calculated sum, average and standard deviation and make the calculation very easy. It is another good example of powerful statistical functinality of Qlik. The centre line of the chart represents average of observations and called CL(centre line). The upper and lower lines of the CL are called UCL(Upper Control Limit) and LCL(Lower Control Limit) respectively, showing divergence of 3 times the standard deviation value from the average. In other words, it is the objective of this control chart to grasp the value falling within the range corresponding to 6 times the standard deviation up and down as the value within the control limit. And this kind of control chart is called as 'X-bar R control chart' usually and it is the most frequently used for process controlling because of its effectiveness and easiness of creation.
## 2-3.Gantt chart
### In this section, I'd show you an example of "gantt chart" as one sample of typical project scheduling visualisation in the manufacturing industry. 
 ![Gantt example](/images/gantt.bmp)
### Above is the a simple sample of gantt chart. In this chart you can see the quarterly scheduling of some tasks in the projects chlonologically. The time pitch of time span can be set automatically in accordance with the data selected. Also you can see the duration of tasks indicated on the end of bars.
