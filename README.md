# HongKong-Airbnb
Well, one day covid-19 will be eradicated, and you have a chance to travel to Hongkong. Of course,  you wanna rent the most suitable listing according to your demands.
We're  here to help you to pick up the "one of the kinds" for you, so you will not be "lost in HongKong" ,mates :D 

The data is sourced from the Inside Airbnb website http://insideairbnb.com/get-the-data.html which hosts publicly available data from the Airbnb site. The dataset comprises of 2 main tables:

Detailed listings data.

Detailed reviews

**Our Target**: Out of three most famous areas (Yau Tsim mong, Wan Chai and Central & Western), which location are the most recommended to our tourists based on 4 factors: Price, Room Type, Review Rate and Host.

**Our target audiences**: Whoever wants to go to Hongkong and desires to rent the suitable airbnb.

**Note**: There are 4 types of room from Airbnb: Private room, Hotel room, Shared room and Entire home or apartment.

## I. Order of the analysis

## Clean data

### 1. Remove unwanted data. 

In the dataset, there are a lot of unnessary columns ( duplicated information, unused data) we decide to remove them:

- scrape_id
- last_scraped 
- description
- picture_url
- host_url
- host_location
- host_about
- host_picture_url
- host_thumbnail_url
- neighbourhood
- neighbourhood_group_cleansed
- neighborhood_overview
- property_type 
- bathrooms
- minimum_minimum_nights 
- maximum_minimum_nights
- minimum_maximum_nights
- maximum_maximum_nights
- minimum_nights_avg_ntm
- maximum_nights_avg_ntm
- calendar_updated
- calendar_last_scraped
- number_of_reviews_ltm
- number_of_reviews_l30d
- license
- host_listings_count
- host_neighbourhood
- first_review
- last_review

### 2. Changing datatype and dealing with missing data

#### Host
- Remove the '%' from the columns host_response_rate, host_acceptance_rate and change these columns to float type.
- Filling the missing value with the mean of other rows in those columns.
- Remove remaining nan values in columns.

#### Room type

- Change bedrooms and beds columns to the int type
- Filling the missing value based on the type of property
- Changing the bathroom column to int and fill the missing values.

#### Price
- Caculate the average price per one person based on the accommodate( how many people able to stay in) and create the new column "Price_Accomodate"

#### Rating and review
- There are different review rates, we decide to remove duplicated data



### 3. Check the duplication of the table
-  We check to see any duplicated rows in the table and any duplicated listing_id.
If anything is fine, we just move on.

### 4. Check mislabeled data and detect ourliers, any illogical data
- We detect that there's small portion of listings with NO BEDS (it's quite strange), since it's accounted for small percentage and does not help our analytic. We will drop them.

- After clean all the data, we move to EDA.

## EDA (Exploratory Data Analysis)

### 1. Host
There are different graphs we draw: 
- Average host response rate, host acceptant rate over 3 areas
- Total host, Total 'Super' Host over 3 locations
- Percentage of Host response time and instant booking
- Kinds of amennities ( like kitchen, washer, air conditions etc.) over 3 districts.

### 2. Room Type
- The percentage of listings in terms of room type
- Number of people can stay in each room types ( divided into 3 groups: up to 4, from 4 to 10, more than 10 people)
- Minimum nights require by host for each type (average)
-  Average beds and bathrooms for each room type.
### 3. Price
- Average pricer per person for each area
- Total property for each area
- Price vs Room type etc.
### 4. Rating and reviews
- Total reviews per neiboughood
- Room type reviews per area
- Score rating distribution for each area
### 5. Map 
We design the small application when you fill all the information needed (room type, number of people , price, review, beds), it will spot all properties that satify conditions on google map. When you click the spot, it'll lead you to URL of this listing on Airbnb directly ( pretty cool huh?)

Have fun with it!!!

## II. Presentation
our presentation will be on the Google data studio ( you can find the link on top of the ipynb), so we will take you through the overview of each area. 
Then we do the comparisons on 4 factors ( price, room type, rating and amenities) to find the most desirable neiboughood !!! 
Find out which one by yourself !!!


