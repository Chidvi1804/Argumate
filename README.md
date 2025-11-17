Argumate – AI Legal Case Agent

Argumate is an AI-powered autonomous legal analysis system designed to predict outcomes of European Court of Human Rights (ECHR) cases.
It integrates agentic reasoning, precedent retrieval, counter-argument generation, and continuous learning to function as an intelligent legal case assistant.

📘 Dataset

This project uses the ECHR (European Court of Human Rights) NAACL 2021 Dataset, publicly available on Kaggle.

Dataset Source

You must download the dataset from the original provider:

🔗 Kaggle ECHR Dataset
https://www.kaggle.com/datasets/mathurinache/ecthrnaacl2021

Files Used in This Project

The following files from the dataset must be placed inside the /data folder:

train.jsonl

dev.jsonl

test.jsonl

These contain:

Legal case facts

Full judgment text

Violated articles

Conclusions

Metadata fields for training the Argumate system

Due to Kaggle licensing, these dataset files cannot be uploaded directly to GitHub.
Users must download them manually from the dataset link.

✨ Key Features
1. Outcome Prediction

Argumate predicts:

Violated Articles

Whether Article(s) were breached

Case-level labels from ECHR dataset

2. Precedent Retrieval

For each case, the system fetches supporting precedents from:

Training set embeddings

Similar fact-based judgments

Case-law reasoning traces

3. Legal Reasoning Engine

Argumate generates:

Structured reasoning explanation

Point-wise justification

Cited precedent support

Alignment with legal arguments

4. Confidence Scoring

For each prediction, the system outputs:

Confidence score (0–1)

Reliability analysis

Interpretation of uncertainty

5. Reasoning Quality Evaluation

A built-in evaluator scores:

Logical coherence

Precedent alignment

Legal soundness

Completeness

6. Counter-Argument Generator

Argumate automatically constructs opposing arguments, including:

Defense-side reasoning

Alternative interpretations

Weaknesses in predicted decision

Rebuttals

🧠 Agentic Workflow

Argumate uses an agent-based architecture consisting of:

Goal Manager

Context Manager

Evaluator Module

Guard Rails / Safety Checks

Persistent State Manager

Continuous Learning Loop

This allows the model to function like an intelligent legal agent rather than a simple classifier.

🚀 Modes of Operation
🔹 Mode 1 — Manual Input Case Mode

User inputs any legal case text directly.
The system then outputs:

Predicted outcome

Violated articles

Precedents

Reasoning

Counter-arguments

Confidence

Reasoning quality score

🔹 Mode 2 — Auto-Watcher Mode

When enabled, Argumate continuously monitors:

/new_cases/


Whenever a new .txt case file appears:

It automatically loads it

Processes with the entire agent pipeline

Generates results

Stores outputs in:

/results/
or
/results_agentic/


This allows Argumate to function like a live legal assistant on new incoming cases.

📂 Project Structure
Argumate/
│
├── checkpoints/               # Training embeddings & state
├── checkpoints_agentic/       # Agentic pipeline checkpoints
│
├── data/                      # Dataset (user must add)
│    ├── train.jsonl
│    ├── dev.jsonl
│    ├── test.jsonl
│
├── Endpoints/                 # API utility functions
│
├── new_cases/                 # Folder watched in auto-watcher mode
├── results/                   # Outputs from normal pipeline
├── results_agentic/           # Outputs from agentic pipeline
│
├── Argumate_final.ipynb       # Full implementation notebook
└── README.md

⚙️ Technologies Used

Python

Sentence Transformers

Pandas / NumPy

Agentic reasoning modules

Google Colab runtime

Embedding-based precedent retrieval

Persistent memory for continuing sessions

📜 Note on Dataset Availability

Due to licensing restrictions, dataset files (train/dev/test) are not included in the GitHub repository.

Users must manually download them from:

https://www.kaggle.com/datasets/mathurinache/ecthrnaacl2021

After downloading, place them in:

/data/
