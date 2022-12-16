# TMDB-Movies-Analysis
## Table of Contents
```
Introduction
Data Wrangling
Exploratory Data Analysis
Conclusions
```
## Introduction

<sub>This data set contains information about 10,000 movies collected from The Movie Database (TMDb), including user ratings and revenue. According to the dataset, We generate several questions:<sub/>
```
Which year has the highest release of movies?
Which Movie Has The Highest Or Lowest Profit? Top 10 movies which earn highest profit?
Movie with Highest And Lowest Budget?
Which movie made the highest revenue and lowest as well?
Movie with shorest and longest runtime?
Which movie get the highest or lowest votes (Ratings).
Which Year Has The Highest Profit Rate?
Which length movies most liked by the audiences according to their popularity?
Average Runtime Of Movies From Year To Year?
Which genres are most popular from year to year?
What kinds of properties are associated with movies that have high revenues?
```
## Questions
```
1. Which genres are most popular from year to year?
2. What kinds of properties are associated with movies that have high revenues?
```

## Data Wrangling & Cleaning
```
- Removing the duplicate data
- Droping some columns that are useless
- Droping null values columns which has small portion in dataset
- Changing the data type
```
# Exploratory Data Analysis
## Research Question 1 Which genres are most popular from year to year?
<sub>For this question, I choose to use popularity score to determine the most popular genres. I didn't use vote_average because the total vote for each movie is different. On analyzing the popular movies from 1960, following steps can be made:<sub/>
```
- Seperating the genres colunm. We notice in genres columns, it contains multiple values separated by pipe (|) characters.
- Calculate the average popularity score by each genres in every single year.
- Extracting the max average popularity score in each year and find out the genres type.
- Creating the bar plot to observe which genres is the most popular one.
```
## Result: We can see clearly that over all years, the adventure is the most popular genres.
> 
- From the plot, we can see the adventure genres is counted 14 times with the max average popularity score during 1960-2015.
- Animation is also popular because the frequency is over 10 times.
- The action, music, mystery, science fiction, western, history and thriller generes are below 2 times which means they are also not likely to be the most popular genres in the future.
## Research Question 2 What kinds of properties are associated with movies that have high revenues?
<sub>According to real life experience, we assume that popularity, budget, vote_average and runtime might associate with movies that have high revenues.<sub/>
> 
- Using sns.regplot() function to draw the scatter and regression line.
- Extracting that four properties from original dataset and finding the pairwise correlation of factors.
- Creating a correlation matrix plot
## Result:
>
- From scatter plot, we find that popularity,budget,vote_average and runtime have positive relationship with revenue.
- Budget and popularity have a stronger positive liner correlation.
- The correlation between revenue and budget is 0.73 which means we can assume if we invest a larger budget, the revenue has more posibility to increase.
- The correlation between revenue and polularity is 0.66 which means if the movie become more popular, the revenue seems to be increasing.
# Conclusions
```
1. Based on analysis, the adventure is the most popular genres.
2. Popularity and budget are more associated with movies that have high revenues.
```
# Limitations:
```
1. For the first question, some movies have several genres and we separate them. However, those genres for one movie correspond to the same popularity score. If we only analyse the movie with individual score, the result would be more accurate.
2. For the second question, there are some zero value in revenue and budget columns we haven't dropped might influence the result.
3. We only use porpularity factor as the standard for popular movie. The voting score can also be a consideration to test if a movie is popular or not.
4. For the movies that have high revenue, I assume popularity,budget,vote_average and runtime as potential influence factor based on my life experience. There might be other properties also associated with high revenue that I didn't include.
5. There is no evidence to see the budget and revenue column use the same currency unit. So it is possible that different movies have budget in different currency according to different production company.
6. When I did the data cleaning process, splitting the '|' in the cell into rows is a challenge for me.
```
