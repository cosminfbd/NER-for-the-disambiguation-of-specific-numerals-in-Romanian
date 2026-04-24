# Romanian Human-Quantifying Numeral Disambiguation Using BERT

## 📌 Project Overview
This project focuses on enhancing Romanian numeral transcription systems by disambiguating the words "un" and "o". Using a Transformer-based (BERT) model, the system successfully distinguishes between contexts where these words act as human-centric numerals (e.g., "un expert" — one expert) and cases where they function as indefinite articles (e.g., "un accident" — an accident).

## 🏗️ Model Architecture
- Base Model: `bert-base-romanian-cased-v1`
- Task: Named Entity Recognition
- Tagging Scheme: BIO

## 📊 Performance Metrics
| Metric        | Score         |
| ------------- |:-------------:|
| Accuracy      | right-aligned |
| F1-Score      | centered      |
| Training Epochs | 5           |
