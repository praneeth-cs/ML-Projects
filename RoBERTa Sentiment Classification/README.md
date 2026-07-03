# RoBERTa Sentiment Classification

A Natural Language Processing (NLP) project that fine-tunes the **RoBERTa-base** transformer model for multi-class sentiment classification using the **SST-5 (Stanford Sentiment Treebank)** dataset.

## Overview

This project demonstrates the complete workflow of training and evaluating a transformer-based sentiment analysis model using the Hugging Face Transformers ecosystem.

The model is fine-tuned to classify text into five sentiment categories:

- Very Negative
- Negative
- Neutral
- Positive
- Very Positive

## Features

- Fine-tuning RoBERTa-base for sentiment classification
- Dataset preprocessing and tokenization
- Model training using Hugging Face Trainer API
- Interactive sentiment prediction
- Masked token prediction (word suggestions)
- Performance evaluation using:
  - Accuracy
  - Precision
  - Recall
  - F1 Score
- Confusion Matrix visualization

## Dataset

- SST-5 (Stanford Sentiment Treebank)
- Loaded directly using the Hugging Face `datasets` library.

## Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- Hugging Face Datasets
- Scikit-learn
- NumPy
- Matplotlib
- Seaborn
- Pandas

## Repository Contents

```text
├── roberta_sentiment_classification.ipynb
├── requirements.txt
└── README.md
```

## Results

The notebook trains a RoBERTa-base model on the SST-5 dataset and evaluates its performance using multiple classification metrics and a confusion matrix.
