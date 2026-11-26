# FinMate AI – Day 1 🚀
### Building the Foundation of an AI Finance Assistant

## 📌 Overview
Day 1 focuses on building the basic AI-powered assistant for **FinMate AI**, a project designed to help small retail businesses understand and manage their finances.

The initial version uses a Large Language Model (LLM) to answer finance-related questions through a simple chat function.

## 🛠️ Technologies Used
- **Python** – Programming language
- **Google Colab** – Development environment
- **LangChain** – LLM integration
- **Groq API** – AI model access
- **ChatGroq** – Connecting LangChain with Groq models
- **Prompt Guard** – Exploring prompt injection detection

## ✨ What I Built
- Integrated Groq API with LangChain.
- Initialized the LLM using `ChatGroq`.
- Created a custom system prompt for FinMate AI.
- Developed an `ask()` function to interact with the AI.
- Tested the assistant with finance-related questions.
- Explored Prompt Guard for detecting potentially malicious prompts.

## 🧠 Key Concepts Learned
1. Large Language Models (LLMs)
2. System Prompts
3. LLM initialization using ChatGroq
4. `llm.invoke()` for sending messages to an AI model
5. Prompt Injection and Prompt Guard

## 💬 Sample Interaction

**User:** Can you tell me my monthly profit?

**FinMate AI:** Please provide your income and expense records so I can help calculate your monthly profit.

## 📂 Project Structure

```text
FinMate-AI/
│
└── Day-1/
    ├── FinMate_AI_Day1.ipynb
    └── README.md
```

## 🚧 Current Limitations
- No database integration yet.
- Cannot store actual business transactions.
- Cannot calculate real profit without transaction records.
- Prompt Guard has been explored separately and is not yet integrated into the assistant.

## 🎯 Next Steps
Gradually extend FinMate AI with transaction understanding, income and expense tracking, and financial calculations.

---

**Learning in public | Building step by step | Dream. Learn. Build. Repeat.**
