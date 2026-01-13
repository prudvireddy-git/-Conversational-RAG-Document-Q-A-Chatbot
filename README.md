📄 Conversational RAG with PDFs (Streamlit + LangChain)

This project implements a Conversational Retrieval-Augmented Generation (RAG) application using Streamlit, LangChain, Groq LLMs, Chroma vector store, and HuggingFace embeddings.
Users can upload one or more PDFs and ask questions conversationally, with chat history awareness across sessions.

🚀 Features

📤 Upload multiple PDF files

🔍 Semantic search using embeddings

🧠 Context-aware question reformulation using chat history

💬 Conversational Q&A with memory (session-based)

⚡ Fast inference using Groq (Gemma2-9B-IT)

🗂️ Vector storage using Chroma

🧵 Persistent chat history per session

🏗️ Architecture Overview
User Question
     │
     ▼
Chat History → History-Aware Retriever
     │
     ▼
Relevant PDF Chunks (Chroma)
     │
     ▼
LLM (Groq Gemma2-9B-IT)
     │
     ▼
Concise Answer (with memory)

🧰 Tech Stack

Streamlit – UI

LangChain – RAG pipeline

Groq – LLM inference

HuggingFace Embeddings – all-MiniLM-L6-v2

ChromaDB – Vector store

PyPDFLoader – PDF parsing

📦 Installation
1️⃣ Clone the Repository
git clone https://github.com/your-username/conversational-rag-pdf.git
cd conversational-rag-pdf

2️⃣ Create a Virtual Environment
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows

3️⃣ Install Dependencies
pip install -r requirements.txt

🔐 Environment Variables

Create a .env file in the root directory:

HF_TOKEN=your_huggingface_token


💡 The Groq API key is entered directly in the Streamlit UI for security.

▶️ Run the Application
streamlit run app.py

🖥️ How to Use

Enter your Groq API Key

Provide a Session ID (used for chat memory)

Upload one or more PDF files

Ask questions related to the PDFs

Continue chatting with contextual memory 🎯

🧠 How Chat History Works

Each session ID maintains its own ChatMessageHistory

Questions are reformulated using previous messages

Enables follow-up questions like:

“Explain that in simpler terms”
“What was the conclusion?”

⚙️ Key Components Explained
🔹 History-Aware Retriever

Rewrites follow-up questions into standalone queries using past conversation context.

🔹 Retrieval Chain

Fetches relevant document chunks from Chroma and injects them into the LLM prompt.

🔹 RunnableWithMessageHistory

Maintains stateful conversations across user inputs.

📌 Limitations

Temporary PDF storage (temp.pdf) is overwritten per upload

Chroma vector store is in-memory (not persistent)

Designed for small to medium PDFs

🛠️ Possible Enhancements

✅ Persistent vector storage

✅ File-specific metadata filtering

✅ Streaming responses

✅ Multi-user authentication

✅ Source citation in answers

📜 License

MIT License

🙌 Acknowledgements

LangChain

Groq

HuggingFace

Streamlit
