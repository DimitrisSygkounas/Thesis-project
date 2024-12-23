Introduction
This repository demonstrates a Retrieve-Augmented Generation (RAG) pipeline applied to legal documents in five European languages: English, Italian, French, Spanish, and Greek. The system utilizes four different vector databases—ChromaDB, Qdrant, Weaviate, ElasticSearch, and Pinecone—to evaluate the performance of embedding-based retrieval and summarization.

The primary goal is to test the system's ability to process, retrieve, and summarize legal texts from European laws such as GDPR, AI Act, DMA, and DSA. Performance is assessed by comparing the retrieved summaries to predefined answers using cosine and semantic similarity.

Workflow Overview
The workflow is consistent across all vector databases and languages, following these key steps:

Data Preparation:

Legal texts are split into smaller chunks for efficient processing.
Each chunk is embedded using a pre-trained transformer model.
Query Processing:

Queries are generated in two phases:
20 queries created by ChatGPT for initial evaluation.
80 additional queries generated by Gemini for deeper analysis.
Queries are embedded and used to retrieve the most relevant chunks from the database.
Summarization:

Retrieved chunks are summarized using a Hugging Face summarization model.
Comparison:

The generated summaries are compared to predefined answers using:
Cosine Similarity: Measures vector similarity.
Semantic Similarity: Measures textual similarity using sentence embeddings.
Performance Evaluation:

Query response time (latency) is recorded for each database.
Similarity metrics are analyzed to evaluate retrieval and summarization accuracy.
Vector Databases Overview
1. ChromaDB
ChromaDB provides efficient vector storage and retrieval with minimal configuration. The system integrates seamlessly for all five languages, ensuring consistent performance.

Strengths: Simple setup and reliable chunk retrieval.
Challenges: None noted; the system operates as expected.

2. Qdrant
Qdrant supports high-performance retrieval with normalized embeddings for enhanced accuracy.

Strengths: Fast and scalable vector search capabilities.
Challenges: Slight retrieval inconsistencies with ambiguous terms in Italian and Greek texts.

3. Weaviate
Weaviate offers metadata-enriched retrieval and language-specific optimizations.

Strengths: Excellent support for multilingual processing.
Challenges: Slightly slower retrieval for larger chunks (e.g., French).

4. ElasticSearch
ElasticSearch combines text-based search with vector similarity for enhanced retrieval.

Strengths: Robust configuration options for language-specific adjustments.
Challenges: Requires fine-tuning for rare terms in Greek and ambiguous terms in Italian and Spanish.

5. Pinecone
Pinecone is a cloud-based solution designed for high-performance vector search.

Strengths: Scalable and consistent across all languages.
Challenges: Preprocessing adjustments required for Greek to improve rare-term handling


This project highlights the potential of combining modern vector databases with RAG pipelines to process legal documents in multiple languages. The repository offers a comparative study of database performance, providing valuable insights into retrieval efficiency and summarization accuracy across diverse linguistic datasets.
For detailed workflow explanations, refer to the respective Jupyter notebooks.
