# nosql-challenge

The purposes of this exercise include performing CRUD (Create, Read, Update, Delete) operations on a NoSQL database and analyzing the results to answer specific questions about establoshments in the UK.

## Part One (located in NoSQL_setup_starter.ipynb):

The database called uk_food was created and populated by importing a json file into MongoDB. The resulting collection is called establishments. A missing halal restaurant called Penang Flavours was added to the database and was used as a reference for most of the analysis. Due to it missing partial data (specifically the BusinessTypeID), the entire database was queried to locate the equivalent of "Restaurant/Cafe/Canteen" used on other records, since this was the classification of Penang Flavours.

The database was further updated by converting the longitude and latitude to floats and the RatingValue to integers instead of strings. Records containing data for the Local Authority of Dover were also removed.

## Part Two (located in NoSQL_analysis_starter.ipynb):


## Questions to resolve: 
### Which establishments have a hygiene score equal to 20?

For context, hygiene was rated on a scale of 0 through 20. 20 represents a poor score in this area, while a score closer to 0 indicates a better rating.

Below is a partial screenshot of the resulting DataFrame for establishments that had the worst hygiene score of 20. As mentioned, there were 41 establishments that were categorized as the worst hygiene possible.

![alt text](Resources/images/hygiene_twenty.png)

### Which establishments in London have a RatingValue greater than or equal to 4?
On the opposite end of the spectrum, the RatingValue given to an establishment was on the scale of 1 to 5. 1 represented a low rating while a 5 represented a high rating.

Below is a screenshot of the establishments in London that had a rating of at least 4. There were 33 establishments that fit this qualification.

![alt text](Resources/images/london_rating_four.png)


### What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

This query involved locating the longitude and latitude of the newly added Penang Flavours restaurant to be used as a reference to find the top five establishments that have the highest rating and sorted by hygiene, from the best hygiene to the worst. Noticeably, it can be seen that the highest rated establishments tended to have better scores in hygiene. Below are those establishments that are within +/- 0.01 degrees in latitude and longitude of Penang Flavours.

![alt text](Resources/images/top_five.png)

### How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

The final topic that was explored involved finding out how many establishments in each of the local authorities had a hygiene score of 0 (the best hygiene). It was discovered that there were 55 total local authorities that had establishments with the best hygiene score possible. A screenshot of that DataFrame's head is below.

![alt text](Resources/images/hygiene_zero.png)






