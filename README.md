# An analysis to determine key metrics about home sales data

<img width="746" alt="Screenshot 2023-04-09 at 1 19 42 PM" src="https://user-images.githubusercontent.com/106120403/230786958-dc308d09-858e-4058-8bb1-51f6434d8a44.png">

I used SparkSQL to answer the following questions:
1. What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.

<img width="166" alt="Screenshot 2023-04-09 at 1 05 37 PM" src="https://user-images.githubusercontent.com/106120403/230786332-5bdaa9f1-b0f7-4630-b5c4-5fc0e3f422b5.png">

2. What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.

<img width="166" alt="Screenshot 2023-04-09 at 1 06 16 PM" src="https://user-images.githubusercontent.com/106120403/230786355-27e1b24e-e6fe-4e7b-a99d-af47034b6fb0.png">

3. What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.

<img width="166" alt="Screenshot 2023-04-09 at 1 06 49 PM" src="https://user-images.githubusercontent.com/106120403/230786376-23aaf15f-7437-4449-9a60-2cb577610da2.png">

4. What is the "view" rating for homes costing more than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.

It took 0.2325 seconds to run this query.

<img width="348" alt="Screenshot 2023-04-09 at 1 07 29 PM" src="https://user-images.githubusercontent.com/106120403/230786407-d4786b8d-d383-4c53-a990-191c64df9b72.png">

I cached my data in a temporary data and used this cached data to run the query that filters out the view ratings with an average price of greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.

It took 0.1461 seconds to run this query. This took less than half the time to run compared to the uncached data above.

<img width="348" alt="Screenshot 2023-04-09 at 1 10 39 PM" src="https://user-images.githubusercontent.com/106120403/230786541-4c20058a-f47b-4a6a-b3a1-ad9f109f92ab.png">

I partitioned by the "date_built" field on the formatted parquet home sales data and created a temporary table for the parquet data to run the query that filters out the view ratings with an average price of greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.

It took 0.7188 seconds to run this query. This took less the time to run compared to the uncached data above but took longer than the data that was only cached and not partioned.

<img width="348" alt="Screenshot 2023-04-09 at 1 15 43 PM" src="https://user-images.githubusercontent.com/106120403/230786803-b75567c8-e8c6-4555-8ccc-88b0a90b792c.png">

I uncached the home_sales temporary table and verified that the home_sales temporary table is uncached using PySpark.

