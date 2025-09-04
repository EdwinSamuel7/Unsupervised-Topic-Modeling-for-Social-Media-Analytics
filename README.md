## Overview

This project implements a topic modeling system that combines relevance feedback with GSDMM (Gibbs Sampling Dirichlet Multinomial Mixture) algorithm to analyze and cluster BBC-related tweets. The system uses a multi-stage approach to identify relevant documents, extract directional words, and perform topic clustering on social media content.

## Features

- **GSDMM Topic Modeling**: Implements the Movie Group Process algorithm for short text clustering
- **Relevance Feedback System**: Combines keyword-based retrieval with Bayesian filtering
- **Text Preprocessing Pipeline**: Comprehensive text cleaning and normalization
- **Directional Word Identification**: Uses multinomial sampling to identify topic-specific vocabulary
- **Probabilistic Document Scoring**: Implements Bayesian factor analysis for document relevance assessment
- **Multi-stage Filtering**: Sequential filtering workflow for improved clustering accuracy

## Technical Workflow

### 1. Initial Document Retrieval
- Extracts BBC-related tweets using keyword matching
- Creates initial pseudo-relevant document set

### 2. Vocabulary Building and Term Analysis
- Constructs corpus vocabulary from all tweets
- Calculates term frequency statistics across relevant and irrelevant document sets
- Computes directional word weights using frequency ratios

### 3. Directional Word Selection
- Applies multinomial sampling based on calculated term weights
- Identifies 15 key directional words that characterize relevant content

### 4. Document Collection Expansion
- Uses directional words to find additional relevant documents
- Applies Bayesian factor scoring to filter candidates

### 5. Topic Clustering
- Implements GSDMM algorithm with K=15 topics
- Processes final document collection through topic modeling
- Generates topic-word distributions and document assignments

## GSDMM Parameters

- **K**: 15 topics
- **Alpha**: 0.1 (document-topic concentration)
- **Beta**: 0.1 (topic-word concentration)
- **Iterations**: 100
- **Threshold (tau)**: 8 for Bayesian filtering

## Clustering Algorithm

Uses GSDMM (Movie Group Process) for short text clustering, which is particularly suitable for social media content with limited context. The algorithm handles variable document lengths effectively and is designed specifically for clustering short texts like tweets where traditional topic modeling approaches may struggle.

The clustering process involves:
- Random initialization of documents to topics
- Iterative reassignment based on topic popularity and word similarity
- Convergence when document transfers stabilize
- Final topic-word distribution generation

## Future Improvements

- Implement automatic topic number selection using coherence scores
- Add comprehensive evaluation metrics (silhouette analysis, perplexity)
- Integrate modern embedding techniques (BERT, Word2Vec)
- Enhance preprocessing with lemmatization and Named Entity Recognition
- Develop parameter optimization for different datasets
- Add visualization components for topic distributions
- Implement cross-validation for model validation
