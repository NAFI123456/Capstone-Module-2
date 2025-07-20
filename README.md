# Capstone-Module-2-Muhammad Nafi Adziq

## Background
 Supermarket Teby Meong is a popular highly demanded super store available on every country. This dataset gives off a glimpse of customer datasets from the famous Teby Meong Supermarket so we could do an understanding and anaylisis on how the customer varies on Teby Meong mart. With this data we must search for data errors and fix data inputs so that we can pull an outcome that would make more profit just by analyzing the data.
 
## Problem Formula
- What is customer behaviour?
- Data distribution supermarket income according to customer categories? 
- Customers income according to customer categories?
- The campaign is most famous on which category?
- Is the website effectiveness comparable to any other shopping methods?

- ## Data Dictionary
  
- **People**

- ID: Customer's unique identifier
- Year_Birth: Customer's birth year
- Education: Customer's education level
- Marital_Status: Customer's marital status
- Income: Customer's yearly household income
- Kidhome: Number of children in customer's household
- Teenhome: Number of teenagers in customer's household
- Dt_Customer: Date of customer's enrollment with the company
- Recency: Number of days since customer's last purchase
- Complain: 1 if the customer complained in the last 2 years, 0 otherwise
  
**Products**
  
- MntWines: Amount spent on wine in last 2 years
- MntFruits: Amount spent on fruits in last 2 years
- MntMeatProducts: Amount spent on meat in last 2 years
- MntFishProducts: Amount spent on fish in last 2 years
- MntSweetProducts: Amount spent on sweets in last 2 years
- MntGoldProds: Amount spent on gold in last 2 years
  
**Promotion**

- NumDealsPurchases: Number of purchases made with a discount
- AcceptedCmp1: 1 if the customer accepted the offer in the 1st campaign, 0 otherwise
- AcceptedCmp2: 1 if the customer accepted the offer in the 2nd campaign, 0 otherwise
- AcceptedCmp3: 1 if the customer accepted the offer in the 3rd campaign, 0 otherwise
- AcceptedCmp4: 1 if the customer accepted the offer in the 4th campaign, 0 otherwise
- AcceptedCmp5: 1 if the customer accepted the offer in the 5th campaign, 0 otherwise
- Response: 1 if the customer accepted the offer in the last campaign, 0 otherwise
  
**Place**

- NumWebPurchases: Number of purchases made through the company’s website
- NumCatalogPurchases: Number of purchases made using a catalog
- NumStorePurchases: Number of purchases made directly in stores
- NumWebVisitsMonth: Number of visits to the company’s website in the last month

## Data Cleaning

### Null Value and Duplicates

In data cleaning we check all of the null value and duplicates, so far the null value is only 1% of the data and the duplicates is not available in this dataset. 

Knowing that the null value is very small compared to the whole data, it will not affect the data significantly by removing it.

### Value Uniqueness

In column ['Marital_Status'] and ['Education'] there are a total of 5 odd value.

['Marital_Status']
- Together
- Alone
- Absurd
- YOLO

These unique values is then changed to match the other available value options,

- Together -> Married
- Alone -> Single
- Absurd -> Single
- YOLO -> Single

['Education']
- 2n Cycle

After researching the data thoroughly the value '2n Cycle' is actually refering to the educational degree 'Master', 

- 2n Cycle -> Master

To ease data reading there is also one additional value that has been changed 'Graduation'.

- Graduation -> Bachelor

### Additional Column

In the data cleaning session, there are 4 new columns made.

- ['MntTotal'] : This new column serves as a presentation of total amount of money spent per customer
- ['TotalChildHome'] : Depict the total amount of children per customer's home
- ['TotalCmpAcc'] : Shows the total of campaign accepted by each customer
- ['NumPurchasesTotal'] : Sums up all the amount of purchases the customer has made.

### Data Loading

Data is saved as 'SuperMarket Clean.csv' in the same directory as this capstone file location.

## Data Analysist / Data Exploring

### 1. What is Customer Behaviour

#### A. Is there any pairing in customer behaviour?

https://www.bmj.com/about-bmj/resources-readers/publications/statistics-square-one/11-correlation-and-regression

A simple search from the world wide web shows that a correleation is identified by:

- Very weak: 0 to 0.19
- Weak: 0.2 to 0.39
- Moderate: 0.4 to 0.59
- Strong: 0.6 to 0.79
- Very strong: 0.8 to 1.0

As shown from the heatmap, there is no strong correlation reaching more than 60%. The highest correlation achieved by customers is at 59% when the customer gets fish products and fruit at the same purchase, meanwhile the weakest correlation is standing low at only 35.7% for gold products and sweets.

Recommended approach:

- Relive a new campaign that discounts the price when a fish products and fruits is bought at the same purchase.
- Set a new campaing offer for a free set of sweet product after a certain amount of gold products purchases, so the customer experiences an introduction of sweet products.

#### B. Is customers expense based on their yearly income?

The scatterplot doesnt show any extreme fluctuations even tough we have had to remove the outliers to get a glimpse of the data clearly, the only trend that the Income againts MntTotal data visualization experiences is an upward trend, which means that the <b>customer income affects the customer expense<b>.

The higher the customer gets yearly the more the customer spends.

Recommended approach:

- Make an offer of customer subscription, targeting the customer with lower income by adding specialized offer of free products, discounts, etc.

### 2. Data distribution of store Income Based on Categories

#### A. Average Store Income Based off the column category ['Marital_Status']

In this data visualization we use the 'barplot' function, in the 'barplot' function we compare between column ['MntTotal'] and ['Marital_status']. From the data visualization we can see that the highest average store income per ['Marital_Status'] group is on group 'Widow', but this claim might be biased because the amount of customer that is labeled as 'Widow' might have a smaller population compared to the whole. To show the whole distribution of the data spread we call the 'boxplot' function.

After calling the 'boxplot' function we can then bring to a conclusion of the data distribution not only the average.

Recommended approach:

- This problem could easily be fixed at a specific date, valentine should be a great time to give either the broken hearted or the lovey dovey ones a chance of attraction. ex:
  - Spesific discount for couples, by giving discount to 'married' people if they perchance shop together.
  - Make a package mix with items for broken hearted people ex: a package filled with tissues and scented candles.

#### B. Average Store Income Based off the column category ['Education']

The Average of store income based on the categories on column ['Education'] is held by the group 'Master'.

Recommended approach:

- Special campaign event where customers with higher education status gets more discount.

### 3. The campaign is most famous on which category?

#### A. Which category on column ['Education'] accepts the campaign most.

On this part we must make a seperate data frame removing the customers that does not accept any campaign avialable, the data frame is then named as 'dfFilterTotalCmpAcc'. With this part now done, making the data visualization is the next step to making a great data analyst.

We can now conclude that most of the people that accepted the campaign based of the column ['Education'] comes from the group 'Bachelor' standing on a high percentage of 49.7% dominating the rest of the group by half of the entire population.

Recommended approach:

- Form a specified group offering the campaign targeting the group with less campaign accepted value.

#### B. Which category on column ['Marital_Status'] accepts the campaign most.

The category from column ['Marital_Status'] that thrist most for campaign is on group 'Married' standing high at 64.5% of the population.

Recommended approach:

- Form a specified group offering the campaign targeting the group with less campaign accepted value.

### 4. Customers Income Based on Categories 

#### A. Based on column ['Marital_Status']

On this session we split the data visualization into two parts, one including the outliers and the other with the outliers removed. The data visualization with outliers is not easily readable therefore we add another column that is already conditioned.

Before the cleaning we can simplify the result by looking at the data visualization, the highest recorded yearly income is placed on group 'Married' but because the highest income is only held by one singular customer we clean the data by removing the outliers. After the cleaning the highest data recorded has changed, setting the highest holder on group 'Single'.

#### B. Based on column ['Education']

Unlike column ['Marital_Status'], the highest recorded data before and after cleaning is the same (excluding outliers). Column ['Education'] yearly income is stable with group 'Bachelor' as the top data before and after cleaning.

### 5. Is Website Activity Comparable to any other methods?

#### Method Comparison

Customer purchasing activity is split into 4 parts store purchasing, website purchasing, catalog purchasing and discount purchasing. In this spesific part we are comparing wether the website purchasing activity is comparable to any other methods.

From the piechart we can see that website purchasing is not actually the most popular way of shopping, its ranked as the second most preferable way of shopping, one after store purchasing (39.0%). We can now conclude that it is more likely comparable to the other methods, but do they differ a significant much in their value count?.

In the piechart it is shown that website purchases has 27.5% percent of the population meanwhile the other two less known method distributes evenly between each other therefore not having a lot of difference 17.9% (Catalog) and 15.6% (Discount). In conclusion, website purchases is comparable to the other methods available.

#### Website Activity

Customer that visits the website has a 77% of purchasing something.

Recommended approach:

- Develop offers only available in website purchases

## Data Visualization

https://public.tableau.com/app/profile/muhammad.nafi.adziq/viz/Capstone2DataVisualization/Dashboard1?publish=yes

![Alt Text](https://public.tableau.com/views/Capstone2DataVisualization/Dashboard1?:language=en-GB&publish=yes&:sid=&:display_count=n&:origin=viz_share_link)
