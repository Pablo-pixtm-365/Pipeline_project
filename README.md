<h1>Pipeline Project</h1>

<h2> Introduction</h2>

There exist many ways to work with data, from small data and big data.<br>
There is not an specific tool that we can use to work with and many approaches and methods to deal with. <br>
In this case, as a part of our Schoolar Project and course we saw many tools, and many methods. We decided to work with Spark, Mongo, Python and Bokeh. <br>
The project is divided in many past, starting from Data Adquisition, pre processing, built of the model, prediction and visualitation. <br>
The objetive of this project is to answer the following questions: 
* What are the most likely places where an earthquake could occur in 2017?
* Is there a big difference in the number of earthquakes that have occurred during the years from 1965 to 2016?
* Are there any incremental changes in the average magnitude of earthquakes over the years?
<h2>Justification</h2>
<h3> Pipeline</h3>

* Data Source: 
  * We took the useful earthquakes'data set (1965-2016) from **Kaggle**. <br>
  We used this platform as our way to get the data, nevertheless, the original data belongs to *The National Earthquake Information Center* 
  
* Data Acquisition:
  * Even when we obtained the data from *kaggle* it's important to know that this type of data is usually obtained by analog sensors that take samples of signals that come from the outside world, such as time, temperature, sound, light (they do not have a fixed value). These sensors are connected to a device that does the conversion of analog values to computational values (with which we can work).<br>
However, the precise moment of obtaining data from us would be from our device, with which we download and begin the analysis of the previously mentioned dataset.

* Data Cleaning:
  * We used **Apache Spark** due to its speed, its interactive console, that allows us to manage and run its APIS in Python. On the other hand, our idea was to work with more than one cluster and, as an advantage, it allows to manipulate the data quickly and tolerates failures. However, for many reasons, we only worked with one cluster. 

* Data Storage:
  * We decided to used **Mongo DB** as our main source to storage the dataset. <br>
  We chose this database tool because was the one we are getting to work with. 
  Other reasons were the *Multi-platform, High performance and Availability, and last the Easy Scalability*

* Analytical Modeling: 
  * The main objetive was to develop and implement a model saw in the course, in this case we decided to use a Random Forest. 
  
* Data Analysis and Visualization:
  * As our last part, after develop the model and pre process the whole data we did an analyze to answer the questions already present using visualizations with *Bokeh*

<h3>Data Cleaning</h3>

As we said before we worked with using *Pyspark* (Belongs to Spark) in python to deal with the Cleaning Process. <br>
Pyspark has two development modes, one is the local mode and the other is the cluster mode. Since what we did was a **demonstration**, we made use of the local mode. <br> 
The first step for our predictive model is cleaning the data. For this, as previously mentioned, pyspark was used, among other libraries such as pyspark.sql. from spark.sql sparksession had to be imported because it provides a single-entry point to interact with the Data frames in spark and is also used to make each record and execute SQL queries.<br>
To configure a session in pyspark you have to define how many cores the information will be processed in, in our case we used two, we also give the application a name, the name we gave it was 'quake_etl', and we also set the configuration to connect the database to mongodb later, and finally the getorCreate () method is used. 
