# Semantic Search with FastText and Annoy

This repository demonstrates a semantic search application that uses FastText for word vector embeddings and Annoy for fast nearest-neighbor search. The goal is to perform efficient text-based searches on a large dataset, enabling users to retrieve similar words or phrases based on semantic meaning.

## Overview

In this implementation, we use FastText, a library by Facebook for learning word representations, and Annoy, a library for approximate nearest neighbor search. Together, these tools allow us to build a fast and scalable semantic search system.

## How It Works

1. **Dataset Loading**: 
   - The dataset is loaded from a CSV file containing text data (e.g., `center_state` column).
   - Missing data is removed to ensure clean input for the model.

2. **Text Tokenization**: 
   - The text data is tokenized into individual words using the NLTK tokenizer.

3. **FastText Model Training**: 
   - A FastText model is trained on the tokenized text. FastText creates word embeddings that capture semantic relationships between words, even for out-of-vocabulary words.

4. **Annoy Index Creation**:
   - Annoy is used to index the word vectors for fast retrieval. The index is built using the word vectors and saved for later use.

5. **Semantic Search**:
   - The semantic search function takes a query (a string of words), tokenizes it, converts the tokens into word vectors using the trained FastText model, and computes the average vector for the entire query.
   - Using this query vector, the function retrieves the top N nearest neighbors from the Annoy index, which are semantically similar words or phrases.

6. **Example Query**: 
   - Users can input a query such as "delhi state", and the system returns the most semantically similar words or phrases from the dataset.

## Installation

1. Clone this repository:

```bash
git clone https://github.com/abshek7/W2V-Annoy.git
