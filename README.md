# Machine Translation: English to French AND Locality Sensitive Hashing (LSH): Document Search

This repository explores two related applications of word embeddings: cross-lingual word translation and Locality Sensitive Hashing (LSH) for document search.

## Overview

This project demonstrates how word embeddings can be used for machine translation and efficient document retrieval. It consists of two main components:

1.  **Word Embedding Translation:** This component focuses on translating words between English and French using learned transformation matrices.
2.  **LSH Document Search:** This component implements LSH to efficiently search for similar documents (tweets in this case) given a query tweet.

**Special Note:** for Machine Translation, this repo does not contain the code to generate word embeddings. They are already stored in the *data* folder.
## Project Structure

The repository is organized as follows:

* data/en.fr-train.txt
* data/en.fr-test.txt
* data/en_embeddings.p
* data/fr_embeddings.p
* machine-translation-and-lsh.ipynb: main project jupyter notebook
* utils.py: helper functions
* unittest.py: test cases to check the correctness of functions in main file

## Dependencies

The following Python libraries are required:

*   `numpy`
*   `pdb`
*   `pickle`
*   `string`
*   `time`
*   `nltk`
*   `os`

You can install them using pip:

```bash
pip install numpy pdb pickle string time nltk os
```

Or with conda:

```bash
conda install -c conda-forge numpy scipy scikit-learn gensim pandas annoy
```

## Word Embedding Translation
### Methodology

* Loading Embeddings: Pre-trained word embeddings for English and French are loaded.
* Learning Transformation Matrices: A transformation matrix is learned to map English word embeddings to the French embedding space. 
* Translation: To translate an English word, its embedding is multiplied by the transformation matrix.
* Nearest Neighbor Search: The nearest neighbor (using cosine similarity) of the transformed embedding in the French embedding space is found, representing the translated word.

## LSH Document Search
### Methodology

  * Document Embeddings: Embeddings for each document (tweet) are generated.
  * LSH Indexing: An LSH index is built using the document embeddings. This index allows for efficient approximate nearest neighbor search.
  * Querying: Given a query tweet, its embedding is calculated, and the LSH index is queried to retrieve similar tweets.

### Data

* Word Embeddings: The data directory should contain pre-trained word embeddings for English (en_embeddings.p) and French (fr_embeddings.p). You can download these from various sources (e.g., fastText, GloVe, Word2Vec). 
* Tweet Data: the sample tweets data is istalled through the nltk toolkit

## Further Work

  * Explore different word embedding models and training methods.
  * Experiment with different LSH implementations and parameters.
  * Evaluate the translation quality using more sophisticated metrics (e.g., BLEU score).
  * Apply the LSH method to larger datasets.

## Author

M. Ehtishaam Tanveer
