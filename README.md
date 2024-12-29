## Project Overview
The core of this project is based on analyzing data from the UK Food Standards Agency. This data includes food hygiene ratings of various establishments across the UK.
# NoSQL Challenge: UK Food Hygiene Ratings

1. **Database Setup**: Load the establishments data into a MongoDB database and perform basic setup tasks.
2. **Database Update**: Insert new data, modify existing entries, and remove unwanted data as required by the project.
3. **Exploratory Data Analysis**: Query and analyze the data to answer specific questions regarding hygiene ratings, establishment locations, and other key factors.

---

## Part 1: Database and Jupyter Notebook Setup

In this part, we work with MongoDB and the provided dataset `establishments.json` to create a database called `uk_food` and a collection called `establishments`. We perform the following tasks:

1. **Importing Data**: Import the provided JSON file into MongoDB using the `mongoimport` command.
2. **Setting up the Database**: Create a database named `uk_food` and a collection named `establishments`.
3. **Database Exploration**: Use PyMongo to interact with the database, and Pretty Print (pprint) to format the output.

### Key Steps:
- List all databases in MongoDB to confirm `uk_food` exists.
- List all collections in the `uk_food` database to ensure the `establishments` collection is present.
- Use `find_one()` to display one document from the collection.
- Assign the `establishments` collection to a variable for further use.

---

## Part 2: Database Updates

In this part, we update the database as requested by the magazine editors:

1. **Insert a New Restaurant**: Add data for a new halal restaurant named "Penang Flavours" located in Greenwich.
2. **Business Type Update**: Find the `BusinessTypeID` for "Restaurant/Cafe/Canteen" and update the new restaurant with this ID.
3. **Remove Data**: Remove all establishments located in Dover from the database.
4. **Data Type Correction**: Correct data types for fields like `latitude`, `longitude`, and `RatingValue` to ensure they are stored as decimal numbers and integers.

### Key Steps:
- Use `update_one()` to add "Penang Flavours" to the database.
- Use `find()` to query and find the `BusinessTypeID` for the given `BusinessType`.
- Use `count_documents()` to check the number of documents in Dover before and after removal.
- Use `update_many()` to convert latitude and longitude to decimal numbers and `RatingValue` to integers.

---

## Part 3: Exploratory Data Analysis

In this part, we analyze the data to answer several questions that will help the magazine editors make decisions:

### Key Questions to Answer:
1. **Hygiene Score of 20**: Find all establishments with a hygiene score of 20 and display the results.
2. **Establishments in London with a RatingValue >= 4**: Find establishments in London with a rating value of 4 or higher.
3. **Top 5 Establishments with RatingValue of 5**: Sort the top 5 establishments with a RatingValue of 5 by the lowest hygiene score, nearest to the new "Penang Flavours" restaurant.
4. **Establishments with Hygiene Score of 0**: Group establishments by Local Authority area that have a hygiene score of 0, and sort them by the count.

### Key Steps:
- Use `count_documents()` to get the number of documents that match a query.
- Use `pprint()` to display the first document of the result.
- Use Pandas to convert the results into a DataFrame and display the first 10 rows.
- Perform aggregation using MongoDB's `aggregate()` method to group and sort the data based on the hygiene score.

---

## Technologies Used

- **MongoDB**: A NoSQL database for storing and querying the establishment data.
- **PyMongo**: Python driver for interacting with MongoDB.
- **Pandas**: Used for data manipulation and analysis.
- **Jupyter Notebook**: Interactive environment for coding and analysis.

---

## Setup Instructions

1. **Clone the Repository**: 
   ```bash
   git clone https://github.com/your-username/nosql-challenge.git
   cd nosql-challenge
