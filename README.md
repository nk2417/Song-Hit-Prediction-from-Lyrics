# Song-Hit-Prediction-from-Lyrics
Predicting whether a song is a "hit" using lyrics-based NLP models, framed as binary classification. Labels are derived from Billboard Hot 100 chart appearances and lyrics are sourced from the Genius API.

## Directory Structure

```bash
├── balanced_2000_df.csv
├── exploratory_analysis.ipynb
├── data_setup.ipynb
├── bow.ipynb
├── word2vec_knn_svm.ipynb
├── logreg_bow.ipynb
├── logreg_word2vec.ipynb
├── nb_dt.ipynb
├── nb_dt_precision_recall.ipynb
├── bert.ipynb
├── bert_precision_recall.ipynb
└── graphs.ipynb
```

## Where to Find Code

All notebooks are at the root of the repo. Each corresponds to a specific model or pipeline stage.


## Where to Find Data

`balanced_2000_df.csv` is at the root of the repo. It is a balanced 2000-sample dataset combining Spotify metadata and Billboard Hot 100 labels, with lyrics fetched via the Genius API.


## How to Run the Code

All notebooks are Google Colab notebooks. You will need:
- A Kaggle API token (username + key) to access the Spotify dataset
- A Genius API client access token for lyrics scraping

## Order to Run

1. `data_setup.ipynb` — fetch and merge datasets, attach lyrics
2. `exploratory_analysis.ipynb` — inspect class balance, lyric distributions
3. `bow.ipynb` — generate Bag-of-Words features (used by Naive Bayes, Decision Trees, Logistic Regression BoW)
4. `word2vec_knn_svm.ipynb` — generate Word2Vec embeddings and run KNN/SVM models
5. `logreg_bow.ipynb` / `logreg_word2vec.ipynb` — Logistic Regression on BoW and Word2Vec features respectively
6. `nb_dt.ipynb` / `nb_dt_precision_recall.ipynb` — Naive Bayes and Decision Tree models
7. `bert.ipynb` / `bert_precision_recall.ipynb` — BERT model
8. `graphs.ipynb` — run after model results are available

## Data Sources

- [Billboard Hot 100 — Kaggle](https://www.kaggle.com/datasets/dhruvildave/billboard-the-hot-100-songs)
- [Spotify Songs with Audio, Lyrics and Genres — Kaggle](https://www.kaggle.com/datasets/serkantysz/550k-spotify-songs-audio-lyrics-and-genres)

## Non-Standard Libraries & APIs

- [LyricsGenius](https://lyricsgenius.readthedocs.io/en/master/) — Python client for the Genius API, used to scrape song lyrics
- [Genius API](https://docs.genius.com/) — source of all lyrics data
- [opendatasets](https://github.com/JovianML/opendatasets) — used to download Kaggle datasets directly in Colab
- [Gensim](https://radimrehurek.com/gensim/models/word2vec.html) — used to train Word2Vec embeddings
- [Hugging Face Transformers](https://huggingface.co/docs/transformers/index) — used to load and fine-tune BERT

## Models

- [BERT (bert-base-uncased) — Hugging Face](https://huggingface.co/google-bert/bert-base-uncased)
- [Word2Vec — Gensim](https://radimrehurek.com/gensim/models/word2vec.html)
