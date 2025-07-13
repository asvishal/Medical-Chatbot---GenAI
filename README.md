Medical-Chatbot---GenAI
# 🧠 Medical Chatbot - GenAI
Medical Chatbot - GenAI is a Generative AI-powered web application that leverages Large Language Models (LLMs), vector embeddings, and Retrieval-Augmented Generation (RAG) techniques to provide intelligent, context-aware answers to medical-related queries. The application is designed using Flask and integrates OpenAI's language models with Pinecone vector database for semantic search over medical documents.

# 🚀 Features
🔍 Semantic search over domain-specific PDFs using embeddings

🧠 Natural language understanding using OpenAI LLM

🔗 Retrieval-Augmented Generation (RAG) pipeline for grounded answers

🌐 Web interface using Flask

☁️ Pinecone integration for scalable vector indexing

📄 PDF ingestion and processing pipeline

🛠️ Modular codebase with prompt engineering

# 🗂️ Project Structure
medical-chatbot-genai/
│
├── app.py                  # Flask server and routes
├── store_index.py          # Embedding generation and Pinecone indexing
├── setup.py                # Project setup configuration
├── template.py             # Project file scaffolding utility
├── research/
│   └── trials.ipynb        # Experimental notebooks
├── src/
│   ├── helper.py           # PDF loader, text splitting, embeddings
│   ├── prompt.py           # Custom system prompts
│   └── __init__.py         # Package initializer
├── .env                    # Environment variables

# 📦 Key Python Packages & Their Roles
| Package                    | Purpose                                                            |
| -------------------------- | ------------------------------------------------------------------ |
| flask                    | Web framework to serve the chatbot UI and handle requests          |
| langchain                | Framework to manage prompt templates, chains, and LLM integrations |
| langchain_openai         | OpenAI wrapper to query GPT-based models                           |
| langchain_pinecone       | Pinecone integration for LangChain's retriever interface           |
| pinecone                 | Vector database for storing and retrieving document embeddings     |
| dotenv                   | To load API keys from `.env`                                       |
| pathlib, os, logging     | For filesystem operations and logging during setup                 | 

# 🧠 How It Works
# ✅ Embedding & Indexing
PDFs in Data/ are loaded and split into chunks.

Each chunk is embedded using HuggingFace embeddings.

These embeddings are indexed into Pinecone with cosine similarity as the metric.

File: store_index.py

# 🔗 Retrieval-Augmented Generation (RAG)
On receiving a user query from the UI, relevant chunks are retrieved from Pinecone.

These are passed to the LLM with a system prompt to generate a contextual, reliable response.

File: app.py

# 🗨️ Prompt Engineering
Prompts are configured in src/prompt.py to instruct the LLM with the right persona and scope for reliable answers.

