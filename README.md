# RAG-based Chat with PDF and Text

## Overview

This application allows users to interact with a chatbot that answers questions based on the content of uploaded PDF and text documents. It uses **Retrieval-Augmented Generation (RAG)** to retrieve relevant information from the documents and generate AI-driven responses. The app is built with **Streamlit** and provides an intuitive interface for file uploads, question-answering, and chat history management.

---

## Features

- **File Upload**: Upload and process PDF and text files.
- **RAG-based QA**: The chatbot retrieves and generates answers based on document content.
- **Chat History**: View or clear chat history from previous interactions.
- **Document Linking**: Link directly to specific PDF pages if content matches.
- **Vector Store**: Efficient retrieval using **FAISS** for document embeddings.

---

## How It Works

1. **Document Processing**:
   - The app accepts PDF and text files.
   - PDF content is extracted using **PyPDFLoader**, and text files are processed by **TextLoader**.
   - Files are stored temporarily in the `temp_uploads/` directory.
  
2. **Text Splitting**:
   - Text is split into chunks using **RecursiveCharacterTextSplitter** for efficient processing.

3. **Embedding Generation**:
   - Chunks are passed through the **Azure OpenAI Embeddings** model to generate vector embeddings.
   
4. **Vector Store**:
   - Embeddings are stored in **FAISS** for fast, accurate retrieval.
   
5. **Conversational Chain**:
   - Questions are answered using **ConversationalRetrievalChain**, retrieving relevant document chunks.

6. **PDF Linking**:
   - If applicable, responses include links to the specific PDF pages.
   
7. **Chat History**:
   - Chat history is saved in `chat_history.json` and can be viewed or cleared.

---


