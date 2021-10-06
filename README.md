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
* The business team assumed that properties bouth out of summer season and with a price bellow the region's median price shall be sold with 30% over the purchased price and properties bouth on summer season and with a price bellow the region's median price shall be sold with 10% over the purchased price.









This project also wants to validate some hypothesis through data analysis:

H1) Properties with a good condition and waterfront view are 50% more expensive on average than properties with good condition but without waterfront view;

H2) Properties with building year before 1955 are cheaper on average;

H3) Properties without basement have a square footage of the land space 15% bigger than properties with it;

H4) The propertie's price growth YoY (year over year) it's 10%;

H5) Properties with 3 bathrooms have a MoM growth of 15%.

H6) Properties with 2 or more floors are 40% more expensive on average than the others

