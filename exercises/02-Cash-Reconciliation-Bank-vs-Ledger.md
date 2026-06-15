# Exercise 2 — Cash Reconciliation (Bank vs. Ledger)

- **App:** Excel for the web
- **Workflow:** Reconcile bank-reported balances against the internal cash ledger; flag and explain every difference
- **Workbook:** **Cash-Reconciliation.xlsx** (tabs: `Bank`, `Ledger`, `Legacy`)
- **Estimated time:** 25 minutes
- **Difficulty:** Core — the daily control

---

## Objective

Build a complete two-way cash reconciliation with Copilot: match columns, difference and status columns, exception highlighting, and a reviewer-ready summary — the work of an hour of XLOOKUP wrangling, in minutes, with you verifying every step. The seeded data contains a real-world mix: a timing difference, a one-sided item on each side, and a small rounding variance.

## Before you start

- [ ] Workbook open in **Excel for the web**, AutoSave on, **working on a copy**.
- [ ] Both tabs are tables: `Bank` (bank-reported closing balances) and `Ledger` (internal cash ledger), same date.
- [ ] Note the seeded issues: one account is missing from the Ledger (unposted at the bank), one is missing from the Bank (file not yet delivered), the Money Market Sweep shows a timing difference, and one account has a small rounding variance.

## What Copilot is doing here

Copilot generates real `XLOOKUP`/`IF` formulas into new columns and explains them. **Key constraint:** Copilot only sees the *open workbook* — that's why both balances live as tabs in one file. (On desktop Excel, Copilot can import a table from another workbook via a refreshable Power Query connection; in the web you consolidate first. Your instructor may demo this.)

---

## Steps

### Step 1 — Record control totals (manual, 1 minute)
Before Copilot touches anything, note: Bank row count and total Balance; Ledger row count and total Balance. (Select the balance columns — the status bar shows count and sum.) These are your tie-out anchors.

### Step 2 — Build the match column (**Allow editing**)
```text
On the Bank sheet, add a column called "Ledger Balance" that uses XLOOKUP to find each Account ID in the Ledger table and return its Ledger Closing Balance. If the account is not found, return "NOT IN LEDGER". Explain the formula you used.
```
Read the explanation — that's your review of the formula.

### Step 3 — Difference and status columns
```text
Add two columns to the Bank table: "Difference" = Bank Closing Balance minus Ledger Balance (blank if the account is missing from the ledger), and "Recon Status" with the value "Matched" if the difference is zero, "Variance" if nonzero, and "Missing from Ledger" if not found.
```

### Step 4 — Reverse direction
```text
Now check the other direction: on the Ledger sheet, add a column "In Bank?" that flags any Account ID that does not appear in the Bank table. Then tell me how many accounts are missing from each side.
```
**Why this matters:** one-direction recons miss the items that exist only on the other side. Always reconcile both ways.

### Step 5 — Highlight and isolate exceptions
```text
In the Bank table, highlight rows where Recon Status is not "Matched" in light red, and apply a filter to show only those rows. Then summarize the exceptions: count and total dollar amount by Recon Status.
```

### Step 6 — Explain an inherited formula (Chat only — bonus habit)
Go to the `Legacy` tab, click any cell in the "Legacy Variance Flag" column, and ask:
```text
Explain what the formula in this cell does, step by step, in plain language for someone reviewing this cash reconciliation. Note anything fragile about it, such as the hard-coded $100 threshold or how it would behave on a blank balance.
```

### Step 7 — Reviewer summary
```text
Write a short cash reconciliation summary I can send to my manager: total bank balance, total ledger balance, the net difference, the number of matched accounts, the number and dollar value of variances, and the one-sided items on each side with their Account IDs and a likely reason (timing, unposted, file not received). I will verify each figure against the sheet.
```

---

## Deliverable

The reconciled workbook (match/difference/status columns both directions, exceptions highlighted) plus the verified summary you can send to your manager.

## Verify before you rely on it

- [ ] Control totals from Step 1 still match — no rows dropped or duplicated.
- [ ] Re-perform the Money Market Sweep variance by hand: Bank balance minus Ledger balance. Does the amount match, and is "timing" a reasonable explanation?
- [ ] Confirm the one-sided items: search the opposite tab for each Account ID to prove it really is missing.
- [ ] Summary figures (Step 7) tie to the filtered counts on the sheet.

## Key takeaways

- **One workbook, multiple tabs** — consolidate before reconciling; Copilot can't see your second file.
- Always reconcile **both directions** — a timing difference and an unposted item look identical until you check each side.
- "Explain the formula you used" turns every Copilot build into a reviewable one.
- Copilot found the differences; **you** decide which are real variances and which are timing.

---

*Next: Exercise 3 — Rolling Cash-Flow Forecast & Liquidity Analysis.*
