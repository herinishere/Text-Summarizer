# Text Summarization using T5 + TextRank

## Overview
This project builds an abstractive patent summarization system by
combining extractive TextRank (SpaCy) with a fine-tuned T5 model.
The system is trained and evaluated on the BigPatent dataset.

## Key Features
- TextRank-based extractive preprocessing
- Fine-tuned T5 for abstractive summarization
- Evaluation using BERTScore
- Clean training and inference pipeline

## Model
- Base model: T5-small
- Framework: PyTorch + HuggingFace Transformers

## Dataset
- BigPatent (Northeastern University)
- 5k training samples, 1k validation samples

