# INSIGHT PROJECT - House Rocket

![alt text](https://fasthomes.org/public/img/fast/house-for-sale.jpg)

This project aims to assist a real estate company to maximize it's proffits by indicating a selection of properties based on the best conditions, so the company could buy and sell them. 

## 1. House Rocket
### 1.1. Business Understanding:

House Rocket company belongs to the real estate sector and work with buying and selling properties. It has been consolidated by making good decisions using the technology on your favor.

The House Rocket's CEO wish to maximize the company profits by finding great opportunities, therefore this case will provide insights so the company can find these opportunities. 

The company's strategy is to buy good properties with low prices to sell them later with higher prices. The greater the difference, the bigger the company's profit. However, there are many features influencing their prices and we don't have enought people to analyze this dataset manually. 

### 1.2. Business Question:
In order to take it, it will be provided 2 lists indicating the best properties to buy and the best period to sell them, as well as a visualization link. 
The two main questions behind the project are:
1) What are the properties that house rocket should buy, and for what price?

2) Once purchased, when it's the best time to sell it and for what price?

### 1.3. Data Overview:
Our data has been obtained through the link bellow:
https://www.kaggle.com/harlfoxem/housesalesprediction

This dataset shows all properties available to purchase. Check bellow to see some attributes and it's mean:

| FEATURE       | DESCRIPTION                                                                      |
| ------------- |:--------------------------------------------------------------------------------:|
| id            | Unique ID for each home sold                                                     |                             
| date          | Date of the home sale                                                            |
| price         | Price of each home sold                                                          |
| bedrooms      | Number of bedrooms                                                               |
| bathrooms     | Number of bathrooms, where .5 accounts for a room with a toilet but no shower    |
| sqft_living   | Square footage of the apartments interior living space                           |
| sqft_lot      | Square footage of the land space                                                 |
| floors        | Number of floors                                                                 |
| waterfront    | A dummy variable for whether the apartment was overlooking the waterfront or not |
| view          | An index from 0 to 4 of how good the view of the property was                    |
| condition     | An index from 1 to 5 on the condition of the apartment                           |                 
| grade         | An index from 1 to 13, where 1-3 falls short of building construction and design,7 has an average level of construction and design, and 11-13 have a high quality level of construction and design.|
| sqft_above    | The square footage of the interior housing space that is above ground level      |
| sqft_basement | The square footage of the interior housing space that is below ground level      |
| yr_built      | The year the house was initially built                                           |     
| yr_renovated  | The year of the house’s last renovation                                          | 
| zipcode       | What zipcode area the house is in                                                |   
| lat           | Lattitude                                                                        |
| long          | Longitude                                                                        |
| sqft_living15 | The square footage of interior housing living space for the nearest 15 neighbors |
| sqft_lot15    | The square footage of the land lots of the nearest 15 neighbors                  |

### 1.4. Business Assumptions:
Considering the business understanding during the exploratory data analysis, some assumptions were considered in order to create a few insights. The assumptions are listed bellow:

* Values (11 and 33) on column bathrooms were considered outliers, adjusting their values on properties with similar square foot living. 
* Duplicate "ID" values were removed, considering the newest ones
* For properties condition's scale we considered: 'bad' for condition < 3, 'regular' for condition = 3 and 'good' for condition > 3.
* The year's season has a great influency on our prices. By research, summer season was considered the best period to sell properties
* The business team assumed that properties bouth out of spring season and with a price bellow the region's median price shall be sold with 30% over the purchase price and properties bouth on spring season and with a price bellow the region's median price shall be sold with 10% over the purchase price. 
https://themortgagereports.com/44135/whats-the-best-time-of-year-to-sell-a-home

## 2. Planning Solution
### 2.1. Data analysis:
After collecting the data, it was necessary to treat and explore it. On these steps, data was cleaned, transformed (types) and analysed with the assistance of descriptive statistics in order to identify outliers. 

* Created Features:
  * Season: Season when property was purchased
  * Sell Price: Price that property shall be sold, based on the season
  * Profit: Represents the difference between sell price and price

* Descriptive Statistics:

| attributes    |	maximum   |	minimum |	mean          |	median    |	std           |
|---------------|:---------:|:-------:|:-------------:|:---------:|:-------------:|
| price         |	7700000.0 |	75000.0 |	541649.962726 |	450000.00 |	367306.361583 |
|	bedrooms      |	10.0      |	0.0     |	3.369845      |	3.00      |	0.905393      |
|	bathrooms     |	8.0       |	0.0     |	2.117349      |	2.25      |	0.769895      |
|	sqft_living   |	13540.0   |	290.0   |	2082.704936   |	1920.00   |	919.125029    |
|	sqft_lot      |	920423.0  |	520.0   |	14819.491045  |	7614.00   |	36763.790341  |
|	floors        |	3.5       |	1.0     |	1.496198      |	1.50      |	0.540376      |
|	sqft_above    |	9410.0    |	290.0   |	1790.960440   |	1560.00   |	829.007154    |
|	sqft_basement |	4820.0    |	0.0     |	291.744495    |	0.00      |	442.771655    |
|	yr_built      |	2015.0    |	1900.0  |	1971.098433   |	1975.00   |	29.384591     |
|	yr_renovated  |	2015.0    |	0.0     |	84.729800     |	0.00      |	402.421625    |
|	sqft_living15 |	6210.0    |	399.0   |	1988.314378   |	1840.00   |	685.683099    |
|	sqft_lot15    |	871200.0  |	651.0   |	12785.961280  |	7620.00   |	27374.828923  |









This project also wants to validate some hypothesis through data analysis:

H1) Properties with a good condition and waterfront view are 50% more expensive on average than properties with good condition but without waterfront view;

H2) Properties with building year before 1955 are cheaper on average;

H3) Properties without basement have a square footage of the land space 15% bigger than properties with it;

H4) The propertie's price growth YoY (year over year) it's 10%;

H5) Properties with 3 bathrooms have a MoM growth of 15%.

H6) Properties with 2 or more floors are 40% more expensive on average than the others

