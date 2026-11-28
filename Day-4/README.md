# FinMate AI – Day 4: Building a Tool-Using AI Agent

## 1. Overview

Day 4 focuses on developing a tool-using AI agent for FinMate AI using LangChain and Groq.

FinMate AI is designed to help small retail business owners manage their financial transactions, track income and expenses, retrieve financial records, and calculate business profit.

In this task, we connected an AI agent to Google Sheets so it can interact with actual financial records using Python tools.

## 2. Technologies Used

- Python
- Google Colab
- LangChain
- Groq API
- Google Sheets
- Pydantic

## 3. Tasks Completed

### Step 1: Groq and Google Sheets Integration

- Installed the required LangChain and Google Sheets libraries.
- Connected the Groq LLM using the API key stored in Google Colab Secrets.
- Authenticated Google Sheets using a Google account.
- Created a spreadsheet named `FinMate Transactions`.
- Prepared columns to store financial information.

### Step 2: Transaction Data Model

Created a `Transaction` class using Pydantic to define and validate financial transaction details.

The model contains:

- Date
- Transaction Type (Income or Expense)
- Category
- Description
- Amount

Added validation to ensure transaction amounts are positive.

### Step 3: Created FinMate Tools

Created three tools using LangChain's `@tool` decorator.

**1. add_transaction()**

- Accepts income or expense details.
- Validates transaction information using the Transaction model.
- Saves confirmed transactions to Google Sheets.

**2. get_financial_summary()**

- Retrieves saved financial records.
- Calculates total income.
- Calculates total expenses.
- Calculates profit using:

  `Profit = Total Income - Total Expenses`

**3. get_recent_transactions()**

- Retrieves recent transactions from Google Sheets.
- Displays their date, amount, category, description and transaction type.

### Step 4: AI Agent Creation

Created the FinMate AI agent using LangChain's `create_agent()`.

- Connected the Groq language model.
- Registered all three financial tools.
- Added a system prompt defining FinMate's role and instructions.
- Added rules to prevent the AI from inventing financial information.
- Implemented conversation history for follow-up questions.

### Step 5: Testing FinMate AI

Tested the agent with different financial queries:

- General conversations about business finance.
- Recording business income.
- Recording business expenses.
- Confirming transactions before saving.
- Retrieving recent transactions.
- Calculating total income, expenses and profit.

## 4. FinMate AI Workflow

The following workflow explains how FinMate processes a user's request.

1. **User Input:** The business owner asks a financial question or provides a transaction.
2. **AI Understanding:** The Groq LLM understands the user's request.
3. **Tool Selection:** The LangChain agent decides which financial tool is required.
4. **Tool Execution:** The selected Python tool performs the requested operation.
5. **Google Sheets:** Transaction information is saved or retrieved from the spreadsheet.
6. **Calculation:** Python calculates financial totals and profit when required.
7. **AI Response:** FinMate presents the result in simple language.

### Workflow Diagram

```text
       User
        |
        v
   FinMate AI
        |
        v
   Groq LLM
        |
        v
  LangChain Agent
        |
        v
    Tool Selection
        |
   +----+------------------+
   |           |           |
   v           v           v
Add         Get         Get Recent
Transaction Summary    Transactions
   |           |           |
   +-----------+-----------+
               |
               v
         Google Sheets
               |
               v
        Financial Results
               |
               v
         FinMate Response
```

## 5. Example Interaction

**User:** I earned Rs 8000 from sales today.

**FinMate:** Collects the required transaction details and asks for confirmation before saving.

**User:** Yes, I confirm. Save it.

**FinMate:** Saves the confirmed income transaction to Google Sheets.

**User:** Calculate my total business profit.

**FinMate:** Uses `get_financial_summary()` to retrieve records and calculate the result.

## 6. Google Sheets Structure

FinMate stores transaction records in the following format:

| Date | Transaction Type | Category | Description | Amount |
|---|---|---|---|---:|
| 2026-11-28 | income | Sales | Daily sales | 8000 |
| 2026-11-28 | expense | Stock Purchases | Stock purchase | 2000 |

*These are example records showing the spreadsheet structure.*

## 7. Learning Outcomes

Through Day 4, I learned:

- How AI agents work with external tools.
- How to create tools using LangChain.
- How to validate structured data using Pydantic.
- How to integrate Google Sheets with Python.
- How to retrieve and store financial records.
- How to perform financial calculations using Python.
- How an AI agent selects tools based on user requests.

## 8. Day 4 Result

Successfully developed the first tool-using version of FinMate AI, capable of interacting with users, saving confirmed financial transactions, retrieving records from Google Sheets and calculating business profit.

**Project:** FinMate AI  
**Day:** 4  
**Focus:** LangChain Agents, Tools and Google Sheets Integration
