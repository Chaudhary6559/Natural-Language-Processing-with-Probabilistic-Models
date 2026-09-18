# Parts-of-Speech Tagging Using Hidden Markov Models

## Overview

This assignment implements a **Parts-of-Speech (POS) tagger** for natural language text. POS tagging assigns grammatical categories such as **noun, verb, adjective, adverb, pronoun,** and **preposition** to individual words in a sentence.

Because many English words can serve multiple grammatical roles depending on their context, POS tagging is fundamentally a sequence prediction problem. For example, the word *well* can function as a noun, verb, adjective, adverb, or interjection depending on how it is used.

The assignment develops a POS tagging system using a **Hidden Markov Model (HMM)** and the **Viterbi algorithm**. The model learns relationships between POS tags and words from tagged training data and then uses those relationships to predict the most likely sequence of tags for previously unseen text.

---

## Objectives

The main objectives of this assignment are to:

* Understand how Parts-of-Speech tagging works.
* Work with tagged natural language corpora.
* Create word and POS-tag dictionaries from training data.
* Calculate word and tag frequencies.
* Construct the **transition matrix** of an HMM.
* Construct the **emission matrix** of an HMM.
* Handle unknown words using preprocessing and special tokens.
* Implement the **Viterbi algorithm** for sequence prediction.
* Apply dynamic programming to POS tagging.
* Evaluate the accuracy of the POS tagging model.

---

## Dataset

The assignment uses **Wall Street Journal (WSJ)** tagged text data.

| Dataset        | Purpose                                                   |
| -------------- | --------------------------------------------------------- |
| WSJ-2_21.pos   | Training data                                             |
| WSJ-24.pos     | Testing data                                              |
| hmm_vocab.txt  | Training vocabulary                                       |
| test_words.txt | Preprocessed test words                                   |
| utils_pos.py   | Utility functions for preprocessing and word/tag handling |

The training corpus is used to obtain word, tag, transition, and emission statistics. The separate test corpus is used to evaluate the trained POS tagger.

### Unknown Words

A POS tagger may encounter words that were not present in its training vocabulary. The preprocessing stage therefore converts certain unknown words into informative unknown-word tokens.

For example, word characteristics such as suffixes can provide useful grammatical information. A word ending in `-ize` may provide evidence that it is a verb.

---

## Methodology

### 1. Data Preprocessing

The tagged corpus is processed to separate words and their corresponding POS tags.

The preprocessing stage also:

* Identifies sentence boundaries.
* Builds the vocabulary.
* Handles words outside the known vocabulary.
* Generates special unknown-word tokens.
* Prepares training and testing sequences.

---

### 2. Creating Dictionaries

The training data is used to create dictionaries containing information such as:

* Word frequency.
* POS-tag frequency.
* Word-tag frequency.

These counts provide the statistical information required to construct the HMM.

The assignment implements:

```text
create_dictionaries()
```

The resulting dictionaries provide the foundation for calculating transition and emission probabilities.

---

### 3. Baseline POS Prediction

A basic POS prediction approach is implemented before introducing the full HMM.

For each word, the model can use the most frequently observed POS tag associated with that word in the training corpus.

The assignment implements:

```text
predict_pos()
```

This provides a baseline that can later be compared with the HMM-based approach.

---

### 4. Hidden Markov Model

The POS tagger models the relationship between:

* **Hidden states:** POS tags
* **Observations:** Words

The model consists primarily of two probability matrices.

#### Transition Matrix — A

The transition matrix represents the probability of moving from one POS tag to another:

$$
A_{ij} = P(t_j \mid t_i)
$$

where:

* \(t_i\) is the previous POS tag.
* \(t_j\) is the current POS tag.

For example, the probability of a noun being followed by a verb can be learned from the training corpus.

The assignment implements:

```text
create_transition_matrix()
```

---

### 5. Emission Matrix — B

The emission matrix represents the probability of observing a particular word given a POS tag:

$$
B_{ij} = P(w_j \mid t_i)
$$

where:

* \(t_i\) is a POS tag.
* \(w_j\) is a word.

For example, certain words are much more likely to occur as nouns than as verbs.

The assignment implements:

```text
create_emission_matrix()
```

Smoothing is used when necessary to avoid zero probabilities for events that were not observed in the training data.

---

## 6. Viterbi Algorithm

The **Viterbi algorithm** is used to determine the most probable sequence of POS tags for a given sequence of words.

Rather than evaluating every possible tag sequence, Viterbi uses **dynamic programming** to efficiently keep track of the best sequence found at each position.

The implementation consists of three main stages:

### Initialization

The first word is initialized using:

* Initial tag probabilities.
* Emission probabilities.

```text
initialize()
```

### Forward Pass

The forward step calculates the highest probability of reaching each tag at each word position.

```text
viterbi_forward()
```

The recurrence combines:

* Previous best probability.
* Transition probability.
* Current word's emission probability.

### Backward Pass

After processing the complete sentence, the algorithm traces backward through the stored information to recover the optimal sequence of POS tags.

```text
viterbi_backward()
```

---

## 7. Model Evaluation

The completed POS tagger is applied to the test dataset.

The predicted POS tags are compared with the known ground-truth tags to calculate model accuracy.

```text
compute_accuracy()
```

The evaluation provides a quantitative measurement of how effectively the HMM-based POS tagger assigns grammatical categories to unseen text.

---

## Workflow

```text
WSJ Tagged Training Data
          ↓
      Preprocessing
          ↓
  Word / Tag Dictionaries
          ↓
   ┌──────┴──────┐
   ↓             ↓
Transition     Emission
Matrix A       Matrix B
   └──────┬──────┘
          ↓
    Viterbi Algorithm
          ↓
   Predicted POS Tags
          ↓
     Test Dataset
          ↓
      Accuracy
```

---

## Key Concepts

* Parts-of-Speech (POS) Tagging
* Natural Language Processing
* Hidden Markov Models
* Hidden States and Observations
* Transition Probabilities
* Emission Probabilities
* Word and Tag Frequencies
* Unknown Word Handling
* HMM Smoothing
* Viterbi Algorithm
* Dynamic Programming
* Sequence Prediction
* Baseline POS Tagging
* Model Evaluation
* Accuracy

---

## Technologies

* **Python**
* **Jupyter Notebook**
* **NumPy**
* **Pandas**
* **Collections / defaultdict**
* **Mathematical probability**
* **Hidden Markov Models**
* **Dynamic Programming**

---

## Learning Outcomes

After completing this assignment, the following concepts and practical skills are developed:

* Understanding the purpose and challenges of POS tagging.
* Working with linguistically annotated text.
* Building statistical dictionaries from a corpus.
* Calculating transition probabilities between POS tags.
* Calculating emission probabilities for words and tags.
* Understanding the structure of an HMM for NLP.
* Handling unknown words using linguistic features.
* Implementing the Viterbi algorithm.
* Applying dynamic programming to sequence prediction.
* Evaluating a POS tagging model on unseen data.

---

## Notebook

The main implementation is contained in:

```text
Parts_of_Speech_Tagging.ipynb
```

The notebook contains the complete workflow, including preprocessing, dictionary creation, HMM probability matrices, Viterbi decoding, and model evaluation.

---

## Course Information

**Course:** Natural Language Processing with Probabilistic Models
**Specialization:** Natural Language Processing
**Course:** Course 2
**Assignment:** Assignment 2 — Parts-of-Speech Tagging

---

## Purpose

This project demonstrates how probabilistic models can be applied to an important NLP sequence-labeling problem. By combining **Hidden Markov Models, transition and emission probabilities, and Viterbi decoding**, the assignment provides a practical foundation for understanding how statistical NLP systems infer linguistic structure from text.
