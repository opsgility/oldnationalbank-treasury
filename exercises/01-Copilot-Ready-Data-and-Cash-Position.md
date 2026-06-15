# Exercise 1 — Copilot-Ready Data & Daily Cash Position

- **App:** Excel for the web
- **Workflow:** Clean a messy position pull, then consolidate bank balances into one daily cash position
- **Workbooks:** **Cash-Position-Raw.xlsx** (cleanup), then **Daily-Cash-Position.xlsx** (tabs: `Account-Master`, `JPMorgan`, `BofA`, `Wells-Fargo`, `FX-Rates`)
- **Estimated time:** 20 minutes
- **Difficulty:** Foundational — do this first

---

## Objective

Learn the #1 success factor for Copilot in Excel — data shape — then use Copilot to consolidate multiple bank "exports" into a single consolidated cash position, convert currencies, and summarize by bank and entity. This is the daily Treasury reality: many balances, many places, one number leadership wants.

## Before you start

- [ ] Both workbooks open in **Excel for the web**, AutoSave on, **working on a copy**.
- [ ] Open `Cash-Position-Raw.xlsx` — notice the merged title, the stacked two-row header, the per-bank subtotal rows mixed into the data, the blank rows, the JPMorgan account numbers that lost their leading zeros, and the CAD balances that aren't converted.

## What Copilot is doing here

Copilot reads **table-shaped** data: one header row, unique headers, no merged cells, no subtotal rows, no blank rows/columns. Most "Copilot doesn't work" complaints are data-shape problems. Then, because Copilot only sees the **open workbook**, consolidation across banks works by referencing the tabs that live in one file.

---

## Part A — Make the raw pull Copilot-ready (`Cash-Position-Raw.xlsx`)

### Step 1 — Diagnose (Chat only)
Switch the Copilot pane to **Chat only** and run:
```text
Look at the data on this sheet and tell me what would prevent Copilot from analyzing it reliably. Check for merged cells, multiple header rows, subtotal rows mixed into the data, blank rows or columns, account numbers stored as numbers that have lost leading zeros, and trailing spaces in text. List each issue and where it is.
```
Read the list — that is your cleanup plan.

### Step 2 — Restructure to a clean table (**Allow editing**)
```text
Restructure this data into a proper Excel table on a new sheet called CleanPosition: a single header row with the columns Account Name, Account Number, Entity, Currency, Opening Balance, Closing Balance. Remove the merged title, the stacked header, every per-bank subtotal row, and all blank rows. Keep the original sheet unchanged.
```

### Step 3 — Fix the account numbers and spacing
```text
In the CleanPosition table, format Account Number as text with leading zeros preserved (10 digits), and trim leading and trailing spaces from Account Name. Tell me how many cells you changed in each column.
```

> Also run **Data tab → Clean Data** for spacing, capitalization, and number-vs-text inconsistencies — it shows each suggestion for you to Apply or Ignore.

---

## Part B — Consolidate the daily position (`Daily-Cash-Position.xlsx`)

### Step 4 — Build the consolidated position (**Allow editing**)
The `JPMorgan`, `BofA`, and `Wells-Fargo` tabs each hold daily closing balances. Run:
```text
Create a new sheet called Consolidated. Combine the rows from the JPMorgan, BofA, and Wells-Fargo sheets into one table with columns Account ID, Account Name, Date, Currency, Closing Balance, and a Bank column showing which sheet each row came from. Keep only the most recent date for each account.
```

### Step 5 — Add entity and account type from the master
```text
Using the Account-Master sheet, add Entity and Account Type columns to the Consolidated table by matching on Account ID with XLOOKUP. Explain the formula you used.
```

### Step 6 — Convert CAD to USD
```text
Add a USD Equivalent column to the Consolidated table. For USD accounts it equals Closing Balance; for CAD accounts multiply Closing Balance by the CAD rate on the FX-Rates sheet. Show the rate you used and total the USD Equivalent column.
```

### Step 7 — Summarize the position for leadership
```text
On a new sheet, summarize the consolidated position: total USD-equivalent cash, a breakdown of cash by Bank, by Entity, and by Account Type, and the three largest single account balances. Present as small labeled tables. I will verify each figure against the source.
```

---

## Deliverable

A clean `CleanPosition` table, and a consolidated daily position with USD conversion plus a leadership summary of total cash by bank, entity, and account type.

## Verify before you rely on it

- [ ] Total USD-equivalent cash ties to the sum of the source tabs (select the Closing Balance columns and check the status-bar sum, converting CAD by hand for one account).
- [ ] Account numbers kept their leading zeros (JPMorgan accounts begin with `00`).
- [ ] Each account appears **once** in the consolidated table (no bank double-counted).
- [ ] The CAD account used the FX-Rates rate, not 1.0.

## Key takeaways

- **Data shape is the #1 success factor** — fix merged cells, subtotals, and blanks before judging Copilot's answer.
- Copilot only sees the **open workbook** — consolidation works because the bank exports are tabs in one file.
- `XLOOKUP` against a master table is the backbone of position reporting; always ask Copilot to **explain the formula**.

---

*Next: Exercise 2 — Cash Reconciliation (Bank vs. Ledger).*
