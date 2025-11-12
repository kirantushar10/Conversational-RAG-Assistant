# 🧠 Conversational RAG Assistant

An advanced **Retrieval-Augmented Generation (RAG)** chatbot built with **LangChain**, **Groq Llama 3**, **Chroma**, and **Hugging Face embeddings**.  
It supports **multi-turn conversations**, **contextual memory**, and **LangSmith tracing** for real-time observability.

---

## 🚀 Features

- ⚡ **Retrieval-Augmented Generation (RAG):** Combines knowledge retrieval with LLM reasoning for context-aware Q&A.  
- 💬 **Conversational Memory:** Remembers past user messages using `ChatMessageHistory` and `RunnableWithMessageHistory`.  
- 🧠 **Contextual Question Rewriting:** Uses a history-aware retriever to reformulate follow-up questions automatically.  
- 🔍 **Semantic Search with Chroma:** Embeds and retrieves relevant text chunks using `HuggingFaceEmbeddings`.  
- 🧰 **LangSmith Tracing:** Real-time tracking, debugging, and performance visualization for your LangChain runs.  
- 🌐 **Web Data Loader:** Dynamically loads and processes external blog content for question answering.  

---

## 🧰 Tech Stack

| Component | Library / Model | Description |
|------------|----------------|--------------|
| **Framework** | [LangChain](https://www.langchain.com) | Orchestrates LLM chains and RAG pipelines |
| **LLM Provider** | [Groq API (Llama 3)](https://groq.com) | High-speed inference for chat completions |
| **Embeddings** | `all-MiniLM-L6-v2` (Hugging Face) | Creates vector representations of text |
| **Vector Store** | [ChromaDB](https://www.trychroma.com) | Stores and searches embedded document vectors |
| **Prompt Management** | `ChatPromptTemplate` | Formats system and user messages for LLM input |
| **Memory System** | `ChatMessageHistory` + `RunnableWithMessageHistory` | Retains conversation context |
| **Tracing & Monitoring** | [LangSmith](https://smith.langchain.com) | Observes and debugs LLM pipelines |
| **Data Loading** | `WebBaseLoader` | Scrapes and ingests online data sources |

---

## ⚙️ Installation & Setup

Follow these steps to install, configure, and run the **Conversational RAG Assistant** on your local machine.  

---

### Step 1: Clone the Repository

Clone the repository from GitHub and navigate to the project directory.

```bash
git clone https://github.com/kirantushar10/Conversational-RAG-Assistant.git
cd Conversational-RAG-Assistant
```
### Install Dependencies

```bash
python -m venv venv
source venv/bin/activate   # (Windows: venv\Scripts\activate)
pip install -r requirements.txt
```
