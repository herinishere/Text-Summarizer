# Text Summarization using T5 + TextRank (MMR)

## 📌 Overview
This project implements a **hybrid text summarization system** that combines  
**extractive summarization (TextRank + MMR)** with **abstractive summarization (T5)**.

The system is designed for **long technical documents**, especially patents,  
and is trained and evaluated using the **BigPatent dataset**.

---

## ✨ Key Features
- Extractive summarization using **TextRank (spaCy)**
- Redundancy reduction using **Maximal Marginal Relevance (MMR)**
- Sentence embeddings using **Sentence-BERT (MiniLM)**
- Abstractive summarization using **T5-small**
- Evaluation using **BERTScore**
- End-to-end training and inference pipeline

---

## 🧠 Model Details
- **Base Model:** T5-small  
- **Architecture:** Encoder–Decoder Transformer  
- **Framework:** PyTorch + HuggingFace Transformers  
- **Decoding Strategy:** Beam Search  
- **Repetition Control:** No-repeat n-gram constraint  

---

## 📂 Dataset
- **Name:** BigPatent  
- **Source:** Northeastern University  
- **Task:** Abstractive patent summarization  

### Dataset Fields
- `description` – Long patent text  
- `abstract` – Human-written summary  

### Dataset Split Used
- Training samples: 2000  
- Validation samples: 100  

---

## ⚙️ Pipeline Architecture

### 1️⃣ Extractive Summarization
- Sentence segmentation using **spaCy**
- Sentence ranking using **TextRank**
- Sentence embeddings via **Sentence-BERT**
- Sentence selection using **MMR** to balance relevance and diversity

### 2️⃣ Abstractive Summarization
- Extracted sentences are concatenated
- Input format:
- - T5 generates fluent abstractive summaries

---

## 🏋️ Training Configuration
- **Optimizer:** AdamW  
- **Loss Function:** Cross-Entropy  
- **Learning Rate:** 2e-4  
- **Batch Size:** 2  
- **Epochs:** 3  
- **Mixed Precision (FP16):** Disabled  
- **Checkpoint Saving:** Per epoch  

---

## 📊 Evaluation
- **Metric Used:** BERTScore  
- Measures semantic similarity between generated and reference summaries  

### Reported Metrics
- Precision  
- Recall  
- F1 Score  

---

## 🚀 Performance
- **Model load time:** ~3 seconds  
- **Inference time:** < 1 second per document (GPU)  
- **Training time:** ~30–40 minutes for 2000 samples (GPU)

---

## 📦 Dependencies
```bash
pip install torch transformers datasets spacy pytextrank \
sentence-transformers bert-score

