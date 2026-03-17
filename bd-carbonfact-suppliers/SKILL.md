---
name: bd-carbonfact-suppliers
description: >
  Business Development skill for prospecting suppliers/factories to onboard them onto Carbonfact for Suppliers (suppliers.carbonfact.com). Use this skill whenever the user provides supplier data (website URL, materials, stakeholder LinkedIn URLs, company context) and needs: phase diagnosis, tailored outreach sequences, objection handling, market opportunity mapping, or next-action plans to secure an introductory call/demo. Also trigger when the user mentions any supplier or factory name, shares a LinkedIn URL of a sustainability contact, asks about LCA data sharing with brands, discusses EU regulations (CSRD, PEF, AGEC, French Eco-Score) in the context of supply chain, asks about supplier segmentation, competitive positioning vs Vaayu/Fairlymade/consultancies, wants to draft cold emails to material companies, or discusses friction analysis in the supplier onboarding funnel. This skill operates in the language of the input — if French, reply in French; if Spanish, reply in Spanish; if English, reply in English.
---

# BD Skill — Carbonfact for Suppliers

## How to Use This Skill

Provide any combination of the following about the supplier you want to prospect:

| Input | Example | Required? |
|---|---|---|
| **Company website** | `https://www.manteco.com` | Strongly recommended — Claude will fetch and analyze it |
| **Material/process** | "recycled polyester yarn", "bio-based leather" | Helpful if not on website |
| **Contact LinkedIn URL** | `https://linkedin.com/in/jane-doe` | Helps personalization + engagement readiness score |
| **Company name** | "Manteco" | Minimum needed if no URL |
| **Additional context** | "They supply On and Patagonia", "Met them at ISPO", "A brand client referred them" | Improves classification accuracy |

**Minimum input**: a company name or website URL. The more context you give, the better the output.

**Example prompts**:
- `"Prospect this supplier: https://www.manteco.com — they make recycled wool fabrics"`
- `"Draft outreach for EcoFiber SRL, contact is Maria Rossi (Head of Sustainability). They have GRS certification and sell to VF Corp."`
- `"Analyze this supplier and tell me if it's worth pursuing: https://www.example-supplier.com"`
- `"I met this supplier at Première Vision, here's their site: [URL]. They seem interested but worried about data privacy."`

---

## Pipeline

When the user provides supplier context (website, materials, key stakeholder LinkedIn URL, notes), execute these steps in order:

1. **Research the supplier** → fetch website, extract materials, certifications, clients, sustainability claims
2. **Classify** → Tier 1, 2, or 3
3. **Diagnose phase** → Phase 0, 1, 2, or 3
4. **Score the lead** → ICP score (0–100)
5. **Calculate intro-call probability** → % likelihood of booking a demo
6. **If probability < 50%** → output specific recommendations to increase conversion
7. **Map market opportunity** → regulated markets + brand segments creating demand
8. **Select prospecting angle** → A (organize, don't duplicate), B (be where sourcing happens), or C (regulation as sales pitch)
9. **Inject pain points into emails** → rewrite email body around the supplier's specific pains — do NOT just fill in template placeholders
10. **Generate tailored outreach** → email sequence (Initial + FU1 + FU2) built from pain-injected structure
11. **Prepare objection handling** → top 3 likely objections predicted from pain profile
12. **Define warm referral strategy + next action**

**Language rule**: Always reply in the language of the user's input. Email drafts must also match the target recipient's language (French for French suppliers, etc.).

---

## 1. Supplier Research (CRITICAL — always do this first)

When the user provides a supplier website URL:
1. Use `web_fetch` to retrieve the site homepage and any `/sustainability`, `/about`, `/materials`, `/certifications` pages
2. Extract: materials/processes offered, certifications (GRS, OEKO-TEX, Bluesign, LWG, ISO 14040/44), sustainability claims, published LCA data, client logos/names, key contacts (Head of Sustainability, Innovation Director)
3. If a LinkedIn URL is provided, note the person's title and role for personalization
4. Use this extracted data to populate the classification, ICP scoring, and email personalization — do not ask the user for information you can find yourself

If the URL is not provided, ask the user for it or for the key data points needed to classify.

---

## 2. Supplier Segmentation

### Tier 1 — LCA-Ready Innovators
- **Profile**: Has at least one third-party or internally reviewed LCA. Sells to brands with regulatory obligations (CSRD, PEF, AGEC). Often next-gen materials (recycled, bio-based, waterless).
- **Signals**: LCA on website, ISO 14040/44 references, certifications (GRS, OEKO-TEX, Bluesign, LWG), partnerships with On/Patagonia/Allbirds/VF Corp.
- **Angle**: "You already have the data — let it work harder for you."

### Tier 2 — LCA-Aware, Not Structured
- **Profile**: Has environmental data (EPDs, internal carbon reports, partial LCAs) but not standardized. Sells to mid-market brands, may have been asked for LCA data.
- **Signals**: Sustainability page but no downloadable LCA, carbon goals without numbers, certifications but no product-level footprint.
- **Angle**: "Your clients are starting to ask — be ready before they demand it."

### Tier 3 — No LCA, Needs One
- **Profile**: No LCA documentation. May have basic certifications. Wants to enter regulated markets.
- **Signals**: No sustainability section, or generic statements only. May be in emerging markets (Turkey, Bangladesh, Vietnam, India).
- **Angle**: "Your competitors are getting verified — don't fall behind."

### Prospecting Angles (test per supplier)

| Angle | Best for | Core premise |
|---|---|---|
| **A — "Organize, don't duplicate"** | Tier 1–2 | Replace repetitive PDF/NDA/email per-brand with one verified profile |
| **B — "Be where sourcing happens"** | Tier 1, 3 | 200+ brands run material simulations on Carbonfact daily — be in the comparison |
| **C — "Regulation is your sales pitch"** | Tier 2–3 | CSRD/PEF/French Eco-Score are turning LCA data into a market-entry requirement |

---

## 3. ICP Scoring (Ideal Customer Profile)

Score each criterion 0–20. Total = ICP score out of 100.

| Criterion | /20 | Scoring |
|---|---|---|
| **LCA Maturity** | /20 | 20=published third-party LCA · 15=internal LCA/EPD · 10=partial data · 5=certs only · 0=nothing |
| **Client Base Quality** | /20 | 20=sells to Carbonfact clients or CSRD/PEF brands · 15=brands with public sustainability goals · 10=mid-market · 5=no demand · 0=unknown |
| **Regulatory Exposure** | /20 | 20=EU-based or selling into EU · 15=California/NY exposure · 10=emerging regulation · 5=minimal · 0=none |
| **Material Innovation** | /20 | 20=next-gen (recycled, bio-based, waterless) · 15=improved conventional · 10=standard+certs · 5=commodity · 0=unknown |
| **Engagement Readiness** | /20 | 20=inbound/warm referral · 15=active on sustainability topics · 10=sustainability contact identifiable · 5=generic contact · 0=no contact |

**Priority**: 80–100 pursue immediately · 60–79 within 2 weeks · 40–59 batch outreach · <40 park, revisit quarterly.

---

## 4. Phase Detection

| Phase | Signals | Goal | Exit criteria |
|---|---|---|---|
| **0 — Unaware** | No LCA/sustainability data-sharing mention. Not selling to regulated brands. | Educate on WHY data matters | Acknowledges trend, expresses curiosity |
| **1 — Aware, Passive** | Has sustainability content. Knows Carbonfact/competitors may exist. Shares PDFs manually. | Show cost of inaction + ease of action | Clicks link, replies, accepts LinkedIn |
| **2 — Evaluating** | Asked about data privacy, process, competitors. Comparing options. | Overcome specific objections. Build trust. | Agrees to intro call/demo |
| **3 — Ready** | Expressed intent. May have started sharing docs. Waiting on internal approval. | Remove last friction. Set date. | Intro call booked and confirmed |

---

## 5. Customer Pathway (Cold → Onboarded)

| Stage | Key friction | How to overcome |
|---|---|---|
| **Cold → Aware** | No perceived need | Lead with regulation (CSRD/PEF). Reference their materials. "200+ brands already evaluate suppliers on Carbonfact." |
| **Aware → Interested** | Data privacy fear, "why free?" | Access-control model (you decide who sees what). Business model: brands pay, not suppliers. Manteco testimonial. NDA available. |
| **Interested → Demo** | Timing, internal buy-in, unclear ROI | Regulation timeline urgency. Offer 15-min no-commitment demo. Position as "feedback session." |
| **Demo → Profile** | LCA not ready, approval needed | Start with one material. Free review. Checklist of minimum requirements. Sign NDA if needed. |
| **Profile → First Request** | No immediate brand requests | Proactively connect brand sustainability teams. Share analytics. Newsletter/LinkedIn feature. |

---

## 6. Intro-Call Probability

### Scoring model (add points):

| Factor | Points |
|---|---|
| Tier 1 / Tier 2 / Tier 3 | +25 / +15 / +5 |
| ICP ≥80 / 60–79 / 40–59 | +15 / +10 / +5 |
| Warm referral from brand/supplier | +20 |
| Inbound interest | +25 |
| Identified decision-maker | +10 |
| Only generic contact (info@) | −5 |
| Active on LinkedIn (sustainability) | +5 |
| Sells to Carbonfact brand clients | +10 |
| EU-based or selling into EU | +5 |
| Already uses competitor platform | −5 |
| Previously contacted, no response | −10 |
| Language/cultural alignment with BD | +5 |

### Interpretation

| Score | Probability | Action |
|---|---|---|
| ≥70 | High (>70%) | Prioritize. Full sequence + LinkedIn. |
| 50–69 | Medium (50–70%) | Standard sequence. May need all 3 emails + LinkedIn. |
| 30–49 | Low (30–50%) | Adjust approach — see recommendations below. |
| <30 | Very low (<30%) | Park. Re-engage on trigger event. |

### If < 50% — levers to pull:
1. **Find a better contact** (LinkedIn Sales Navigator, Apollo, Hunter.io) → +15–20 pts
2. **Get a warm intro** from a Carbonfact brand client → +20 pts
3. **Wait for trigger event** (regulation deadline, trade show)
4. **Change channel** (LinkedIn DM, comment engagement before email)
5. **Lower the ask** ("Can I send a 2-min video?" instead of "15-min demo")
6. **Leverage competitor presence** on the platform (tactfully)
7. **Involve a Carbonfact brand client** who buys from this supplier (demand-side pull)

---

## 7. UVP Framework: Why / What / How

All outreach uses this structure:

- **WHY**: Brands face CSRD/PEF/AGEC pressure to use verified product-level data. Suppliers without structured LCA data risk exclusion. Meanwhile, suppliers drown in repetitive per-brand data requests (PDFs, NDAs, emails).
- **WHAT**: Carbonfact for Suppliers is free. Organize LCA data once, share with multiple brands from one verified profile. You control access. 200+ brands (On, Carhartt, The North Face, GANNI) already use Carbonfact's eco-design tools where your data becomes discoverable.
- **HOW**: Share existing LCA → Carbonfact Science team verifies free → Profile goes live → Brands discover and request access → You decide who sees what.

### CTA Strategy
Every email drives toward: **booking the 15-min intro call**. If they decline or go cold, deploy **warm referral CTA**: "Even if timing isn't right — do you know a brand or someone who might be interested?"

---

## 8. Pain-to-Email Injection (CRITICAL — this is what makes emails convert)

The templates in `references/email-sequences.md` are starting structures, NOT fill-in-the-blank forms. The real work is rewriting the email body around the supplier's specific pain points. Generic templates get ignored. Pain-aware emails get replies.

### How it works

After research (Step 1) and angle selection (Step 8), identify the supplier's top 2–3 pain points. Then restructure the email using this logic:

**Initial Outreach** — Lead with their #1 pain, not with Carbonfact.

| If #1 pain is... | Open the email with... | Then pivot to Carbonfact via... |
|---|---|---|
| Credibility gap (post-crisis, no third-party verification) | Acknowledge their rebuilding effort + what's impressive about their progress | "Free LCA verification by our Science team adds a third-party credibility layer at no cost" |
| Repetitive data requests (admin burden) | Name the problem: "I'm guessing every brand asks for the same data in a different format" | "One verified profile replaces that cycle — brands access it when they need it" |
| Discovery / need more brand relationships | Reference their material's strengths + the brands who'd want it | "200+ brands compare materials inside Carbonfact daily — your data should be in the comparison" |
| Already has own platform/library | Compliment what they've built + identify the gap it doesn't fill | "Your [library/platform] shows what's available. Carbonfact shows what impact it has — that's where the sourcing decision happens" |
| Data sharing anxiety | Lead with control, not with sharing | "You never share the actual LCA document. Brands see verified data only. You approve every request." |
| Regulatory pressure from clients | Reference the specific regulation + deadline affecting their clients | "Your clients under [CSRD/PEF/Eco-Score] need this data from you. Suppliers who provide it proactively get priority." |

**Follow-up 1** — Reinforce with a proof point that addresses their #2 pain.

- If #2 is discovery → show example profile + mention comparable supplier already receiving requests
- If #2 is credibility → reference the free verification process + PEF alignment
- If #2 is volume anxiety → mention the 200+ brand network as inbound demand channel
- If #2 is "more work" → emphasize one-time upload, Carbonfact handles the rest

**Follow-up 2** — Create urgency from their specific situation, not generic regulation pressure.

- If post-crisis: "Brands are building shortlists now. Verified data accelerates trust recovery."
- If competitor is on platform: "I noticed [COMPETITOR] recently joined — given you're in the same space, you'd want to be in the comparison."
- If strong brand overlap: "Brands are already comparing materials on Carbonfact with generic estimates. Your verified data replaces those estimates — that's how you show up as the better choice, inside the tool where the decision happens."
- Always close with warm referral P.S.

### Anti-patterns — what NOT to do

- **Don't just swap placeholders.** `[MATERIAL]` → "recycled polyester" is not personalization. Referencing their specific production milestone or client partnership IS.
- **Don't lead with Carbonfact.** Lead with THEIR situation. Carbonfact is the solution, not the opening.
- **Don't use all three pain points in one email.** One pain per email. Stack them across the sequence.
- **Don't assume pains.** If the research didn't surface evidence for a pain, don't include it. An email that addresses an imaginary problem is worse than a generic one.

### When no deep research is available

If the user only provides a company name and URL (no pre-research from `b2b-prospect-research`), fall back to the standard templates in `references/email-sequences.md` — but still personalize using whatever was extracted from the website in Step 1. The templates are the floor, not the ceiling.

---

## 9. Reference Files

For detailed content, read these files from `references/` as needed:

| File | When to read |
|---|---|
| `references/email-sequences.md` | As the starting structure for email drafts — then rewrite using pain injection (Section 8) |
| `references/objection-handling.md` | When preparing objection responses or handling supplier pushback |
| `references/competitive-positioning.md` | When asked about Vaayu, Fairlymade, consultancies, or "how are you different?" |
| `references/market-opportunity.md` | When mapping regulatory demand drivers or brand segment overlap |
| `references/linkedin-cadence.md` | When planning multi-channel outreach including LinkedIn |
| `references/faq.md` | When answering supplier questions about how the platform works, data security, pricing, verification process |
| `references/tracking-template.md` | When the user wants to track pipeline status across multiple suppliers |

Read `references/email-sequences.md` for the base structure, then apply pain injection from Section 8. Read `references/faq.md` when handling objections or preparing for calls.

---

## 9. Output Template

When the user provides supplier data, respond with this structure:

```
## Supplier Analysis: [COMPANY NAME]

### Classification
- **Tier**: [1/2/3] — [one-line justification]
- **Phase**: [0/1/2/3] — [one-line justification]
- **ICP Score**: [X/100] — [breakdown: LCA Maturity /20, Client Base /20, Regulatory Exposure /20, Material Innovation /20, Engagement Readiness /20]

### Intro Call Probability
- **Score**: [X points] → **[X]% probability**
- **If < 50%**: [specific recommendations]

### Market Opportunity
- **Materials**: [list]
- **Regulated markets**: [which regulations apply]
- **Carbonfact brand overlap**: [which Carbonfact clients source similar materials]
- **Urgency driver**: [specific regulation/deadline]

### Recommended Approach
- **Channel**: [Email / LinkedIn / Referral / Combination]
- **Sequence**: [A (Tier 1) / B (Tier 2) / C (Tier 3)]
- **Angle**: [A/B/C — with rationale]
- **Personalization points**: [specific references for outreach]

### Pain Points Driving the Approach
- **Pain #1 (Initial email)**: [Pain + evidence] → [How email addresses it]
- **Pain #2 (FU1)**: [Pain + evidence] → [How FU1 reinforces]
- **Pain #3 (FU2 urgency)**: [Pain + evidence] → [Urgency angle used]

### Email Drafts
[Initial Outreach — opens with Pain #1 from their perspective, pivots to Carbonfact as the solution. NOT a template with swapped placeholders.]
[Follow-up 1 (3–5 days) — proof point addressing Pain #2, example profile, reinforce angle]
[Follow-up 2 (5–7 days) — urgency from Pain #3 or their specific situation, warm referral P.S.]

### Top 3 Objections & Responses
1. [Objection] → [Response]
2. [Objection] → [Response]
3. [Objection] → [Response]

### Warm Referral Strategy
- **When**: [after FU2 no-reply / "not now" / successful onboarding]
- **Ask**: [personalized referral request]
- **Who they might refer**: [based on network]

### Next Action
[Concrete step with timeline]
```

---

## 10. Product Feedback Capture

Every supplier interaction generates signals. When the user reports friction or feedback from a supplier, capture it in this format:

| Category | What to log |
|---|---|
| **Feature request** | Exact ask + context |
| **Friction point** | Where in the funnel + what blocked progress |
| **Competitive intel** | Which competitor + what they offered |
| **Market signal** | Regulation mention + brand demand + timeline |
| **New objection** | Objection text + what was tried |

Output as a structured note the user can paste into their tracking tool.

---

## Key References
- **Carbonfact for Suppliers**: https://suppliers.carbonfact.com
- **Example profile**: https://suppliers.carbonfact.com/en/processes/73908f26-333e-4934-a1e9-0c7163e6bedc
- **Main platform**: https://www.carbonfact.com
- **Customers**: https://www.carbonfact.com/customers
- **Trust center**: https://trust.carbonfact.com
