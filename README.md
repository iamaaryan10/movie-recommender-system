# 🎬 Movie Recommender System

A content-based movie recommender system that suggests similar movies based on user input. The system uses Natural Language Processing (NLP) and cosine similarity to recommend movies and displays posters using the TMDB API.

---

## 🚀 Live Demo
👉 [https://your-app-link.streamlit.app](https://movie-recommender-system-2d83jermov8rcn2tixvpun.streamlit.app/)

---

## 📌 Features
- Recommends top 5 similar movies
- Displays movie posters using TMDB API
- Interactive UI built with Streamlit
- Fast similarity computation using caching

---

## 🧠 Approach

### 1. Dataset
- TMDB 5000 Movies dataset
- TMDB 5000 Credits dataset

---

### 2. Data Preprocessing
- Merged movies and credits datasets
- Selected relevant features:
  - movie_id
  - title
  - overview
  - genres
  - keywords
  - cast (top 3)
  - director (from crew)
- Removed irrelevant columns:
  - budget, homepage, production countries, etc.
- Converted JSON-like columns into lists
- Removed spaces between words (e.g., "Sam Worthington" → "SamWorthington")

---

### 3. Feature Engineering
- Combined all important features into a single column: **tags**
- Created a new DataFrame with:
  - movie_id
  - title
  - tags

---

### 4. Text Processing
- Converted text to lowercase
- Applied **stemming** using NLTK
- Removed stopwords

---

### 5. Vectorization (Core Step)
- Used **Bag of Words (CountVectorizer)**
- Parameters:
  - `max_features = 5000`
  - `stop_words = 'english'`
- Converted tags into numerical vectors

---

### 6. Similarity Calculation
- Used **cosine similarity** to measure closeness between movies
- Used `enumerate()` to retain index while sorting
- Selected top 5 most similar movies

---

### 7. Deployment
- Built UI using Streamlit
- Deployed using Streamlit Cloud
- Integrated TMDB API for fetching movie posters

---

## 🛠 Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- NLTK
- Streamlit
- TMDB API

---

## 🔑 API Usage
This project uses TMDB API to fetch movie posters.

---

## 🎯 Future Improvements
- Add search autocomplete
- Hybrid recommendation system (content + collaborative)
- Display ratings, genres, and overview
- Improve UI (Netflix-style)

---

## 🙌 Author
Aaryan Shrivastava
