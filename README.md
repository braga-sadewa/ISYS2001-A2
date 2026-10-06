# Smart Finance Tracker - Project Overview

## Table of Contents
- [Project Purpose](#project-purpose)
- [User Pain Points & Solutions](#user-pain-points--solutions)
- [Scope & Deliverables](#scope--deliverables)
- [System Architecture: 7 Core Jobs](#system-architecture-7-core-jobs)
- [Gradio Integration & UI](#gradio-integration--ui)
- [Sample Input & Output](#sample-input--output)
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

## Sample Input & Output

This section demonstrates the core behavior of the app in a simple, realistic example. It shows how a user can add transactions, view their financial list, and receive AI-supported insights from the dashboard.

### Example Input

#### User Profile
```
Name: Sarah
Currency: AUD
```

#### Transaction Entries
```
Date: 2024-10-01
Type: Expense
Amount: 45.50
Category: Groceries
Account: Commonwealth Bank

Date: 2024-10-02
Type: Income
Amount: 1500.00
Category: Salary
Account: Commonwealth Bank

Date: 2024-10-03
Type: Expense
Amount: 120.00
Category: Entertainment
Account: Westpac
```

### Example Output

#### Transaction Table
```
| ID | Date       | Type    | Amount   | Category      | Account            |
|----|------------|---------|----------|---------------|--------------------|
| 1  | 2024-10-01 | Expense | -45.50   | Groceries     | Commonwealth Bank  |
| 2  | 2024-10-02 | Income  | 1500.00  | Salary        | Commonwealth Bank  |
| 3  | 2024-10-03 | Expense | -120.00  | Entertainment | Westpac            |
```

#### Dashboard Summary
```
Total Income (October 2024): AUD 1500.00
Total Expenses (October 2024): AUD 165.50
Net Cash Flow: AUD 1334.50

Expenses by Category:
- Groceries: AUD 45.50 (27.5%)
- Entertainment: AUD 120.00 (72.5%)

Income by Account:
- Commonwealth Bank: AUD 1500.00

Expense by Account:
- Commonwealth Bank: AUD 45.50
- Westpac: AUD 120.00
```

#### AI Assistant Example
```
User: "How much did I spend on entertainment?"

AI: "Hi! Based on your recent data, you spent AUD 120.00 on entertainment this month. This makes up 72.5% of your total spending, so it is currently the largest expense category. If you want, I can also suggest ways to reduce this category next month. Take care!"
```

This demonstrates how the project works as a user-friendly personal finance assistant: data is entered, categorised, summarised, and then explained in a natural language format.

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

#### 2. **Runtime AI (Google Gemini 3.5 Flash)**

**Purpose:** Provide friendly, beginner-friendly financial insights during app usage.

**How it Works in the App:**
- The user enters transactions into the Gradio interface
- The app calculates totals, category breakdowns, and account summaries
- This structured financial data is passed to the Gemini model through the AI assistant feature
- Gemini interprets the numbers and produces a natural-language explanation in a simple, conversational tone

**Why Gemini Was Chosen:**
- It is lightweight and fast for quick user interaction
- It responds naturally without rigid financial jargon
- It helps everyday users understand their spending patterns more easily
- It works well in a personal finance context where users want simple explanations, not technical or overly formal advice

**Personality & Communication Style:**
- **Casual & Approachable:** Uses friendly greetings and a warm tone
- **Beginner-Friendly:** Avoids jargon and explains results in plain language
- **Context-Aware:** Uses real financial data from the user's entries
- **Helpful & Practical:** Can answer questions like spending trends, category totals, balance summaries, and unusual changes

**Example Queries Gemini Can Answer:**
- "How much did I spend on food this month?"
- "What is my biggest expense category?"
- "Am I spending more than I earn?"
- "Can you explain my recent spending trend?"

**What Gemini Does Not Do:**
- It does not invent missing financial data
- It does not claim to be a qualified financial advisor
- It only responds based on the information the app provides

**Safety & Reliability:**
- The app passes only calculated, visible financial data to the AI assistant
- Errors are handled gracefully if Gemini is unavailable or the API request fails
- AI advice is framed as general guidance rather than professional financial advice

**Model Details:**
- **Model:** Google Gemini 3.5 Flash
- **Library:** `google-genai`
- **Purpose:** Fast, responsive financial explanation generation in the app interface

### AI Responsibility and Limits
- AI was used to accelerate planning and implementation, but the final logic was reviewed and adapted by the developer
- Development-time AI (ChatGPT) supported the design-to-code workflow and code translation
- Runtime AI (Gemini) enhances user experience through explanation and insight generation
- The AI is a support tool, not a substitute for professional financial advice

---

## Additional Notes

- **Assessment 3 Requirement:** This app is designed with complete explainability — every line of code in Jobs 1-6 can be fully explained as part of the assessment
- **Simplification Principle:** Complexity was intentionally reduced to ensure sustainability and user adoption
- **System Testing:** All 7 jobs have been tested and integrated through Gradio
- **AI Transparency:** AI-assisted development and runtime AI are clearly documented in the project narrative
- **Open for Feedback:** This is an MVP (Minimum Viable Product) that can be extended based on user needs

---

**Happy tracking! 🎉**
