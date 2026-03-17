# Deep Prospect Research — Carbonfact for Suppliers BD

This is the research methodology for Step 1 of the BD pipeline. Execute all 4 phases before moving to classification (Step 2).

## Phase 1: Company Status & Credentials

**Use `web_search` and `web_fetch` to find:**

### 1.1 Production/operational status
- Current production capacity and scale
- Facility locations
- Recent operational changes (expansions, closures, restarts, acquisitions)
- Technology or process innovations

### 1.2 Client/partnership commitments
- Named brand partnerships or volume commitments (get specific names and dates)
- Recent contract announcements
- Strategic partnerships (fiber producers, manufacturers, retailers)
- Customer testimonials or case studies

### 1.3 Technical credentials
- LCA studies or carbon footprint data — look for specific numbers: kg CO₂e, % reduction, system boundaries
- Certifications (GOTS, OEKO-TEX, Bluesign, GRS, LWG, B Corp, ISO 14040/44)
- Third-party verification studies (who reviewed, when)
- EPDs (Environmental Product Declarations)
- Environmental claims with quantified impact

### 1.4 Financial/ownership context
- Funding rounds or investment announcements (amount, date, investors)
- Ownership changes (PE acquisitions, restructuring, mergers)
- Revenue/valuation if public
- Bankruptcy, financial stress, or credit warnings — this changes the entire approach

**Key principle:** Look for NUMBERS and DATES. "11 brand commitments" beats "several partners." "Q4 2026 production restart" beats "upcoming launch." "−2 kg CO₂e per kg pulp" beats "low carbon footprint." If you can't find a number, flag it as a data gap.

---

## Phase 2: Recent Context & Timeline (last 3–6 months)

**Search for:**
- Product launches or production milestones
- Executive changes or strategic pivots
- Regulatory developments affecting the company
- Industry events, trade show appearances, or partnerships announced
- Market challenges, competitive threats, or public criticism
- LinkedIn activity from key stakeholders (what are they posting about?)

**Synthesize into:**
- **Recent wins:** New clients, milestones, funding, awards
- **Recent challenges:** Delays, financial pressure, market shifts
- **Inflection points:** Major changes that shift their strategy — new regulation, new ownership, new market entry

---

## Phase 3: Pain Point Identification

Every pain point MUST have evidence. No assumptions. No invented pains.

### For suppliers/manufacturers:

| Pain category | What to look for | Evidence sources |
|---|---|---|
| **Discovery/visibility** | Hard for brands to find them | No presence on sourcing platforms, limited digital marketing |
| **Data sharing anxiety** | IP protection concerns, NDA fatigue | Mentions of proprietary processes, reluctance to publish data |
| **Volume anxiety** | Need committed orders, not just interest | Small production runs, fundraising for scale-up |
| **Price premium justification** | Struggle to prove ROI vs conventional | Price comparisons in press, "premium" language |
| **Credibility gaps** | Need third-party verification, trust rebuilding | Bankruptcy history, greenwashing accusations, no third-party LCA |
| **Regulatory compliance** | CSRD, DPP, French Eco-Score pressure | EU-based or selling into EU, compliance mentions |
| **Repetitive data requests** | Multiple brands asking same data, different formats | Large client base, manual PDF/email processes |
| **Capacity constraints** | Can't scale to meet demand | Waitlists, expansion announcements |

### For brands/retailers:

| Pain category | What to look for |
|---|---|
| **Supply chain transparency** | Don't know environmental impact of materials |
| **Regulatory pressure** | CSRD Scope 3, ESPR, DPP deadlines |
| **Greenwashing risk** | Need credible, verified sustainability data |
| **Supplier discovery** | Can't find innovative material sources at scale |
| **Cost pressures** | Sustainable materials cost more — need to justify |

**Output format per pain point:**
```
Pain Point: [Clear, specific statement]
Evidence: [Quote, data point, or recent action proving this]
Source: [Clickable markdown link — format: [Source title](URL) — Month Year]
Severity: Critical / High / Medium
```

**Source links are mandatory.** Every pain point needs a clickable URL. If you can't find a source for a pain, don't include it. The final output must contain a Sources section at the bottom with all URLs used in the analysis, formatted as clickable markdown links: `[Title](URL) — key finding`.

---

## Phase 4: Pain → Carbonfact Solution Mapping

For each pain identified in Phase 3, map to a specific Carbonfact for Suppliers capability. This feeds directly into the pain-to-email injection (Section 8 of the main skill).

| Supplier pain | Carbonfact solution | Proof point |
|---|---|---|
| Discovery/visibility | Profile discoverable inside eco-design tools used by 200+ brands | Brands compare materials in real-time simulations |
| Data sharing anxiety | Brands see verified data + system boundary only — never the raw LCA. Brand-by-brand access control, revocable anytime | Access control dashboard, NDA available |
| Repetitive data requests | One verified profile replaces per-brand PDF/NDA/email cycles | Angle A: "Organize, don't duplicate" |
| Credibility gaps | Free LCA verification by Carbonfact Science team (PEF-aligned, ISO 14040/44) | Verification at no cost, comparable methodology |
| Price premium justification | Verified environmental data lets brands quantify impact advantage vs conventional | Eco-design simulations show the delta |
| Regulatory compliance | Brands under CSRD/PEF need product-level supplier data — suppliers who provide it get priority | French Eco-Score rollout, CSRD Scope 3 deadlines |
| Volume anxiety | Visibility to 200+ brands creates inbound demand pipeline | Brand discovery → access requests → commercial conversations |

### Messaging Alignment (pain → angle → sequence)

| If strongest pain is... | Lead with angle... | Email sequence |
|---|---|---|
| Repetitive data requests / admin burden | **A — Organize, don't duplicate** | Sequence A or B |
| Discovery / need more brand relationships | **B — Be where sourcing happens** | Sequence A or B |
| Regulatory pressure / market access | **C — Regulation is your sales pitch** | Sequence B or C |
| Credibility rebuilding (post-crisis, no LCA) | **Free verification as trust signal** | Sequence C |
| Data sharing anxiety (dominant) | **Lead with access control + NDA** in opener | Any sequence, modify opener |

### Objection Pre-Loading (pain → predicted objection)

| Pain profile | Likely objection | Pre-load from |
|---|---|---|
| Data sharing anxiety is high | "What about confidentiality?" | Objection #1 |
| Already has own platform/library | "We already manage our own data" | Custom: complementary layer |
| Financial stress / post-crisis | "Why is it free?" | Objection #2 |
| Large existing client base | "We already share with clients directly" | Objection #3 |
| No LCA at all | "We don't have the data yet" | Objection #8 |
| Competitor platform in use | "We already use [competitor]" | `references/competitive-positioning.md` |

---

## Quality Checks (before moving to Step 2)

1. **Source verification:** Every claim has a URL + date. No invented pain points.
2. **Recency:** Flag if most information is >12 months old. Prioritize last 3 months.
3. **Numbers:** Replace vague claims ("low carbon") with data ("−2 kg CO₂e/kg"). Flag gaps.
4. **Pain evidence:** Each pain has a source — not an assumption from the industry.
5. **Stakeholder mapping:** At least one named contact with title.
6. **Carbonfact mapping:** Every pain is mapped to a solution + angle before proceeding.
