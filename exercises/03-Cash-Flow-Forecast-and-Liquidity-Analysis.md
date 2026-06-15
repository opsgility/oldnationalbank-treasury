# Exercise 3 — Rolling Cash-Flow Forecast & Liquidity Analysis

- **App:** Excel for the web
- **Workflow:** Compare forecast vs. actual, project the cash runway, and stress-test liquidity
- **Workbook:** **Cash-Flow-Forecast.xlsx** (tabs: `Forecast`, `Assumptions`)
- **Estimated time:** 30 minutes
- **Difficulty:** Core — the headline analysis

---

## Objective

Turn a 13-week rolling forecast into decision-ready liquidity analysis: variance of forecast vs. actual, a projected cash runway against the opening position, the weeks that breach the operating buffer, and a "what-if" stress scenario — with Copilot building the formulas, pivots, and a chart, and you owning the judgment.

## Before you start

- [ ] Workbook open in **Excel for the web**, AutoSave on, **working on a copy**.
- [ ] `Forecast` is a table: Week Ending, Week #, Category, Flow Type (Inflow/Outflow), Forecast, Actual. The first **five** weeks have actuals; later weeks are forecast-only.
- [ ] `Assumptions` holds the opening cash position, the $8M policy minimum, the $12M operating buffer, and the $25M revolver.

## What Copilot is doing here

Copilot writes variance formulas, builds PivotTables and charts by prompt, and answers shaping questions about the data. **Boundary:** Copilot models the numbers and surfaces the weeks that look tight — **you** decide whether to pre-fund, draw the revolver, or ride it out.

---

## Steps

### Step 1 — Forecast accuracy on the actual weeks (**Allow editing**)
```text
For the weeks that have an Actual value, add a column "Variance" = Actual minus Forecast and a column "Variance %" = Variance divided by Forecast, formatted as a percentage. Leave both blank where there is no Actual. Then tell me the three categories with the largest average forecast error and whether we tend to over- or under-forecast each.
```

### Step 2 — Net weekly cash flow
```text
Create a PivotTable on a new sheet showing total Forecast and total Actual by Week Ending, split by Flow Type (Inflow vs Outflow). Add a row that computes Net Cash Flow per week (inflows minus outflows). Use Actual where it exists and Forecast otherwise.
```

### Step 3 — Project the cash runway
```text
Using the opening cash position from the Assumptions sheet, build a weekly projected closing cash balance: opening cash plus the cumulative net cash flow week by week (Actual where available, Forecast after). Put it on a new sheet called Runway with columns Week Ending, Net Cash Flow, Projected Closing Cash.
```

### Step 4 — Flag the buffer and policy breaches
```text
On the Runway sheet, compare Projected Closing Cash to the $12,000,000 operating buffer and the $8,000,000 policy minimum from the Assumptions sheet. Add a Status column: "OK" at or above the buffer, "Below buffer" between the minimum and the buffer, and "BELOW POLICY MINIMUM" under the minimum. Highlight Below-buffer weeks yellow and below-minimum weeks red. Tell me the first week we drop below the buffer and the lowest point in the 13 weeks.
```

### Step 5 — Chart the runway
```text
Create a line chart of Projected Closing Cash by Week Ending on the Runway sheet, with horizontal reference lines (or marker series) at the $12M buffer and the $8M policy minimum. Title it "13-Week Liquidity Runway".
```

### Step 6 — What-if stress scenario (ideation)
```text
Act as a treasury analyst. Model a downside scenario on a new sheet: customer collections come in 15% below forecast for the next 4 weeks and one $5,000,000 investment maturity slips by 2 weeks. Recompute the projected closing cash and tell me whether and when we would breach the $8M policy minimum, and how much revolver draw would keep us at or above the $12M buffer. Show your assumptions clearly — these are scenario inputs, not a decision.
```

### Step 7 — Liquidity narrative for the ALCO update
```text
Draft a short liquidity commentary I can put in the ALCO update: current opening position, projected low point and which week, the main drivers of the dip, forecast accuracy on recent weeks, and the recommended action with its trade-off (ride it out vs. draw the revolver). Keep it to one paragraph plus three bullets. I will verify every number before it goes in the deck.
```

---

## Deliverable

A forecast workbook with variance analysis, a projected liquidity runway with buffer/policy flags and a chart, a documented downside scenario, and a verified one-paragraph liquidity commentary.

## Verify before you rely on it

- [ ] Re-add one week's inflows and outflows by hand and confirm the Net Cash Flow figure.
- [ ] Confirm the runway uses **Actual** for the first five weeks and **Forecast** afterward — not one or the other throughout.
- [ ] The low point and the breach week match what the chart shows.
- [ ] In the stress scenario, confirm the inputs Copilot used are exactly the ones you specified (15%, 4 weeks, $5M, 2-week slip).

## Key takeaways

- The structure you ask for is the analysis you get — name the columns and the thresholds explicitly.
- Copilot is excellent at **what-if** modeling, but you must check that it used **your** scenario inputs.
- The runway and the buffer/policy flags turn a forecast into a decision; the decision stays yours.

---

*Next: Exercise 4 — Inbox Summary to Treasury Briefing & Draft as Delegate.*
