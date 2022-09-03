# Background
Alphabet Soup wants to develop a tool that can help with selecting  applicants for funding that have the best chance of success in their ventures. In this project data from Alphabet Soup was used to train a  nueral network model that can to help identify funding applicants that have the best chance of succeeding.


To build the model a CSV file containing more than 34,000 organizations that have received funding from Alphabet Soup over the years was used. Within this dataset a number of columns that capture metadata about each organization, such as:

* **EIN** and **NAME**—Identification columns
* **APPLICATION_TYPE**—Alphabet Soup application type
* **AFFILIATION**—Affiliated sector of industry
* **CLASSIFICATION**—Government organization classification
* **USE_CASE**—Use case for funding
* **ORGANIZATION**—Organization type
* **STATUS**—Active status
* **INCOME_AMT**—Income classification
* **SPECIAL_CONSIDERATIONS**—Special consideration for application
* **ASK_AMT**—Funding amount requested
* **IS_SUCCESSFUL**—Was the money used effectively
* 
# Step 1: Preprocess the Data
The following steps were taken to clean up the data and suitable for analysi
EIN and NAME columns were removed to from the dataset as they where not relevant to the analysis
 ![image](https://github.com/mayooks/Alphabet-Soup-Funding-Success-Prediction-Model/blob/main/Images/Picture%2033.png)

The data had no rows with Null values as confirmed by the  code below.
![image](https://github.com/mayooks/Alphabet-Soup-Funding-Success-Prediction-Model/blob/main/Images/Picture%201-second.png)

The code below indicated that the data had duplicated columns. However on close inspection it appeared that different organisation with similar profiles were flagged as duplicates. Therefore it was decided not to delete the columns that were flagged as duplicates.
![image](https://github.com/mayooks/Alphabet-Soup-Funding-Success-Prediction-Model/blob/main/Images/Picture%202.png)

The number of unique values and data types in each column were determined using the nunique() and dtypes functions.The IS_SUCCESSFUL column has two integers that were unique making it ideal target variable             ![image](https://github.com/mayooks/Alphabet-Soup-Funding-Success-Prediction-Model/blob/main/Images/Picture%203.png)

The CLASSIFICATION and APPLICATION_TYPE type columns had 17 and 71 unique values respectively. This is too large for encoding. Therefore binning was used to reduce the unique values in the CLASSIFICATION and APPLICATION_TYPE columns. To do this all unique values that had counts less that 200 value counts were put into the “other” category. This reduced the value counts in this column to 9 from 17

![image](https://github.com/mayooks/Alphabet-Soup-Funding-Success-Prediction-Model/blob/main/Images/Picture%204.png)
![image](https://github.com/mayooks/Alphabet-Soup-Funding-Success-Prediction-Model/blob/main/Images/Picture%205.png)

The CLASSIFICATION column had 71 unique values. This was reduced to 71 to 5 buy filtering out all unique values that had less 1000 value counts. This meant that the classification column had 5 unique values . After the filtering a new dataframe X was formed
![image](https://user-images.githubusercontent.com/103529769/188284526-2d416423-6d87-4aa8-bb74-c62c0d6dd78c.png)

