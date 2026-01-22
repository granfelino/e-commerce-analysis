# E-commerce data analysis in python

* Data source: [LINK](https://www.kaggle.com/datasets/carrie1/ecommerce-data)
* This analysis was to train and solidify my pandas skills in cleaning, transforming and then analyzing and aggregating data.

-----
### Cleaning process:
* To start I used `.describe(include="all")` to get an overview of what values, ranges and extremes I can expect in each column.
* I look what dtypes columns have gotten automatically assigned.
* I look how many missing values each column has.
* Then I take each column and analyze its contents:
    1. I look for a pattern which describes the majority of the rows.
    2. I try to look for rows not matching this pattern.
    3. I try to look for values which should not be possible (e.g. negative price).
    4. I look at quantiles (0.001, 0.01, 0.99, 0.999) to see what extremes I can expect.
    5. I check wether the extremes make sense.
    6. I filter out missing rows or fill them appropriately.
    7. I assign the cleaned column its appropriate dtype.
* I drop duplicates from the dataset.
* I check once again if there are any values missing to make sure I did not skip anything.

-----
### Analysis
* The data stems from an UK retailer (information from the source, but also pretty obvious from analysis, since the revenue comes mainly from UK).
* This dataset spans one year of invoice data: 2010-12 to 2011-12.

* On average there are about 26 different products in an invoice.

[Quantile distribution of revenue](./plot/quantile_distribution.png)
* The majority of the revenue comes from invoices of very pricey orders (quantile 80-100% brings in the majority of the revenue).

* The revenue levels differs from month to month, usually very much (changes of order 20-57% over month).
* Notable months are:
    * December 2011 -> big drop in revenue from the previous month. Does the retailer not offer any Christmas presents ideas?
    * March, May, September and November 2011 -> gained a lot of revenue in comparison to their previous months.

* Apart from UK where the store is based the following countries generate a lot of revenue for the retailer:
    1. Netherlands
    2. Ireland
    3. Germany
    4. France
    5. Australia
    6. Spain
    7. Switzerland

* Among the top 3 countries by revenue, by month, outside of UK, these were present:
    * Germany
    * Ireland
    * France
    * Netherlands
    * Australia
    * Singapore <- was not in the top countries by total revenue - appeared once in April 2011
