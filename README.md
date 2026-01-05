# Movie Recommendation System  
**Collaborative Filtering & Matrix Factorization (kNN → Tuned SVD)**

## Project Summary
Built a personalized movie recommendation system that predicts user ratings for unseen movies and generates **Top-5 recommendations**.  
The system addresses **choice overload** and demonstrates how collaborative filtering models perform on a **highly sparse user–item matrix**.

---

## Problem & Value
**Problem:** Users disengage when they cannot quickly find relevant content.  
**Solution:** Predict user preferences from historical ratings and surface the most relevant movies.

**Business Value**
- Improves content discovery
- Supports “Recommended for You” personalization
- Helps reduce churn and increase engagement

---

## Data
- **Dataset:** [MovieLens](https://grouplens.org/datasets/movielens/latest/) - [ml-latest-small](https://files.grouplens.org/datasets/movielens/ml-latest-small.zip )
- **Users:** 610  
- **Movies:** 9,742  
- **Ratings:** 100,836 (0.5–5.0 scale)
- **Key challenge:** ~98% sparsity

---

## Modeling Approach
Implemented and compared **two forms of collaborative filtering**:

1. **Neighborhood-based CF**
   - Item-based `KNNBaseline` (Pearson baseline similarity)

2. **Model-based CF (Matrix Factorization)**
   - `SVD` with latent user/movie factors
   - Hyperparameter tuning via GridSearchCV
   - Selected as final model

A bias-only baseline was used for benchmarking.

---

## Evaluation
- **Metrics:** RMSE, MAE (rating accuracy)
- **Final holdout performance:**  
  - RMSE ≈ 0.87  
  - MAE ≈ 0.67  

Also demonstrated:
- Existing-user recommendations
- Cold-start handling via seeded ratings
- Popularity-based fallback for true cold start

---

## Tech Stack
- Python
- pandas, NumPy, matplotlib
- scikit-learn
- Surprise (recommender systems)

---

## Repository Structure

```text
├── notebooks/          # Jupyter notebook analysis
├── data/               # MovieLens CSV files
├── reports/
│   └── figures/        # Visualizations
├── presentation/       # Non-technical presentation
├── requirements.txt    # Python dependencies
└── README.md
```

---

## Future Improvements
- Ranking metrics (Precision@K, Recall@K, NDCG@K)
- Hybrid recommender using genres/tags
- Implicit feedback (clicks, watch time)
- Online A/B testing

