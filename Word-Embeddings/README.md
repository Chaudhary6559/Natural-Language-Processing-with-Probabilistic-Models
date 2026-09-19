# Word Embeddings with the Continuous Bag of Words (CBOW) Model

## Overview

This assignment explores **word embeddings** and their application to Natural Language Processing (NLP), particularly sentiment analysis.

Word embeddings represent words as numerical vectors that can capture useful syntactic and semantic relationships. Instead of relying only on positive and negative word counts, vector representations allow machine learning models to learn patterns from language.

The assignment implements the **Continuous Bag of Words (CBOW)** model, which learns word vectors by predicting a target word from its surrounding context words. The model is trained from scratch using forward propagation, a cost function, backpropagation, and gradient descent.

The learned word vectors are then visualized to explore the relationships between words in the embedding space.

---

## Objectives

The main objectives of this assignment are to:

* Understand the concept of word embeddings.
* Learn how the CBOW model represents words.
* Prepare context-target training examples.
* Create batches of training data.
* Initialize model parameters.
* Implement the softmax function.
* Perform forward propagation.
* Calculate the cost function.
* Implement backpropagation.
* Update model parameters using gradient descent.
* Train word vectors from scratch.
* Visualize learned word embeddings.

---

## Model: Continuous Bag of Words (CBOW)

The **CBOW model** predicts a target word using the surrounding context words.

For example, given the sentence:

> I am happy because I am learning

Using a context window of two words on each side, the model can use:

| Component | Words             |
| --------- | ----------------- |
| Context   | I, am, because, I |
| Target    | happy             |

The context words are represented using one-hot vectors, which are averaged to form the model input.

The model learns to predict the target word from this averaged context representation.

---

## Model Architecture

The assignment implements a neural network with the following general structure:

```text
Context Words
      ↓
One-Hot Encoding
      ↓
Average Context Vectors
      ↓
Embedding / Hidden Layer
      ↓
ReLU Activation
      ↓
Output Layer
      ↓
Softmax
      ↓
Predicted Target Word
```

The model uses trainable weight matrices and bias vectors to learn word representations and predict target words.

---

## Methodology

### 1. Model Initialization

The model parameters are initialized before training.

The assignment implements:

```text
initialize_model()
```

This step prepares the weight matrices and bias vectors used in the neural network.

### 2. Softmax Function

The softmax function converts output scores into a probability distribution over the vocabulary.

```text
softmax()
```

This allows the model to estimate the probability of each word being the target.

### 3. Forward Propagation

Forward propagation passes the averaged context representation through the neural network to produce output probabilities.

```text
forward_prop()
```

The model uses a hidden layer with ReLU activation followed by an output layer and softmax.

### 4. Cost Function

The cost function measures the difference between the model's predicted word distribution and the actual target word.

The training process aims to reduce this cost by adjusting the model parameters.

### 5. Backpropagation

Backpropagation calculates gradients of the cost with respect to the model parameters.

```text
back_prop()
```

These gradients indicate how the weights and biases should be adjusted to improve the model's predictions.

### 6. Gradient Descent

Gradient descent updates the model parameters using the calculated gradients.

```text
gradient_descent()
```

Repeated training iterations allow the model to learn useful word representations from context-target examples.

---

## Training Workflow

```text
Text Corpus
     ↓
Tokenization
     ↓
Context-Target Pairs
     ↓
Batch Generation
     ↓
Model Initialization
     ↓
Forward Propagation
     ↓
Cost Calculation
     ↓
Backpropagation
     ↓
Gradient Descent
     ↓
Learned Word Vectors
     ↓
Visualization
```

---

## Visualizing Word Embeddings

After training, the learned word vectors are visualized to explore how words are positioned in the embedding space.

Visualization helps illustrate how numerical representations can encode relationships between words based on their contexts.

---

## Key Concepts

* Natural Language Processing
* Word Embeddings
* Continuous Bag of Words (CBOW)
* Context Windows
* One-Hot Encoding
* Context-Target Pairs
* Neural Networks
* Embedding Matrices
* Softmax
* ReLU Activation
* Forward Propagation
* Cost Functions
* Backpropagation
* Gradient Descent
* Mini-Batch Training
* Word Vector Visualization
* Sentiment Analysis

---

## Technologies

* **Python**
* **Jupyter Notebook**
* **NumPy**
* **Pandas**
* **Mathematical Operations**
* **Neural Network Fundamentals**
* **Data Visualization**

---

## Learning Outcomes

After completing this assignment, the following skills are developed:

* Understanding how word embeddings represent language numerically.
* Explaining how CBOW predicts target words from context.
* Preparing context-target pairs for neural language modeling.
* Creating batches for model training.
* Implementing neural network components from scratch.
* Understanding forward and backward propagation.
* Applying gradient descent to optimize model parameters.
* Training word vectors using contextual information.
* Visualizing learned word representations.
* Connecting word embeddings to downstream NLP applications such as sentiment analysis.

---

## Notebook

The main implementation is contained in:

```text
Word_Embeddings.ipynb
```

The notebook covers CBOW model construction, training, optimization, and visualization of the learned word vectors.

---

## Course Information

**Course:** Natural Language Processing with Probabilistic Models
**Specialization:** Natural Language Processing
**Course:** Course 2
**Assignment:** Assignment 4 — Word Embeddings

---

## Purpose

This project provides a practical introduction to learning word representations using a neural language model. By implementing CBOW from scratch, it demonstrates how context, neural network training, and optimization can be combined to learn word vectors that support NLP tasks such as sentiment analysis.
