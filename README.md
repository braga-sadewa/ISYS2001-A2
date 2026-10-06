# Smart Finance Tracker - Project Overview

## Table of Contents
- [Project Purpose](#project-purpose)
- [User Pain Points & Solutions](#user-pain-points--solutions)
- [Scope & Deliverables](#scope--deliverables)
- [System Architecture: 7 Core Jobs](#system-architecture-7-core-jobs)
- [Gradio Integration & UI](#gradio-integration--ui)
- [How to Access the App](#how-to-access-the-app)
- [AI Documentation](#ai-documentation)

---

## Project Purpose

This project develops a **Smart Finance Tracker** — a centralized, user-friendly application designed to help multi-account users track all their expenses and income in one unified source of truth. The tracker simplifies financial management by consolidating fragmented banking data across multiple accounts and providing intelligent insights through an AI-powered assistant.

**Key Philosophy:** Simplicity is the principle. This app focuses on everyday users who need straightforward, intuitive financial tracking without complexity.

---

## User Pain Points & Solutions

### Identified Pain Points
1. **Scattered Information** — Expenses tracked across multiple banking apps with no central location
2. **Inconvenient Manual Checking** — Need to check 2+ different accounts to view total balance and input transactions
3. **Manual Reporting** — Manually calculating monthly totals and generating reports using external calculators
4. **Information Overload** — Multiple apps without a single source of truth create cognitive overwhelm

### How This App Solves Them
- ✅ **Centralized Dashboard** — All expenses from multiple accounts in one place
- ✅ **Instant Account Overview** — View total balance across all accounts at a glance
- ✅ **Auto-Generated Reports** — Monthly and annual dashboards automatically calculated
- ✅ **Single Source of Truth** — One app, one unified expense record
- ✅ **AI Assistant** — Friendly finance persona provides insights and explanations (using Google Gemini)

---

## Scope & Deliverables

### What's Included
1. **User-Friendly Interface** — Simple input form for adding expenses with error correction
2. **Transaction Management** — Add, view, delete, categorize, and tag transactions
3. **Automated Processing** — Real-time categorization by date, type, and account
4. **Transaction List Output** — Clean table view of all recorded transactions
5. **Dashboard Generation** — Monthly and annual visual dashboards with charts
6. **AI Finance Assistant** — Gemini-powered persona analyzing and summarizing metrics
7. **Multi-Currency Support** — Input transactions in any currency (editable per session)

### Out of Scope
- Automated banking app integration (manual input only)
- Credit card support (debit transactions only)
- Budget goals, savings calculators, or recommendation rules
- Database normalization (accepts redundancy for simplicity)
- Multiple user support or shared expenses
- Duplicate transaction prevention

---

## System Architecture: 7 Core Jobs

The entire 42-step process is distilled into **7 main jobs**:

| Job | Function | Responsibility |
|-----|----------|-----------------|
| **Job 1** | **User Profile** | Store and manage user name and currency preference |
| **Job 2** | **Add Transaction** | Create and validate income/expense entries with unique IDs |
| **Job 3** | **View & Delete** | Display transactions in table format and delete by ID |
| **Job 4** | **Analyse Transactions** | Calculate totals, monthly/annual summaries, by category and account |
| **Job 5** | **Generate Dashboard** | Create visual charts (bar, line, pie) and financial summary tables |
| **Job 6** | **AI Assistant** | Integrate Google Gemini for friendly financial insights and explanations |
| **Gradio** | **UI Integration** | Build interactive web interface connecting all 6 jobs into one cohesive app |

### Data Flow
```
User Input → Job 1-2 → Job 3 (Display) → Job 4 (Calculate) → Job 5 (Visualize) → Job 6 (AI) → Gradio (Serve)
```

---

## Gradio Integration & UI

The app is built using **Gradio**, a Python framework for creating web-based interfaces. It provides:

- **User Profile Tab** — Set name and currency
- **Add Transaction Tab** — Input new income/expense entries
- **View Transaction Tab** — Browse all transactions and delete by ID
- **View Report Tab** — Display monthly/annual dashboards with interactive charts
- **AI Assistant** — Ask the finance assistant questions about your data

### Key Features
- Real-time validation and error handling
- Auto-completion and recall of previous inputs (categories, accounts)
- Interactive charts (bar charts for monthly, line charts for annual trends, pie charts for categories)
- Clean, tabular transaction list
- Live Gradio link generated when running the notebook

---

## How to Access the App

### Step-by-Step Instructions

1. **Open the Notebook** → Access `22347705_ISYS2001_A2_CODE.ipynb` in Google Colab or Jupyter Notebook

2. **Install Dependencies** → Run all code cells in order (pip installs included)

3. **Run All Cells** → Execute the entire notebook from top to bottom:
   - Job 1-6 cells (foundational logic)
   - Gradio cell (UI builder)

4. **Get the Gradio Link** → Once executed, a public Gradio URL will be printed in the output, e.g.:
   ```
   Running on public URL: https://[random-id].gradio.live
   ```

5. **Access the App** → Click the link or copy it into your browser

6. **Start Using** → 
   - Enter your name and currency in "User Profile" tab
   - Add transactions via "Add Transaction" tab
   - View summaries and charts in "View Report" tab
   - Ask the AI assistant for insights

---

## AI Documentation

### How AI Was Used

**Model:** Google Gemini 3.5 Flash via `google-genai` library

**Purpose:** Provide friendly, beginner-friendly financial insights without rigid professional jargon

### AI Assistant Features

**Personality & Tone:**
- Casual and friendly (not a rigid financial advisor tone)
- Beginner-friendly explanations for everyday users
- Concise but informative responses
- Warm greetings ("Hi!") and closing phrases ("Take care!")

**Capabilities:**
- Analyzes transaction lists and dashboards
- Answers user questions about expenses, income, trends
- Provides context-aware insights based on user's actual financial data
- Handles irrelevant questions gracefully (redirects to finance context)

**Integration Points:**
- **View Transaction** → Ask AI about your transaction list
- **View Report** → Ask AI about monthly or annual dashboard trends

**Data Passed to AI:**
- Total income, expense, and net cash flow
- Monthly and annual summaries
- Expense breakdown by category with percentages
- Income/expense by account

**Safety & Limitations:**
- Disclaims that advice is generic, not professional financial guidance
- Only uses data provided (no invented figures)
- Gracefully handles API errors with fallback messages

---

## Additional Notes

- **Assessment 3 Requirement:** This app is designed with complete explainability — every line of code in Jobs 1-6 can be fully explained as part of the assessment
- **Simplification Principle:** Complexity was intentionally reduced to ensure sustainability and user adoption
- **System Testing:** All 7 jobs have been tested and integrated through Gradio
- **Open for Feedback:** This is an MVP (Minimum Viable Product) that can be extended based on user needs

---

**Happy tracking! 🎉**
