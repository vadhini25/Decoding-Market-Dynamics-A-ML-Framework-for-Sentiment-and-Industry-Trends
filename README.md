# Decoding Market Dynamics: A ML Framework for Sentiment and Industry Trends

This project analyzes the impact of financial news on stock market indices, focusing on three main stages: Sentiment Analysis, Industry Classification, and Impact Assessment. This architecture processes financial news articles, assigns sentiment scores and industry relevance, and correlates this information with historical stock index data to predict market trends.

## Architecture Components and Workflow
1. Data Ingestion Layer
    - Sentiment Analysis Dataset: Trained using the Financial News Sentiment Dataset.
    - Historical Index Data: Collected using the Angel One SmartAPI to fetch timestamped open, high, low, close, and volume data for   the      NIFTY index.


2. Sentiment Analysis Module:
    - Preprocessing: News articles are preprocessed using URL removal, stop word removal, removing non-word and non-whitespace characters, 
  stemming, Lemmatization, tokenization and vectorization.
    - Model Selection: Evaluated multiple models to determine the best sentiment analyzer:
      Lexicon-based Models: VADER, finVADER.
      Machine Learning Models: SVM (linear, RBF, polynomial, and sigmoid kernels), CatBoost.
      Deep Learning Model: finBERT
    - Result: finBERT achieved the highest accuracy of 89%, making it the chosen model for sentiment analysis.


3. Industry Classification Module:
    - Classification Categories: Articles are categorized into the following industries: auto, bank, financial services, FMCG, healthcare,IT, media, metal, pharmaceutical, realtor, consumer durables, and oil and gas.
    - Classification Approach: Lexicon-based classification was implemented due to the absence of a labelled training dataset.



4. Data Integration Layer
    Combines sentiment scores and industry classifications with historical NIFTY index data. This enriched dataset facilitates time-series    analysis and prediction.



5. Impact Assessment Module:
    - Model Selection: Long Short-Term Memory (LSTM) network is used to model the relationships between sentiment scores, industry              classifications, and historical index movements.
    - Prediction Output: The LSTM model generates impact assessments and predictions for different industries and overall market trends based   on the analyzed news and historical data.
