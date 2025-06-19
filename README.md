# 🔍 Sentiment Analysis using BERT and Transformers

This project leverages the power of the **BERT (Bidirectional Encoder Representations from Transformers)** model for performing sentiment analysis on text data. Built using the Hugging Face `transformers` library and deployed via `Gradio`, this application classifies input text as **positive**, **negative**, or **neutral** with high accuracy and interpretability.

---

## 📁 Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Model](#model)
- [Usage](#usage)
- [Web Interface (Gradio)](#web-interface-gradio)
- [Evaluation](#evaluation)
- [Limitations](#limitations)
- [Contributors](#contributors)
- [License](#license)

---

## 📖 Overview

This project implements a fine-tuned BERT model designed for real-time sentiment classification. The model is integrated into a simple user interface that enables non-technical users to interact with state-of-the-art NLP models without writing any code.

---

## 🧠 Architecture


##Raw Text → Tokenizer (BERT) → Transformer Encoder → Classifier Head → Sentiment Label

- Tokenization using `BertTokenizer`
- Encoder from `bert-base-uncased`
- Classifier: Fully Connected Layers on top of `[CLS]` token
- Output: Softmax layer with 3-class sentiment probabilities

---

## 🏗️ Model

- Base Model: `bert-base-uncased`
- Fine-tuned for: **Sentiment Classification**
- Optimizer: `AdamW`
- Learning Rate Scheduler: Linear warmup
- Epochs: 3–5
- Loss Function: CrossEntropyLoss
- Batch size: 16 (train), 32 (eval)

---





                                                                                                                                                                                    
                                                                                                                                                                                    
                                                                                                                                                                                  
## ⚠️ Limitations (Code-wise)


🚀This project, while effective for general sentiment analysis, has several technical and practical limitations. First, the BERT model used (bert-base-uncased) can only process inputs up to 512 tokens. Any text longer than this is automatically truncated during tokenization, which may lead to the loss of important context, especially in longer reviews or documents. Additionally, the model is trained exclusively on English text. As such, it lacks multilingual capabilities and performs poorly on non-English inputs.

🚀The model also struggles to detect sarcasm, irony, or nuanced expressions of sentiment. Since it relies purely on word-level patterns learned during training, phrases like “Oh great, just what I needed today” may be misclassified as positive due to the presence of words like “great.” Moreover, the classifier is designed to predict one of three fixed sentiment categories: Positive, Negative, or Neutral. This hardcoded configuration limits its flexibility when dealing with more detailed emotional states (e.g., sadness, anger, excitement) unless retrained with a different label schema.

🚀Finally, the model’s performance can be affected by class imbalance in the training data. In cases where certain sentiments are underrepresented, the classifier may become biased toward the dominant class. The predictions are made using a softmax function, which always chooses the most likely class—even when the model is uncertain—without providing confidence scores or thresholds for ambiguity.
 
 
**MIT License**

**Copyright (c) 2025 Teja Thota**


                                                                                                                                                                                    

