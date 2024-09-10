# IPL-Auction-Analysis
1. Data Loading and Initial Exploration:
The dataset pertains to cricket player performance statistics, focusing on variables such as "AGE," "RUNS," "WICKETS," and other key metrics.
The dataset also includes categorical data related to "TEAM" and "PLAYING ROLE," which are used in later steps for interaction terms.
After loading the dataset, data cleaning and filtering were done to ensure that variables like "SOLD PRICE" (dependent variable) and other performance metrics are ready for regression analysis.
2. Feature Engineering:
Interaction Terms:
Interaction terms between key features were created, particularly focusing on the relationship between "PLAYING ROLE" (like Batsman, Bowler, Wicket Keeper) and "TEAM."
The idea was to see if a player’s role combined with their team has a significant impact on the selling price.
These interaction terms allow the model to capture more nuanced relationships in the data, though their effectiveness is evaluated in the later stages.
3. Building the Regression Model:
The primary focus was to build an Ordinary Least Squares (OLS) regression model to predict the dependent variable: "SOLD PRICE."
The independent variables include performance-based statistics like:
AGE (of the player)
RUNS scored by the player
WICKETS taken
TEAM the player belongs to (e.g., MI, CSK, etc.)
PLAYING ROLE (Batsman, Bowler, Wicket Keeper)
Interaction terms between these categorical variables and numeric values (such as Runs, Wickets, etc.)
4. Model Fitting:
Using Python's statsmodels library, the OLS regression was fitted to the data.
The following steps were executed:
Dependent Variable (Target): "SOLD PRICE" was used as the target variable.
Independent Variables: Multiple numeric and categorical predictors were used in the model.
Interaction Effects: The role-team interaction terms were key in testing if the combination of a player's role in a specific team impacts their value in the market.
5. Regression Results and Analysis:
R-squared Value: The model achieved an R-squared of 0.712, meaning that about 71.2% of the variation in the dependent variable ("SOLD PRICE") can be explained by the independent variables.
This is a relatively good fit, suggesting that the model performs well in predicting player prices based on their performance data.
Coefficients and Statistical Significance:
The model output includes coefficients for each predictor, along with their standard errors, t-values, and p-values (statistical significance).
Certain variables like AGE and TEAM_MI (Team Mumbai Indians) showed significant correlations with the sold price.
AGE had a slightly negative coefficient, meaning older players may be sold for slightly lower prices.
TEAM_MI had a significant effect, indicating players from Mumbai Indians are sold at different rates compared to players from other teams.
Interaction Terms:
The interaction between PLAYER ROLE and TEAM did not show a very strong effect on the target variable, as seen from the lack of statistical significance for many of the interaction terms.
This suggests that while a player’s role and team are individually important, the combination of these factors doesn’t strongly influence player value.
6. Model Limitations and Conclusion:
Although the model fit was reasonably good, there are areas that could be improved. Specifically:
Some interaction terms did not contribute significantly to the model and could potentially be dropped in future iterations.
The performance data variables like RUNS and WICKETS had weaker-than-expected effects on the final model, indicating the need for more robust feature selection or engineering.
The results suggest that while player statistics like runs, wickets, and age matter, the team they play for and their role in the team also have an influence on their market value.
Future improvements could include more advanced modeling techniques or the inclusion of additional variables such as player form, injuries, or captaincy roles.
