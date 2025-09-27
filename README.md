NAME; Vishal Vusnagiri

Student Id; 7000763454

Course; Natural Language Processing


##  Project Overview

This repository contains two small NLP and ML exercises implemented in Python:

1. **Bigram Language Model**

   * Implements a statistical language model using Maximum Likelihood Estimation (MLE).
   * Trained on a small toy corpus (`I love NLP`, `I love deep learning`, `deep learning is fun`).
   * Computes unigram and bigram counts, estimates probabilities, and evaluates given test sentences.

2. **Evaluation Metrics from a Confusion Matrix**

   * Computes precision, recall (per-class), and macro/micro-averaged metrics from a 3-class confusion matrix.
   * Demonstrates how evaluation differs between macro-averaging (class-level fairness) and micro-averaging (overall system accuracy).

---

## 🚀 1. Bigram Language Model

### Training Corpus

```
<s> I love NLP </s>  
<s> I love deep learning </s>  
<s> deep learning is fun </s>
```

### Features

* Computes **unigram and bigram counts**.
* Estimates bigram probabilities using **MLE**:
  [
  P(w_i | w_{i-1}) = \frac{\text{Count}(w_{i-1}, w_i)}{\text{Count}(w_{i-1})}
  ]
* Implements a function to compute the probability of any sentence.
* Tests two sentences and prints which one the model prefers (based on probability).

### Example Sentences Tested

1. `<s> I love NLP </s>`
2. `<s> I love deep learning </s>`

### Usage

```bash
python bigram_model.py
```

Expected output: unigram counts, bigram counts, probabilities of test sentences, and which sentence is preferred.

---

## 📊 2. Evaluation Metrics from a Confusion Matrix

### Confusion Matrix (System Predictions vs Gold Labels)

| System \ Gold | Cat | Dog | Rabbit |
| ------------- | --- | --- | ------ |
| **Cat**       | 5   | 10  | 5      |
| **Dog**       | 15  | 20  | 10     |
| **Rabbit**    | 0   | 15  | 10     |

### Tasks Implemented

* Per-class **precision** and **recall**.
* **Macro-averaged precision & recall** (equal weight to each class).
* **Micro-averaged precision & recall** (aggregate over all predictions).

### Example Results

* Cat → Precision = 0.25, Recall = 0.25
* Dog → Precision = 0.444, Recall = 0.444
* Rabbit → Precision = 0.40, Recall = 0.40

Macro Precision/Recall = 0.365
Micro Precision/Recall = 0.389

### Usage

```bash
python eval_metrics.py
```

Expected output: per-class metrics, macro-averaged, and micro-averaged results.

---

## 📝 Interpretation

* **Bigram Model**: Prefers the sentence that aligns better with training data probabilities.
* **Evaluation Metrics**:

  * *Macro*: balances classes (good for imbalanced datasets).
  * *Micro*: favors overall performance (good for balanced evaluation).

---

## 📂 File Structure

```
project/
│── bigram_model.py        # Bigram language model implementation
│── eval_metrics.py        # Confusion matrix evaluation implementation
│── README.md              # Documentation (this file)
```

---

## ⚡ Requirements

* Python 3.x
* NumPy (for eval_metrics.py)

