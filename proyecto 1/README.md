# Programming Project for NBA Predictions with KMeans

## Problem Definition
In the world of sports, it's crucial to be able to predict what will happen in the future. What I aim to achieve in this project is to predict, based on the last three seasons (2020-2021, 2021-2022, and 2022-2023), which players will improve, worsen, or maintain their performance. This information is vital for sports executives and coaches because knowing what will happen in the future allows them to make better decisions.

I collected the databases for 2020-2021, 2021-2022, and 2022-2023 from Kaggle, importing them to my computer. Several things were done during the data cleaning and preparation process, including:

- Removing duplicate players and putting the last team the player played for in the "TOT" position.
- Removing players who do not appear in all three seasons.
- Setting the players' names as the index.
- Converting categorical variables to numeric.
- Renaming columns to identify which year they are from.
- Normalizing dataset values.
- Discretizing some statistics.

## Exploratory Data Analysis
I made several comparisons of statistics to see if there was a relationship between two statistics. Some interesting insights I found were:

- There is a direct relationship between points scored and turnovers generated. The more points a player generates, the more turnovers they create.

- There is a relationship between points scored and the number of free throws attempted. The more points a player scores, the more free throws they attempt.

- Another interesting relationship is that a player's rebounds are related to the number of free throws attempted.

After using the KMeans algorithm, I used bar charts to understand more easily the trend of players within that cluster.

## Methodology 
The libraries used were:

- Pandas: for dataframe management.
- Numpy: for operations with np.arrays.
- Matplotlib.pyplot: for data visualization.
- Sklearn.cluster.KMeans: for grouping players with similar trends.
During the project development, certain unexpected things arose:

- How to evaluate the model's effectiveness.
- How to convert the "Tm" variable to numeric.
- Discovering that the dataset for the 2020-2021 season was incomplete and only contained data for a portion of the season.

## Predictive Analysis 
I decided to use the KMeans algorithm, which is an unsupervised clustering algorithm. This fits well with my project because I do not have a "Y" that tells me the results; I only have "X" columns and not "Y" columns.

For data preparation, the operations specified in the data collection and preparation section were performed. In addition to that, the three dataframes were concatenated into one, using the player's name as the reference point.

The data was trained and predicted in a single line with the fit_predict() operator based on the dataset with the data, and then a new "Cluster" column was created from the fit_predict() result.

The model was evaluated using the statistics from the 2023-2024 season and comparing the players' performance with the KMeans predictions. The same data cleaning and feature engineering process was applied to this database as was done with the initial databases.