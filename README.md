# 🐦 Tweet Sentiment Analyzer using Twitter API & NLP

This project collects real-time tweets about **Tesla** using the Twitter API, processes them with **NLP models**, and classifies sentiment as **Positive, Negative, or Neutral**. It uses both **DistilBERT** and **TextBlob** for robust sentiment detection, and visualizes sentiment trends over time.

---

## 📌 Problem Statement

Social media platforms like Twitter are rich sources of public opinion data. Businesses can leverage sentiment analysis to monitor brand reputation, detect emerging issues, and understand customer perceptions.

This project aims to:
- **Collect** real-time tweets related to Tesla.
- **Analyze** sentiment using both deep learning (DistilBERT) and lexicon-based (TextBlob) methods.
- **Visualize** trends and detect spikes in negative sentiment that may require immediate attention.

---

## 📊 Data Source

We use the **Twitter API** to fetch recent tweets matching the query `Tesla -is:retweet lang:en`.

Key details:
- **Library**: Tweepy (API v2 Client)
- **Metadata collected**: creation date, author ID, tweet text
- **Preprocessing**:
  - Remove URLs, mentions, hashtags
  - Convert to lowercase
  - Strip extra spaces
- **Date extraction** for time-series grouping

---

## 🧠 Models Used

Two sentiment analysis approaches are combined:

### 🔷 DistilBERT (Transformer Model)
- Context-aware deep learning model from HuggingFace Transformers
- Fine-tuned on sentiment classification tasks
- Handles complex sentence structures better than simple lexicon methods

### 🔷 TextBlob (Lexicon-Based)
- Uses polarity scores to assign sentiment
- Fast and interpretable
- Provides quick secondary validation for DistilBERT results

---

## ⚙️ Workflow

1. **Authenticate** with the Twitter API using Tweepy.
2. **Fetch tweets** in batches with filtering conditions.
3. **Preprocess text** to clean and normalize.
4. **Run sentiment classification** with DistilBERT and TextBlob.
5. **Aggregate results** by date and sentiment label.
6. **Visualize** sentiment trends over time with Matplotlib & Seaborn.
7. **Export results** to CSV for further analysis.

---

## 📈 Evaluation & Visualization

- Sentiment counts plotted over time to detect trends
- Ability to identify sudden spikes in negative sentiment
- Data stored in `tweet_sentiments.csv` for reproducibility

**Example Output:**
```text
Text: "Tesla's new update is amazing!"
DistilBERT → Label: POSITIVE | Score: 0.98
TextBlob → Sentiment: Positive
```

**Visualization Example:**
Line chart showing Positive, Neutral, and Negative sentiment counts per day.

---

## 📁 Project Structure
```
Tweet-Sentiment-Analyzer/
├── TweetAnalyzer.ipynb
├── tweet_sentiments.csv
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 📦 Requirements
- Python 3.x
- Tweepy
- Transformers
- TextBlob
- Pandas
- Matplotlib
- Seaborn

Install dependencies:
```bash
pip install -r requirements.txt
```

---

## 🚀 How to Run
1. Create a Twitter Developer account and generate API credentials.
2. Add your credentials to the notebook/script.
3. Run the notebook to:
   - Fetch tweets
   - Process and analyze sentiment
   - Visualize results
4. View `tweet_sentiments.csv` for saved results.
