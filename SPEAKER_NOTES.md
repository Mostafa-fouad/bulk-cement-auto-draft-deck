# Speaker Notes — Supplier Quote Pricing → Extraction

**Length:** 6 slides · aim for **6–8 minutes** + questions
**Controls:** `→` / `Space` = next · `←` = back · `F` = fullscreen · `Home`/`End` = first/last

---

### The 15-second version
> "Procurement receives supplier quotations as PDFs and photos and types them into the portfolio by hand — about 130 hours a month. We extract the prices, a person confirms each line, and those prices land in the supplier portfolio. Then, when an RFQ is raised, the quotation auto-fills from that portfolio. Same judgment, almost none of the typing — down to about 9 hours a month, a 93% cut."

### One thing to remember
**We extract into the portfolio. Then quotations auto-fill from it.**

---

## Slide 1 — Title

**On screen:** "From a supplier quote PDF to an auto-filled quotation." Team with roles.

**Say this:**
> "Hi everyone — this is about getting supplier quote prices into the portfolio without the typing, and then auto-filling every quotation from that portfolio. Quotes arrive as PDFs and photos, often scanned Arabic. Today we re-key them by hand. I'll cover the problem, the flow, the impact, and the edge — about six minutes."

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

**Transition:** "That's the input. Here's the edge."

---

## Slide 5 — The Edge

**On screen:** Sticky "this is the edge." RFQ raised → Price lookup → Draft, pre-filled.

**Say this:**
> "Once those confirmed prices sit in the supplier portfolio, we get the edge: quotations auto-fill. When an RFQ is raised for a city, we look up the latest portfolio price for each SKU and auto-create a draft with the supplier and the credit price already filled. The manager opens a draft, not a blank grid — they review and send instead of re-typing."

**Transition:** "So, in short."

---

## Slide 6 — In Short

**On screen:** "From a scanned quote to a pre-filled draft — without the typing." Badges: 93% less work, Human confirms every line, Quotations auto-fill. Mizan callout.

**Say this:**
> "In short: from a scanned quote to a pre-filled draft, without the typing. We extract into the portfolio, a person confirms every line, and then every quotation auto-fills from that portfolio. That's the 93 percent cut — and the foundation for quotation auto-pricing with Mizan. Happy to walk through any of this — what questions do you have?"

---

## Q&A (short)

- **AI writing prices?** No. Confirm first, then write.
- **Arabic scans?** That's the input. Confidence + one-by-one confirm.
- **Product missing?** Create with existing EN/AR naming, then price. Still behind the human gate.
- **New write API?** No. Existing portfolio PATCH.
- **93% / 130 / 9?** Procurement team's estimate of re-keying vs reviewing.
- **Auto-draft RFQs?** Yes — that's the edge. Portfolio lookup → pre-filled draft. Manager still reviews.
- **Mizan?** Extract into one portfolio, auto-fill quotations from it. First step toward a central pricing engine.

## Presenter tips

- Six slides: scene → problem → extract flow → number → **auto-fill edge** → wrap.
- Don't bury auto-fill. Extraction without it is just cheaper data entry.
- If asked about Approaches A/B/C, point at the design doc — don't derail.
