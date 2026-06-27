# 🛡️ FinGuard-MAS: Autonomous Enterprise Financial Auditing

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity)

> **An enterprise-grade, supervised multi-agent system designed to autonomously analyze massive SEC filings and financial transcripts without context bloat.**

FinGuard-MAS is a production-first architecture that tackles the two biggest bottlenecks in modern Multi-Agent Systems (MAS): systemic inefficiencies (token bloat) and unpredictable failure loops[cite: 1]. 

Inspired by the lightweight SUPERVISORAGENT framework, this project introduces a real-time, non-intrusive meta-supervisor that intercepts agent-tool interactions[cite: 1]. It proactively corrects execution errors, purifies excessively long HTML context windows, and breaks inefficient action loops to deliver robust financial data extraction at scale[cite: 1].

---

## ⚠️ The Problem: MAS in Financial Auditing

When deploying standard LLM agents to analyze complex financial documents (like 10-K or 10-Q SEC filings), the systems often degrade rapidly:
*   **Context Flooding:** Agents scrape verbose web pages or raw HTML tables, flooding their context windows and obscuring critical financial metrics[cite: 1].
*   **Inefficient Loops:** Agents adopt sub-optimal strategies, getting trapped in repetitive actions (e.g., repeatedly clicking "page down" instead of using a direct search query)[cite: 1].
*   **Error Propagation:** A single hallucinated variable or broken Python script can poison the reasoning of all downstream quantitative agents[cite: 1].

## 💡 The Solution: Runtime Adaptive Supervision

FinGuard-MAS operates on a **Supervised Multi-Agent System (SMAS)** paradigm[cite: 1]. It utilizes a lightweight, LLM-free adaptive filter that acts as a tripwire[cite: 1]. The expensive supervisor LLM is only triggered at critical junctures to execute one of three strategies[cite: 1]:

1.  **Adaptive Observation Purification:** Refines excessively long or noisy tool outputs (like raw SEC HTML) to improve the signal-to-noise ratio[cite: 1].
2.  **Guidance for Inefficiency:** Provides pragmatic, course-correcting hints when an agent enters a sub-optimal loop[cite: 1].
3.  **Proactive Error Correction:** Diagnoses the root cause of explicit tool or code execution errors and provides a direct fix[cite: 1].

This intervention architecture has been shown to reduce token consumption by an average of 29.68% on complex benchmarks without compromising task success rates[cite: 1].

---

## ⚙️ System Architecture

The core of FinGuard-MAS consists of a base agent swarm and the overriding supervisor middleware.

### Base Agents
*   **📡 Collector Agent:** Navigates financial databases, scraping massive SEC filings and earnings transcripts.
*   **🧮 Quantitative Agent:** Executes local Python code to calculate complex compliance metrics (e.g., Debt-to-Equity, Altman Z-score).
*   **📝 Reporter Agent:** Synthesizes verified data into a unified markdown compliance audit.

### Workflow Visualization

```text
[ Financial Query ] 
       │
       ▼
[ Base Agent Swarm ] ──(Action/Tool Call)──┐
       ▲                                   │
       │                                   ▼
       │                      [ LLM-Free Heuristic Filter ]
       │                                   │
       │     (Trigger: Excessive Length, Error, or Loop Detected)
       │                                   │
[ Corrected Context/Hint ]                 ▼
       └─────────────── [ Meta-SUPERVISOR AGENT Intervention ]

```

---

## 🚀 Getting Started

### Prerequisites

* Python 3.10+
* API keys for your chosen LLM providers (e.g., OpenAI, Anthropic, or local deployment via Ollama).

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/NadeemAhmad3/supervised-audit-agents.git
cd finguard-mas

```


2. **Set up a virtual environment:**
```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

```


3. **Install dependencies:**
```bash
pip install -r requirements.txt

```


4. **Environment Variables:**
Create a `.env` file in the root directory and add your keys:
```env
OPENAI_API_KEY=your_api_key_here
FINANCIAL_DATA_API_KEY=your_api_key_here

```



### Quick Start

Run a basic financial audit extraction with the supervisor enabled:

```bash
python main.py --target "Tesla Inc. 10-K 2023" --extract "Segment Revenue and Risk Factors" --enable-supervisor

```

---

## 📊 Performance & Benchmarks

FinGuard-MAS prioritizes scalable, enterprise-grade systems over beginner-level implementations. By tracking token usage via the integrated telemetry, users can visualize the direct economic impact of the supervisor.

*(Note: Add your custom telemetry graphs or W&B dashboard screenshots here once you run your initial tests).*

---

## 📬 Connect with the Author

**Nadeem Ahmad**

*Machine Learning Engineer & Full-Stack AI Developer*

Dedicated to building scalable, product-first Generative AI architectures, multi-agent systems, and automated workflows.

* **Email:** [engrnadeem26@gmail.com](mailto:engrnadeem26@gmail.com)
* **LinkedIn:** [nadeem-ahmad3](https://www.linkedin.com/in/nadeem-ahmad3/)

---

*If you find this project helpful for your enterprise AI workflows, please consider giving it a ⭐ on GitHub!*

```

```
