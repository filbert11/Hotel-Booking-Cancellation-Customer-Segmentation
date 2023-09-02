# Hotel Booking Cancellation Customer Segmentation
## Introduction

Booking cancellation is one of the factors affecting hotel revenue management forecast. In order to reduce hotel booking cancellations, we explore customer segmentation of our guests at resort hotel H1. This allows us to understand the customer segmentation that has the highest cancellation rate. We then can design hotel products and services to better serve our customers and to reduce hotel booking cancellation which in turn will allow us to improve our hotel revenue management forecast.

The dataset used in this project is obtained from “Hotel Booking Demand Datasets” (Antonio et al., 2019) which is obtained from https://www.sciencedirect.com/science/article/pii/S2352340918315191

## Exploratory Data Analysis (EDA)
There are 10 category of rooms, there are too many categories. Thus, we narrow down the rooms into 3 categories: Budget, Economy and Premium.
Room A and P are categorised as budget as the median cost is much lower.
Room D, E, B and F are categorised together as Economy as there is big jump of price to room L.
Room G, C and H are categorised as Premium.
Based on the new room price category, most customers book premium rooms for the resort hotel.
![RoomPrice](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/RoomPrice.jpeg)

Each booking comes with a meal option. Most customers have opted for BB (Breakfast and Bed) booking.
![Meal](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/Meal.jpeg)

Most customers stay for a short stay (<7 days). In terms of each booking stay, most customers stay for 1 day.
![TotalStay](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/TotalStay.jpeg)

There are 124 different customers' nationalities staying at this hotel with majority customers are from Portugal follows by United Kingdom, Spain, etc.
![CountryDistribution](https://github.com/filbert11/Hotel-Booking-Cancellation-Customer-Segmentation/blob/main/plot/CountryDistribution.jpeg)

