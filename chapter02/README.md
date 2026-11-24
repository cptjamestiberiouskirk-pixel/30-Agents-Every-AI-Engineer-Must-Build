# Chapter 2: The Agent Engineer's Toolkit

**Book:** *30 Agents Every AI Engineer Must Build* by Imran Ahmad (Packt Publishing, 2026)

---

## Overview

This repository is the executable companion to **Chapter 2** of *30 Agents Every AI Engineer Must Build*. It covers the full agent engineering stack: frameworks (LangChain, LangGraph, LlamaIndex, AutoGPT, CrewAI, AutoGen), LLM selection guidelines, vector databases, RAG pipelines, tool integration patterns, and cloud-native development platforms.

Every code cell runs **without an API key** in Simulation Mode, powered by a `MockLLM` layer that returns chapter-derived responses. When an API key is provided (OpenAI, Anthropic, or Google) or Ollama is running locally, the notebook seamlessly switches to Live Mode. Each provider has its own pre-executed notebook variant.

## Quickstart

To read the worked examples on GitHub, open the [Chapter 2 simulation notebook](ch02_agent_toolkit__RUN_NO_KEY_SIMULATION.ipynb). Its saved output is available without installing Python or using an API key.

```bash
# 1. Clone the repository
git clone https://github.com/PacktPublishing/30-Agents-Every-AI-Engineer-Must-Build.git
cd ./30-Agents-Every-AI-Engineer-Must-Build/
cd chapter02

# 2. Create a virtual environment (recommended)
python -m venv .venv
source .venv/bin/activate   # Linux/Mac
# .venv\Scripts\activate    # Windows
```

To run the examples locally, keep the full repository checkout and run these commands from `chapter02` with your virtual environment active. Jupyter opens the notebook, and SymPy performs the calculation in the calculator example.

```bash
python -m pip install notebook sympy
jupyter notebook ch02_agent_toolkit.ipynb
```

For a simulation run, use an environment without provider credentials. If the notebook prompts for an API key, press Enter to leave it blank.

## Section Map

The notebook is organized into cell groups that mirror the chapter's sections:

| Cell Group | Chapter Section | Concept Demonstrated |
|---|---|---|
| **1** | Setup | Environment setup, API key auto-detection, mode banner |
| **2** | §2.1 — Framework Landscape | Comparison of LangChain, LangGraph, LlamaIndex, AutoGPT, CrewAI, AutoGen |
| **3** | §2.2 — LangChain Agent | ReAct pattern with Calculator + WebSearch tools |
| **4** | §2.2 — LangChain Memory | Buffer vs. Summary memory comparison |
| **5** | §2.3 — LangGraph Workflow | Stateful graph: research → analyze → decide → respond |
| **6** | §2.3 — LangGraph State | TypedDict schema + Mermaid diagram |
| **7** | §2.4 — Framework Selection | Selection criteria + integration patterns |
| **8** | §2.5 — Hybrid Routing | Multi-model query router (Mistral/Claude/GPT-4o) |
| **9** | §2.6 — RAG Pipeline | Simulated vector search with similarity scores |
| **10** | §2.7 — LangChain Tools | StockPriceTool abstraction pattern |
| **11** | §2.8 — Function Calling | OpenAI JSON schema + mock execution |
| **12** | §2.9 — Cloud Platforms | AWS / Azure / Google Cloud comparison |
| **13** | Summary | Chapter takeaways and next steps |

## Repository Structure

```
chapter02/
│
├── README.md                            # This file
├── .gitkeep                             # Git placeholder
├── chapter_02_agent_toolkit.ipynb       # Primary deliverable
└── mock_llm_layer.py                    # Mock infrastructure module
```

## Simulation Mode

When no API key is detected, the notebook activates **Simulation Mode**:

- `MockLLM` replaces the LLM client transparently (works identically across all providers)
- All responses are pre-authored from Chapter 2 content
- A `[SIMULATION]` prefix confirms activation at startup
- Every cell executes successfully with no external dependencies

Both modes use color-coded logging:
- **Blue** `[INFO]`: Agent initialization, step entry
- **Green** `[SUCCESS]`: Completed steps, valid returns
- **Red** `[HANDLED ERROR]`: Caught exceptions, fallback activation

## Pre-Executed Notebook Variants

Every notebook is pre-executed with outputs saved. Pick the variant that matches your setup:

| Notebook | Provider | Description |
|---|---|---|
| [ch02_agent_toolkit__RUN_NO_KEY_SIMULATION.ipynb](ch02_agent_toolkit__RUN_NO_KEY_SIMULATION.ipynb) | Simulation | No API key — MockLLM responses |
| [ch02_agent_toolkit__RUN_OPENAI_GPT4o.ipynb](ch02_agent_toolkit__RUN_OPENAI_GPT4o.ipynb) | OpenAI GPT-4o | Live LLM via `OPENAI_API_KEY` |
| [ch02_agent_toolkit__RUN_CLAUDE_Sonnet4.ipynb](ch02_agent_toolkit__RUN_CLAUDE_Sonnet4.ipynb) | Claude Sonnet 4 | Live LLM via `ANTHROPIC_API_KEY` |
| [ch02_agent_toolkit__RUN_GEMINI_Flash25.ipynb](ch02_agent_toolkit__RUN_GEMINI_Flash25.ipynb) | Gemini Flash 2.5 | Live LLM via `GOOGLE_API_KEY` |
| [ch02_agent_toolkit__RUN_LOCAL_OLLAMA_DeepSeek_V2_16B.ipynb](ch02_agent_toolkit__RUN_LOCAL_OLLAMA_DeepSeek_V2_16B.ipynb) | Local Ollama | DeepSeek V2 16B — no API key |

All variants produce equivalent output. Compare them to see how different providers handle the same agent tasks.

For local LLM setup instructions (Ollama + DeepSeek on Windows, macOS, and Linux), see **[LOCAL_LLM_SETUP.md](LOCAL_LLM_SETUP.md)**.

For a detailed comparison of how each provider performs on this chapter's tasks — including Bloom's taxonomy ratings, strengths/weaknesses, and per-dimension scores — see **[LLM_COMPARISON.md](LLM_COMPARISON.md)**.

## Requirements

- **Python:** 3.10+ (recommended: 3.11 or 3.12)
- **Local simulation:** Install Jupyter Notebook and SymPy. Start Jupyter from `chapter02` so the notebook can import the included `mock_llm_layer.py` module.
- **API Key:** Optional — any of OpenAI, Anthropic, Google, or local Ollama. Simulation Mode works without any.

## License

This code is provided as educational companion material for *30 Agents Every AI Engineer Must Build* by Imran Ahmad (Packt Publishing, 2026). See the book for full terms of use.

## Author

**Imran Ahmad** — Author of *30 Agents Every AI Engineer Must Build* (Packt Publishing, 2026)
