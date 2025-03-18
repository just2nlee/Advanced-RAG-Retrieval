# Advanced RAG Pipeline for Natural Language Processing Intro

This repository demonstrates how to build and evaluate an advanced Retrieval-Augmented Generation (RAG) pipeline with three retrieval methods on the PDF document `introduction-to-natural-language-processing.pdf`:

- **Auto Merging Retrieval** (using hierarchical chunking)
- **Standard RAG** (direct query engine)
- **Sentence Window Retrieval** (using fixed window sizes)

We use **llama_index** for document indexing and vector store creation and **Truera (TruLens)** for evaluating the retrieval performance. The evaluation metrics include Answer Relevance, Context Relevance, and Groundedness.

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Setup](#setup)
- [Results and Tuning](#results-and-tuning)

## Overview

This project implements three retrieval strategies for a RAG system over the PDF `introduction-to-natural-language-processing.pdf`:

1. **Auto Merging Retrieval**: Uses a `HierarchicalNodeParser` with small chunk sizes to merge nodes intelligently.
2. **Sentence Window Retrieval**: Uses a `SentenceWindowNodeParser` to create fixed windows of sentences.
3. **Standard RAG (Direct Query Engine)**: Uses the base query engine provided by llama_index.

Each index is stored in a vector database and later queried. We use TruLens (a component of Truera) to evaluate retrieval outputs based on:
- **Answer Relevance**
- **Context Relevance**
- **Groundedness**

## Requirements

- Python 3.8+
- [llama_index](https://github.com/jerryjliu/llama_index) (formerly GPT Index)
- [TruLens / Truera evaluation package](https://github.com/trulens/trulens_eval) for feedback evaluations
- [HuggingFace Transformers](https://github.com/huggingface/transformers) for embeddings
- A vector database backend (e.g., FAISS) if not using the default in-memory store
- Additional dependencies listed in `requirements.txt`

## Setup

1. **Clone the Repository**: git clone "Link to the repository"      cd advanced-rag-pipeline
2. **Install Dependencies**: pip install -r requirements.txt
3. **Configure API Keys**: Create a .env file in the root directory with your API keys (for OpenAI if used) --> OPENAI_API_KEY=your_openai_api_key

## Results and Tuning
- Experiment with similarity_top_k, rerank_top_n, and chunk_sizes to improve retrieval.
- Track context relevance, groundedness, and answer relevance metrics.