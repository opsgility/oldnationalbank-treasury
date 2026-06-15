# Exercise 5 — Cash & Liquidity Update Deck

- **App:** PowerPoint (with Copilot) — single exercise
- **Workflow:** Turn the liquidity forecast and runway into a short leadership update deck
- **File:** **Cash-Flow-Forecast.xlsx** — the same workbook from Exercise 3, now containing your `Runway` sheet, the `Forecast` sheet, and `Assumptions`
- **Estimated time:** 15 minutes
- **Difficulty:** Light — point Copilot at the workbook and let it build the deck

---

## Objective

Close the loop: have Copilot draft a clean, short cash & liquidity update deck for the CFO or ALCO **straight from your forecast workbook** — no copy-pasting numbers into the prompt. The judgment and the figures are already done in Exercise 3; this is about turning that one file into something presentable in minutes.

## Before you start

- [ ] Exercise 3 complete and saved — `Cash-Flow-Forecast.xlsx` now has the `Runway` sheet plus the verified `Forecast` and `Assumptions` sheets.
- [ ] That workbook is in your **OneDrive** (Copilot in PowerPoint can only reference files saved in your Microsoft 365 environment).
- [ ] PowerPoint open (web or desktop) with the **Copilot** pane available.

## What Copilot is doing here

Copilot drafts slides grounded in a **file you point it at**. **It does not decide the message** — you reference the verified workbook and the recommendation; Copilot reads the sheets and arranges them. Treat the first draft as a starting layout, then tighten the words and **re-check every figure** against the workbook before it leaves your hands.

---

## Steps

### Step 1 — Draft the deck from your forecast workbook (Copilot in PowerPoint)
In the Copilot pane, type `/` (or use **Add content**) to reference **Cash-Flow-Forecast.xlsx** so Copilot pulls the numbers itself:
```text
Create a clean, executive 5-slide cash & liquidity update for the CFO using /Cash-Flow-Forecast.xlsx. Read the Assumptions sheet for the opening position, the $8M policy minimum, and the $12M operating buffer, and the Runway sheet for projected closing cash by week.
Slide 1 — Title: "Weekly Cash & Liquidity Update" with this week's date and "ONB Treasury".
Slide 2 — Opening Position & Policy Limits: opening cash, the $12M buffer, and the $8M policy minimum from the Assumptions sheet.
Slide 3 — 13-Week Liquidity Runway: the projected low point and which week it falls in, and whether we stay above the $8M minimum.
Slide 4 — Forecast Accuracy & Drivers: the largest forecast variances and what drives the dip.
Slide 5 — Recommendation: ride it out vs. draw $5M on the revolver, with the trade-off in one line.
Keep it clean and executive — minimal text, one idea per slide.
```
> **Referencing a file:** the `/` reference (or **Add content**) points Copilot at the workbook in OneDrive so it reads the figures directly. You don't paste numbers — but you still verify every figure it pulls.

### Step 2 — Bring in the runway chart
Copy the **13-Week Liquidity Runway** chart from your Excel runway sheet and paste it onto Slide 3. Then:
```text
Reformat slide 3 so the runway chart is the focus, with the projected low point and the $8M policy minimum called out in a short caption.
```

### Step 3 — Tighten the language
```text
Review the deck and make the wording more executive: cut filler, keep one key message per slide, and make sure every slide title states a conclusion rather than a topic. Don't change any of the numbers.
```

### Step 4 — Speaker notes (optional)
```text
Add brief speaker notes to each slide with the one or two points I should say out loud, including the recommendation trade-off on the final slide.
```

---

## Deliverable

A 5-slide cash & liquidity update deck built from your verified Excel outputs, with the runway chart on the position/runway slide and a clear recommendation slide.

## Verify before you rely on it

- [ ] Every number on every slide matches `Cash-Flow-Forecast.xlsx` — re-check the opening position, the low point, and the week number against the `Runway` and `Assumptions` sheets.
- [ ] The recommendation slide states the trade-off you actually intend, not a Copilot-invented one.
- [ ] No figure appears on a slide that you haven't personally tied back to the workbook.
- [ ] Titles state conclusions; the deck reads as *your* update, not a generic template.

## Key takeaways

- Bring **verified** numbers to PowerPoint — Copilot arranges content, it does not validate figures.
- Paste real charts from Excel rather than asking Copilot to invent visuals.
- "Make each title a conclusion, don't change the numbers" is the prompt that turns a draft into an executive deck.

---

*That's the full workflow: clean the data, consolidate the position, reconcile, forecast and stress liquidity, brief it in Outlook, and present it in PowerPoint — with you verifying and deciding at every step.*
