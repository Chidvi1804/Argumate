Argumate – AI Legal Case Agent

Argumate is an AI-powered autonomous legal analysis system designed to predict outcomes of European Court of Human Rights (ECHR) cases.
It integrates agentic reasoning, precedent retrieval, counter-argument generation, and continuous learning to function as an intelligent legal case assistant.

📘 Dataset

This project uses the ECHR (European Court of Human Rights) NAACL 2021 Dataset, publicly available on Kaggle.

Dataset Source
You must download the dataset manually:

🔗 https://www.kaggle.com/datasets/mathurinache/ecthrnaacl2021

Dataset Files Required
Place these files inside the /data directory:
-train.jsonl
-dev.jsonl
-test.jsonl

These contain:
-Case text
-Conclusions
-Violated articles
-Metadata fields used by Argumate


Note: These files cannot be uploaded to GitHub due to Kaggle licensing.

✨ Features
1. Outcome Prediction

Argumate predicts:
-Violated articles
-Whether each article was breached
-Case-level decision outcomes

2. Precedent Retrieval

-Retrieves similar ECHR cases from training embeddings to support:
-Evidence
-Legal grounding
-Past judgments
-Case similarity reasoning

3. Legal Reasoning Engine
Generates:
-Detailed structured reasoning
-Step-by-step justification
-Precedent citations
-Interpretation of case facts

4. Confidence Scoring

Each prediction includes:

-Confidence score
-Reliability estimate
-Error likelihood analysis

5. Reasoning Quality Evaluation

Scores the reasoning based on:
-Logical consistency
-Precedent alignment
-Argument soundness
-Completeness

6. Counter-Argument Generator

Automatically generates:

-Defense-side arguments
-Alternative case interpretations
-Challenges to predicted outcomes
-Weakness analysis

🧠 Agentic Workflow

Argumate uses a multi-agent architecture including:

-Goal Manager
-Context Manager
-Evaluator Module
-Guard Rails
-Persistent Memory
-Continuous Learning Loop

This enables advanced autonomous behaviour similar to a legal research agent.

🚀 Modes of Operation

🔹 Mode 1 — Manual Input Case Mode
User directly inputs legal case text.
The system outputs:

-Predicted outcome
-Violated articles
-Precedents
-Reasoning
-Counter-arguments
-Confidence
-Reasoning quality score


🔹 Mode 2 — Auto-Watcher Mode
When enabled, Argumate continuously monitors:
/new_cases/
Whenever a new .txt case file appears:
It automatically loads the file
Processes it using the agent pipeline
Saves results into:
/results/
or
/results_agentic/


📂 Project Structure
Argumate/
│
├── checkpoints/               # Model states
├── checkpoints_agentic/       # Agentic workflow memory
│
├── data/                      # Dataset directory (user must add)
│   ├── train.jsonl
│   ├── dev.jsonl
│   ├── test.jsonl
│
├── Endpoints/                 # API/helper modules
│
├── new_cases/                 # Folder watched in auto-watcher mode
├── results/                   # Manual mode outputs
├── results_agentic/           # Auto-watcher outputs
│
├── Argumate_final.ipynb       # Full implementation
└── README.md


⚙️ Technologies Used:

Python
Sentence Transformers
NumPy / Pandas
Agentic workflow modules
Embedding-based retrieval
Google Colab environment
