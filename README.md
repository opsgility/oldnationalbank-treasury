# Copilot for Treasury — ONB Hands-On Exercises

Hands-on materials for the *Microsoft 365 Copilot for Treasury* session (Old National Bank). The session is anchored in **Excel** (cash position and liquidity forecasting), with **Outlook** for summarizing and drafting, and a single **PowerPoint** exercise to turn the numbers into an update deck.

## Start here
- [Pre-Work — Set up and upload your practice materials](prework/00-PreWork-Setup-and-Upload.md) — **complete before the session.**

## Exercises
1. [Copilot-Ready Data & Daily Cash Position](exercises/01-Copilot-Ready-Data-and-Cash-Position.md) — *Excel*
2. [Cash Reconciliation — Bank vs. Ledger](exercises/02-Cash-Reconciliation-Bank-vs-Ledger.md) — *Excel*
3. [Rolling Cash-Flow Forecast & Liquidity Analysis](exercises/03-Cash-Flow-Forecast-and-Liquidity-Analysis.md) — *Excel*
4. [Inbox Summary to Treasury Briefing & Draft as Delegate](exercises/04-Inbox-Summary-and-Draft.md) — *Outlook*
5. [Cash & Liquidity Update Deck](exercises/05-Cash-and-Liquidity-Update-Deck.md) — *PowerPoint*

## Sample materials (`assets/`)
- `Cash-Position-Raw.xlsx` — a deliberately messy daily position pull (merged cells, subtotals, mixed formats) for the data-prep lesson
- `Daily-Cash-Position.xlsx` — multiple bank "exports" as tabs (`JPMorgan`, `BofA`, `Wells-Fargo`) plus an `Account-Master` and `FX-Rates` tab, for consolidation
- `Cash-Reconciliation.xlsx` — bank-reported balances vs. internal ledger, with seeded timing and one-sided variances, plus a `Legacy` formula tab
- `Cash-Flow-Forecast.xlsx` — a 13-week rolling forecast with actuals on the first five weeks and an `Assumptions` tab (opening cash, policy minimum, revolver)
- `Practice-Inbox-Pack.md` — four synthetic Treasury email threads you email to yourself in pre-work

## How to use
Each exercise is self-contained: objective, prerequisites, step-by-step prompts, a deliverable, and a verification checklist. All prompts are copy-paste ready. Work in **Excel for the web** and **Outlook on the web** with the sample materials saved in OneDrive.

## Ground rules
Copilot accelerates the mechanics; the treasury professional decides. **There is no Track Changes in Excel — work on a copy** and rely on OneDrive version history. Copilot only sees the **open workbook** (consolidate exports as tabs first) and the **mail you can open**. Nothing sends, schedules, or moves money until a person clicks the button. Verify every balance, total, rate, date, and flagged variance before it goes into a position report, a forecast, a covenant certificate, or an email. Use only synthetic sample data inside ONB's Microsoft 365 tenant — never live balances, account numbers, or counterparty information.
