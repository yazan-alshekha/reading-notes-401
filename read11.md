# Data Science

It is a set of disciplines and practices that handle data in a scientific manner. The foundations of data science are mostly Mathematics and Statistics, sometimes Software Engineering would play a role as well.

Usually, it includes but not limited to these steps:
1. Data acquisition
2. Data cleaning & wrangling
3. Data Engineering
4. Utilization of data


1. Data acquisition
To play with data, you need to have data first.
The data could be in the form of .CSV files. Excel file (.XLSX) is a typical form, or it could be available by API calls, or someone has done the dirty work already and they are all in DWH(Data WareHouse) or Data Lake.

In addition, web scraping is also one way to go as well. Web scraping is useful when you need to acquire data that CSV export and API method are not viable (especially for business competitors’ data). My best friend Anastasia Reusova wrote an article for this topic. Free free to check that out if you are interested to learn the details.

2. Data cleaning & wrangling
In the actual working environment, data is rarely ready to be used right away.
Data could be in the nested structure for storage saving purpose (e.g. Bigquery and NoSQL), could be normalized (like general databases). The data need to be flattened before usage.
Or, the application generating data went haywire and polluted the data recently. That would require sanity checking and data cleaning as well.
This is usually the most time-consuming and painful part for Data Scientists, Analysts and Data Engineers. Roughly 60~80% of the data science people’s time goes to this part, 10% goes to meetings & presentation and only the rest for the sexiest part: playing with algorithms.

3. Data Engineering

Simply put, the point of Data Engineering is building a stable and reliable architecture for data storage and consumption. It is a extremely vital part as all kinds of data science tricks depends on it.
If there is no good data to use, NONE of the data science gimmicks could work.
Well engineered data should be clean, fast and cheap (in terms of computational resources, hence money as well) for robust consumption right away.

4. Utilization of data
This is the sexy part that people couldn’t stop talking about.
From traditional consumption like building an application, doing ad hoc analysis, dashboarding and the recent fancy thing such as Machine Learning, this is the step people care so much.
There will be more articles covering this part, stay tuned for more ;)


**Big Data**

There are various definitions online and in Wikipedia. Yet due to the rapidly changing nature of the tech industry itself, it would be much safer to simply define it with the size & structure elements.

![](https://miro.medium.com/max/700/1*hvVfvzIvrTw0COyaBCFnwQ.png)

As for “Big Data”, there are other formats of data as well: images, videos, voice recordings, etc. Good examples would be Google Photos for images data, Netflix for videos, voices recordings (songs) in Spotify.
And of course, “Big Data” would be BIG. Big enough to make it impossible for a regular laptop to process. Hence, solutions like Google Bigquery, Hadoop and MapReduce are introduced.
