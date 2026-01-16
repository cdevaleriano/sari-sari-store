# Sari Sari Store Analytics
The dashboard presents the performance of a fictional _sari-sari store_, a small convenience shop in the Philippines. It helps the business owner understand customer patterns to make inform decisions on inventory and daily operations.

## Problem Statement
A fictional sari-sari store owner requires clear insight that directly impact profitability and sustainability. The owner wants to know how much revenue the store generates over time, which products drive or hinder performance, whether stockouts are causing lost sales, which items are overstocked and tying up limited capital, how sales fluctuate across days and time periods, when peak sales occur, and which products should be prioritized for restocking. Without clear answers to these questions, the store owner is unable to make informed, data-driven decisions to optimize inventory, maximize sales opportunities, and improve overall business performance.

## Data Source
Using a dataset from Kaggle that is modified with the help of AI, data showcasing gross sales, purchased goods, payment method used, and time of purchase were analyzed. The dataset is under public domain which allows me to modify such dataset to represent scenarios simulating real-world transactions in a _sari-sari store_.

## Data Cleaning
I first checked if the types assigned for each column are correct, changing data categories as needed. Then, I checked for missing values, to which there are none. I also created a "Number of Goods Sold" column which helped me later on in data modeling. All of this is done using PowerQuery.

## Data Modeling
I only have a singular flat dataset. To generate a star-schema, I created the Price and Data dimensions by duplicating the original flat dataset. For the Price dimension, I filtered the dataset copy to just transactions with only 1 product sold using the "Number of Goods Sold" column I created earlier. For the Data dimension, I sorted all the date-time values present in the data. I used the transaction date-time and product sold as my fact table, where transactions with more than one goods sold are separated per column and pivoted to allow a two-column fact table to be formed. The keys for the whole schema are the transaction date-time and the name of the product sold.

## Insights & Recommendations
- During the month of February 2024, peanut butter, eggs, and toothpaste are the top 3 products sold. This shows the need of restocking the aforementioned products on a regular basis.
- Sales shows its peaks from days 14-20, which implies that it is ideal to restock before pay-day (middle of the month) to maximize revenue.
- In the latter half of the month, a high amount of mobile payment (e-wallet) payments was observed. As monthly limits are present in e-wallets, it is recommended to prepare these platforms for transactions at this time of the month.
- As no costs were present in the data, this may be included to determine profits for future analysis.


