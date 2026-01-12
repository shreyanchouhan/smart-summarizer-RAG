# SmartSummarizerRAG

## Overview
SmartSummarizerRAG is a context-aware document retrieval and summarization system. It utilizes state-of-the-art NLP techniques, including text embeddings, clustering, and retrieval-augmented generation (RAG), to enhance document search and summarization capabilities.

## Features
- **Text Embedding**: Leverages HuggingFace transformer models for high-quality text embeddings.
- **Clustering & Visualization**: Uses UMAP for dimensionality reduction and Gaussian Mixture Models (GMM) for clustering.
- **Context-Aware Retrieval**: Implements cosine similarity-based search for efficient document retrieval.
- **Summarization**: (Upcoming) Integration of summarization models for concise document insights.

## Installation
Ensure you have Python installed, then install dependencies:
```sh
pip install -r requirements.txt
```

## Usage
```python
from src.embedding import get_embedding
from src.clustering import cluster_embeddings
from src.retrieval import retrieve_similar

documents = ["Text 1", "Text 2", "Text 3"]
embeddings = [get_embedding(doc) for doc in documents]
labels, reduced_embeddings = cluster_embeddings(embeddings)
top_docs = retrieve_similar(embeddings[0], embeddings)
print("Top documents:", top_docs)
```

## Directory Structure
```
SmartSummarizerRAG/
│── notebooks/          # Jupyter Notebooks for experiments
│── src/                # Main source code
│    ├── embedding.py   # Code for text embedding using HuggingFace
│    ├── clustering.py  # UMAP and GMM clustering
│    ├── retrieval.py   # Context-aware retrieval implementation
│    ├── summarization.py # Summarization model integration
│    ├── visualization.py # BIC & Matplotlib visualizations
│── tests/              # Unit tests
│    ├── test_embedding.py   # Tests for embedding functions
│    ├── test_clustering.py  # Tests for clustering functions
│    ├── test_retrieval.py   # Tests for retrieval system
│    ├── test_summarization.py  # Tests for summarization module
│── requirements.txt    # Python dependencies
│── README.md           # Project documentation
│── setup.py            # If you plan to make it installable
│── .gitignore          # Ignore unnecessary files (e.g., models, datasets)
```

## Future Enhancements
- Integrate summarization models (BART, T5, etc.)
- Improve clustering accuracy using advanced ML techniques
- Deploy as a web-based search interface

## License
This project is licensed under the MIT License.
