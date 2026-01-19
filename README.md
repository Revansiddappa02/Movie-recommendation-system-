
# Movie Recommender System

## 1️⃣ Project Title
**Movie-Match-Engine**  
*A content-based recommendation system utilizing NLP and Cosine Similarity.*

## 2️⃣ Short Description
This project implements a recommendation engine that suggests movies based on metadata similarity. By analyzing genres, keywords, cast, and directors from "The Movies Dataset," the system builds a "Metadata Soup" and uses natural language processing to calculate similarity scores. It features optimized data storage using Parquet for fast inference and is integrated with a Django backend.

## 3️⃣ Features / Functionality
- **Automated Dataset Retrieval**: Integrated Kaggle API for direct dataset downloading and extraction.
- **NLP Preprocessing**: Utilizes `SnowballStemmer` for word normalization and `CountVectorizer` for feature extraction.
- **Similarity Matrix**: Implements a Cosine Similarity matrix to find the top 14 most relevant movie recommendations.
- **High-Performance Storage**: Uses **Apache Parquet** (via PyArrow) to compress the model and database, reducing storage size and increasing read speeds.
- **Web-Ready Backend**: Includes a Django framework structure (`manage.py`) for serving recommendations via a REST API or web interface.

## 4️⃣ Tech Stack
- **Language:** ![Python](https://img.shields.io/badge/python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)
- **Data Analysis:** ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat-square&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=flat-square&logo=numpy&logoColor=white)
- **Machine Learning:** ![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=flat-square&logo=scikit-learn&logoColor=white)
- **NLP:** ![NLTK](https://img.shields.io/badge/NLTK-Green?style=flat-square)
- **Backend:** ![Django](https://img.shields.io/badge/django-%23092E20.svg?style=flat-square&logo=django&logoColor=white)
- **Data Source:** ![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=flat-square&logo=Kaggle&logoColor=white)

## 5️⃣ Project Structure
```text
├── manage.py                  # Django command-line utility
├── requirements.txt           # Project dependencies
├── movie_recommendation/      # Django project settings
├── data/                      # Raw CSV files (credits, keywords, movies)
├── movie_database.parquet     # Optimized processed dataset
├── model.parquet              # Cosine Similarity matrix (compressed)
└── training_notebook.ipynb    # Model training and engineering logic
```

## 6️⃣ Setup / Installation Instructions
1.  **Clone the Repository**
    ```bash
    git clone https://github.com/your-username/movie-recommender.git
    cd movie-recommender
    ```
2.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Kaggle API Setup**
    - Place your `kaggle.json` in `~/.kaggle/`
    - Run the setup cells in the notebook to download `rounakbanik/the-movies-dataset`.
4.  **Database Migration (Django)**
    ```bash
    python manage.py migrate
    ```

## 7️⃣ Usage
1.  **Model Training**
    Execute the training script to generate `movie_database.parquet` and `model.parquet`.
2.  **Inference Script**
    ```python
    # In a Python environment:
    from movie_engine import get_recommendations
    results = get_recommendations("Toy Story", similarity_table)
    print(results)
    ```
3.  **Run Django Server**
    ```bash
    python manage.py runserver
    ```

## 8️⃣ Future Improvements
- **Hybrid Filtering**: Combine content-based results with Collaborative Filtering (user ratings).
- **Deep Learning**: Use Word2Vec or BERT embeddings for more semantic "Metadata Soups."
- **Real-time Scaling**: Migrate Parquet storage to a Vector Database (like Pinecone or Milvus) for production scaling.

## 9️⃣ Author / Contribution
**Developed by REVANSIDDAPPA**

### Contributions
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
