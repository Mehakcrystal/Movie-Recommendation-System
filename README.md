# Movie-Recommendation-System

A personalized movie recommendation system built using **collaborative filtering**, **K-Nearest Neighbors (KNN)**, and **cosine similarity**. The project analyzes user–movie interactions and generates recommendations based on similarity in user rating patterns.

## Overview

Recommendation systems help users discover relevant content by learning from historical interactions. This project builds a collaborative filtering-based movie recommender using the MovieLens dataset.

The workflow covers:

* Data cleaning and exploratory analysis
* User and movie interaction analysis
* User–item matrix construction
* Sparse matrix representation
* Similarity-based recommendation using KNN
* Recommendation analysis and catalog coverage

## Dataset

The project uses the **MovieLens dataset**, containing:

* **100K+ ratings**
* **670+ users**
* **9K+ movies**
* **98%+ user–movie interaction sparsity**

The ratings data contains user IDs, movie IDs, movie titles, and ratings.

## Methodology

### 1. Exploratory Data Analysis

The dataset is analyzed to understand:

* Rating distributions
* User activity
* Movie popularity
* Average movie ratings
* User–movie interaction sparsity

### 2. User–Item Matrix

A sparse user–item matrix is constructed where:

* Rows represent movies
* Columns represent users
* Values represent ratings

The sparse representation makes it possible to work efficiently with the highly incomplete interaction matrix.

### 3. Collaborative Filtering

The recommender uses **item-based collaborative filtering**.

For a selected movie, the system identifies movies with similar user-rating patterns using:

* **Cosine similarity**
* **K-Nearest Neighbors (KNN)**

The nearest movies are returned as personalized recommendations.

### 4. Recommendation Analysis

The system was evaluated across a sample of users to examine recommendation diversity and catalog coverage.

The recommender surfaced **700+ unique movies**, achieving approximately **9.1% catalog coverage** across the evaluated users.

## Results

| Metric                    | Result |
| ------------------------- | -----: |
| Ratings analyzed          |  100K+ |
| Users                     |   670+ |
| Movies                    |    9K+ |
| Interaction sparsity      |   98%+ |
| Unique movies recommended |   700+ |
| Catalog coverage          |   9.1% |

## Tech Stack

* **Python**
* **Pandas** — data manipulation and analysis
* **NumPy** — numerical computation
* **Matplotlib** — visualization
* **SciPy** — sparse matrix representation
* **Scikit-learn** — KNN and similarity-based modeling
* **Jupyter Notebook / Google Colab**

## Project Structure

```text
Movie-Recommender/
│
├── Movie_Recommender.ipynb
├── README.md
└── data/
    └── ratings.csv
```

> The dataset may be omitted from the repository if its redistribution terms do not permit uploading it. In that case, download it from the original MovieLens source and place it in the `data/` directory.

## How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd Movie-Recommender
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib scipy scikit-learn
```

### 3. Add the dataset

Place the MovieLens `ratings.csv` and corresponding movie metadata file in the `data/` directory.

### 4. Run the notebook

Open:

```text
Movie_Recommender.ipynb
```

and execute the cells sequentially.

## Example

The system can generate recommendations for a movie such as:

```python
recommend_movies(
    "Forrest Gump (1994)",
    ratings,
    movie_stats,
    user_item_matrix,
    movie_mapper,
    movie_inv_mapper,
    model,
    k=10
)
```

The output includes recommended movies along with their similarity scores, average ratings, and rating counts.

## Key Takeaways

* Movie recommendation data is highly sparse, with **98%+ of possible user–movie interactions missing**.
* Collaborative filtering can identify meaningful relationships between movies based on shared user preferences.
* Recommendation coverage provides an additional perspective beyond individual similarity scores.
* Popularity and interaction frequency are important considerations when interpreting recommendation results.

## Future Improvements

Potential extensions include:

* Precision@K and Recall@K evaluation with improved sampling strategies
* Hybrid content + collaborative filtering
* Matrix factorization using SVD
* Cold-start handling for new users and movies
* Popularity-aware recommendation ranking
* Interactive recommendation dashboard

## Author

**Mehak**
IIT Bombay
B.Tech — Environmental Science & Engineering | Minor in AI & Data Science
