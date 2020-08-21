# Creating a recommender system using the MovieLens 100k dataset

##### Contributors:
##### - Dan Hales, danhalesprogramming@gmail.com
##### - Nick Pardue, nickpardue@gmail.com

### [Our Presentation]

![nextflik.jpeg](https://github.com/danhales/mod-4-project/blob/master/Images/nextflik.jpeg)

### Our Business Problem
We decided to create a movie recommendation website to compete with Netflix. As such, we needed a way of recommending movies to users who visit our site, based off of movies they've previously seen and rated.

We were given data sourced from [MovieLens]. Using this data, we sought to find out the following:
- Do popular movies tend to be more highly rated?
- How do users tend to rate movies?
- On average, are there any genres that are rated higher than others?
- Are there any genres that tend to get more ratings?

### Data Sets
Our Sourced Data
- [MovieLens 100k]

[Our Cleaned Data] 


### Cleaned Data Description
We analyzed a dataset of 100k movie ratings from 610 users, across just under 10k movies. Each contained the following *relevant* variables:
 - movieId
    - A numerical identifier of the movie being rated.
 - title
    - The title of the movie being rated.
 - userId
     - The user who submitted the rating.
 - rating
     - The rating a user gave to a movie, ranging between 0.5 and 5. 
 - genres
    - The genre(s) of the movie being rated.
 

### Exploratory Analysis

 ##### Figure 1: Do popular movies tend to be more highly rated?
 - We found that, yes, movies with a higher number of ratings tend to have a higher average score (between a 3 and 4). 
 
![pop_movies.png](https://github.com/danhales/mod-4-project/blob/master/Images/pop_movies.png)

 ##### Figure 2: How do users tend to rate movies?
 - We found that users tend to rate movie movies around 3.5 to 4. Additionally, we the vast majority of users will rate less than 100 movies, and as users rate more movies, their average rating tends to converge towards the aforementioned average.
 
![user_ratings](https://github.com/danhales/mod-4-project/blob/master/Images/user_ratings.png)

 ##### Figure 3: On average, are there any genres that are rated higher than others?
- Looking at the average rating of each genre, there seems to be no indication of a genre that tends to be rated significantly higher than others.
 
![genre_rating.png](https://github.com/danhales/mod-4-project/blob/master/Images/genre_rating.png)

 ##### Figure 4: Are there any genres that tend to get more ratings?
 - After ruling out a genre's average rating as a factor of which type of movies we should seek out for expanding our library, we decided to look into total number of ratings for each genre. We assume that this will give an accurate representation of what kinds of movies users tend to watch. Consulting the chart, we will continue to seek out movies that fall under a mixture of the Drama, Comedy, Action, Adventure, and Thriller genres.cn

![genre_num.png](https://github.com/danhales/mod-4-project/blob/master/Images/genre_num.png)


### Modeling

 ##### Figure 1: Results on Training Data Set
 - We split our original data set into a training and a test set (80:20), and then used our new model on the training set. We found out that in predicting the rating of a movie our user has not seen yet will fall within 0.70 of the user's true rating. With the test data, our predictions fell within 0.89 points of the user's true rating. We feel as if this is an acceptable amount of error because the difference in a 4-star rating and a 5-star is not that much.
 
 ![rmse.png](https://github.com/danhales/mod-4-project/blob/master/Images/rmse.png)
 
 ##### Figure 2: Prediction Output
 - Here's an example of a given user's rating from the test data. The ratings for Toy Story and Toy Story 3 were outside of the 0.89 range of error, but the other predictions were spot on. 
 
 ![results.png](https://github.com/danhales/mod-4-project/blob/master/Images/results.png)




### Limitations
- We would like to gather more users and their ratings, so that we can update our model and provide more accurate predictions. 

### Future Improvements
- Gather more users and ratings.
- Implement user keywords for the creation of new features.
- Implicit data collection to see how many times a user watches a movie, how much of a movie they watch, info on binge-watching, etc.


### Reproducing Our Results
Download the [MovieLens 100k] dataset, and then follow along with our [Executive Notebook] to produce a copy of our results.

### Repo Navigation
```
├── Images
│   ├── .DS_Store
│   ├── genre_num.png
│   ├── genre_rating.png
│   ├── nextflik.jpeg
│   ├── pop_movies.png
│   ├── results.png
│   ├── rmse.png
│   └── user_ratings.png
│
├── .DS_Store
│
├── Movie Recommender.pdf
│
├── README.md
│
├── data.zip
│
└── index.ipynb

```

### Sources of Images Used in Presentation
Sources can be found in [our presentation]'s speaker notes.



[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)
  
   [our presentation]: <https://github.com/danhales/mod-4-project/blob/master/Movie%20Recommender.pdf>
   [speaker notes]: <https://docs.google.com/presentation/d/1xnrlgDIvaFU81D9UaHOV6xwSMlestMnAqT6yQaIody4/edit?usp=sharing>
   [movielens]: <https://movielens.org/>
   [movielens 100k]: <https://grouplens.org/datasets/movielens/>
   [our cleaned data]: <https://github.com/danhales/mod-4-project/blob/master/data.zip>
   [executive notebook]: <https://github.com/danhales/mod-4-project/blob/master/index.ipynb>


