# nosql-challenge


## Part 1: Database and Jupyter Notebook Set Up 

Include the mongoimport command text you used to import establishments.json in a markdown cell at the beginning of your Jupyter notebook file 

The mongoimport command text correctly drops any existing establishments collection before importing establishments.json into MongoDB 

The database is named uk_food and the collection is named establishments 

Correctly imports PyMongo and Pretty Print 

An instance of the Mongo Client is created 

Lists the databases you have in Mongo, which includes uk_food 

Lists the collection(s) in the uk_food database, which includes establishments in the output 

Uses find_one() and pprint to display one document in the establishments collection 

The establishments collection is assigned to a variable 

## Part 2: Update the Database 

The supplied data for the "Penang Flavours" restaurant is correctly inserted into the establishments collection 

A query is performed to find the BusinessTypeID for "Restaurant/Cafe/Canteen" and returns only the BusinessTypeID and BusinessType fields 

The "Penang Flavours" document is updated with the correct value for BusinessTypeID 

A query is correctly performed to delete all the documents in the collection where "Dover Local Authority" is the value for LocalAuthorityName 

A count_documents() check is performed before and after the removal of the Dover documents to ensure the documents were removed

An update_many() query is performed to convert the latitude and longitude fields from strings to decimal numbers

## Part 3: Exploratory Analysis 

Question 1: Which establishments have a hygiene score equal to 20?

A query is correctly performed to find the establishments with a hygiene score of 20 

count_documents() is used to list the correct number of documents (answer: 41) 

The first result is printed using pprint 

The results are converted to a Pandas DataFrame and displays the first 10 rows 

Question 2: Which establishments in London have a RatingValue greater than or equal to 4?

A query is correctly performed to find the establishments in London with a RatingValue greater than or equal to 4

The query uses the $regex operator to locate the London establishments 

count_documents() is used to list the correct number of documents (answer: 34) 

The first result is printed using pprint 

The results are converted to a Pandas DataFrame and displays the first 10 rows 

Question 3: What are the top 5 establishments with a RatingValue of '5', sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"? 

A query is correctly performed to find the establishments within 0.01 degree of the "Penang Flavours" restaurant

The query also limits the results to establishments with a RatingValue of 5 

The query uses the sort() method in PyMongo to sort in ascending order on the hygiene score 

The query uses the limit() method in PyMongo to limit the results to 5 

All five results are printed using pprint 

The results are converted to a Pandas DataFrame and displayed 

Question 4: How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas. 

An aggregation pipeline is built to include a match query, group, and sort 

The match query matches documents with a hygiene score of 0 

The group step of the pipeline is grouped on LocalAuthorityName and counts the number of documents

The sort step of the pipeline sorts the count of the documents in descending order 

The aggregation pipeline is correctly sent to the aggregate() method 

The results from the aggregation query is cast as a list and then saved to a variable 

The first ten results are printed using pprint 

The results are converted to a Pandas DataFrame and displays the first 10 rows 