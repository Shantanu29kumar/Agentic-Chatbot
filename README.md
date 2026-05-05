# 🧠 AI Navigator – Chat, Search & Stay Updated

AI Navigator is a simple yet powerful app that brings together **AI chat, real-time web search, and AI news tracking** into one seamless experience.

Instead of switching between tools, you can **ask, explore, and stay updated** — all in one place.

---

## 🚀 Features

### 💬 AI Chat
Have natural conversations with an AI assistant powered by modern language models.

### 🌐 Smart Search
Get better answers using real-time web search when needed.

### 📰 AI News Summaries
Fetch the latest AI news and automatically convert it into clean, readable summaries.

---

## 🧩 Why This Project

- Combines **chat + search + news** in one app
- Uses a **structured AI workflow (LangGraph)**
- Clean and interactive **Streamlit UI**
- Designed to be **modular and extendable**

---

## 📁 Project Structure

- `app.py` — Streamlit launch point.
- `src/langgraphagenticai/main.py` — app orchestrator and graph runner.
- `src/langgraphagenticai/graph/graph_builder.py` — constructs workflows for each use case.
- `src/langgraphagenticai/nodes/` — chatbot and AI news nodes.
- `src/langgraphagenticai/UI/streamlitui/` — UI layout and result rendering.
- `src/langgraphagenticai/UI/uiconfigfile.ini` — app settings and UI options.
- `AINews/` — auto-generated AI news summary files.

---

## 🔧 Technical Details

### What it uses

- `Streamlit` for the user interface
- `LangGraph` for stateful AI workflow graphs
- `Groq` (via `langchain_groq`) for the LLM backend
- `Tavily` for real-time AI news search

### Supported Use Cases

- **Basic Chatbot** — conversation-only assistant.
- **Chatbot With Web** — chatbot with tool-enabled responses.
- **AI News** — fetches AI news, summarizes it, and saves it as markdown.

---

## ⚙️ Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

---

## 🔧 Configuration

Update `src/langgraphagenticai/UI/uiconfigfile.ini` to change:

- `PAGE_TITLE`
- `LLM_OPTIONS`
- `USECASE_OPTIONS`
- `GROQ_MODEL_OPTIONS`

Valid keys are entered in the app sidebar during runtime.

---

## ▶️ Usage

Run the app locally with:

```bash
streamlit run app.py
```

Then open the Streamlit UI and:

1. Select `Groq` as the LLM.
2. Pick a Groq model.
3. Enter your `GROQ_API_KEY`.
4. Choose a use case.
5. If `Chatbot With Web` or `AI News`, enter `TAVILY_API_KEY`.
6. For `AI News`, choose a timeframe and click `Fetch Latest AI News`.

---

## 📝 Notes

- The `AI News` feature uses `TavilyClient` to fetch news and the Groq LLM to summarize it.
- Generated summaries are saved to `AINews/{frequency}_summary.md`.
- If you see token limit errors, choose a smaller Groq model or reduce the article payload.
- The `Chatbot With Web` feature integrates tools, with responses handled through the graph workflow.

---

## 🛠️ Troubleshooting

- If the app does not show summaries, ensure valid API keys are provided.
- If the Groq model fails with token errors, lower the number of fetched articles or use a model with higher token limits.
- If the UI returns no response, verify the selected use case and review the Streamlit logs for detailed exceptions.

 