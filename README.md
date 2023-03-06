# Rentalytics
Analyzing Airbnb Data to Optimize Your Stay

## Data Cleaning
- Dropped columns that were deemed unnecessary such as information about the host's location and description column which wouldn't be helpful in model training
- Converted text columns with numerical values such as "bathrooms_text" into numerical values, counting shared-bathrooms as half of a private bathroom
- dropped the $ and converted price column into numerical value
- Used an imputer to fill in null values
- Dropped listings which were missing price values, neighbourhood, bedrooms, beds, and other values deemed important
- Used one-hot encoding to convert categorical columns into numerical values
- Replaced t and f values with 1 and 0
- Created a different column for each amentiy available
- removed price outliers

## EDA
- Visualized the distribution of price
- Created a scatterplot to see the correlation between price and number of bedrooms
- Used a correlation matrix to determine which columns had the strongest correlation with price
- Looked at the distribution of neighbourhood frequency

## Model Selection
- Attempted a linear regression model which performed very poorly with 700+ columns, but performed significantly better when the number of features was in the 20s.
- Attempted a Random Forest model which performed significantly better then the linear regression model when there were 700+ features, but only slightly better when the feature number was in the 20s.
- Attempted a XGBoost model which had comparable performance to the Random Forest without hyperparameter turning when there were 700+ features, and slightly worse when the feature number was in the 20s.

## Feature Engineering
- Created a distance_from_toronto column which calculates the distance between the Airbnb listing and the CN tower using the Haversine formula.
