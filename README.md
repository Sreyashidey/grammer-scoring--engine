#  Grammar Scoring Engine – Optimization Summary

This project aims to predict grammar quality scores from spoken English audio samples. Two models were developed and optimized:

###  Model 1: Audio Feature-Based Regressor
- Extracted features using `librosa` (e.g., MFCCs, spectral features, ZCR).
- Trained a **stacked ensemble regressor** combining SVR, GradientBoosting, and RidgeCV.
- Achieved reasonable results but lacked direct linguistic insight.

###  Model 2: Transcription + NLP Feature Regressor
- Converted audio to text via automatic speech recognition (ASR).
- Extracted linguistic features (e.g., word count, POS tags, avg. word length) using `nltk`.
- Trained a **RandomForestRegressor**, which improved performance significantly.

###  Final Performance (Model 2)
- **RMSE**: 0.5030
- **MAE**: 0.4144
- **R² Score**: 0.7695

By shifting from raw audio features to transcription-based linguistic features, the model better captured grammatical correctness and aligned more closely with human scoring.
