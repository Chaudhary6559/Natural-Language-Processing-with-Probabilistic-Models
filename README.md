# Natural Language Processing with Probabilistic Models

## Overview

This repository contains programming assignments completed as part of the **Natural Language Processing with Probabilistic Models** course, part of the Natural Language Processing Specialization.

The projects explore how probabilistic and neural approaches can be used to process, analyze, and understand natural language. They cover spelling correction, grammatical sequence labeling, statistical language modeling, next-word prediction, and word embeddings.

Through hands-on implementations in Python, the assignments build practical understanding of core NLP techniques, including Bayesian reasoning, Hidden Markov Models (HMMs), N-gram language models, the Viterbi algorithm, and the Continuous Bag of Words (CBOW) model.

---

## Repository Contents

This repository contains four programming assignments:

| # | Assignment                     | Main Topics                                           |
| - | ------------------------------ | ----------------------------------------------------- |
| 1 | Autocorrect                    | Word probabilities, edit distance, Bayesian reasoning |
| 2 | Parts-of-Speech Tagging        | HMMs, transition and emission matrices, Viterbi       |
| 3 | Language Models: Auto-Complete | N-grams, smoothing, perplexity, next-word prediction  |
| 4 | Word Embeddings                | CBOW, neural networks, backpropagation, word vectors  |

---

## Projects

### 1. Autocorrect

<text size="sm" color="secondary">Folder: `Autocorrect/`</text>

This project implements a probabilistic spelling correction system that generates and ranks candidate corrections for misspelled words.

The system uses word frequencies, edit operations, and probability estimates to identify likely corrections.

**Key concepts:**

* Word frequency and probability
* Candidate generation
* Insert, delete, replace, and switch operations
* One-edit and two-edit candidates
* Minimum edit distance
* Bayesian reasoning for spelling correction

**Notebook:** `Autocorrect/Autocorrect.ipynb`

---

### 2. Parts-of-Speech Tagging

<text size="sm" color="secondary">Folder: `Parts-of-Speech-Tagging/`</text>

This project develops a POS tagging system that assigns grammatical labels to words based on their context.

It introduces Hidden Markov Models and uses the Viterbi algorithm to identify the most probable sequence of POS tags for a sentence.

**Key concepts:**

* Parts-of-Speech tagging
* Tagged text corpora
* Word and tag frequency dictionaries
* Hidden Markov Models
* Transition matrix and emission matrix
* Unknown-word handling
* Viterbi algorithm
* Dynamic programming
* Model accuracy evaluation

**Notebook:** `Parts-of-Speech-Tagging/Parts_of_Speech_Tagging.ipynb`

---

### 3. Language Models: Auto-Complete

<text size="sm" color="secondary">Folder: `Language-Models-Auto-Complete/`</text>

This project builds a prototype auto-complete system using an N-gram language model trained on Twitter text data.

The model learns word-sequence patterns, estimates conditional probabilities, and suggests a likely next word given a partial sentence.

**Key concepts:**

* Text preprocessing and tokenization
* Training and testing data
* Vocabulary and out-of-vocabulary words
* Unigram, bigram, and higher-order N-grams
* Conditional probability estimation
* K-smoothing
* Perplexity
* Next-word prediction

**Notebook:** `Language-Models-Auto-Complete/Language_Models_Auto_Complete.ipynb`

---

### 4. Word Embeddings

<text size="sm" color="secondary">Folder: `Word-Embeddings/`</text>

This project implements the Continuous Bag of Words (CBOW) model to learn numerical word representations from context.

The model predicts a target word from its surrounding context words. It is trained from scratch using neural network operations and optimization techniques, followed by visualization of the learned word vectors.

**Key concepts:**

* Word embeddings
* Continuous Bag of Words (CBOW)
* Context windows and context-target pairs
* One-hot encoding
* Neural network initialization
* Softmax and ReLU
* Forward propagation
* Cost function
* Backpropagation
* Gradient descent
* Word vector visualization

**Notebook:** `Word-Embeddings/Word_Embeddings.ipynb`

---

## Learning Progression

The assignments introduce different approaches to language processing, moving from word-level probability calculations to sequence models and learned vector representations.

```text
Autocorrect
    ↓
Word probabilities and spelling correction
    ↓
Parts-of-Speech Tagging
    ↓
Hidden Markov Models and sequence prediction
    ↓
Language Models: Auto-Complete
    ↓
N-gram probabilities and next-word prediction
    ↓
Word Embeddings
    ↓
CBOW and neural word representations
```

Together, these projects demonstrate several foundational methods used in NLP, from statistical approaches to neural language modeling.

---

## Technologies and Tools

* **Python** — implementation and data processing
* **Jupyter Notebook** — interactive coding and experimentation
* **NumPy** — numerical computations and vector operations
* **Pandas** — data handling and analysis
* **NLTK** — text processing and tokenization
* **Mathematical probability** — statistical modeling
* **Neural network fundamentals** — forward propagation, backpropagation, and optimization
* **Data visualization** — exploring learned word vectors

---

## Skills Demonstrated

* Text preprocessing and tokenization
* Probabilistic modeling for NLP
* Word frequency and conditional probability calculations
* Bayesian spelling correction
* Sequence labeling with Hidden Markov Models
* Transition and emission probability estimation
* Dynamic programming with the Viterbi algorithm
* Statistical language modeling using N-grams
* Smoothing and perplexity-based evaluation
* Contextual next-word prediction
* Neural word embedding training
* Backpropagation and gradient descent
* Visualization of word representations

---

## Repository Structure

```text
Natural-Language-Processing-with-Probabilistic-Models/
│
├── Autocorrect/
│   ├── Autocorrect.ipynb
│   └── README.md
│
├── Parts-of-Speech-Tagging/
│   ├── Parts_of_Speech_Tagging.ipynb
│   └── README.md
│
├── Language-Models-Auto-Complete/
│   ├── Language_Models_Auto_Complete.ipynb
│   └── README.md
│
├── Word-Embeddings/
│   ├── Word_Embeddings.ipynb
│   └── README.md
│
└── README.md
```

Each assignment folder contains its corresponding Jupyter notebook and a README describing the project, methodology, key concepts, and learning outcomes.

---

## Course Information

**Course:** Natural Language Processing with Probabilistic Models
**Specialization:** Natural Language Processing
**Platform:** Coursera
**Course Number:** 2

---

## Purpose

This repository documents my practical learning in probabilistic and neural approaches to Natural Language Processing.

By completing these assignments, I explored how language data can be processed using word probabilities, statistical sequence models, N-gram language models, and neural word embeddings. These projects provide a foundation for further study in NLP, language modeling, and modern AI applications.
