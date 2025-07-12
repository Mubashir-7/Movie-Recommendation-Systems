# 🎬 Movie Recommendation Systems

Welcome to the **Movie Recommendation Systems** repository!
This repository features **two distinct movie recommendation engines** — each with its own unique dataset, methodology, and application focus. Whether you're looking for Indian cinema recommendations or general movie suggestions, this project delivers smart, accurate, and content-based recommendations.

---

## 📌 Project Overview

This repository includes:

1. **Indian Movie Recommendation System** – A specialized recommender system tailored for Indian films.
2. **General Movie Recommendation System** – A broader system for global movie recommendations using content-based filtering.

---

## 🧠 1. Indian Movie Recommendation System

This model is finely tuned to recommend **Indian movies** by analyzing both **textual and numerical attributes** such as genre, rating, and language.

### ✅ Core Functionality

* Recommends movies based on **similarity metrics** using a combination of features.
* Takes into account user preferences for **movie title**, **genre**, and **expected rating**.

### 📊 Dataset

* **Filename:** `indian movies.csv`
* **Key Features:** `Movie Name`, `Genre`, `Language`, `Rating(10)`, `Votes`, `Timing(min)`, `Year`

### ⚙️ Technical Architecture

* **Data Preprocessing:**

  * Cleaned and normalized features: `'Year'`, `'Timing(min)'`, `'Rating(10)'`, `'Votes'`, `'Genre'`, `'Language'`, `'Movie Name'`
  * Handled missing values and ensured uniform data types

* **Feature Engineering:**

  * Created a new column named `Features` by **concatenating**:
    `'Movie Name' + Genre + Rating + Language`

* **Text Vectorization:**

  * Used **TF-IDF Vectorizer** (`sklearn.feature_extraction.text.TfidfVectorizer`) to convert the text features into a numerical vector space

* **Recommendation Model:**

  * Implemented a **K-Nearest Neighbors (KNN)** model
  * Metric: **Cosine Similarity**
  * Algorithm: **Brute Force Search**

* **Accuracy:**

  * Achieved an impressive **99.72% accuracy** on internal validation

### 🎯 Recommendation Process

1. Accepts user input: `movie title`, `preferred genre`, and `desired rating`
2. Transforms the input into a feature vector using the pre-trained TF-IDF model
3. Finds the **top 10 nearest movies** using cosine similarity
4. Displays a list of recommended movies with details: `Movie Name`, `Genre`, `Rating`

---

## 🌐 2. General Movie Recommendation System

This system is designed for a **global audience**, providing content-based movie recommendations using descriptive metadata.

### ✅ Core Functionality

* Recommends movies by evaluating **content similarity** to the user’s chosen movie
* Focuses on descriptive elements like **genres, cast, keywords**, and more

### 📊 Dataset

* **Filename:** `movies.csv` (assumed)
* **Selected Features:** `genres`, `keywords`, `tagline`, `cast`, `director`

### ⚙️ Technical Architecture

* **Data Preprocessing:**

  * Null handling: Replaced missing values with empty strings for consistency
  * Unified text features into a new column called `Combined Features`

* **Text Vectorization:**

  * Applied **TF-IDF Vectorizer** to transform textual content into vector format

* **Similarity Computation:**

  * Calculated **cosine similarity** between all movie vectors

* **Input Matching:**

  * Used `difflib.get_close_matches()` to find the best match for user input

### 🎯 Recommendation Process

1. User enters a movie title
2. System finds the **closest match** from the dataset
3. Computes similarity scores between this movie and the entire dataset
4. Returns a ranked list of the **top 15 most similar movies**

---

## 🛠️ Tech Stack

| Component         | Tool/Library                                         |
| ----------------- | ---------------------------------------------------- |
| Language          | Python 3.x                                           |
| Data Processing   | pandas, numpy                                        |
| Text Processing   | sklearn (TfidfVectorizer, NearestNeighbors), difflib |
| Similarity Metric | Cosine Similarity                                    |
| IDE               | Jupyter Notebook / VS Code                           |

---



📧 Email: (mubashirajaz17@gmail.com)



