# Sentiment Analysis of CSR Racing 2 Reviews

**NOTE: THIS README FILE IS AI GENERATED.**

This project is a submission for a deep learning module by **Dicoding Indonesia**. This project performs sentiment analysis on user reviews of the CSR Racing 2 mobile game collected from Google Play Store. The workflow includes data scraping, text preprocessing, automatic sentiment labeling, model training, and sentiment prediction for new review texts.

## Project Structure

```
.
├── Scraping_Analisis_Sentimen_Leonardo_Sanjaya.ipynb
├── Model_Analisis_Sentimen_Leonardo_Sanjaya.ipynb
├── Inference_Analisis_Sentimen_Leonardo_Sanjaya.ipynb
├── ulasan_CSR2.csv
├── model_dnn.h5
├── tfidf.h5
└── README.md
```

## Dataset

The dataset consists of user reviews collected from the Google Play Store page of CSR Racing 2 using the `google-play-scraper` library.

Application ID:

```
com.naturalmotion.customstreetracer2
```

The collected reviews are stored in:

```
ulasan_CSR2.csv
```

## Workflow

### 1. Data Collection

Run:

```
Scraping_Analisis_Sentimen_Leonardo_Sanjaya.ipynb
```

This notebook:

- Scrapes user reviews from Google Play Store.
- Stores review data into CSV format.
- Creates the dataset used for training and analysis.

### 2. Data Preprocessing & Model Training

Run:

```
Model_Analisis_Sentimen_Leonardo_Sanjaya.ipynb
```

Main processes:

#### Data Cleaning

- Remove null values
- Remove duplicate reviews
- Remove irrelevant columns

#### Text Preprocessing

- Case folding
- Special character removal
- Slang word normalization
- Tokenization
- Stopword removal

#### Sentiment Labeling

Sentiment labels are generated automatically using the NLTK VADER lexicon-based sentiment analyzer.

Labels:

- Positive
- Neutral
- Negative

#### Visualization

The notebook generates:

- Sentiment distribution pie chart
- Word cloud for all reviews
- Positive review word cloud
- Negative review word cloud

#### Feature Extraction

- TF-IDF Vectorization

#### Model Training

Several model configurations are evaluated, including:

1. Logistic Regression + TF-IDF
2. Dense Neural Network (DNN) + TF-IDF
3. GRU + Word2Vec
4. LSTM + Word2Vec

## Inference

Run:

```
Inference_Analisis_Sentimen_Leonardo_Sanjaya.ipynb
```

This notebook:

- Loads the trained model.
- Applies the same preprocessing pipeline used during training.
- Converts text using the saved TF-IDF vectorizer.
- Predicts sentiment for new user input.

Example:

```python
kalimat_baru = input("Masukkan kalimat baru: ")
Prediksi_Sentimen(kalimat_baru)
```

Output:

```
Positif
```

or

```
Netral
```

or

```
Negatif
```

## Dependencies

Main libraries used:

- pandas
- numpy
- nltk
- scikit-learn
- tensorflow / keras
- gensim
- matplotlib
- wordcloud
- google-play-scraper
- joblib

Install dependencies:

```bash
pip install pandas numpy nltk scikit-learn tensorflow gensim matplotlib wordcloud google-play-scraper joblib
```

## Author

Leonardo Sanjaya

## Notes

- The sentiment labels used for training are generated automatically using VADER and are not manually annotated.
- The same preprocessing pipeline must be applied during both training and inference to ensure consistent results.
