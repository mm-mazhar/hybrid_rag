# Hybrid RAG | WEBSITE CRAWLER | A Document Q&A Application with LanceDB

<p align="center">
  <table>
    <tr>
      <td>
        <a href="LICENSE">
          <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License">
        </a>
      </td>
      <td>
        <a href="https://www.python.org/">
          <img src="https://img.shields.io/badge/Python-3.9-blue" alt="Python Badge">
        </a>
      </td>
      <td>
        <a href="https://lancedb.github.io/">
          <img src="https://img.shields.io/badge/LanceDB-%23228BE6.svg?style=for-the-badge&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAAAXNSR0IArs4c6QAAAnVJREFUOBGNUtFuwjAQ3p0bK/0w7eD0N7g01A17q1+QW0I0g4oG+QpEQYJ5v/e2+R8J0+J2YV8W7o949rJc5Lw73Lq+i9aF6l+5Xl83n/7/8/8/n/u/r0eI4yQ0Z0f4dM8h0dD9n39P+Lz+U4b02P8/n8N6t9rNbrczN4yQfR7x+/+/1eiqF6Xm488+n0240b6b+f577+9Hn8R/s53Oczk7b153+2+Vqj79/v9+v46gUjI4uL4N8vLycY8n/cW7b0V0Y9K2trY5f0J7iP3y7r/b6d47U47Z88V+z0a+Xp13+g7V6/Wd1k0h6u+YqF66X63X6738v9J/J7Z6/X6j/10+l3V3h6s99v11o16a+r88L8f5+V19m72lTjI5lJ12p6/X6qE/fL+gX6846+k7e/Z8d3Q84tE4hI+h8v+Yf9Xm09U7vT7f2i2u92n7O/oH1p8z/J0iE34jP45k183hF5l3mJ1eP8/6w2a0K+19g8+Jm/qg5q14i76iP7w3qZ4zJ+t6vV6p78gD/pY5XvS+S3nFp+KxH/eXh9vH9b649wJ+vYwAAAAASUVORK5CYII=" alt="LanceDB Badge">
        </a>
      </td>
      <td>
        <a href="https://openai.com/">
          <img src="https://img.shields.io/badge/OpenAI-white?style=for-the-badge&logo=openai&logoColor=black" alt="OpenAI Badge">
        </a>
      </td>
      <td>
        <a href="https://pypi.org/project/docling/">
          <img src="https://img.shields.io/badge/DocLing-blueviolet" alt="DocLing Badge">
        </a>
      </td>
      <td>
        <a href="https://streamlit.io/">
          <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=Streamlit&logoColor=white" alt="Streamlit Badge">
        </a>
      </td>
    </tr>
  </table>
</p>

<table>
    <tr>
      <td>
        <a href="">
          <img src="https://i.imgur.com/cejiHpU.png" alt="Steamlit App Screenshot">
        </a>
      </td>
    </tr>
  </table>

## Overview

Streamlit-based application that enables you to ask questions about documents and receive answers based on the content of those documents. It uses a Hybrib Retrieval-Augmented Generation (RAG) to find relevant information within the document and generate accurate, context-aware responses.

**Key Features:**

*   **Document Input Flexibility:** Supports PDFs, URLs, and website sitemap extraction.
*   **Intelligent Chunking:** Documents are intelligently split into chunks to optimize retrieval accuracy and context.
*   **Vector Database Powered by LanceDB:** Utilizes LanceDB to store document chunks as embeddings for efficient similarity search.
*   **OpenAI Integration:** Leverages OpenAI's models for embedding generation and question answering.
*   **Chat History:** Maintains chat history for each document to provide a more engaging and personalized experience.
*   **Easy-to-Use Interface:**  Streamlit provides a user-friendly interface for document selection, question input, and result display.

## Workflow

- Document Input: The user provides a document (PDF, URL, Website).
- Document Extraction and Chunking: The document is extracted and split into smaller chunks.
- Embedding Generation: Each chunk is converted into a vector embedding using OpenAI's embedding models.
- LanceDB Vector Store: The embeddings are stored in LanceDB, along with associated metadata (filename, page numbers, etc.).
- User Question: The user asks a question related to the document.
- Embedding Generation: The question is converted into a vector embedding using the same OpenAI model.
- Similarity Search: LanceDB is used to perform a similarity search, finding the document chunks that are most relevant to the question.
- Context Retrieval: The text from the relevant document chunks is retrieved.
- LLM (OpenAI): The user's question and the retrieved context are fed into an OpenAI language model.
- Answer Generation: The LLM generates an answer based on the provided context.
- User Output: The answer is displayed to the user.

## Tools Used
- Python: The core programming language.
- Streamlit: For building the user interface.
- LanceDB: As the vector database to store and search document embeddings.
- OpenAI API: For generating embeddings and providing question-answering capabilities.
- DocLing (docling): A library for document conversion and processing.
- dotenv: For managing environment variables.
- tiktoken: For tokenization.
- PyYAML: For configuration file parsing.

## Installation

1. Clone the repository:
    ```bash
    git clone [your_repository_url]
    cd [directory]
    ```
2. Create and activate a virtual environment:
    ```bash
    python -m venv .venv
    source .venv/bin/activate  # On Linux/macOS
    .venv\Scripts\activate  # On Windows
    ```
3. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
4. Configure Environment Variables:
    - Create a .env file in the root directory of the project.
    - Add your OpenAI API key:
    ```
    OPENAI_API_KEY=your_openai_api_key
    ```
    - Adjust configurations in ./configs/docPipeline_configs.yaml according to your needs:

## Running the Application

1. Run the Streamlit app:
    ```bash
    streamlit run src/app/app.py
    ```
2. Access the application in your web browser at http://localhost:8501.



