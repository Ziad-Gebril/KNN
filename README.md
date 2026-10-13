# Collaborative Filtering Recommendation System

## Overview

This project implements and evaluates a collaborative filtering recommendation system using the **MovieLens `ml-latest-small` dataset**. The goal is to predict users' movie ratings based on similarities between users or items.

The project explores different similarity measures, compares user-based and item-based collaborative filtering, and evaluates their performance using prediction error metrics.

## Dataset

- **Dataset:** MovieLens `ml-latest-small`
- **Content:** Movie ratings provided by users.
- **Main data:** User IDs, movie IDs, and ratings.

The dataset is used to build a user-item rating matrix and generate rating predictions.

## Features

- **Similarity Measures**
  - Euclidean-based similarity
  - Cosine similarity
  - Pearson correlation

- **Collaborative Filtering Approaches**
  - User-based collaborative filtering
  - Item-based collaborative filtering

- **Model Evaluation**
  - Root Mean Squared Error (RMSE)
  - Mean Absolute Error (MAE)
  - Prediction coverage

- **Parameter Experiments**
  - Comparison of different numbers of nearest neighbors (`k`)
  - Evaluation of different similarity measures
  - Comparison of user-based and item-based approaches

- **Bonus Experiment**
  - Mean-centered rating prediction to investigate the effect of user rating biases.

## Methodology

### 1. Similarity Calculation

The system calculates similarity scores between users or movies using Euclidean-based similarity, cosine similarity, and Pearson correlation.

Each measure captures similarity differently, allowing their effects on recommendation accuracy to be compared.

### 2. User-Based Collaborative Filtering

The system identifies users with similar rating patterns to the target user. Their ratings are then used to predict the target user's rating for a movie.

### 3. Item-Based Collaborative Filtering

The system identifies movies similar to the target movie based on users' rating patterns. Ratings for similar movies are used to predict the target user's rating.

### 4. Evaluation

The different configurations are evaluated using RMSE and MAE. Prediction coverage is also considered to measure the proportion of test cases for which the system successfully generates predictions.

## Experimental Results

The best-performing configuration in the reported experiments was:

| Configuration | Result |
|---|---:|
| Approach | Item-based CF |
| Similarity | Euclidean |
| Number of neighbors (`k`) | 50 |
| RMSE | 0.924326 |
| MAE | 0.715924 |
| Prediction coverage | 92.82% |

Item-based collaborative filtering with cosine similarity and `k = 50` achieved the second-best reported performance, with an RMSE of `0.950446` and an MAE of `0.734755`.

These results suggest that item-based collaborative filtering with Euclidean similarity performed best among the tested configurations.

## Technologies Used

- Python
- NumPy
- Pandas
- Jupyter Notebook
- MovieLens dataset

## How to Run

1. Clone or download this repository.
2. Install the required Python libraries.
3. Download the MovieLens `ml-latest-small` dataset if it is not already included.
4. Open the project notebook in Jupyter Notebook or Google Colab.
5. Run the cells in order to load the dataset, calculate similarities, generate predictions, and evaluate the different configurations.

Install the commonly used dependencies with:

```bash
pip install numpy pandas jupyter
```

Additional libraries may be required depending on the notebook's imports.

## Conclusion

This project demonstrates how collaborative filtering can be used to build a movie recommendation system. By comparing different similarity measures, neighborhood sizes, and recommendation approaches, the experiments show how these choices affect prediction accuracy and coverage.

The results highlight the potential of item-based collaborative filtering for this dataset, particularly when using Euclidean-based similarity with 50 neighbors.

## Author

Student project — Collaborative Filtering and Recommendation Systems.
