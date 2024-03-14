# PUBG_game_winner_pred
The target is to Create a predictive model which is an attempt to predict the win probability of the Pubg match.

* Data Descritption

- <b>DBNOs -</b> Number of enemy players knocked.
- **assists -** Number of enemy players this player damaged that were killed by teammates.
- **boosts -** Number of boost items used.
- **damageDealt -** Total damage dealt. Note: Self inflicted damage is subtracted.
- **headshotKills -** Number of enemy players killed with headshots.
- **heals -** Number of healing items used.
- **Id -** Player’s Id
- **killPlace -** Ranking in match of number of enemy players killed.
- **killPoints -** Kills-based external ranking of player. (Think of this as an Elo ranking where only kills matter.) If there is a value other than -1 in rankPoints, then any 0 in killPoints should be treated as a “None”.
- **killStreaks -** Max number of enemy players killed in a short amount of time.
- **kills -** Number of enemy players killed.
- **longestKill -** Longest distance between player and player killed at time of death. This may be misleading, as downing a player and driving away may lead to a large longestKill stat.
- **matchDuration -** Duration of match in seconds.
- **matchId -** ID to identify match. There are no matches that are in both the training and testing set.
- **matchType -** String identifying the game mode that the data comes from. The standard modes are “solo”, “duo”, “squad”, “solo-fpp”, “duo-fpp”, and “squad-fpp”; other modes are from events or custom matches.
- **rankPoints -** Elo-like ranking of player. This ranking is inconsistent and is being deprecated in the API’s next version, so use with caution. Value of -1 takes place of “None”.
- **revives -** Number of times this player revived teammates.
- **rideDistance -** Total distance traveled in vehicles measured in meters.
- **roadKills -** Number of kills while in a vehicle.
- **swimDistance -** Total distance traveled by swimming measured in meters.
- **teamKills -** Number of times this player killed a teammate.
- **vehicleDestroys -** Number of vehicles destroyed.
- **walkDistance -** Total distance traveled on foot measured in meters.- 
- **weaponsAcquired -** Number of weapons picked up.
- **winPoints -** Win-based external ranking of player. (Think of this as an Elo ranking where only winning matters.) If there is a value other than -1 in rankPoints, then any 0 in winPoints should be treated as a “None”.
- **groupId -** ID to identify a group within a match. If the same group of players plays in different matches, they will have a different groupId each time.
- **numGroups -** Number of groups we have data for in the match.
- **maxPlace -** Worst placement we have data for in the match. This may not match with numGroups, as sometimes the data skips over placements.
- **winPlacePerc -** The target of prediction. This is a percentile winning placement, where 1 corresponds to 1st place, and 0 corresponds to last place in the match. It is calculated off of maxPlace, not numGroups, so it is possible to have missing chunks in a match.


## Introduction:
**In this report, we present our findings on building a machine learning model to predict the winner of PUBG (PlayerUnknown's Battlegrounds) matches. The objective of this project was to develop a model that accurately predicts the winner based on various in-game features.

## Dataset Description:
**The dataset used for this project consists of various in-game features such as player kills, distance traveled, number of weapons acquired, etc., collected from PUBG matches. The dataset contains both numerical and categorical features, providing a diverse set of information for training the prediction model.

## Challenges Faced:

**Missing Values: One of the major challenges encountered was handling missing values within the dataset. Several features had missing values which needed to be addressed before training the model. We employed techniques such as mean imputation for numerical features and mode imputation for categorical features to handle missing values effectively.

**Feature Engineering: The raw dataset contained numerous features, some of which were redundant or irrelevant for prediction purposes. Feature engineering was crucial to select relevant features and create new informative features. We performed feature selection techniques such as correlation analysis and recursive feature elimination to identify the most predictive features for the model.

**Imbalanced Data: The dataset exhibited class imbalance, with a disproportionate number of matches ending in different outcomes (win/loss). This imbalance could potentially bias the model's predictions. To address this issue, we applied techniques such as oversampling the minority class and using appropriate evaluation metrics like F1-score to account for class imbalance.

**Model Selection: Choosing the most suitable machine learning algorithm for the prediction task was another challenge. We experimented with various algorithms including linear regression, decision trees, ensemble methods (e.g., Random Forest, Gradient Boosting), and advanced algorithms like XGBoost. Each algorithm has its advantages and limitations, and the selection was based on factors such as accuracy, interpretability, and computational efficiency.

## Techniques Used:

**Data Preprocessing: We performed comprehensive data preprocessing steps including handling missing values, feature scaling, encoding categorical variables, and feature selection to prepare the dataset for model training.

**Feature Engineering: Feature engineering played a crucial role in improving the model's performance. We derived new features such as kill-death ratio, player rating, and team size to capture additional information relevant to the prediction task.

**Ensemble Learning: Ensemble learning techniques such as Random Forest and Gradient Boosting were employed due to their ability to handle complex relationships in the data and produce robust predictions. These models combine multiple weak learners to improve overall performance and generalize well to unseen data.

## Conclusion:
**Based on our experimentation and evaluation, we found that [insert best performing model here] emerged as the most effective model for predicting PUBG match winners. This conclusion was reached after overcoming various challenges related to data preprocessing, feature engineering, and model selection. Moving forward, further refinements and optimizations can be made to enhance the model's performance and make it suitable for practical deployment in real-world scenarios.
