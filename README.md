# Ollama LangChain Chatbot 🤖

This project is a localized AI assistant built using **LangChain** and **Ollama**. It demonstrates how to deploy and interact with Large Language Models (LLMs) locally on your hardware, ensuring data privacy and reducing API costs.

## 📚 Learning Objectives
Through this project, I explored:
* **Local LLM Orchestration:** Running `Llama2` locally using Ollama to bypass external API dependencies.
* **LangChain Expression Language (LCEL):** Implementing a declarative chain using the `|` (pipe) operator to link Prompts, LLMs, and Output Parsers.
* **Observability & Tracing:** Integrating **LangSmith** to monitor latency, trace execution steps, and debug model responses in real-time.
* **Web Interface Development:** Building a reactive UI using **Streamlit** for seamless user interaction.

---

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Framework:** [LangChain](https://www.langchain.com/)
* **LLM Provider:** [Ollama](https://ollama.com/) (Model: `llama2`)
* **UI:** [Streamlit](https://streamlit.io/)
* **Monitoring:** [LangSmith](https://smith.langchain.com/)
* **Environment:** `python-dotenv` for secure secret management

---

## 🚀 Getting Started

### 1. Prerequisites
* Install [Ollama](https://ollama.com/download)
* Pull the Llama2 model:
  ```bash
  ollama pull llama2
  ```


### 2.  Installation
```
git clone [https://github.com/your-username/ollama-langchain-chatbot.git](https://github.com/your-username/ollama-langchain-chatbot.git)
cd ollama-langchain-chatbot
pip install -r requirements.txt
```
### 3. Environment Setup
* Create a .env file in the root directory and add your LangChain credentials:

```
LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=your_langsmith_api_key_here
LANGCHAIN_PROJECT="Ollama-Chat-Bot"
```
### 4. Running the App
```
streamlit run app.py
```
🏗️ Architecture
----------------

The application follows a modular pipeline:

1.  **User Input:** Streamlit captures the query.

2.  **Prompt Template:** The query is wrapped in a System/User message structure.

3.  **LLM Execution:** The `ChatOllama` class communicates with the local Ollama server (at `127.0.0.1:11434`).

4.  **Output Parsing:** The raw response is converted into a clean string via `StrOutputParser`.

5.  **Tracing:** Every step is logged to LangSmith for performance analysis.

### Streamlit Interface

![Dashboard](/Dashboard.png "Sample")



### LangSmith Tracing Dashboard

![LangSmith](/LangSmith.png "Sample")