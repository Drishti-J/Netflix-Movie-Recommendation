
# 🎬 Netflix Movie Recommendation System

### Built with the Netflix Prize Dataset using Python + scikit-surprise

---

## 🚀 Overview

This project builds a collaborative filtering-based movie recommendation system using the **Netflix Prize dataset**. It predicts personalized ratings for unseen movies and generates recommendations using **SVD** (Singular Value Decomposition).

This model replicates the logic behind real-world recommender systems like Netflix, Amazon, or YouTube — showing how to go from raw ratings to personalized recommendations.

---

## 📂 Dataset

**Netflix Prize Data**  
- 24M+ ratings
- 470K+ users
- 4.5K+ movies

Parsed from `combined_data_1.txt`.  
Movie titles mapped using `movie_titles.csv`.

---

## 🔧 Setup

1. Clone this repo or open the notebook in Google Colab.
2. Upload your `kaggle.json` key.
3. Install dependencies:

```python
!pip install --upgrade pip setuptools wheel
!pip install --upgrade numpy==1.23.5
!pip install --no-binary scikit-surprise scikit-surprise
!pip install kaggle
```

4. Download the Netflix dataset via Kaggle API:

```python
!mkdir -p ~/.kaggle
!cp /content/kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json
!kaggle datasets download -d netflix-inc/netflix-prize-data -p /content/netflix_data --unzip
```

---

## 🧠 Model Architecture

- Matrix Factorization using `SVD` from `surprise`
- RMSE and MAE evaluation via cross-validation
- Trained on a sample of 100K–200K rows for speed
- Cold-start prevention: recommends only for users in the training set

---

## 🎯 Features

- Parses massive Netflix Prize data efficiently
- Predicts movie ratings using user–movie interactions
- Personalized Top 10 movie recommendations
- Matches `MovieID` to actual titles
- Clean separation of data, model, and output

---

## 📈 Model Performance

| Metric | Value (on 200K sample) |
|--------|------------------------|
| RMSE   | ~1.019                 |
| MAE    | ~0.818                 |

---

## 🔍 Sample Output

```
User 1664010:
Liked Movies:
- Patch Adams (5⭐)
- The Truman Show (4⭐)
- The Matrix (5⭐)

Top Recommendations:
- The Sixth Sense (4.88⭐)
- Finding Nemo (4.85⭐)
- Batman Begins (4.84⭐)
...
```

---

## 📦 Libraries Used

- pandas, numpy
- surprise
- matplotlib, seaborn
- ipywidgets (optional)

---

## 🧩 Possible Extensions

- 🎨 Add genre-based hybrid filtering
- 🧠 Try neural collaborative filtering (NCF)
- 🌐 Deploy using Streamlit or Gradio
- 📦 Use TMDb API for real-time metadata and posters

---

## 🧑‍💻 Author

Built by **Adnan Al-Teez**  
Learning recommender systems through hands-on implementation.  
Designed to simulate the Netflix algorithm pipeline using real data.

---

## 🧠 Want to Try It?

> Open the notebook in [Google Colab](https://colab.research.google.com/), upload your Kaggle token, and start building your own recommender today.
