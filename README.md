Movie Recommendation Systems
This repository contains two distinct movie recommendation systems, each designed with a unique approach and dataset.

1. Indian Movie Recommendation System
This system is specialized in recommending Indian movies, leveraging various attributes for precise suggestions.

Core Functionality: Recommends movies based on similarity using textual and numerical features.

Data Used: Utilizes a dataset named "indian movies.csv," processing movie names, genres, languages, and ratings.

Technical Approach:

Data Preprocessing: Involves cleaning and converting data types for features like 'Year', 'Timing(min)', 'Rating(10)', 'Votes', 'Genre', 'Language', and 'Movie Name'.

Feature Combination: Creates a comprehensive 'Features' string by concatenating 'Movie Name', 'Genre', 'Rating(10)', and 'Language'.

Vectorization: Employs TfidfVectorizer from sklearn.feature_extraction.text to convert the textual features into a numerical matrix.

Model: Uses a NearestNeighbors model with 'cosine' metric and 'brute' algorithm to find similar movies.

Accuracy: The model demonstrates a high accuracy of approximately 99.72%.

Recommendation Process:

Takes user input for a movie title, desired genre, and expected rating.

Transforms the input into a feature vector using the pre-trained TF-IDF vectorizer.

Finds the top 10 nearest neighbors (movies) based on cosine similarity.

Outputs a list of recommended movies including their names, genres, and ratings.

2. General Movie Recommendation System
This system provides broader movie recommendations by analyzing key descriptive elements of films.

Core Functionality: Recommends movies by finding content-based similarities to a user's chosen movie.

Data Used: Processes a dataset (likely "movies.csv" based on the code) with selected features including 'genres', 'keywords', 'tagline', 'cast', and 'director'.

Technical Approach:

Feature Selection: Focuses on 'genres', 'keywords', 'tagline', 'cast', and 'director' as primary features for recommendation.

Data Handling: Fills any missing (null) values within the selected features with empty strings to ensure robustness.

Combined Features: Concatenates the selected textual features into a single string for each movie.

Vectorization: Employs TfidfVectorizer to convert these combined textual features into a numerical representation.

Similarity Calculation: Utilizes cosine_similarity to compute the similarity score between movies based on their vectorized features.

Recommendation Process:

Prompts the user to enter a movie name for which they want recommendations.

Uses difflib.get_close_matches to find the closest match to the user's input from the dataset's movie titles.

Calculates similarity scores for the closest matched movie against all other movies.

Sorts movies by their similarity score in descending order.

Outputs a list of recommended movies, typically the top 15 most similar ones.
