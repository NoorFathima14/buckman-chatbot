Multimodal Chatbot
===============

A multimodal chatbot designed to simplify file querying, processing, and intelligent response generation. Buckman Chatbot supports diverse file types (PDF, CSV, DOCX, PNG, JPEG, MP4), processes text, images, and videos, and enhances responses with web search validation and caching for performance. Built with open-source technologies, it’s a user-friendly solution for students, researchers, educators, and professionals.

Overview
--------

This Chatbot is a web-based application that allows users to upload, process, and query files in various formats, including PDFs, images, and videos. It leverages multimodal processing to handle text, images, and videos, and uses natural language querying to provide intelligent, Markdown-formatted responses with syntax highlighting. The chatbot validates responses using web search (Google Custom Search API) and caches them with Redis for faster retrieval of repeated queries. It’s designed for academic research, content analysis, lecture summarization, and more, targeting students, researchers, educators, and professionals.

Key Features
------------

*   **Diverse File Support**: Processes PDFs, images, videos (PDF, CSV, DOCX, PNG, JPEG, MP4).
    
*   **Efficient Querying**: Replaces manual searching with fast, automated extraction.
    
*   **Multimodal Processing**: Handles multiple media types with intelligent querying.
    
*   **Web Search Validation**: Enhances responses with Google Custom Search API.
    
*   **Response Caching**: Caches query responses in Redis for instant retrieval of previously used queries.
    
*   **Markdown Rendering**: Displays responses with syntax-highlighted code blocks using React-Markdown and React-Syntax-Highlighter.
    
*   **File Management**: Upload, list, and delete files with ease.
    
*   **User-Friendly Interface**: Straightforward and intuitive design built with React.
    
*   **Optimization**: Parallelizes file processing and web search, saving 5.61s (from 25.52s to 19.91s) for efficient resource utilization and faster responses.
    
*   **Containerization**: Uses Docker for seamless deployment and scalability across services.
    

Technologies Used
-----------------

*   **Frontend**: React, Vite, React-Markdown, React-Syntax-Highlighter; Nginx for serving.
    
*   **Backend**: FastAPI, Tesseract OCR; Uvicorn for high-performance API serving.
    
*   **Database & Caching**: ChromaDB for vector storage; Redis container for caching.
    
*   **Containerization**: Docker and Dockerfile for scalability and consistency.
    
*   **NLP**: Sentence Transformers for embeddings and text processing.
    
*   **RAG Pipeline**: Haystack for retrieval-augmented generation, enabling efficient document querying.
    
*   **Web Search**: Google Custom Search API for response validation and enhancement.
    
*   **LLM**: Mistral-7B via Ollama container for local inference, enhancing multimodal processing.
    

Installation
------------

### Prerequisites

*   Python 3.8+
    
*   Node.js 16+
    
*   Docker and Docker Compose
    
*   Git
    

### Steps
    
1.  **Set Up Environment Variables**:
    
    *   bashCollapseWrapCopycp .env.example .env
        
    *   Update .env with your API keys and configuration (e.g., Google Custom Search API key, Redis settings).
        
2.  bash cd backend pip install -r requirements.txt
    
    
3.  **Run with Docker**:
    
    *   Ensure Docker is running.
        
    *   This will start the backend (FastAPI), frontend (React), Redis, and Ollama containers.
        

Usage
-----

1.  **Upload Files**:
    
    *   Use the web interface to upload files (PDF, CSV, DOCX, PNG, JPEG, MP4).
        
    *   Supported file types are processed automatically (e.g., text extraction from PDFs, transcripts from videos).
        
2.  **Query the Chatbot**:
    
    *   Enter a natural language query, such as “What are the key findings in the file, and are they consistent with recent studies?”
        
    *   The chatbot processes the query, retrieves relevant content, validates with web search, and generates a response.
        
3.  **View Responses**:
    
    *   Responses are displayed in Markdown format with syntax-highlighted code blocks.
        
    *   Repeated queries are served instantly from the Redis cache.
        
4.  **Manage Files**:
    
    *   List and delete uploaded files as needed through the interface.
        

Workflow
--------
### Workflow Steps

1.  **User Interaction**: Upload files and submit a query via the React frontend.
    
2.  **File Processing**: Extract text/audio using FastAPI and Tesseract OCR.
    
3.  **Parallel Operations**: Process files and perform web search in parallel.
    
4.  **Sequential Embedding**: Generate embeddings with Sentence Transformers, stored in ChromaDB.
    
5.  **RAG Pipeline**: Retrieve relevant content using Haystack and ChromaDB.
    
6.  **Response Generation**: Generate a response with Mistral-7B via Ollama.
    
7.  **Caching**: Cache the response in Redis.
    
8.  **Response Delivery**: Display the Markdown-formatted response on the frontend.
    

Contact
-------

*   **Author**: Noor Fathima
    
*   **GitHub**: [NoorFathima14](https://github.com/NoorFathima14)
    

For questions, suggestions, or collaboration, feel free to open an issue or reach out directly!

This README provides a professional and detailed overview of your project, making it easy for others to understand, use, and contribute to Buckman Chatbot. Let me know if you’d like to adjust or add more sections!
