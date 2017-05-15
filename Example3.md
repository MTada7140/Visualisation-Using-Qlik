# 3.Visualisation example of financial analysis

## 2-1.Data model
###   I'd present the data model for this example as follows.
![Manu Data model1](/images/dataForManu1.bmp)
### The first one is the quite simple one with only one 'observation' data and an index in it. I'll show you the 'SPC chart' using this one on the following section. For creating this data, I have used the 'Autogeneration' capability of data in Qlik. The load script I created is as follows.
![Manu Data model2](/images/manuDataGenerate.bmp) 
### In this script I used rand() function in order to create random numbers with normal distribution. In order to create data series looks like natural, I combined two rand() functions in this formula. With this capability, you can create as many rows of data as you like.
![Autogenerate script](/images/dataForManu2.bmp) 
### The second one is the data model of project scheduling. Just like the model of retail, I created original data in MySql database and extracted the data from it using ODBC connection. With this model, I'd like to show you an example of 'gantt chart' in the following section.
## 2-2.Sample of 'SPC(statistics process control) chart'
### In this section, I would show you the sample of SPC control charts(also known as Shewhart cgarts) based on the data model explained in the previous sections.
 ![control chart Sample](/images/controlChart.bmp)
### In the sample above, you can see how a SPC chart works. You can grasp the behaviour of a manufacturing proces at a glance. Alongside the chart, you can see the main statistics of the data. To create SPC charts, it is essential for us to calculate and present these statistics. In order to calculate these statistices, I prepared three variables using 'Let' statements in the script shown in 2-1. These variables store the pre-calculated sum, average and standard deviation and make the calculation very easy. It is another good example of powerful statistical functinality of Qlik. The centre line of the chart represents average of observations and called CL(centre line). The upper and lower lines of the CL are called UCL(Upper Control Limit) and LCL(Lower Control Limit) respectively, showing divergence of 3 times the standard deviation value from the average. In other words, it is the objective of this control chart to grasp the value falling within the range corresponding to 6 times the standard deviation up and down as the value within the control limit. And this kind of control chart is called as 'X-bar R control chart' usually and it is the most frequently used for process controlling because of its effectiveness and easiness of creation.
## 2-3.Gantt chart
### In this section, I'd show you an example of "gantt chart" as one sample of typical project scheduling visualisation in the manufacturing industry. 
 ![Gantt example](/images/gantt.bmp)
### Above is the a simple sample of gantt chart. In this chart you can see the quarterly scheduling of some tasks in the projects chlonologically. The time pitch of time span can be set automatically in accordance with the data selected. Also you can see the duration of tasks indicated on the end of bars.
