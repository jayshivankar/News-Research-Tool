# News Article Retrieval using LangChain, OpenAI Embeddings & FAISS

This web app allows users to process URLs containing articles, build embeddings using OpenAI’s embeddings, and perform efficient similarity searches using FAISS. It retrieves relevant answers based on the processed articles.

## Features
- Input URLs directly or upload text files containing URLs.
- Automatically fetch and process article content through LangChain’s `UnstructuredURLLoader`.
- Split text and generate embeddings using OpenAI’s embeddings API.
- Store and index embeddings using FAISS for fast retrieval.
- Answer user queries based on indexed content, providing relevant article URLs as sources.
- The app features a simple, interactive interface powered by Streamlit.

## Project Structure
- **main.py**: The main Streamlit application script that serves the web app.
- **requirements.txt**: A list of Python dependencies needed to run the project.
- **faiss_store_openai.pkl**: A pickle file that stores the FAISS index for quick future access.
- **.env**: Configuration file where your OpenAI API key should be stored.

## How it Works

### 1. Input URLs
On the sidebar of the web app, you can:
- Enter URLs directly.
- Upload a text file that contains multiple URLs.

### 2. Process URLs
Once the URLs are entered or uploaded, click **“Process URLs”**. This will:
- Fetch article content from the URLs using LangChain’s `UnstructuredURLLoader`.
- Split the article into smaller chunks for more efficient processing.
- Generate embedding vectors for the text chunks using OpenAI’s/Hugging face embeddings.
- Index the embeddings using FAISS, which allows for fast similarity searches.

### 3. Querying
After processing, you can input any query in the query box. The app will search the FAISS index and retrieve the most relevant articles based on your query. The system will return answers along with the source URLs from which the information was retrieved.

### 4. Save & Load FAISS Index
The FAISS index will be saved in `faiss_store_openai.pkl` as a pickle file. This allows you to load the index for future use, speeding up future searches without needing to reprocess the URLs.

## Requirements

To run this project, you need the following Python packages:

- streamlit
- langchain
- openai
- HuggingFace
- faiss-cpu
- requests
- unstructured
- pandas

Install the dependencies using:

```bash
pip install -r requirements.txt
