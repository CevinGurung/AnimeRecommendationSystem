# Anime Recommendation System (Content-Based + KNN + K-Means)

A simple **Anime Recommendation System** built in **Google Colab (Python)** using the `anime.csv` dataset.  
This project cleans the dataset, performs feature engineering using **TF-IDF**, and applies **three recommendation approaches**:

1. **Cosine Similarity (Content-Based Filtering)**
2. **K-Nearest Neighbors (KNN)**
3. **K-Means Clustering + Recommendation (within cluster)**

It also includes multiple **visualizations** (Matplotlib + Seaborn) to explain dataset insights and algorithm outputs.

---

## 📌 Features

- Upload dataset directly in Google Colab
- Dataset cleaning (missing values, duplicates, invalid values)
- Exploratory Data Analysis (EDA) visualizations:
  - Rating distribution
  - Episodes distribution
  - Members distribution
  - Top genres
  - Anime type distribution
  - Correlation heatmap
- Feature engineering:
  - TF-IDF vectorization for `genre` + `type`
  - Standard scaling for numeric features (`rating`, `episodes`)
  - Combined feature matrix using sparse matrices
- Recommendation algorithms:
  - Cosine similarity recommendations
  - KNN recommendations (cosine distance)
  - K-Means clustering recommendations
- Evaluation visualizations:
  - Elbow method (K vs inertia)
  - Cluster size distribution
  - PCA 2D scatter plot (clusters)
  - Seaborn recommendation overlap heatmap (between algorithms)

---

## 📂 Dataset

The dataset file used is:

- `anime.csv`

Expected columns (may vary slightly depending on dataset version):

- `name`
- `genre`
- `type` *(optional but recommended)*
- `episodes`
- `rating`
- `members` *(optional)*

---

## ⚙️ Technologies Used

- **Python**
- **Google Colab**
- **Pandas / NumPy** (data processing)
- **Matplotlib / Seaborn** (visualization)
- **Scikit-learn** (ML algorithms)
- **SciPy Sparse** (efficient feature matrix operations)

---

## 🧠 Algorithms Used

### 1) Cosine Similarity (Content-Based Filtering)
- Converts anime `genre` and `type` into TF-IDF vectors
- Measures similarity between anime using cosine similarity
- Recommends top N most similar anime

✅ Best suited for this dataset because it is feature-based (no user ratings history).

---

### 2) KNN (Nearest Neighbors)
- Uses `NearestNeighbors` from scikit-learn
- Finds the closest anime based on cosine distance
- Similar to cosine similarity but uses a KNN approach

---

### 3) K-Means Clustering + Recommendation
- Reduces high-dimensional features using PCA / TruncatedSVD
- Groups anime into clusters using K-Means
- Recommends anime from the same cluster using cosine similarity

Used mainly for:
- segmentation/grouping
- visualization and report explanation

---

## 📊 Visualizations Included

### Before Cleaning
- Missing values bar chart
- Missingness pattern (first 200 rows)

### After Cleaning
- Rating, Episodes, Members distributions
- Top 15 genres bar chart
- Anime type distribution bar chart
- Correlation heatmap

### After Algorithms
- Elbow method (cluster selection)
- Cluster sizes bar chart
- PCA 2D scatter plot (clusters)
- Silhouette score plot
- Score distribution comparison (boxplot/violin)
- Recommendation overlap heatmap (Cosine vs KNN vs K-Means)

---

## ▶️ How to Run (Google Colab)

1. Open Google Colab  
2. Copy and paste the notebook code blocks  
3. Upload `anime.csv` when prompted  
4. Run all cells in order

---

## 🧪 Testing

The system is tested using these anime titles:

```python
TEST_TITLES = [
    "Naruto",
    "Death Note",
    "One Piece",
    "Shingeki no Kyojin",
    "Steins;Gate"
]

## 👤 Author

**Cevin Gurung**  
