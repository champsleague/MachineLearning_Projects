# Machine_Learning_Projects  

### Machine Learning Movie Recommendation System



### Business Objective 
* Our Business Objective is to make Movie Recommendation System by using user’s data
* The System filters and predicts movies that corresponds to user’s favor.
* It’s a system for people who are thinking about which movie to choose


![image](https://user-images.githubusercontent.com/94350277/204816396-5c3b3409-323d-48bf-a981-9e222c0677a1.png)  
Source : NETFLIX(https://www.netflix.com/kr/)  


### Data Exploration & Preprocessing
* We used 2 datasets to make recommendation & test system
* Main Dataset is ‘TMDB 5000 Movie Dataset’  
https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata

* Test Dataset is ‘The Movies Dataset’  
https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset


* Kmeans - Clustering  
![image](https://user-images.githubusercontent.com/94350277/204838127-a590d3ef-2755-4b89-baa4-20f27a1bc967.png)  

* DBSCAN - Clustering  
![image](https://user-images.githubusercontent.com/94350277/204838234-2b59a2ce-0d7f-465d-9dd3-54e7ceb838c1.png)  


* Use 'ratings.csv', 'movie_metadata.csv‘ to fit Main dataset and joined 2 datasets by using ‘movieId’
* TMDB 5000 Movie Dataset has no ratings, so join The Movies Dataset’s ‘ratings.csv’ by using 'tmdbId‘ feature.  
![image](https://user-images.githubusercontent.com/94350277/204837862-62d00f2d-d589-450f-8f1a-dee3fefc9401.png)  

* Normalize Numerical data using Min Max Scaler, Standard Scaler
* Encoding Categorical data using One-hot Encoding
![image](https://user-images.githubusercontent.com/94350277/204837824-5bf3f5ed-81e8-4989-ad6c-5f5a8354d09e.png)  

------------------------------------------------------

### Modeling

#### Matrix Facorization  
* TMDB 5000 Movie Dataset has no ratings, so join ‘ratings.csv’ of ‘The Movies Dataset’ by using 'tmdbId‘ feature.
* Made Matrix using joined data 
* Made pivot table and non-zero values.
* Training RMSE Learning rate = 0.02, epoch = 100, RMSE remained 0.22 
* Truncate using SVD  
 
![image](https://user-images.githubusercontent.com/94350277/204835223-1fbdafc1-89fc-49e5-9602-eceea6d48ef6.png)  




#### Content Based Filtering
* Get weighted vote using Genre's similarity distance.
* First, get double number of recommendation results by  Genre’s similarity.
* Second, get recommendation results using weighted vote  
![image](https://user-images.githubusercontent.com/94350277/204835710-f451662a-95be-40b9-b44c-eaf5148ac3e8.png)  
10 movies recommendation of ‘The Godfather’  




#### Collaborative based Filtering  
* Generating movie weight based on the user rating and user's view
* Make recommendation system based on criteria 50% voted averaged movies and 50% of popular movies  
![image](https://user-images.githubusercontent.com/94350277/204835924-fde3c903-91b1-449e-8296-7faf2fd85c13.png)  
Generate scores and sort it based on the criteria set in the starting.  



#### KNN
* Convert string type to binary type of 4 features [‘genres’, ‘cast’, ‘director’, ‘keywords’]
* Generate similarity distance for 4 features
* Get neighbor using KNN model with keywords  
![image](https://user-images.githubusercontent.com/94350277/204836125-b33c4d02-e931-4674-84db-4a9f31ccf9cf.png)  
Keyword = ‘God Father‘, K = 10  






