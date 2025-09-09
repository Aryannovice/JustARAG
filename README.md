# RAG Business Document Q&A System

A Retrieval-Augmented Generation (RAG) system designed for analyzing business documents using Pinecone vector database and OpenAI.

## Prerequisites

- Python 3.8 or higher
- OpenAI API key
- Pinecone API key

## Setup

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Create a `.env` file** in the project root with your API keys:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   PINECONE_API_KEY=your_pinecone_api_key_here
   PINECONE_ENV=us-east-1-aws
   ```

3. **Prepare your documents:**
   - Place your PDF business documents in the project directory
   - The system works best with business/financial documents

## Usage

1. **Open the notebook:**
   ```bash
   jupyter notebook "RAGFinal(Yardstick).ipynb"
   ```

2. **Run the cells in order:**
   - Cell 1: Installs required packages (if needed)
   - Cell 2: Loads environment variables
   - Cells 5-15: Document processing and vector database setup
   - Cells 17-19: Question answering system

3. **Upload and process documents:**
   - Update the file path in the notebook to point to your PDF
   - The system will automatically chunk and index your documents

4. **Ask questions:**
   - Use the `ask()` function to query your documents
   - Example: `ask("What were the main revenue drivers last quarter?")`

## Features

- **Hybrid Search:** Combines dense vector search with sparse keyword search
- **Cross-encoder Reranking:** Improves search relevance
- **Batch Processing:** Handles large documents efficiently
- **ReACT Agent:** Uses reasoning and acting for better responses

## File Structure

- `RAGFinal(Yardstick).ipynb` - Main notebook with the RAG system
- `requirements.txt` - Python dependencies
- `processed_chunks.pkl` - Cached document chunks (auto-generated)
- Sample PDFs for testing

## Notes

- The system creates a Pinecone index called "rag-business-qa"
- Documents are chunked into smaller pieces for better retrieval
- The system is optimized for business and financial document analysis
