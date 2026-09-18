# Autocorrect Using Probabilistic Models

This project implements an **autocorrect and spelling-suggestion system** using probability, string manipulation, and minimum edit distance.

Completed as **Assignment 1** of the *Natural Language Processing with Probabilistic Models* course, the project explores how probabilistic language models and edit-distance techniques can be combined to identify likely corrections for misspelled words.

---

## 📌 Project Overview

Autocorrect systems attempt to determine what a user intended to type when a word contains a spelling error.

This project builds a simplified probabilistic autocorrect system that generates candidate corrections based on possible spelling edits and selects the most likely correction using word probabilities derived from a corpus.

The approach combines:

* Word frequency statistics
* Probability estimation
* String manipulation
* Edit distance
* Dynamic programming
* Bayesian reasoning

---

## 🎯 Objectives

* Process a text corpus and calculate word frequencies.
* Calculate word probabilities from corpus statistics.
* Generate candidate words from misspelled input.
* Implement common spelling edits.
* Generate candidates one and two edits away from a word.
* Rank candidate corrections using probability.
* Implement minimum edit distance.
* Apply dynamic programming to string comparison.
* Understand how probabilistic autocorrect systems work.

---

## 📂 Dataset

The assignment uses a text corpus to estimate word frequencies and probabilities.

The corpus provides the statistical information required to determine which candidate correction is more likely to be a valid word.

| Property             | Description               |
| -------------------- | ------------------------- |
| Data type            | Text corpus               |
| Main use             | Word frequency estimation |
| Model input          | Misspelled word           |
| Candidate generation | Edit operations           |
| Prediction           | Most probable correction  |

---

## ⚙️ Methodology

### 1. Data Preprocessing

Process the text corpus to obtain a vocabulary and calculate the frequency of individual words.

These frequencies are then converted into probabilities.

### 2. Word Probability

Estimate the probability of a word occurring in the corpus:

```text
P(word) = word_count / total_words
```

These probabilities help rank possible spelling corrections.

### 3. String Manipulation

Generate possible misspellings and corrections using four basic edit operations:

| Operation | Description                  |
| --------- | ---------------------------- |
| Delete    | Remove one character         |
| Switch    | Swap two adjacent characters |
| Replace   | Replace one character        |
| Insert    | Add one character            |

For example:

```text
"te"
  ↓
"the"
```

An autocorrect system can use these operations to generate possible intended words.

### 4. One-Edit Candidates

Generate all possible words that are **one edit away** from the input word.

These candidates provide the first set of possible corrections.

### 5. Two-Edit Candidates

If an appropriate correction is not found among one-edit candidates, generate candidates that are **two edits away**.

This expands the search space while still keeping the correction process manageable.

### 6. Probabilistic Correction

Candidate words are evaluated according to their probability in the corpus.

The system selects the candidate with the highest estimated probability among the valid candidates.

The underlying probabilistic reasoning is based on Bayes' rule:

```text
P(c | w) ∝ P(w | c) × P(c)
```

where:

* `w` = observed misspelled word
* `c` = intended correct word
* `P(c | w)` = probability that `c` is the intended correction
* `P(c)` = probability of the candidate word

### 7. Minimum Edit Distance

Implement **minimum edit distance** to determine the smallest number of operations required to transform one string into another.

The algorithm uses dynamic programming to efficiently calculate the optimal edit path.

---

## 🔄 Workflow

```text
Text Corpus
     ↓
Process Corpus
     ↓
Count Word Frequencies
     ↓
Calculate Word Probabilities
     ↓
Misspelled Word
     ↓
Generate One-Edit Candidates
     ↓
Generate Two-Edit Candidates
     ↓
Filter Valid Words
     ↓
Rank Candidates by Probability
     ↓
Predicted Correction
```

For minimum edit distance:

```text
Input Word + Candidate Word
          ↓
   Dynamic Programming
          ↓
 Minimum Edit Distance
          ↓
   Optimal Edit Path
```

---

## 🧠 Key Concepts

* Probabilistic Language Models
* Autocorrect
* Spell Checking
* Bayes' Rule
* Word Frequencies
* Word Probabilities
* Corpus Processing
* String Manipulation
* Edit Distance
* Minimum Edit Distance
* Dynamic Programming
* Candidate Generation
* Probability-Based Ranking
* NLP

---

## 🛠️ Technologies & Tools

* Python
* Jupyter Notebook
* NumPy
* Pandas
* Natural Language Processing techniques
* Python string manipulation
* Dynamic programming

---

## 📈 Learning Outcomes

By completing this assignment, I practiced:

* Working with text corpora and word-frequency statistics.
* Computing probabilities from observed word frequencies.
* Applying probabilistic reasoning to spelling correction.
* Implementing string-edit operations from scratch.
* Generating candidate corrections at different edit distances.
* Ranking candidate words using probability.
* Implementing minimum edit distance with dynamic programming.
* Understanding the fundamental principles behind autocorrect systems.

---

## 📁 Notebook

`Autocorrect.ipynb`

The notebook contains the complete implementation of corpus processing, word probabilities, spelling-edit operations, candidate generation, probabilistic correction, and minimum edit-distance calculation.

---

## 📚 Course Information

| Field           | Details                                                |
| --------------- | ------------------------------------------------------ |
| Course          | Natural Language Processing with Probabilistic Models  |
| Assignment      | Assignment 1 — Autocorrect                             |
| Topic           | Probabilistic Spelling Correction                      |
| Main techniques | Word Probabilities, Edit Distance, Dynamic Programming |
| Environment     | Jupyter Notebook                                       |

---

## 👨‍💻 Purpose

This project is part of my NLP and machine learning portfolio, demonstrating practical understanding of probabilistic language modeling, spelling correction, string algorithms, and dynamic programming.
