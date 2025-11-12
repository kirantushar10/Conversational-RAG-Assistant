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
### Step 2: Install Dependencies

```bash
python -m venv venv
source venv/bin/activate   # (Windows: venv\Scripts\activate)
pip install -r requirements.txt
```
### Step 3: Add API Keys and Run

Create a .env file in the project root and add:

```bash
LANGCHAIN_API_KEY = "Add your LangChain API key here"
LANGCHAIN_PROJECT = "Conversational RAG Assistant"
HF_TOKEN = "Add your Hugging Face API key here"
GROQ_API_KEY = "Add your Groq API key here"
LANGCHAIN_TRACING_V2 = "true"
```

### Step 4: Run the Chatbot (Jupyter Notebook Version)

Since this project runs inside a Jupyter Notebook, you don’t need to execute a `.py` file.  
You can start the chatbot directly in your browser by opening and running the notebook.

Add a Website of Your Choice: Find the section in the notebook where the loader is defined

```bash
loader = WebBaseLoader(
    web_paths=("https://example.com",),
)
```
The chatbot will scrape that site, create embeddings, and build a vector database (Chroma) from its text — letting you chat based on that website’s content.

### Step 5 — View LangSmith Dashboard

1. Open https://smith.langchain.com

2. Log in with your LangSmith account linked to your LANGCHAIN_API_KEY

3. Select your project Conversational RAG Assistant

4. Inspect traces, prompts, retrieved documents, and model responses in detail.

---

## 🧩 How It Works

1. Document Loading & Splitting: Uses WebBaseLoader and RecursiveCharacterTextSplitter to load and chunk web content.

2. Embeddings Generation: Text chunks are embedded into vectors using HuggingFaceEmbeddings.

3. Vector Storage & Retrieval: Stores embeddings in Chroma and retrieves semantically similar chunks based on user queries.

4. LLM Response Generation: Combines retrieved documents with the user query to generate a concise, contextually grounded response.

5. Conversation Memory: Uses RunnableWithMessageHistory to automatically track and remember previous exchanges.

6. Tracing with LangSmith: Every chain run, retriever query, and LLM call is logged for easy debugging and performance monitoring.

---

## 💬 Example Conversation

User: What is self-reflection?
Bot: Self-reflection is the process of analyzing one’s thoughts and behavior.

User: Tell me more about it.
Bot: It helps individuals learn from past experiences and improve future decision-making.

User: What is task decomposition?
Bot: Task decomposition means breaking a complex task into smaller, manageable steps.

---


