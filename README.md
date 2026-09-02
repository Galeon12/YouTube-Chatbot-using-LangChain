# YouTube Video Chatbot 🎥🤖

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1aMfDS7X2K4MUIcYzmy0YT4-SbHyJE0gN)

A powerful interactive chatbot that allows you to "talk" to any YouTube video! This project leverages **LangChain** and **OpenAI's LLMs** to extract video transcripts, generate embeddings, and perform Retrieval-Augmented Generation (RAG). Instead of watching hours of video, just drop the link and ask questions to instantly get the insights you need.

## Features ✨

- **Automatic Transcript Extraction**: Pulls transcripts directly from YouTube using `youtube-transcript-api` (or custom fallback mechanisms like `yt-dlp`).
- **Semantic Search**: Uses LangChain and FAISS for efficient chunking, embedding, and retrieval of video content.
- **Context-Aware Q&A**: Uses a conversational Retrieval-Augmented Generation (RAG) pipeline so you can ask complex, multi-part questions about the video's contents.
- **Ready to Run**: The provided Jupyter Notebook can be run locally or directly in Google Colab without complex setups.

## How it Works ⚙️

1. **Ingestion**: We download the transcript for a given YouTube Video ID.
2. **Chunking**: The transcript is split into meaningful text chunks using LangChain's `RecursiveCharacterTextSplitter`.
3. **Vector Database**: We generate embeddings for these chunks (using OpenAI) and store them in a local `FAISS` vector index.
4. **Retrieval & Generation**: When you ask a question, the pipeline finds the most relevant transcript segments and uses an LLM to formulate an accurate answer.

## Usage 🚀

The easiest way to use this project is by running the notebook directly in Google Colab.

1. Click the "Open in Colab" badge at the top of this README.
2. When prompted in the notebook, securely enter your `OPENAI_API_KEY`. (Note: Never hardcode your API key in the notebook cells!)
3. Run the cells sequentially to build the pipeline.
4. Provide a YouTube video URL and start chatting!

## Setup Locally 💻

If you prefer to run this locally:

1. Clone this repository:
   ```bash
   git clone https://github.com/Galeon12/YouTube-Chatbot-using-LangChain.git
   cd YouTube-Chatbot-using-LangChain
   ```
2. Create a virtual environment and install the required dependencies (refer to the imports in the notebook).
3. Set your environment variables (e.g., using a `.env` file):
   ```env
   OPENAI_API_KEY=your_api_key_here
   ```
4. Open and run `rag_using_langchain.ipynb` in your preferred Jupyter environment (e.g., VS Code or JupyterLab).

## Security Note 🔒

**Always protect your API keys.** The code is structured to read the API key from environment variables or prompt for it interactively. Do not commit `.env` files or notebooks with hardcoded keys to version control.
