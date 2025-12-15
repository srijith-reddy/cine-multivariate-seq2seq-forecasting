# CineSeq
## Decay-Aware Multivariate Seq2Seq Forecasting for Movie Box-Office Revenue

CineSeq is a research-oriented forecasting framework for short-horizon movie box-office prediction.  
It combines structural exponential decay modeling with multivariate external signals using a
hybrid LSTM–GRU sequence-to-sequence architecture.

The core idea:
> Box-office revenue follows a dominant exponential decay pattern; forecasting improves when models
respect this structure while selectively incorporating auxiliary signals.

---

## What This Project Does

- Builds a leakage-safe weekly panel for 30 films (2010–2023)
- Validates exponential decay at both movie and dataset levels
- Trains a Seq2Seq LSTM–GRU model for 4-week-ahead forecasting
- Adds attention-based decoding to improve temporal relevance
- Extracts trailer-based emotion embeddings via transfer learning + knowledge distillation
- Interprets predictions using Integrated Gradients

---

## Modeling Philosophy

- Decay as structure, not noise
- External signals model deviations, not the baseline
- Interpretability alongside accuracy

---

## Key Components

**Data**
- Weekly box office revenue (The Numbers)
- YouTube trailers, engagement & search interest
- Google Trends
- TMDB metadata (budget, genre, studio, ratings)
- Trailer video & audio streams

**Trailer Representation Learning**
- SCRFD face detection
- FER+ emotion model (teacher)
- Knowledge-distilled student CNN
- Arousal, valence, volatility, emotional arc, audio–visual alignment

**Forecasting Models**
- LSTM encoder + GRU decoder (Seq2Seq)
- Attention-augmented decoder
- Log-scale targets, 4-week forecast horizon

**Evaluation & Interpretation**
- MAE, RMSE, WAPE
- Decay diagnostics (ADF, ACF/PACF)
- Integrated Gradients feature attribution

---

## Key Findings

- Exponential decay dominates revenue dynamics across all films
- Attention reduces test WAPE by ~41%
- Gains are strongest for movies with mid-run deviations from smooth decay
- Content, sentiment, genre, and timing drive late-stage corrections

---

## Author

Saisrijith Reddy Maramreddy  
Statistics & Applied Machine Learning


