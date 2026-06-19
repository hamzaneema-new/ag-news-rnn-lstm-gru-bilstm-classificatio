# 📰 AG News Text Classification using RNN, LSTM, GRU, and Bi-LSTM

## 📌 Project Overview

This project focuses on multi-class text classification using the AG News dataset. The objective is to classify news articles into one of four categories:

* 🌍 World
* ⚽ Sports
* 💼 Business
* 🔬 Sci/Tech

The project compares the performance of four recurrent neural network architectures:

* Simple RNN
* LSTM (Long Short-Term Memory)
* GRU (Gated Recurrent Unit)
* Bidirectional LSTM (Bi-LSTM)

Additionally, Gradient Clipping was applied to study its impact on training stability and model convergence.

---

## 🎯 Objectives

* Understand sequence modeling in NLP.
* Perform text preprocessing and tokenization.
* Convert text into padded numerical sequences.
* Build and train RNN-based architectures.
* Compare model performance using evaluation metrics.
* Analyze the effect of Gradient Clipping.
* Identify the best architecture for news classification.

---

## 📂 Dataset

Dataset: **AG News Topic Classification Dataset**

The dataset contains news articles categorized into four classes:

| Label | Category |
| ----- | -------- |
| 0     | World    |
| 1     | Sports   |
| 2     | Business |
| 3     | Sci/Tech |

Dataset loaded using:

```python
from datasets import load_dataset

dataset = load_dataset("ag_news")
```

---

## 🔧 Text Preprocessing

The following preprocessing steps were performed:

* Extracted text and labels
* Tokenization using Keras Tokenizer
* Vocabulary size limited to 20,000 words
* Converted text into numerical sequences
* Applied sequence padding
* Maximum sequence length set to 100
* Prepared labels for multi-class classification

### Why Tokenization?

Tokenization converts text into numerical representations that can be processed by neural networks.

### Why Padding?

Padding ensures all sequences have the same length, enabling efficient batch processing and consistent model input dimensions.

---

## 🧠 Models Implemented

### 1️⃣ Simple RNN

Architecture:

Embedding → SimpleRNN → Dense → Softmax

---

### 2️⃣ LSTM

Architecture:

Embedding → LSTM → Dense → Softmax

---

### 3️⃣ GRU

Architecture:

Embedding → GRU → Dense → Softmax

---

### 4️⃣ Bidirectional LSTM

Architecture:

Embedding → Bidirectional LSTM → Dense → Softmax

---

### 5️⃣ Gradient Clipping

Implemented Gradient Clipping using:

```python
Adam(
    learning_rate=0.001,
    clipnorm=1.0
)
```

to improve training stability and reduce exploding gradients.

---

## 📊 Model Performance Comparison

| Model      | Training Accuracy | Validation Accuracy | Test Accuracy |
| ---------- | ----------------- | ------------------- | ------------- |
| Simple RNN | 80.99%            | 73.94%              | 76.41%        |
| LSTM       | 95.52%            | 89.96%              | 🥇 91.43%     |
| GRU        | 96.34%            | 90.47%              | 🥈 90.83%     |
| Bi-LSTM    | 97.19%            | 90.67%              | 🥉 90.64%     |

---

## 🏆 Best Model

### LSTM

Test Accuracy: **91.43%**

Reasons:

* Highest test accuracy
* Strong generalization capability
* Effective handling of long-term dependencies
* Stable training behavior

---

## 🔍 Key Findings

### Simple RNN

* Fastest training
* Struggled with long-term dependencies
* Lowest classification accuracy

### LSTM

* Best overall performer
* Excellent generalization
* Highest test accuracy

### GRU

* Comparable performance to LSTM
* Fewer parameters
* More computationally efficient

### Bi-LSTM

* Utilized forward and backward context
* Did not outperform LSTM
* Showed mild overfitting

### Gradient Clipping

* Improved training stability
* Reduced loss fluctuations
* Enhanced validation performance

---

## 📈 Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Pandas
* Matplotlib
* Hugging Face Datasets

---

## 🚀 Results Summary

This project demonstrates the effectiveness of advanced recurrent neural networks for NLP classification tasks. Among all evaluated architectures, LSTM achieved the best performance with a test accuracy of 91.43%, while GRU offered a strong balance between accuracy and computational efficiency.

---

## 👩‍💻 Author

**Neema Hamza**

Data Analytics | Machine Learning | Business Intelligence | AI Enthusiast

---

⭐ If you found this project useful, consider giving it a star!
