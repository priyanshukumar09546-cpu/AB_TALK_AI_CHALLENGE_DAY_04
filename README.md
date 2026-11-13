# Klymb AI Challenge — Day 4: Vectors & Sentence Embeddings

## Overview
This repository contains my implementation for **Day 4 (Vectors - Teaching Meaning to Machines)** of the **Klymb AI Challenge**. The objective is to understand how text is converted into dense vector embeddings so that machines can capture semantic meaning rather than just matching exact keywords.

## Tech Stack & Model
- **Language:** Python 3 (Google Colab)
- **Library:** `sentence-transformers`
- **Model:** `all-MiniLM-L6-v2`

## What I Did
1. Installed and imported `sentence-transformers` in Google Colab.
2. Created a set of 5 sentences mixing semantically similar and completely unrelated contexts:
   - *"A dog is playing in the park."*
   - *"A puppy is running outside on the grass."*
   - *"I love coding in Python and C++."*
   - *"Machine learning models understand vectors."*
   - *"The weather is very sunny today."*
3. Encoded the sentences into dense vector embeddings using `SentenceTransformer('all-MiniLM-L6-v2')`.
4. Computed **Cosine Similarity** between sentence pairs using `util.cos_sim()`.

## Results & Observations
| Sentence Pair | Context | Cosine Similarity Score |
| :--- | :--- | :---: |
| *"A dog is playing in the park."* vs. *"A puppy is running outside on the grass."* | Semantically Similar | **0.3968** |
| *"A dog is playing in the park."* vs. *"I love coding in Python and C++."* | Unrelated | **0.0964** |

### Key Takeaway
Even though *"dog/park"* and *"puppy/grass"* do not share exact keywords, the embedding model recognizes their conceptual similarity and assigns a significantly higher similarity score (`0.3968`) compared to unrelated topics (`0.0964`). This semantic understanding forms the backbone of modern RAG pipelines, recommendation engines, and semantic search.
