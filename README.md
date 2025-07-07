
# LangChain Chatbot 📚🤖

A conversational AI assistant built on **LangChain** and **OpenAI**, designed for interacting with your own documents and data.

---

## 🚀 Features

- **Drag‑and‑drop file ingestion** through a user-friendly UI (supported: PDF, DOCX, TXT, etc.)
- **Chat interface** with adjustable parameters like temperature, vector retrieval `k`, and system prompts
- **Contextual answers with sources**: See where the bot pulls info from
- Easily extendable to support more file types or offline models

---

## 🛠 Technology Stack

- **Python 3.10+**
- [LangChain](https://github.com/langchain-ai/langchain)
- OpenAI API (GPT‑3.5 / GPT‑4)
- Pinecone vector database
- FastAPI backend / Streamlit + React frontend

---

## ✅ Installation & Setup

1. **Clone the repo**  
   ```bash
   git clone https://github.com/yourusername/langchain-chatbot.git
   cd langchain-chatbot
   ```

2. **Install dependencies**  
   - *Python*:  
     ```bash
     pip install -r requirements.txt
     ```
   - *Node (if needed for React UI)*:  
     ```bash
     cd ui && npm install
     ```

3. **Add your API keys**  
   Copy `.env.example` to `.env`:
   ```ini
   OPENAI_API_KEY=your_openai_key
   PINECONE_API_KEY=your_pinecone_key
   PINECONE_ENV=your_pinecone_env
   PINECONE_INDEX=your_index_name
   ```

4. **Initialize Pinecone index**  
   ```bash
   python startup.py
   ```

5. **Launch the app**  
   ```bash
   python app.py
   # or for frontend:
   cd ui && npm start
   ```

---

## 🎯 Usage

1. Open the web app (default: `http://localhost:8000`)
2. Upload your documents via the ingestion interface
3. Start chatting: ask direct questions and get answers with source citations
4. Tweak **temperature**, **vector retrieval k**, and **system prompts** on the fly

---

## 🏗 Architecture

```text
[ Upload File ] → [ Document Loader + Text Splitter ]
     ↓
[ LangChain Embedding → Pinecone Vector Store ]
     ↓
[ Prompt + Retriever → LLM (OpenAI) ]
     ↓
[ Response + Source Snippets → UI ]
```

---

## ✅ What I Learned

- End-to-end pipeline: ingestion → embedding → vector storage → retrieval → generation
- How to tweak prompts and loop in metadata for reliable, context-aware answers
- Building dynamic UI controls to monitor model parameters in real time
- Deploying a vector DB (Pinecone) and integrating it with LangChain

---

## 🔧 Future Plans

- 📝 Add OCR + support for image-based documents
- 🤖 Integrate offline/open-source LLMs (HuggingFace, Vicuna, Alpaca)
- 🛠 Modularize toolchain: easily plug in new retrievers, vector stores, and UIs
- ☁️ Deploy on cloud: Next.js frontend + Docker backend

---

## 📄 About This Project

This chatbot is a polished and extended implementation inspired by the highly‑starred [Haste171/langchain-chatbot](https://github.com/Haste171/langchain-chatbot). I’ve refined the UI, documented the data flow, and built added support for custom frontends.

---

## 📥 Contributing

1. Fork this repo  
2. Create a feature branch (`git checkout -b feature/my-cool-feature`)  
3. Add functionality or bugfixes  
4. Ensure tests pass & update docs  
5. Submit a pull request

---

## 📝 License

This project is released under the **MIT License**.
