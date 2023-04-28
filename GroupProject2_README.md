
# MIST 4610 Group Project 2

Group 21479_9

Rishitha Cheemarla - https://github.com/rishitha-cheemarla/rishitha

Peyton McWhorter - https://github.com/pem83470/Group-9

Andrew Smith - https://github.com/andrewmsjr/Andrew-Smith-4610-Group-9

Somya Tailang - https://github.com/Somya-T/MIST-4610---TEAM-9.git

Ava Weichel - https://github.com/avaweichel/avaweichel


## Data Set Description

AirBnB is a popular worldwide platform that enables people to rent out their properties to travelers from all over the world. It has become a global accommodation platform with listings from over 220 countries. This dataset is very informative as it contains multiple different factors that contribute to a traveler’s considerations when booking an AirBnB. These include data about hosts, locations, and guest reviews. Not only does this data become helpful for travelers looking to stay at these places, but it is also a great source for researchers, data scientists, and AirBnB hosts seeking to gain insights into successful listings for which they can profit off of. Each listing contains detailed information on its location, number of bedrooms, bathrooms, amenities, and reviews. It also contains information about every host of a property such as descriptive profiles, response rates, and acceptance rates. These are essential for indicating a successful AirBnB host, and allows travelers to further trust their hosts with the information. Researchers can also benefit from this information as it would allow them to speculate different economical topics for example how AirBnBs are impacting the local housing markets in a certain area. They can also look up what factors may influence guest satisfaction and if there would be a potential trend on satisfactions in certain areas. Overall, this dataset is a very valuable resource for not only travelers, but also researchers and other AirBnB hosts and we believe it is a great asset as it provides multiple possibilities of questions we can answer for our project.

The AirBnB dataset was obtained through the use of Kaggle, which is a website highlighting different datasets on various topics from all over the world. Kaggle has a unique feature that enables people to find datasets with certain scores of usability out of 10 points. This particular dataset had a score of 10.0 which is why we decided to utilize it. The dimensions of this particular dataset, known as “Listings.csv”, are Listings ID which can be classified as the rows and the rest of the variables can be classified as columns. These include Name, Host ID, Host Since, Host Location, Host Response Time, Host Response Rate, Host Acceptance Rate, Host is Superhost, Host Total Listings Count, Host Identity Verified, Neighborhood, District, City, Latitude, Longitude, Property Type, Room Type, Accommodates, Bedrooms, Amenities, Price, Maximum Nights, Minimum Nights, Review Scores Rating, Review Scores Accuracy, Review Scores Cleanliness, Review Scores Checkin, Review Scores Communication, Review Scores Location, Review Scores Value, and Instant Bookable. These variables have the outputs in various forms such as numeric values, true or false, and word descriptions. Looking at all of these variables, it was a bit overwhelming to decide which ones we would implement into our project, however we decided to use certain variables at a time. For the first question, we decided to use City for rows and the average of the price and count of Listing ID as the columns to compare the listings prices in cities. For the second question, we decided to use the average of the review scores ratings as the rows and the Districts of New York City to compare the ratings of the different boroughs of NYC.

## Questions

Question 1: 
Which cities have the most expensive listings and do those cities have fewer listings?

![Visual 1](https://raw.githubusercontent.com/rishitha-cheemarla/rishitha/main/visual%201.png)

Analysis of Visualization #1:

For the first visualization we posed the question, “Which cities have the most expensive listings and do those cities have fewer listings?” This question is important because when deciding on where to go on vacation/stay for a visit customers will want to have a variety of different options when it comes to cost. Before visualizing the data we predicted that if an AirBnB user wants to visit a city with higher on average AirBnB costs, this would reflect in the fewer number of total listings because of competitive markets and high entrance costs. This prediction does not consistently hold true. For instance Paris has one of the higher average prices but it has substantially more listings than all of the other major cities. This could be due to the fact that Paris is a large fashion hub and tourist area, meaning they could have a larger number of listings and higher average price. This assumption could potentially hold true for New York as well. Hong Kong, Sydney, Paris, Cape Town and New York have high costs of living which could also be related to the higher average price for AirBnB listings in those areas. It is interesting to note that although Rio de Janeiro does not have a high cost of living, it is one of the largest economic and cultural centers of Brazil. Tourism is an important pillar in Brazil’s economy, this could indicate why there is a higher average price for listings located in Rio de Janeiro.

Question 2:
How do AirBnB ratings vary throughout the different neighborhoods of NYC? 

![Visual 2](https://raw.githubusercontent.com/rishitha-cheemarla/rishitha/main/Screen%20Shot%202023-04-27%20at%207.13.49%20PM.png)

![Supplementary Visual](https://raw.githubusercontent.com/rishitha-cheemarla/rishitha/main/supplementary%20visual.jpeg)

Analysis of Visualization #2:

For our second visualization we posed the question, “Where are the highest rated listings in New York City (80-100) and how do they vary in frequency/rating depending on which borough they are in?” This question is important to ask because when customers are looking for an AirBnB to book, they will be looking for one in a prime location with a high rating. To create these visualizations we used data from the city, district, and review scores columns. By filtering the city to New York, district to each of the respective boroughs, and review scores to 80-100 we were able to display the data that we were looking for. We also colorized the review scores ratings with green dots representing scores closer to 80 and red dots representing scores closer to 100. By creating this series of visualizations, we are able to come to the conclusion that the highest frequency of 80+ ratings are centered in Manhattan and the borders closest to Manhattan in the surrounding boroughs. 

In addition to the map of each individual listing rating within the 5 boroughs of New York, we also provided a histogram for the ratings. The histogram is the result of the average rating from guests who stay at an AirBnB in each borough. The average rating for each borough’s listings overall is displayed. The resultant histogram shows that Staten Island has the highest average rating, followed by Brooklyn, the Bronx, Queens, with the lowest being Manhattan. 

## Data Manipulation

For our analysis, we utilized the average price data for each of the listings. Since the price for each of the listings was in each separate country’s currency, we needed to convert each of the prices into a common currency. We took the exchange rates for each country and created a case-when calculated field to convert each price into U.S. dollars for the comparison between the listings that are in different countries.