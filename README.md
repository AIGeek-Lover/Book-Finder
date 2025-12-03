📚 Book Recommendation & Emotion Detection

This repository contains a Jupyter notebook inspired by the freeCodeCamp tutorial (https://www.youtube.com/watch?v=Q7mS1VHm3Yw
), which uses a dataset created by Dylan J. Castillo. While the original walkthrough relies on OpenAI’s embedding model, this project explores a fully open-source alternative by using MiniLM-L6-v2 from HuggingFace for embeddings.
For emotion classification, it incorporates another open-source model: j-hartmann/emotion-english-distilroberta-base, also available on HuggingFace.

Together, these models enable a system that generates personalized book recommendations and provides emotion-aware insights based on user input.

🔍 Data Exploration & Preprocessing

Working with text-based datasets presents unique challenges compared to numerical data. Instead of applying direct mathematical operations, we transform, interpret, and structure language so that machine learning models can process it effectively. The preprocessing workflow includes:

Creating a heatmap to visualize missing values

Identifying books with missing descriptions

Exploring relationships between missing descriptions and publication year

Removing incomplete rows or columns

Examining description length to detect very short or uninformative entries

Relating ISBN-13 patterns to book descriptions

🧠 Vectorization & Semantic Search (LangChain + Chroma)

After preprocessing, book descriptions are converted into vector embeddings to enable semantic search.
This project uses LangChain’s TextLoader to organize raw text into structured Document objects, making the data ready for processing.

These documents are then embedded using the MiniLM model, and the resulting vectors are stored in a Chroma vector database, which indexes them for efficient retrieval. Chroma enables fast and meaningful similarity searches, allowing the system to recommend books based on semantic relevance rather than simple keyword matching.

🎛️ User Interface

A simple, interactive interface was built using Gradio, allowing users to input their preferences, receive book recommendations, and view emotion analysis in an intuitive and user-friendly format.
