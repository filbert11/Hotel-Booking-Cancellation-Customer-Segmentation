# Hotel Booking Cancellation Customer Segmentation
## Introduction

Booking cancellation is one of the factors affecting hotel revenue management forecast. In order to reduce hotel booking cancellations, we explore customer segmentation of our guests at resort hotel H1. This allows us to understand the customer segmentation that has the highest cancellation rate. We then can design hotel products and services to better serve our customers and to reduce hotel booking cancellation which in turn will allow us to improve our hotel revenue management forecast.

The dataset used in this project is obtained from “Hotel Booking Demand Datasets” (Antonio et al., 2019) which is obtained from https://www.sciencedirect.com/science/article/pii/S2352340918315191. 
<br> It is a Resort hotel dataset in Portugal.

## Exploratory Data Analysis (EDA)
There are 10 category of rooms, there are too many categories. Thus, we narrow down the rooms into 3 categories: Budget, Economy and Premium.
<br> Room A and P are categorised as budget as the median cost is much lower.
<br> Room D, E, B and F are categorised together as Economy as there is big jump of price to room L.
<br> Room G, C and H are categorised as Premium.
<br> Based on the new room price category, most customers book premium rooms for the resort hotel.
![RoomPrice](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/RoomPrice.jpeg)

Each booking comes with a meal option. Most customers have opted for BB (Breakfast and Bed).
![Meal](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/Meal.jpeg)

Most customers stay for a short stay (<7 days). In terms of each booking stay, most customers stay for 1 day.
![TotalStay](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/TotalStay.jpeg)

There are 124 different customers' nationalities staying at this hotel with majority customers are from Portugal follows by United Kingdom, Spain, Ireland, France, Germany and then follows by Non-EU countries like China.
![CountryDistribution](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/CountryDistribution.jpeg)

To simplify the different customers' nationalities, the customer nationalities are categorised into Portugal, European countries and Non-european countries.
Majority customers are 1) European, 2) Portugal (local) and 3) Other Countries.
![RecodeCountryDistribution](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/RecodeCountryDistribution.jpeg)

Most customers don't make special requests follows by 1 special request and a small proportion of customer make >=2 special requests.
![SpecialRequests](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/SpecialRequests.jpeg)

There are very few customers who come with a number of total guests > 5 people and most bookings have 2 total guests.
![TotalGuests](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/TotalGuests.jpeg)

Most bookings made are made via Online Travel Agent.
![MarketSegments](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/MarketSegments.jpeg)

The lead time distribution shows majority bookings are made 1 month before the actual stay.
![LeadTimeDistribution](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/LeadTimeDistributions.jpeg)

The peak period for the hotel is August follows by July. This is probably due to Summer holiday.
![ArrivalDateMonth](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/ArrivalDateMonth.jpeg)

## Clustering
Majority of the features are categorical. Thus, KModes algorithm is adopted for this project.As lead time is in numerical values, the time is categorised into 4 quartiles to make it categorical. The categorical features are transformed via get_dummies to maintain the feature name.

To determine the optimal number of cluster, elbow methods are use to find the optimal no of clusters.
<br> Based on the elbow method, the optimal no of cluster is 3.
![ElbowMethod](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/ElbowMethod.jpeg)

Visualisation of each cluster on the data space.
![CustomerSegmentation](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/CustomerSegmentation.jpeg)

To understand the characteristics of each cluster, overall data mean and standard deviation are computed. Next, each cluster label data relative mean and standard deviation to overall data are also computed to understand each cluster label unique characteristics.
<br> The characteristics of each cluster label is plotted as follows:
![CustomerSegmentationCHaracteristics1](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/CustomerSegmentationCharacteristics1.jpeg)
![CustomerSegmentationCHaracteristics2](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/CustomerSegmentationCharacteristics2.jpeg)
![CustomerSegmentationCHaracteristics3](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/CustomerSegmentationCharacteristics3.jpeg)

## Insights and Findings
Based on the relative characteristics of each group, these are the following key characteristic of each group and their cluster names.

Key characteristic for cluster label 0 group:
1. Have kids
2. Have mid booking lead time between 2-week to 2-month period
3. Make special requests
4. Reserve economy and premium room
5. Make online bookings
6. Have 2-4 guests
7. Have long stays
8. Travel during summer school holiday (majority arrives on June, July and August)
9. Interpreted customer group name: Personal (Family)

Key characteristic for cluster label 1 group:
1. Reserved by companies with a lot of booking changes
2. Have highest booking lead time between 6-month to 2-year period
3. Have contract with the hotel or transient party (the booking is associated to at least other transient booking)
4. Are group and travel operator market segments
5. Are from European countries
6. Orders meal
7. Travel all year round (majority arrives on March, April, May, September, October, December)
8. Interpreted customer group name: Group Tour

Key characteristic for cluster label 2 group:
1. Have the highest relative no of booking cancellations
2. Are repeated guests
3. Have lowest booking lead time less than 1-week period
4. Are group customers (the booking is associated to a group)
5. Are corporate, direct and complimentary customers
6. Are from Portugal
7. Have either 1 or more guests
8. Have short stay (1-day to 2-day)
9. Majority arrives on January, February and November
10. Interpreted customer group name: Corporate (Company)

## Product Design and Recommendations
From the data, it looks like the Corporate customers have the highest no of booking cancellations.

To improve the hotel revenue forecast management, we can take the following strategy for the hotel to minimize the hotel booking cancellations:
1. Encourages the customers to make a special request like conducting special celebration, have unique feature like "Pick your guitar" and "DJ turntable" from Hard Rock Hotel Example, etc.
2. Establishes a contract with the company
3. Offers deal for booking with high lead time

## Conclusion
In conclusion, this project uses KMode clustering algorithm to segmentise the hotel booking cancellation customers into 3 segments Personal (Family), Group Tour and Corporate (Company) segments to understand the characteristics of each customer segment to minimise the hotel booking cancellations.

After studying the customer segments for each hotel, product and service could be designed to lower the cancellation rate of the hotel to improve hotel revenue forecast management.
