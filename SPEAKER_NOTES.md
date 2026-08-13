# Speaker Notes — Supplier Quote Pricing → Extraction

**Length:** 6 slides · aim for **6–8 minutes** + questions
**Controls:** `→` / `Space` = next · `←` = back · `F` = fullscreen · `Home`/`End` = first/last

---

### The 15-second version
> "Procurement receives supplier quotations as PDFs and photos — often scanned Arabic — and types every line into the supplier portfolio by hand. That takes about 130 hours a month. We extract the products and prices with AI, a person confirms each line, and then we write to the portfolio. Same judgment, almost none of the typing — down to about 9 hours a month, a 93% cut."

### One thing to remember
**We extract. They still confirm.**

---

## Slide 1 — Title

**On screen:** Title, short subtitle, team with roles.

**Say this:**
> "Hi everyone — this is about getting supplier quote prices into the portfolio without the typing. Quotes arrive as PDFs and photos, often scanned Arabic. Today we re-key them by hand. I'll cover the problem, the flow, and the impact — about five minutes."

**Transition:** "Here's the work today."

---

## Slide 2 — The Problem

**On screen:** Two cards — ~130 hours / month, and a typo sticks.

**Say this:**
> "Supplier quotations arrive as PDFs and photos — often scanned Arabic, mixed languages, units, VAT. Someone reads every line and types it into the supplier portfolio. That data entry is about 130 hours a month. And if the SKU or the unit price is wrong, it stays in the portfolio and every later quote inherits it."

**Don't:** walk a four-step manual loop. The next slide is the new loop.

**Transition:** "Here's what we do instead."

---

## Slide 3 — How It Works

**On screen:** Upload → Extract → Confirm → Write. Sticky: "we extract — they still confirm."

**Say this:**
> "Four steps. Upload the PDF or photo with the supplier and the city — a quote prices one city. Extract: AI returns line items with a confidence score. Confirm: match the SKU and unit, edit the price if needed, create the product only if it's new. Write: the existing portfolio API. Nothing is written until a person confirms the line. We extract. They still confirm."

**Transition:** "What that does to the hours."

---

## Slide 4 — The Impact

**On screen:** 93%. ~130 hours/month → 9 hours/month.

**Say this:**
> "That's a 93 percent cut — from about 130 hours a month of re-typing down to 9 hours of confirming lines. Same judgment. Almost none of the typing."

**Don't:** re-explain the problem. State the number and move.

**Transition:** "And this is the input to something bigger."

---

## Slide 5 — What This Sets Up

**On screen:** Portfolio as the read target. Mizan callout. No 93% recap.

**Say this:**
> "Confirmed prices land in the supplier portfolio — the same place every other module already reads from. That's the input side of a central pricing engine."

**Transition:** "So, in short."

---

## Slide 6 — In Short

**On screen:** "The quote's prices, confirmed into the portfolio — without the typing." Badges: 93% less work, Human confirms every line, Portfolio stays the source of truth. Mizan callout.

**Say this:**
> "In short: the quote's prices, confirmed into the portfolio, without the typing. Upload, extract, confirm, write. Procurement keeps the judgment; the system takes the document work. And this is the foundation for quotation auto-pricing with Mizan — toward one central pricing engine for every module. Happy to walk through any of this — what questions do you have?"

---

## Q&A (short)

- **AI writing prices?** No. Confirm first, then write.
- **Arabic scans?** That's the input. Confidence + one-by-one confirm.
- **Product missing?** Create with existing EN/AR naming, then price. Still behind the human gate.
- **New write API?** No. Existing portfolio PATCH.
- **93% / 130 / 9?** Procurement team's estimate of re-keying vs reviewing.
- **Auto-draft RFQs?** No. Different idea. This only fills the portfolio.
- **Mizan?** This is the input side of a central pricing engine.

## Presenter tips

- Six slides, one job each: scene → problem → flow → number → strategy → wrap.
- If asked about Approaches A/B/C, point at the design doc — don't derail.
