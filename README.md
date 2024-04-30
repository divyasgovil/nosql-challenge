# nosql-challenge
The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. We have been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

# Part 1: Database and Jupyter Notebook Set Up. NoSQL_setup_starter.ipynb for this section of the challenge.

1. Imported the data provided in the establishments.json file and named the database uk_food and the collection establishments. 

2. Within notebook, imported the libraries: PyMongo and Pretty Print (pprint).
Create an instance of the Mongo Client.

3. List the databases in MongoDB. Confirm that uk_food is listed.

4. List the collection(s) in the database to ensure that establishments is there.

5. Find and display one document in the establishments collection using find_one and display with pprint.
Assigned the establishments collection to a variable to prepare the collection for use.

# Part 2: Update the Database. Used NoSQL_setup_starter.ipynb for this section of the challenge.

The magazine editors have some requested modifications for the database before any queries or analysis for them. Made the following changes to the establishments collection:

1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked to include it in the analysis. Added the following information to the database:
{
    "BusinessName":"Penang Flavours",
    "BusinessType":"Restaurant/Cafe/Canteen",
    "BusinessTypeID":"",
    "AddressLine1":"Penang Flavours",
    "AddressLine2":"146A Plumstead Rd",
    "AddressLine3":"London",
    "AddressLine4":"",
    "PostCode":"SE18 7DY",
    "Phone":"",
    "LocalAuthorityCode":"511",
    "LocalAuthorityName":"Greenwich",
    "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",
    "scores":{
        "Hygiene":"",
        "Structural":"",
        "ConfidenceInManagement":""
    },
    "SchemeType":"FHRS",
    "geocode":{
        "longitude":"0.08384000",
        "latitude":"51.49014200"
    },
    "RightToReply":"",
    "Distance":4623.9723280747176,
    "NewRatingPending":True
}
2. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.

3. Update the new restaurant with the BusinessTypeID.

4. The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.

5. Some of the number values are stored as strings, when they should be stored as numbers.

6. Use update_many to convert latitude and longitude to decimal numbers.
   
8. Use update_many to convert RatingValue to integer numbers

# Part 3: Exploratory Analysis. Use NoSQL_analysis_starter.ipynb for this section of the challenge.
Eat Safe, Love has specific questions they want us to answer, which will help them find the locations they wish to visit and avoid.

1. Use count_documents to display the number of documents contained in the result.

2. Display the first document in the results using pprint.

3. Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.

4. Which establishments have a hygiene score equal to 20?

5. Which establishments in London have a RatingValue greater than or equal to 4?

Hint: The London Local Authority has a longer name than "London" so you will need to use $regex as part of your search.

6. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

7. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
