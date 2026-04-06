# 🚀 NLP Task 5: Fine-Tuning BERT for Token Classification

##  Project Overview

This project is part of the **Data Science Internship – February 2026**.
The objective is to fine-tune a **BERT (bert-base-uncased)** model for **token classification tasks** using the Hugging Face Transformers library.

The implementation focuses on:

* Chunking (Phrase Detection)
* Sequence labeling using CoNLL-style dataset

---

##  Objectives

* Understand token classification using transformer models
* Perform chunking using BERT
* Handle tokenization and label alignment
* Train and evaluate a transformer model using Hugging Face Trainer
* Perform inference on custom sentences

---

## 🛠️ Technologies Used

* Python
* Hugging Face Transformers
* Datasets Library
* PyTorch
* SeqEval (Evaluation Metric)
* Google Colab / Jupyter Notebook

---

##  Dataset

The project uses the **CoNLL-2003 dataset** (via Hugging Face).

### Label Type:

* Chunk Tags (B-NP, I-NP, B-VP, etc.)

---

##  Workflow Pipeline

```
Raw Data → Tokenization → Label Alignment → Model Training → Evaluation → Inference
```

---

##  Implementation Details

### 1. Data Preprocessing

* Tokenization using `bert-base-uncased` tokenizer
* Words split into subwords using WordPiece
* Label alignment performed using:

  * First subword → actual label
  * Remaining subwords → `-100` (ignored during training)

---

### 2. Model Setup

* Model: `AutoModelForTokenClassification`
* Pretrained: `bert-base-uncased`
* Configured:

  * `num_labels`
  * `id2label`
  * `label2id`

---

### 3. Training

Training is performed using Hugging Face `Trainer`:

* Learning rate: `2e-5`
* Batch size: `8–16`
* Epochs: `2–3`
* Evaluation strategy: per epoch

---

### 4. Evaluation

Evaluation is done using **SeqEval**:

* Precision
* Recall
* F1 Score

This ensures sequence-level evaluation for token classification tasks.

---

### 5. Inference

The trained model is tested on custom input:

```
Input: John works at Google in California
Output: Token-wise predicted labels (Chunk Tags)
```

---

##  Results

The model successfully learns token-level patterns and predicts chunk labels for unseen sentences.
The performance is measured using F1-score and shows effective learning capability.

---

## POS Tagging vs Chunking

| Aspect     | POS Tagging      | Chunking               |
| ---------- | ---------------- | ---------------------- |
| Level      | Word-level       | Phrase-level           |
| Difficulty | Easy             | Moderate               |
| Output     | Noun, Verb       | NP, VP, PP phrases     |
| Use Case   | Grammar analysis | Information extraction |

---

## ⚠️ Challenges Faced

* Handling subword tokenization
* Aligning labels with tokenized inputs
* Managing ignored tokens (-100)
* Understanding sequence-based evaluation

---

## 💡 Key Learnings

* Transformers are powerful for sequence labeling
* Label alignment is critical in token classification
* SeqEval provides accurate sequence-level evaluation
* Chunking requires contextual understanding of phrases

---


##  Acknowledgment

This project was completed as part of the internship program by **Innomatics Research Labs**.

---

## Author

**Neer Wane**
