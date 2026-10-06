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

This project develops a **Smart Finance Tracker** — a centralized, user-friendly application designed to help multi-account users track all their expenses and income in one unified source of truth. The tracker simplifies financial management by consolidating fragmented banking data across multiple accounts and providing intelligent insights through AI-powered support.

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
- ✅ **AI-Enhanced Support** — Helpful insights to explain spending patterns and financial summaries

---

## Scope & Deliverables

### What's Included
1. **User-Friendly Interface** — Simple input form for adding expenses with error correction
2. **Transaction Management** — Add, view, delete, categorize, and tag transactions
3. **Automated Processing** — Real-time categorization by date, type, and account
4. **Transaction List Output** — Clean table view of all recorded transactions
5. **Dashboard Generation** — Monthly and annual visual dashboards with charts and tables
6. **AI Support** — Helpful finance guidance and transparent AI-assisted development documentation
7. **Currency Label Customization** — User-defined currency label such as AUD, $, IDR, Rp, etc.

### Out of Scope
- Automated banking app integration (manual input only)
- Credit card support (debit transactions only)
- Live currency exchange rate conversion or real-time market data
- Budget goals, savings calculators, or recommendation rules
- Database normalization (accepts redundancy for simplicity)
- Multiple user support or shared expenses
- Duplicate transaction prevention

---

## System Architecture: 7 Core Jobs

The entire 42-step process is distilled into **7 main jobs**:

| Job | Function | Responsibility |
|-----|----------|-----------------|
| **Job 1** | **User Profile** | Store and manage user name and currency label preference |
| **Job 2** | **Add Transaction** | Create and validate income/expense entries with unique IDs |
| **Job 3** | **View & Delete** | Display transactions in table format and delete by ID |
| **Job 4** | **Analyse Transactions** | Calculate totals, monthly/annual summaries, by category and account |
| **Job 5** | **Generate Dashboard** | Create visual charts and financial summary tables |
| **Job 6** | **AI Assistant** | Provide user-facing finance insights and explanations |
| **Gradio** | **UI Integration** | Build interactive web interface connecting all 6 jobs into one cohesive app |

### Dashboard Visualizations
- **Clustered Column Charts** — Monthly and annual income vs expense by account
- **Doughnut Charts** — Expense and income breakdown by category with percentages
- **Summary Tables** — Financial totals and account-by-account breakdowns
- **Transaction List** — Clean table view of all recorded transactions

### Data Flow
```
User Input → Job 1-2 → Job 3 (Display) → Job 4 (Calculate) → Job 5 (Visualize) → Job 6 (AI) → Gradio (Serve)
```

---

## Gradio Integration & UI

The app is built using **Gradio**, a Python framework for creating web-based interfaces. It provides:

- **User Profile Tab** — Set name and currency label
- **Add Transaction Tab** — Input new income/expense entries
- **View Transaction Tab** — Browse all transactions and delete by ID
- **View Report Tab** — Display monthly/annual dashboards with interactive charts and tables
- **AI Assistant** — Ask the finance assistant questions about your data

### Key Features
- Real-time validation and error handling
- Auto-completion and recall of previous inputs (categories, accounts)
- Interactive visualizations (clustered columns for trends, doughnuts for category breakdown, summary tables)
- Clean, tabular transaction list and financial summaries
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
   - Enter your name and currency label in "User Profile" tab
   - Add transactions via "Add Transaction" tab
   - View summaries and charts in "View Report" tab
   - Ask the AI assistant for insights

---

## AI Documentation

### AI Tools Used

This project incorporates AI assistance at two key stages:

#### 1. **Development-Time AI (ChatGPT)**
- **Purpose:** Translate design, pseudocode, and system planning into executable Python
- **Process:** The 42-step design and logic were converted into working Python code for each main job and feature
- **Transparency:** I documented intentionally which outputs I accepted, rejected, and modified, rather than blindly copying AI-generated output
- **Importance:** This reflects my actual AI use in the project, where ChatGPT was used as a coding assistant and planning translator

#### 2. **Runtime AI (Google Gemini)**
- **Purpose:** Provide friendly, beginner-friendly financial insights during app usage
- **Integration:** Users can ask the AI assistant questions about their transaction list and dashboard data
- **Personality:** Casual tone, beginner-friendly explanations, and friendly greetings/closings
- **Capabilities:** Analyzes spending patterns, explains trends, and provides context-aware insights based on actual user data

### AI Highlights
- Clear separation between **development-time AI** (ChatGPT for code generation and translation) and **runtime AI** (Gemini as the user-facing finance assistant)
- Transparent documentation of AI-assisted development decisions
- AI supported the design-to-code workflow, while still requiring human evaluation and refinement
- Gemini remains a lightweight assistant for interpreting financial data after the app was built

### AI Responsibility and Limits
- AI was used to accelerate planning and implementation, but the final logic was reviewed and adapted by the developer
- Gemini advice is presented as general guidance rather than professional financial advice
- The runtime assistant only responds based on the data supplied by the app and does not invent figures

---

## Additional Notes

- **Assessment 3 Requirement:** This app is designed with complete explainability — every line of code in Jobs 1-6 can be fully explained as part of the assessment
- **Simplification Principle:** Complexity was intentionally reduced to ensure sustainability and user adoption
- **System Testing:** All 7 jobs have been tested and integrated through Gradio
- **AI Transparency:** AI-assisted development and runtime AI are clearly documented in the project narrative
- **Open for Feedback:** This is an MVP (Minimum Viable Product) that can be extended based on user needs

---

**Happy tracking! 🎉**
