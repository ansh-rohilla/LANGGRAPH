# LANGGRAPH

A practical collection of Jupyter notebooks for learning how to build stateful AI workflows with [LangGraph](https://langchain-ai.github.io/langgraph/). The examples progress from verifying the installation to composing LLM-powered graphs with Google Gemini.

## What's included

| Notebook | What it demonstrates |
| --- | --- |
| `0_test_installation.ipynb` | A quick check that LangGraph imports successfully. |
| `1_bmi_workflow.ipynb` | A deterministic graph that calculates and classifies BMI. |
| `2_llm_workflow_simple.ipynb` | A one-step question-answering workflow using Gemini. |
| `prompt_chaining.ipynb` | A multi-step graph that generates a blog outline, then turns it into a full article. |

## Prerequisites

- Python 3.10 or later
- A Google AI Studio API key for the Gemini-powered notebooks

## Setup

```bash
git clone https://github.com/<your-username>/LANGGRAPH.git
cd LANGGRAPH
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\\Scripts\\activate
pip install -r requirements.txt
cp .env.example .env
```

Open `.env` and replace the placeholder with your Google API key:

```env
GOOGLE_API_KEY=your_google_ai_studio_api_key
```

Then start Jupyter:

```bash
jupyter notebook
```

Run the notebooks in numerical order. The BMI example needs no API key; the Gemini examples load `GOOGLE_API_KEY` from `.env`.

## How the examples work

Each workflow defines a typed state, registers one or more processing nodes, connects them from `START` to `END`, compiles the graph, and invokes it with an initial state. This keeps the control flow explicit and makes each step easy to inspect or extend.

## Security note

Never commit API keys. `.env` is intentionally excluded from version control; use `.env.example` as the safe configuration template.

## License

This project is provided for learning and experimentation.
