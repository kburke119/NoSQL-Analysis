# NoSQL-Analysis

## Background
The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. I was contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

## Analysis

Database and Jupyter Notebook Set Up:
- Imported the data provided in the establishments.json file from my Terminal. Named the database uk_food and the collection establishments.
- Within my notebook, imported the libraries needed: PyMongo and Pretty Print (pprint).
- Created an instance of the Mongo Client.
- Listed the databases I have in MongoDB. Confirmed that uk_food is listed.
- Listed the collection(s) in the database to ensure that establishment is there.
- Found and displayed one document in the establishments collection using find_one and displayed with pprint.
- Assigned the establishments collection to a variable to prepare the collection for use.

Updated the Database
- The magazine editors had some requested modifications for the database before I could perform any queries or analysis for them. Made the following changes to the establishments collection:
- An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine asked me to include it in my analysis. Added their information to the database.
- Found the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType fields.
- Updated the new restaurant with the BusinessTypeID I found.
- The magazine is not interested in any establishments in Dover, so checked how many documents contain the Dover Local Authority. Then, removed any establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they were deleted.
- Some of the number values are stored as strings, when they should be stored as numbers. Used update_many to convert latitude and longitude to decimal numbers.

Exploratory Analysis:
- Used count_documents to display the number of documents contained in the result.
- Displayed the first document in the results using pprint.
- Converted the result to a Pandas DataFrame, printed the number of rows in the DataFrame, and displayed the first 10 rows.
- Which establishments have a hygiene score equal to 20?
- Which establishments in London have a RatingValue greater than or equal to 4?
- What are the top 5 establishments with a RatingValue of '5', sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
- How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
