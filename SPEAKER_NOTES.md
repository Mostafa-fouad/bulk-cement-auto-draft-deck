# Speaker Notes — Portfolio Pricing → Auto Draft

**Deck:** https://raw.githack.com/Mostafa-fouad/bulk-cement-auto-draft-deck/master/index.html
**Length:** 10 slides · aim for **8–12 minutes** + questions
**Controls:** `→` / `Space` = next · `←` = back · `F` = fullscreen · `Home`/`End` = first/last

---

## How to use this document

Each slide below has four parts:

- **On screen** — what the audience is looking at, so you can glance and stay in sync.
- **Say this** — a natural script you can read almost word-for-word. Don't memorize it; the phrasing is meant to sound like you talking.
- **Key points** — the must-land ideas, in case you go off-script or get a question.
- **Transition** — one line to move cleanly to the next slide.

You do **not** need to prepare anything else. Everything a listener needs is on the slide + in "Say this". If someone asks something deeper, check **Q&A prep** at the end and the **Glossary**.

### The 15-second version (if someone stops you in the hallway)
> "Procurement managers get cement prices by phone every day, put them in a sheet, and then re-type those prices into every single RFQ by hand. We now pull the price straight from the system and auto-create a draft quotation with the price already filled in — so the manager just reviews and sends instead of re-typing. It's behind a feature flag, so it's safe to turn on province by province."

### One thing to remember
The story is **"we remove the re-typing, not the manager's judgment."** If you land only one idea, land that one. The manager still owns the prices — we just stop the copy-paste.

---

## Slide 1 — Title

**On screen:** "From a daily phone-call sheet to an auto-drafted quotation." The service badges (supplier, opportunity, quotation, procurement) and the team names (Ikhlas, Mostafa, Haya, Sami, Jamie).

**Say this:**
> "Hi everyone — thanks for the time. This is a small change with a real day-to-day impact for our procurement managers. Today, pricing Bulk Cement is a manual, repetitive routine. What we've built takes the prices that already live in our system and turns them into a ready-to-go draft quotation — automatically. I'll walk you through the problem, how it works, and how we're rolling it out safely. It should take about ten minutes."

**Key points:**
- This is about **Bulk Cement pricing** in procurement.
- It touches four services: **supplier, opportunity, quotation**, and the **procurement** frontend — but the audience doesn't need to care about the plumbing yet.
- Set expectations: short talk, safe rollout.

**Transition:** "Let me start with what the day looks like for a procurement manager today."

---

## Slide 2 — The Problem

**On screen:** Heading "Today, pricing Bulk Cement is manual and repetitive," with a numbered 4-step loop.

**Say this:**
> "We have one procurement manager per province, and every single day they run the same loop. First, they call the manufacturers to get that day's Bulk Cement prices. They put those prices into a spreadsheet, per factory customer. Then they calculate the buy price and the selling price by hand. And finally — this is the painful part — they re-type those prices into every Bulk RFQ, one by one. The first three steps are real expertise. The fourth step is just copy-paste, and it happens over and over, all day."

**Key points:**
- **One manager per province** — this is a per-person, per-day routine, so the pain multiplies.
- Steps 1–3 (call, sheet, calculate) = the manager's real value. Keep it.
- Step 4 (re-type into every RFQ) = pure busywork. **This is what we're removing.**

**Transition:** "That last step doesn't just cost time — it costs us in a few ways. Let me show you."

---

## Slide 3 — Why It Hurts

**On screen:** Three cards — Slow to respond, Error-prone, Not scalable.

**Say this:**
> "That manual filling hurts us in three ways. First, it's slow — every RFQ waits on someone to copy prices across, which delays the quote we send to a factory customer. Second, it's error-prone — typing prices by hand into each RFQ invites mistakes, and a mistake here is a mispriced deal. And third, it doesn't scale — the knowledge lives in one person's spreadsheet, which is hard to cover when they're out, hard to audit, and hard to grow as we add provinces."

**Key points:**
- Three costs: **speed, accuracy, scalability.**
- Frame errors as **business risk** (mispriced deals), not just typos.
- "Knowledge in one person's sheet" = a continuity/coverage risk.

**Transition:** "So here's what we changed — and it's simpler than you'd think."

---

## Slide 4 — The Solution, In a Nutshell

**On screen:** "Prices flow from the supplier portfolio straight into a draft." Sticky note: "we don't price for them — we just stop the re-typing." Three cards: Look up by SKU, Draft pre-filled, Clear signal.

**Say this:**
> "The key idea is this: the manager still owns the day's prices — we are not pricing anything for them. But instead of them re-typing those prices into every RFQ, the system does it. The prices already live in what we call the supplier portfolio. So when an RFQ comes in, we look up the freshest price for each product, we automatically create a draft quotation with that price already filled in, and we clearly flag those prices as coming from the system so nothing looks like magic. The manager opens a draft that's already populated, instead of a blank form."

**Key points:**
- **Say the sticky note out loud** — "we don't price for them, we just stop the re-typing." It defuses the biggest fear ("is this replacing my judgment?").
- Three moves: **look up by product → pre-fill a draft → flag it as system-sourced.**
- "Supplier portfolio" = where the day's prices already live (see Glossary).

**Transition:** "Let me show you the actual flow, end to end."

---

## Slide 5 — How It Works

**On screen:** A left-to-right flow: **RFQ Raised → Price Lookup (supplier) → Auto Draft (opportunity) → Draft Ready (quotation).** Footnote: best-effort, never blocks the raise.

**Say this:**
> "Here's the whole flow. It starts when a manager raises a Bulk RFQ for a province. That triggers a price lookup — we fetch the latest active portfolio price for each product in that city. Those prices get passed along and a draft quotation is built automatically. The end result is a draft that's ready, with the credit price pre-filled and flagged as portfolio-sourced. One important detail: this whole thing is best-effort and runs in the background. If a price is missing for some reason, we do not block the RFQ from being raised — the manager can always fill it in manually, exactly like today. We never make things worse than the current process."

**Key points:**
- Four steps, one per service — but you can just say "raise → look up → auto-draft → ready."
- **"Best-effort / never blocks the raise"** is the safety message. Say it clearly.
- If a lookup fails, we fall back to today's manual behavior — no regression.

**Transition:** "So what does the manager actually see on their screen?"

---

## Slide 6 — On Screen (procurement-frontend)

**On screen:** "The manager just reviews a pre-filled draft." Three cards: Pre-filled lines, "Auto-filled" badge, Review & override.

**Say this:**
> "From the manager's point of view, almost nothing changes about how they work — it just gets easier. On the Open RFQ pricing page, the draft opens with each line already populated with the supplier and the price, instead of a blank grid. The auto-filled lines carry a small badge, so it's obvious which numbers came from the system rather than being typed by hand. And there's a tooltip that explains where the number came from. Crucially, they can still review and override any line before sending — so they stay fully in control. This is built in our procurement frontend and it's localized for both English and Arabic."

**Key points:**
- The UX is **familiar** — same page, just pre-filled.
- The **badge + tooltip** = transparency; managers trust it because they can see the source.
- **Override is always available** — reinforce "they stay in control."
- It's **bilingual (EN/AR)**.

**Transition:** "Let me put the old way and the new way side by side."

---

## Slide 7 — Before vs After

**On screen:** Two panels. Before: call, hand-calculate, manually fill every RFQ, slow/error-prone. After: portfolio holds prices, draft auto-created, pre-filled per line, manager just reviews.

**Say this:**
> "Side by side: Before, the manager calls manufacturers, hand-calculates buy and sell, then manually fills every single Bulk RFQ from the sheet — slow, error-prone, and tied to one person. After, the portfolio already holds the day's prices, a draft is auto-created the moment an RFQ is raised, the supplier and credit price are pre-filled on every line, and the manager just reviews, tweaks if needed, and sends. Same prices, same expertise — none of the repetitive filling."

**Key points:**
- The **only** thing that changed is the busywork step.
- "Same prices, same expertise" — repeat the reassurance.

**Transition:** "So why is this worth doing?"

---

## Slide 8 — Why It's Worth It (Impact)

**On screen:** A "back-of-napkin" panel: manual filling = a few minutes each; auto-drafted = open & review; typing errors → basically gone. Small caveat that numbers should be confirmed with province teams.

**Say this:**
> "Here's the rough impact — and I want to be honest that this is back-of-a-napkin, not a measured study yet. Today, filling from the sheet takes a few minutes on every RFQ, and that adds up across a full day and across provinces. With an auto-drafted quote, that becomes 'open and review' — the typing is gone. And because nobody's re-keying numbers, pricing typos basically disappear. We'll want to confirm the exact time savings with the province teams once it's live, but directionally: faster quotes, fewer mistakes. And again — the manager's expertise stays in charge of pricing; we're only taking out the copy-paste."

**Key points:**
- **Be upfront that the numbers are rough** — the slide says so, and honesty builds credibility.
- The strong, defensible claims: **less time per RFQ** and **fewer typing errors.**
- Close the loop: expertise stays, copy-paste goes.

**Transition:** "And we're shipping this in a way that's safe and reversible."

---

## Slide 9 — Safe Rollout

**On screen:** "Shipped behind a feature flag." Two cards: Off by default (`enable_portfolio_pricing_auto_draft`), Never blocks a raise.

**Say this:**
> "This is shipped behind a feature flag. That means the whole auto-draft flow is gated right at the start — it stays off until we're ready, and we can switch it on province by province without any redeploy. If we see anything odd, we flip it off instantly. And as I mentioned, it runs asynchronously and best-effort: if the auto-draft ever fails, we just log it, and the RFQ raise itself is completely untouched. So there's no scenario where this new feature blocks someone from doing their job the way they do today."

**Key points:**
- **Feature flag = off by default, gradual, instantly reversible, no redeploy.**
- **Async + best-effort = never blocks the core workflow.**
- This slide is your answer to "what if it breaks?" — you can turn it off.

**Transition:** "So, to sum up."

---

## Slide 10 — In Short (Closing)

**On screen:** "The sheet's prices, delivered as a draft — automatically." Badges: Faster quotes, Fewer errors, Safe flagged rollout. Plus a highlighted "What this sets up" callout about the central pricing engine.

**Say this:**
> "To wrap up: managers keep owning the day's Bulk Cement prices. We take away the repetitive filling, we speed up every quote, and we keep the portfolio as the single source of truth. It's faster, it's less error-prone, and it's rolled out safely behind a flag. And one last thing worth calling out: this isn't a one-off. It's the foundation for quotation auto-pricing with Mizan — the first concrete step toward the company's direction of a single, central pricing engine that powers every module, not just this one. Happy to walk through any part of this in more detail — what questions do you have?"

**Key points:**
- Three-word summary: **faster, fewer errors, safe.**
- **Strategic framing:** this is the **foundation for quotation auto-pricing with Mizan** and the company's **central pricing engine for all modules** — position it as step one, not a one-off.
- End by **opening the floor** for questions.

---

## Q&A prep — likely questions and solid answers

**"Are you replacing the manager / their pricing judgment?"**
> "No. The manager still sets and owns the prices — those prices live in the portfolio. We're only removing the step where they re-type those same prices into each RFQ. They review and can override every line before sending."

**"What happens if the price is wrong or out of date?"**
> "The manager reviews the draft before sending and can override any line. And because the auto-filled lines are badged with a tooltip showing the source, it's easy to spot and correct. The system uses the latest active portfolio price for that product and city."

**"What if the auto-draft fails or a price is missing?"**
> "It's best-effort and runs in the background. If it can't build the draft, the RFQ raise is unaffected and the manager just fills it in manually, exactly like today. It never blocks anyone."

**"Is this live everywhere right now?"**
> "It's behind a feature flag and off by default. We can turn it on province by province without a redeploy, and turn it off instantly if needed."

**"Does this handle other products, not just Bulk Cement?"**
> "Right now the focus is Bulk Cement, since that's where the daily manual-pricing pain is sharpest. The approach — pull the latest portfolio price and pre-fill a draft — could extend to other products later, but that's not in scope for this rollout."

**"Where do the prices actually come from?"**
> "From the supplier portfolio — that's where the day's supplier prices are stored per product and city. The manager's daily prices feed into that, and we read the latest active one at RFQ time."

**"How do managers know which numbers were auto-filled?"**
> "Auto-sourced lines carry a badge, and a tooltip explains where the number came from. Anything they type themselves looks normal."

**"How much time does it actually save?"**
> "Directionally, it turns a few minutes of typing per RFQ into a quick review. We'll confirm the real numbers with the province teams once it's rolled out — I don't want to overstate it before we measure."

**"How does this fit the bigger picture / Mizan?"**
> "This is deliberately a foundation, not a one-off. The same pattern — pull an authoritative price and pre-fill it — is the groundwork for quotation auto-pricing with Mizan. It's the first concrete step toward the company's direction of a single, central pricing engine that serves every module, so pricing logic lives in one place instead of being rebuilt per feature."

**"Which teams / services were involved?"**
> "It spans supplier (the price lookup), opportunity (which orchestrates the auto-draft), quotation (which holds the draft), and the procurement frontend (what the manager sees). Built by Ikhlas, Mostafa, Haya, Sami, and Jamie."

---

## Glossary (quick definitions, in case you're asked)

- **RFQ** — Request For Quote. When a customer wants pricing, an RFQ is raised; the manager responds with a quotation.
- **Bulk Cement** — the product line this feature targets; priced daily from manufacturers.
- **Supplier portfolio** — the store of the day's supplier prices, per product and city. The "source of truth" for pricing.
- **Draft quotation** — a not-yet-sent quotation the manager reviews and finalizes.
- **Credit price** — the price populated on the draft from the portfolio (what shows up pre-filled).
- **Feature flag** — a switch that turns the feature on/off without a code deploy; lets us roll out gradually and reverse instantly.
- **Mizan** — BRKZ's pricing intelligence. This feature is the groundwork for quotation auto-pricing with Mizan and a shared, central pricing engine.
- **Central pricing engine** — the company direction: one place that owns pricing logic and serves every module, instead of each feature rebuilding its own.
- **Best-effort / async** — the auto-draft runs in the background and, if it fails, it never blocks the main action (raising the RFQ).
- **procurement-frontend** — the web app (Next.js + React) where the manager reviews and sends quotes; supports English and Arabic.

---

## Presenter tips

- **Pace:** ~1 minute per slide. If short on time, the slides you can compress are 3 and 7 (they reinforce, don't introduce). Never skip 4, 5, and 9.
- **The three anchors:** (1) "we remove re-typing, not judgment," (2) "it never blocks the RFQ," (3) "it's behind a flag, reversible instantly." If you land those three, the talk succeeds.
- **The forward-looking line:** close by framing this as the **foundation for Mizan auto-pricing and a central pricing engine for all modules** — it shows this is aligned with company direction, not a one-off.
- **If the deck won't fullscreen** on a locked-down browser, press `F` anyway — it falls back to a full-window mode automatically.
- **If you blank:** read the "Say this" line for the current slide. It's written to be spoken as-is.
