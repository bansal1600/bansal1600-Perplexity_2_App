# 🤖 Perplexity 2.0

Perplexity 2.0 is a full-stack AI chat application powered by GPT-4o, LangGraph, and Tavily Search. It streams intelligent, web-augmented responses in real time using Server-Sent Events (SSE).

---

## 🏗️ Architecture

Perplexity 2.0 uses a modular client-server architecture.

### 🧑‍💻 Client — Next.js + React

- Built with **Next.js** and **React**
- Real-time response updates using **Server-Sent Events (SSE)**
- Modular UI components for:
  - Message rendering
  - Typing animation
  - Search progress stages
  - User input

### ⚙️ Server — FastAPI + LangGraph

- Backend API built with **FastAPI**
- Uses **LangGraph** to manage conversation flow
- Integrated with:
  - **OpenAI GPT-4o** for response generation
  - **Tavily Search API** for real-time web search
- Streams responses back to client via **SSE**

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- **Node.js** (v18+)
- **Python** (v3.10+)
- **OpenAI API key**
- **Tavily API key**

---

## 💡 How It Works

1. **User enters a message** in the chat UI.
2. **Client sends the message** to the FastAPI backend.
3. **LangGraph decides** whether the LLM needs to:
   - Answer directly, or
   - Trigger a web search
4. If web search is needed:
   - Query is sent to **Tavily**
   - Results are retrieved and sent to the LLM
5. **LLM generates a response** using internal knowledge + web data.
6. **Response is streamed** back to the client using SSE.
7. **Search stages** (`searching`, `reading`, `writing`) are visualized in real-time.
