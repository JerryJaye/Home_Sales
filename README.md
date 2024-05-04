Challenge 22 - Determine key metrics about home sales data using SparkSQL

## Introduction
This challenge utilises SparkSQL, a powerful tool for big data processing, to analyse and derive key metrics from the "Home_Sales.csv" dataset. The dataset comprises various attributes of homes sold, including prices, locations, sizes, bedrooms, bathrooms, and more, which are essential for understanding market trends and valuations.

This study applied SparkSQL to efficiently perform data manipulation and aggregation tasks, enabling the extraction of the metrics we are looking for. We will also explore how the dataset's structure affects query processing speed to compute these metrics. We will do this by processing the same query directly from data stored in a temporary view, cached data, and partitioned data.

## Method
I coded in a Jupyter Notebook equivalent in Colab. The program first imports all the dependencies Colab requires to perform the work, including starting and then creating a SparkSession. After importing the 'home_sales_revised.csv file into a DataFrame I examined the data using the printSchema function, noting the datatypes.

I created a temporary table called 'home_sales' and then began to process queries, extracting the metrics from the data stored in the temporary table as requested in the instructions. I did the following using the 'temporary view' data set:

. Extracted the average prices of 4-bedroom homes during the period 2019 to 2022;

. Extracted the average prices for 3-bedroom and 3-bathroom houses built from  2010 to 2017. 

. Extracted the average price of a home for each year it was built with three bedrooms, three bathrooms, two floors, and a floor area greater than or equal to 2,000 square feet.

. Extracted the average price of a home per "view" rating having an average home price greater than or equal to $350,000? Determined the run time for this query.

. Cached your temporary table home_sales, and confirmed that the cache was successful

. Extracted the average price of a home per "view" rating having an average home price 

. Using the cached data, I ran the last query to calculate the average home price per  'view' rating with an average home price greater than or equal to $350,000. The query determined the runtime to compare it to the uncached run time.
 
. Partitioned the data by the 'date_built' field on the parquet formatted 'home_sales' data.

. Created a 'temporary table' for the parquet data.

. Using the cached data, I ran the last query to calculate the average home price per  'view' rating with an average home price greater than or equal to $350,000. The query determined  the runtime and compare it to the uncached run time.

. To complete the process, I uncached the home_sales temporary table and confirmed that the uncached was successful.

## Results
. I created a Spark DataFrame from the dataset.

. I created a temporary table of the original DataFrame.

. I wrote a query that returns the average price, rounded to two decimal places, for a four-bedroom house sold each year.

. I wrote a query that returns the average price, rounded to two decimal places, of a house that has three bedrooms and three bathrooms for each year the house was built.

. I wrote a query that returns the average price of a home with three bedrooms, three bathrooms, and two floors and is greater than or equal to 2,000 square feet for each year the house was built, rounded to two decimal places.

. I wrote a query that returns the average price of a home per 'view' rating having an average home price greater than or equal to $350,000, rounded to two decimal places. (The output showed the run time for this query as 0.64 seconds.

. I cached the temporary "home_sales" table and validated the cache.

. I ran the previous query on the cached temporary table, and the run time was computed as 0.57 seconds.

. I partitioned the home sales dataset by the 'date_built' field, and read the formatted parquet data.

. I created a temporary table of the parquet data.

. I ran the previous query on the cached temporary table, and the run time was computed as 0.93 seconds.

. I uncached and verified the uncachement of the "home_sales" parquet temporary table.

## Discussion
This study applied SparkSQL to efficiently perform data manipulation and aggregation tasks, enabling the extraction of the metrics we are looking for. We also explore how the dataset's structure affects query processing speed to compute these metrics. We did this by processing the same query directly from data stored in a temporary view, cached data, and partitioned data.

The work showed that query processing times varied with the format of the dataset processed. With the home_sales dataset stored in memory as a temporary view the processing time was 0.64 seconds. The same query processed after the data were cached was significantly lower at 0.57 seconds. The query was processed using the temporary table of parquet data in 0.93 seconds, higher than the cached data and lower than the original temporary table. I noted that these times were different each time I executed the code.
 
## Conclusion
This project demonstrated the powerful capabilities of SparkSQL in analyzing and optimizing big data queries within the area of real estate analytics. By using a combination of temporary views, caching, and partitioning strategies on the "Home_Sales.csv" dataset, we achieved improvements in query processing speeds. Key findings include a drastic reduction in run time from 0-.93 seconds in a parquet temporary view to 0.57 seconds using cached data, illustrating the efficiency gains from caching. These insights not only highlight the advantages of SparkSQL for data-intensive tasks but also provide a practical framework for future data analyses aiming to optimize computational resources and time.
