# Ames Housing Data / Kaggle Challenge

## Predicting Housing Prices in Ames, Iowa

### My process:

**What data to use?**
Looking at the the data, the file had 2051 rows, with around 80 coloumns. I started to explore the data by reading the dictionary to get familiar with the data/data types. After, I started my cleaning process by first filling in the null columns with values I saw fit. I looked at categorical data and changed some columns to integers and some I dummied depending on the value of the given row. Howver, creating dummy columns for the categorical data led to an increasing number of features given only 2050 entries. After realizing this, I decided to look at the correlation between all data of the numerical columns and sales price. To shorten my time, I chose only columns with above a .4 correlation value to use in my prediction model. While it sounded good at the start, in hind sight I regret not using most of my data and I will explain in the end why.

**Predictive Models**
The three models I used for my predictions were Linear, Ridge, and Lasso Regression. For my training data, I polyfit the data in order to create a polynomial features dataframe to help increase my r2 scores than without polyfitting my data. Using polynmial features increased my r2 scores by almost a value of .10.

**Outcomes and Conclusions**
Choosing highly correlated training data with my target variable worked fine as a first submission but it was hard to improve my model and get better results. Having highly correlated data gave me less outliers. Having less outliers meant my Lasso and Ridge Regression r2 scores would be similar in value. Ridge Regression scaling all the coeffieciens vs Lasso getting rid of all the outliers would obviously lead to some different values depending on the data given but with mine, the scores were similar. Further it was hard for me to create interaction features on my cleaned data because polyfitting my features gave me all combinations squared. This was not good in the end because since my data was decently correlated, some of the combinations would show alot of colinearity and create noise when fitting my model. The only way somehow make my model better was to go through the features by hand and drop features that seemed to show high colinearity. If I would have had more time, I would have used most features given. I would create dummies for categorical data that I didnt turn in numerical values and dorp the dummy columns that has 0 values or close to zero. This would only leave me with correlated dummy features. Lastly I would use a Lasso Regression to get rid of the outliers and give me a better r2 score. I would not have used polynomial features for this dataset. Not polyfitting my features would allow me to create more interaction features and reduce the noise generated by the colinear polynomial features. Doing it this way would allow me more space to itterrate and improve my model.