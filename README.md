# Introduction

## About the Data
Using the tweet archive of the Twitter account @dog_rates (WeRateDogs), 3 datasets were gathered, accessed, and cleaned. Dogs are rated on WeRateDogs, a Twitter account, with a funny comment about the dog. After cleaning, the master dataset was then stored in as a CSV file followed by some insights on the report.



## Project Guide


### Step One
For the first step of the project, data was gathered from three sources, namely; a CSV file containing data on archived tweets, a TSV file containing data on the images in the archived tweets, and a JSON text file of some additional tweet data. 


### Step Two
The  second step, the data was first accessed visually (both within the notebook and also externally using MS Excel). Thereafter, the data was accessed programatically using some `pandas` and its methods. From this process, a total of 14 quality and tidiness issues were discovered, itemized, and then cleaned in the 3rd step. These issues includes:



#### Tidiness issues
1. All 3 tables are based on the same entity, therefore they should be merged to 1 table.

2. Dog stages spread across 4 different columns (`doggo`, `floofer`, `pupper`, `puppo`) 

3. Actual tweet `text` column contains a URL that should be on another column.

4. Dog breed and prediction (True/False) not in one Column



#### Quality issues 
1. Table contains rows not required in analysis (rows indicating retweets, replies and quotes).

2. Some tweets are not dog ratings.

3.  Tweet `source` cloumn contains HTML script.

4. Dog stages representing `null` values as a string `None`.

5. The `rating_denominator` column contains values not equal to 10.

6. The `rating_numerator` column contains values that are not consistent with the usual ratings.

7. Certain dog `name` values are misrepresented. Also, `null` values misrepresented a string `None`.

8. Dog named "O" instead of "O'Malley".

9. Table contains columns not required in the analysis.

10. Incorrect data types in some columns (id, twitter_id, timestamp, retweet_count, favorite_count).


### Step Three
In the third step, copies of the data were  merged and then cleaned systematically using the above list of issues as a guide.  Some of the steps taken to clean up the dataset includes;

- Converging the dog stages into 1 column from 4 different columns

- Spliting columns with more than one variable into separate columns with each column containing a single variable

- Removing some rows not required, such as rows of retweets, replies, and tweet quotes. Also, rows where the images were not of dogs (this depended on some image predictions made using a machine learning algorithm outside the scope of this project)

- Correcting wrongly extracted data, such as some dog names and also dog ratings.

- Dropping some irrelevant columns from the dataframe and also setting data types of some columns appropriately.
