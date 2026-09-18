# Language Models: Auto-Complete

## Overview

This assignment develops a prototype **auto-complete system** using statistical language modeling. Auto-complete systems predict likely words that could follow a user's partially written sentence and are widely used in search engines, messaging applications, email clients, and other text-based systems.

The project builds an **N-gram language model** that learns word-sequence patterns from a corpus of Twitter data. The model estimates the probability of a word given the preceding context and uses these probabilities to suggest the most likely next word.

The assignment also introduces **K-smoothing** to handle words and word sequences that may not have appeared in the training data and uses **perplexity** to evaluate the quality of the language model.

---

## Objectives

The main objectives of this assignment are to:

* Load and preprocess a text corpus.
* Split text into sentences and tokenize the data.
* Create training and testing datasets.
* Identify low-frequency words.
* Replace out-of-vocabulary words with `<unk>`.
* Generate N-gram counts.
* Estimate conditional word probabilities.
* Apply K-smoothing to reduce zero-probability problems.
* Calculate language-model perplexity.
* Build an auto-complete word suggestion system.
* Predict the most likely next word given a sequence of words.

---

## Dataset

The assignment uses a collection of **Twitter text data**.

The raw dataset consists of many tweets stored as a large text corpus, with individual tweets separated by newline characters.

| Data           | Purpose                              |
| -------------- | ------------------------------------ |
| Twitter corpus | Training and testing language models |
| Training split | Learn word and N-gram statistics     |
| Test split     | Evaluate language-model performance  |

The data is processed before modeling to produce tokenized sentences suitable for N-gram analysis.

---

## Methodology

### 1. Data Loading and Preprocessing

The first stage prepares the Twitter corpus for language modeling.

The preprocessing pipeline includes:

* Loading the raw text.
* Splitting the corpus into individual sentences.
* Tokenizing sentences into words.
* Creating training and testing splits.
* Counting word frequencies.
* Identifying low-frequency words.
* Replacing out-of-vocabulary words with `<unk>`.

The main preprocessing functions include:

```text
split_to_sentences()
tokenize_sentences()
get_tokenized_data()
count_words()
get_words_with_nplus_frequency()
replace_oov_words_by_unk()
preprocess_data()
```

This preprocessing helps create a consistent vocabulary and reduces the impact of rare words on the language model.

---

## 2. N-Gram Language Models

An **N-gram** is a sequence of \(N\) consecutive words.

Examples include:

* Unigram → one word
* Bigram → two words
* Trigram → three words
* Four-gram → four words

For example:

```text
"I love machine learning"
```

can produce bigrams such as:

```text
"I love"
"love machine"
"machine learning"
```

and trigrams such as:

```text
"I love machine"
"love machine learning"
```

N-grams allow the model to learn local word-order patterns from the corpus.

---

## 3. N-Gram Counting

The model calculates how frequently different N-grams occur in the training data.

The assignment implements:

```text
count_n_grams()
```

These counts form the basis for estimating the probability of a word occurring after a given context.

For example, a bigram model estimates:

$$
P(w_n \mid w_{n-1})
$$

while a trigram model estimates:

$$
P(w_n \mid w_{n-2}, w_{n-1})
$$

---

## 4. Probability Estimation

The conditional probability of a candidate word is estimated from N-gram frequencies.

The assignment implements:

```text
estimate_probability()
```

A simplified N-gram probability can be expressed as:

$$
P(w_n \mid w_{n-1}) =
\frac{C(w_{n-1},w_n)}
{C(w_{n-1})}
$$

where \(C\) represents the corresponding N-gram count.

---

## 5. K-Smoothing

A major problem with N-gram models is the possibility of **zero probability**.

If an N-gram does not occur in the training corpus, its unsmoothed probability would be zero. This can cause problems when evaluating sentences or predicting future words.

The assignment therefore uses **K-smoothing**:

$$
P(w_n \mid context) =
\frac{C(context,w_n)+k}
{C(context)+kV}
$$

where:

* \(k\) is the smoothing parameter.
* \(V\) is the vocabulary size.
* \(C(context,w_n)\) is the N-gram count.
* \(C(context)\) is the context count.

Smoothing allows the model to assign a small non-zero probability to previously unseen N-grams.

---

## 6. Perplexity

**Perplexity** is used to evaluate the language model.

The assignment implements:

```text
calculate_perplexity()
```

Perplexity measures how well a language model predicts a sequence of words.

A lower perplexity generally indicates that the model assigns higher probability to the observed test sequence.

Conceptually, perplexity can be represented as:

$$
PP(W)=
\left(
\prod_{i=1}^{N}
P(w_i \mid context_i)
\right)^{-\frac{1}{N}}
$$

In practice, logarithms are commonly used to make the computation numerically stable.

---

## 7. Building the Auto-Complete System

The final stage uses the trained N-gram language model to suggest the next word.

The assignment implements:

```text
suggest_a_word()
```

Given a partial sentence such as:

```text
"I eat scrambled"
```

the system evaluates possible next words and selects a candidate with a high estimated probability.

The overall prediction process is:

```text
Input Sentence
      ↓
Tokenization
      ↓
Extract Context
      ↓
Generate Candidate Words
      ↓
Calculate N-Gram Probabilities
      ↓
Rank Candidates
      ↓
Suggested Next Word
```

This demonstrates how a statistical language model can form the foundation of a simple auto-complete system.

---

## Workflow

```text
Twitter Corpus
      ↓
Sentence Splitting
      ↓
Tokenization
      ↓
Train / Test Split
      ↓
Word Frequency Analysis
      ↓
Replace Rare / OOV Words
      ↓
N-Gram Counting
      ↓
Probability Estimation
      ↓
K-Smoothing
      ↓
Perplexity Evaluation
      ↓
Next-Word Prediction
      ↓
Auto-Complete Suggestion
```

---

## Key Concepts

* Natural Language Processing
* Language Models
* N-Grams
* Unigrams
* Bigrams
* Trigrams
* N-Gram Frequency
* Conditional Probability
* K-Smoothing
* Unknown Words
* Out-of-Vocabulary Words
* Vocabulary Management
* Perplexity
* Next-Word Prediction
* Auto-Complete Systems
* Statistical Language Modeling
* Train/Test Data Splitting

---

## Technologies

* **Python**
* **Jupyter Notebook**
* **NumPy**
* **Pandas**
* **NLTK**
* **Mathematical Probability**
* **N-Gram Language Modeling**
* **Dynamic Probability Estimation**

---

## Learning Outcomes

After completing this assignment, the following skills are developed:

* Understanding how statistical language models work.
* Preparing text data for language modeling.
* Tokenizing and preprocessing natural language text.
* Building N-gram frequency tables.
* Estimating conditional word probabilities.
* Understanding and applying K-smoothing.
* Handling unknown and low-frequency words.
* Evaluating language models using perplexity.
* Using contextual word probabilities for next-word prediction.
* Building a basic auto-complete system from an N-gram model.

---

## Notebook

The complete implementation is contained in:

```text
Language_Models_Auto_Complete.ipynb
```

The notebook covers data preprocessing, N-gram construction, probability estimation, smoothing, perplexity calculation, and next-word prediction.

---

## Course Information

**Course:** Natural Language Processing with Probabilistic Models
**Specialization:** Natural Language Processing
**Course:** Course 2
**Assignment:** Assignment 3 — Language Models: Auto-Complete

---

## Purpose

This project demonstrates how **probabilistic language models** can learn patterns in natural language and use those patterns to predict what a user is likely to type next.

It provides a practical foundation for understanding traditional statistical NLP systems and shows how concepts such as **N-grams, conditional probability, smoothing, and perplexity** can be combined to build an auto-complete application.
