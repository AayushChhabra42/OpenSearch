Here's a sample `README.md` for your project that integrates semantic search with OpenSearch using Hugging Face embeddings:

---

# Movie Semantic Search with OpenSearch

This project implements a semantic search engine for movie data using OpenSearch and Hugging Face models to generate embeddings for movie descriptions. The project indexes movie records with their embeddings and allows searching for movies based on a semantic query.

## Features

- **Movie Data Indexing**: Indexes movie data into OpenSearch, including metadata such as title, director, genre, IMDB rating, and overview.
- **Semantic Search**: Uses a Hugging Face model to generate embeddings for movie overviews and performs k-NN search to retrieve semantically similar movies.
- **Scalable**: The system supports adding new movies and querying efficiently.

## Technologies

- **OpenSearch**: For indexing and searching movie records.
- **Hugging Face Transformers**: To generate embeddings from movie overviews.
- **Python**: For scripting the indexing and search logic.
- **OpenSearch-py**: The official Python client for OpenSearch.

## Setup

- Clone the repo
- Create a dot env file setting OPENSEARCH_INITIAL_ADMIN_PASSWORD to your initial password.
- Run docker-compose up -d to orchastrate the opensearch setup
- Explore exp.ipynb to check the usage and implementation of Search

## How It Works

1. **Data Indexing**: Movie records (including metadata and embeddings) are indexed into OpenSearch using the `bulk` API.
2. **Embedding Generation**: Movie descriptions (overviews) are converted into embeddings using a pre-trained Hugging Face model, such as `sentence-transformers/all-MiniLM-L6-v2`.
3. **Semantic Search**: When a search query is provided, the query is converted into an embedding, and OpenSearch is queried using the `knn_vector` field to find similar movies based on semantic meaning.

## Example Queries

- **Search for a similar movie**:
  - Query: `"Leonardo Dicaprio"`
  - Expected Results: Titanic,Shutter Island,Django Unchained

