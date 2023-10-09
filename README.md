# Final-Project-Tableau

## Project/Goals

I selected to work with Option 2 which was a cleaned data set of FIFA players from FIFA 2018 game. The game has more than 17k players with 70 attributes extracted. The goal of this project is to perform Exploratory Data Analysis, observe trends, patterns and outliers. Use those initial observations to tell a meaningful story through visualizations.

## Process
### I connected the dataset to Tableau (without stress), studied and tried to understand the entire dataset. Examined the datatypes. Most of the relevant datatypes were numerical columns.

1. The valuable missing data are number of goals scored, number of matches played, number of assists, passes completed, succesful tackles, successful interceptions, number of club championships won, number of continental and international trophies won for country. It made sense these vital data were missing because the data was downloaded from a one year FIFA game edition.
2. The most important features from the dataset are:
 - `[Age]`
 - `[Name]`
 - `[Nationality]`
 - `[Club]`
 - `[Overall]`
 - `[Value]`
 - `[Worth]`

The other numeric data are also important but these few takes precedence.

### The numerical features are too many to be analyzed individually (this would consume a whole lot of time and reduce efficiency). Two important categories were created:

1. I classified the players based on their `[Overall Player index]` (an index calculated using the formula (`[Overall]` + `[Potential]`) / 2). The classifications are:
 - The number, 1, assigned to "Low Grade", for `[Overall Player Rating]` between 40 and 54.
 - The number, 2, assigned to "Average Grade" for `[Overall Player Rating]` between 55 and 69.
 - The number, 3, assigned to "High Grade" for `[Overall Player Rating]` between 69 and 79.
 - The number, 4, assigned to "Top player" for `[Overall Player Rating]` between 80 and 89.
 - The number, 5, assigned to "Superstar" for `[Overall Player Rating]` above 90. 
     - These classifications was vital to introducing cluster analysis into the visualization.
     - The Clustering created five clusters and some players were not assigned to any of the clusters. The algorithm assigned the order of the clusters in reverse to the above classification. For example, the number, 5, assigned to "Superstar" was designated as `Cluster 1`. The number, 1, assigned to "Low Grade" was designated as `Cluster 5`.

2. I divided the players into  categories based on positions (Strikers, Midfielders, Defenders, Goalies, Playmakers and players with really low stats). These position categories were based on `[Striker's index]`, `[Midfielder's index]`, `[Defender's index]` and `[Goalkeeper's index]`. Each of these indexes were calculated based on the combination of several features that are specific for each position's requirements. For example, the `[Striker's index]` was calculated by taking the average of `[Shot power]`, `[Vision]`, `[Dribbling]`, `[Acceleration]`, `[Ball control]`, `[Finishing]`, `[Heading accuracy]`, `[Sprint Speed]` and `[Reactions]`. Other indexes such as `[Versatility index]` (a player's ability to play in multiple positions), `[Setpieces index]` (freekicks, penalties) and `[Playmaker IQ]` (creating goal chances, creative passes, assists) were calculated.

All the index calculations were done using named calculated fields.

### During the EDA process, the following questions came into focus:
1. What are the most vital contributors (features) to the value of a player?
2. Is there a correlation between the worth of a player and the nationality he comes from?
3. Which player performance metrics has the strongest influence on a player's value?
4. Which player position has the highest payday?
5. How does a player translate moving to a new club into a business decision?

### Dashboards were then focused on attempting to find answers to these questions
 - First dashboard visualizes the influence of `[Age]` on a player's career and performance.
 - Second dashboard visualizes possible correlations between `[Nationality]` and `[Value (€)]` of players.
    - After these findings through visualizations, a question popped up. Are these the only determinants of a player's successful career run?
 - Third dashboard attempts to answer the question by looking into individual metrics of players (by ranking).
 - Fourth dashboard visualizes differences between `[Player Positions]` and correlations to `[Value (€)]`.
 - The final dashboard explores the categories of players by combined salaries and visualizes the possible club moves for players based on their classification.

### Rationale for choice of visualizations
####  The dataset contains a lot of numerical data types, no date/datetime data type and no categorical data types. This rules out the possibility of plotting time series graphs as well as other line graphs related to time. The types of visualizations included in the project are:
 - Bar charts
 - Histograms
 - Stacked bar chart
 - Scatter plots
 - Maps
 - Bubble map
 - Heat map.

## Results
The results of the data visualization were presented using a story. The story begins from the correlations of `[Age]` to other vital features of a player. Then answers the question if `[Nationality]` has a connection to player's value. It proceeds to explain how individual metrics plays it role. Lastly, it finds which position is most financially profitable.

### Key takeaways
 - Age has a strong positive correlation with a player's salary and worth. The average age were players earn the most is approximately 26 years.
 - Players belonging to certain countries tend to be have a more successful career and they have higher market value. Some anomalies deviate from this conclusion.
 - A player's worth is not the only deciding factor for the player's salary. Other metrics such as `[Setpieces index]`, `[Playmaker IQ]`, `[Versatility index]`, `[Overall Player Rating]` also contributes to a player's worth and salary.
 - Players that are strikers generally tend to have higher worth and higher wage compared to other positions.
 - The classification a player falls into will determine the amount of money he can make and the potential clubs that will be willing to pay his worth.


## Challenges 
 - I initially started working on Option 1 because I felt my data visualization skills were insufficient for a standalone task. I spent four to five hours trying to parse the JSON file by extracting relevant columns into Tableau, failed to connect the other Excel files together, not understanding most of the columns in the tables. After going deep down a rabbithole, I deleved into this dataset instead. For this dataset, my greatest challenge was trying to use my basic Tableau skills to gain meaningful insights from the limited data types in the dataset.
 - The cluster analysis I performed reset itself quite a number of times, without me fiddling around with anything.
 - The URL links included in the dataset are dummies. They're probably attached to a special server only the game can access. The pictures are also probably not real-life pictures of the players (most likely animated jpegs).

## Future Goals
Spend more time working on the Cluster analysis for the classification of players by `[Overall Player Ratio]`. Also try to perform a Cluster analysis for the `[Player Positions]` category. Explore other vital contributors (features) to a player's value (such as player performance metrics e.t.c).
