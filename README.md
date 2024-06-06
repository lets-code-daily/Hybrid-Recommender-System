# Hybrid-Recommender-System
Recommendation system for movies based on combined techniques of collaborative filtering as well as content based filtering


# Content-based Filtering Approach
- Create tags using text data like - genres, overview, director, cast
- We can assign weightages as : genres >> cast >> director >> overview
- We can also use Doc2Vec or BERT for overview for better results
- Vectorize these words
- Create Cosine Similarity Matrix
  
  Voila! we have a working content based recommender


# Collaborative Filtering Approach
- Create pivot table with title/movie_id and user_id as rows and columns and ratings as values
- Normalize rating values by subtracting each rating with the average rating for that movie
- Fill NaN values with 0 after normalization
- Vectorize each movie based on the user rating vectors
- Create Cosine Similarity Matrix

We have a working colaborative filtering recommender


# Hybrid Recommendation System
- Assign weightages to the two systems based on our data
- If we have a lot of textual details about the movie and we use a vectorizer that utilizes seantic meaning of the words
   then we can give more weightage to Content Based Filtering Matrix
- If we have a lot of ratings data then we can assign greater weightage to Collaborative Filtering Matrix
- Create Hybrid Matrix => hyb_sim = w1 * cont_sim + w2 * colab_sim

Finally we have used the results of both appraoches and created a Hybrid Recommender System
