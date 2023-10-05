# Home_Sales - Module 22 Challenge (Big Data)

* The spark dataframe was created from the dataset in the S3 bucket (home_sales_df)
* This was then used to create a temp table for the sql queries (home_sales)
* All sql queries were executed and run time is calculated for the 4th query - 0.16817092895507812 seconds
* The temp table was cached and the 4th query was rerun - with run time was reduced to 0.12298989295959473 seconds
* The original spark df (home_sales_df) was used to create parquet data (home_sales_date_built) and partitioned by date built
* Temp table (home_sales_pt) was created using parquet data and the 4th query was rerun - run time increased to 0.18746376037597656 seconds
* The original temp table (home_sales) was unchached

#### So parquet does not necessarily decrease run time. Especially since the query tested required average home sales across different values of partition ie. built years 

### Note - The 4th query question is worded differently for the original temp table vs. the cached and parquet tables. I used the following interpretation:
    "run the query that filters out the view ratings with an average price of greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime."
This translates to listing view ratings where average price is greater than 350K
