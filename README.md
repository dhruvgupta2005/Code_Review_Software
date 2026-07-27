# 🚀 AI-Powered Code Review Comment Classification using CodeBERT

![Python](https://img.shields.io/badge/Python-3.10-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-DeepLearning-red)
![Transformers](https://img.shields.io/badge/HuggingFace-CodeBERT-yellow)
![License](https://img.shields.io/badge/License-MIT-green)

---

# 📖 Project Overview

Modern software projects receive thousands of code review comments every day during Pull Request (PR) reviews. Manually understanding and categorizing these review comments is time-consuming and often inconsistent across reviewers.

This project presents an **AI-powered Code Review Comment Classification System** built using **Microsoft CodeBERT**, a transformer model pre-trained on both programming languages and natural language.

The model automatically predicts the category of a code review comment based on the associated code changes (Diff Hunks) and review comments, enabling developers to better organize, prioritize, and analyze software review feedback.

---

# 🎯 Problem Statement

During collaborative software development, developers review pull requests and provide comments such as:

- Fix this bug.
- This code is inefficient.
- Add unit tests.
- Improve documentation.
- Rename this variable.
- Handle this exception.

Manually categorizing these comments is difficult and does not scale well for large repositories.

This project addresses this challenge by building a deep learning model capable of automatically classifying review comments into predefined software engineering categories.

---

# 💡 Objectives

The primary objectives of this project are:

- Automate software code review comment classification.
- Reduce manual review effort.
- Assist developers in identifying review types quickly.
- Demonstrate the effectiveness of transformer-based models for software engineering tasks.
- Build an end-to-end deep learning pipeline using CodeBERT.

---

# 📊 Dataset

The model was trained using a GitHub Code Review dataset containing review comments collected from software pull requests.

Each training instance contains:

| Feature | Description |
|----------|-------------|
| Diff Hunk | Code changes introduced in the Pull Request |
| Review Comment | Natural language feedback provided by reviewers |
| Label | Ground truth review category |

The project performs **multi-class classification** across **16 software engineering review categories**.

---

# 🏗️ Model Architecture

```
                   Input Data
                        │
                        ▼
        Diff Hunk + Review Comment
                        │
                        ▼
              CodeBERT Tokenizer
                        │
                        ▼
      Microsoft CodeBERT Encoder
                        │
                        ▼
                Dropout Layer
                        │
                        ▼
          Fully Connected Linear Layer
                        │
                        ▼
              Softmax Classification
                        │
                        ▼
         One of 16 Review Categories
```

---

# 🧠 Why CodeBERT?

Unlike traditional NLP models, CodeBERT is trained on both:

- Source Code
- Natural Language

This enables it to learn semantic relationships between programming syntax and human-written review comments, making it highly suitable for software engineering tasks.

---

# ⚙️ Technologies Used

| Category | Tools |
|-----------|------|
| Programming Language | Python |
| Deep Learning | PyTorch |
| NLP | Hugging Face Transformers |
| Model | Microsoft CodeBERT |
| Data Processing | Pandas, NumPy |
| Evaluation | Scikit-learn |
| Notebook | Jupyter Notebook |

---

# 📂 Repository Structure

```
Code_Review_Software/
│
├── Code_review.ipynb          # Complete training and evaluation notebook
├── label_encoder.pkl          # Saved label encoder
├── README.md
```

---

# 🔄 Workflow

```
GitHub Review Dataset
          │
          ▼
Data Cleaning
          │
          ▼
Label Encoding
          │
          ▼
Tokenization using CodeBERT
          │
          ▼
Model Fine-tuning
          │
          ▼
Validation
          │
          ▼
Performance Evaluation
          │
          ▼
Prediction
```

---

# 📈 Training Performance

## Epoch-wise Results

| Epoch | Training Loss | Validation Loss | Accuracy | Weighted F1 | Macro F1 | Precision | Recall |
|------:|--------------:|----------------:|----------:|------------:|----------:|----------:|--------:|
| 1 | 2.3183 | 1.9590 | 48.38% | 49.77% | 33.15% | 56.52% | 48.38% |
| 2 | 1.8002 | 1.7735 | 49.03% | 50.00% | 39.12% | 60.79% | 49.03% |
| 3 | **1.5033** | **1.6972** | **55.92%** | **57.09%** | **43.93%** | **62.13%** | **55.92%** |

---

# 📊 Performance Summary

| Metric | Score |
|---------|-------|
| Accuracy | **55.92%** |
| Weighted F1 Score | **57.09%** |
| Macro F1 Score | **43.93%** |
| Precision | **62.13%** |
| Recall | **55.92%** |
| Final Validation Loss | **1.6972** |

---

# 📉 Training Analysis

During training:

- Training loss consistently decreased from **2.3183** to **1.5033**, indicating successful learning.
- Validation loss also decreased throughout training, suggesting improved generalization.
- Accuracy improved steadily over three epochs.
- Macro F1 increased significantly, indicating better performance across minority classes.
- Precision reached over **62%**, demonstrating the model's ability to produce reliable category predictions.

Overall, the model exhibited stable convergence without signs of severe overfitting during the observed training epochs.

---

# 🏷️ Evaluation Metrics

The model is evaluated using standard multi-class classification metrics:

- Accuracy
- Precision
- Recall
- Weighted F1 Score
- Macro F1 Score
- Cross Entropy Loss

These metrics provide a balanced evaluation, especially for datasets with class imbalance.

---

# ▶️ How to Run

## Clone the repository

```bash
git clone https://github.com/27Shambhavi/Code_Review_Software.git
cd Code_Review_Software
```

---

## Install dependencies

```bash
pip install -r requirements.txt
```

---

## Launch the notebook

```bash
jupyter notebook Code_review.ipynb
```

or

Use **Google Colab**.

---

# 🔮 Future Enhancements

Future improvements may include:

- Increasing training epochs with early stopping
- Hyperparameter optimization
- FastAPI deployment
- Streamlit web application
- GitHub Pull Request integration
- Comparison with GraphCodeBERT and CodeT5
- Support for code-only review classification

---

# 👨‍💻 Author

**Shambhavi Jha**


# 🤝 Acknowledgement

This project was developed during my internship at **Tesreco** as part of an industry-focused research initiative.

The objective of the project was to investigate the use of transformer-based language models for automating software code review comment classification. The repository showcases the implementation of the complete machine learning pipeline, including data preprocessing, model fine-tuning using Microsoft's CodeBERT, performance evaluation, and prediction workflow.

This repository is shared for educational and portfolio purposes to demonstrate the technical work completed during the internship.
