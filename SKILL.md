---
name: b2b-prospect-research
description: >
  Use this skill when preparing for B2B sales meetings, client calls, roleplay simulations, or stakeholder interviews — especially in sustainability, climate tech, fashion, or supply chain contexts. Triggers: 'research [company] for meeting', 'prepare roleplay with [supplier/brand]', 'profile [company] pain points', 'help me understand [company] situation', 'deep dive on [company]', 'prep me for a call with [company]', 'what should I know about [company] before reaching out'. Creates comprehensive company profiles including business status, technical credentials, evidence-backed pain points, and strategic approach — with optional mapping to Carbonfact for Suppliers value propositions when used in BD context. This skill operates in the language of the input.
---

# B2B Prospect Research Skill

## When to Use This Skill

Use when the user needs to:
- Prepare for a sales meeting or client call
- Practice roleplay simulations with specific companies
- Understand a prospect's current situation and pain points
- Build tailored value propositions for B2B conversations
- Research suppliers, brands, or partners in sustainability/fashion/climate tech
- Feed deep research into the `bd-carbonfact-suppliers` skill for outreach generation

## Research Methodology

### Phase 1: Company Status & Credentials

**Use `web_search` and `web_fetch` to find:**

1. **Production/operational status**
   - Current production capacity and scale
   - Facility locations
   - Recent operational changes (expansions, closures, restarts, acquisitions)
   - Technology or process innovations

2. **Client/partnership commitments**
   - Named brand partnerships or volume commitments (get specific names and dates)
   - Recent contract announcements
   - Strategic partnerships (fiber producers, manufacturers, retailers)
   - Customer testimonials or case studies

3. **Technical credentials**
   - LCA studies or carbon footprint data — look for specific numbers: kg CO2e, % reduction, system boundaries
   - Certifications (GOTS, OEKO-TEX, Bluesign, GRS, LWG, B Corp, ISO 14040/44)
   - Third-party verification studies (who reviewed, when)
   - EPDs (Environmental Product Declarations)
   - Environmental claims with quantified impact

4. **Financial/ownership context**
   - Funding rounds or investment announcements (amount, date, investors)
   - Ownership changes (PE acquisitions, restructuring, mergers)
   - Revenue/valuation if public
   - Bankruptcy, financial stress, or credit warnings (critical context — changes the entire approach)

**Key principle:** Look for NUMBERS and DATES. "11 brand commitments" beats "several partners." "Q4 2026 production restart" beats "upcoming launch." "−2 kg CO₂e per kg pulp" beats "low carbon footprint." If you can't find a number, flag it as a gap.

### Phase 2: Recent Context & Timeline

**Search for news from the last 3–6 months:**
- Product launches or production milestones
- Executive changes or strategic pivots
- Regulatory developments affecting the company
- Industry events, trade show appearances, or partnerships announced
- Market challenges, competitive threats, or public criticism
- Social media activity — LinkedIn posts from key stakeholders (what are they talking about?)

**Synthesize into:**
- **Recent wins:** What's going well — new clients, production milestones, funding, awards
- **Recent challenges:** What they're struggling with — delays, financial pressure, market shifts
- **Inflection points:** Major changes that shift their strategy — new regulation, new ownership, new market entry

### Phase 3: Pain Point Identification

Every pain point MUST have evidence. No assumptions.

**For suppliers/manufacturers, investigate:**

| Pain category | What to look for | Evidence sources |
|---|---|---|
| **Discovery/visibility** | Hard for brands to find them; rely on trade shows and word of mouth | No presence on sourcing platforms, limited digital marketing |
| **Data sharing anxiety** | IP protection concerns, NDA fatigue, competitor intelligence fears | Mentions of proprietary processes, reluctance to publish data |
| **Volume anxiety** | Need committed orders, not just interest signals | Small production runs, capacity utilization mentions, fundraising for scale-up |
| **Price premium justification** | Struggle to prove ROI of sustainable materials vs conventional | Price comparisons in press, "premium" language, cost reduction initiatives |
| **Credibility gaps** | Need third-party verification, trust rebuilding (esp. post-crisis) | Bankruptcy history, greenwashing accusations, lack of third-party LCA |
| **Regulatory compliance** | CSRD, Digital Product Passport, French Eco-Score, PEF pressure | EU-based or selling into EU, mentions of compliance preparation |
| **Repetitive data requests** | Multiple brands asking for same data in different formats | Large client base, manual PDF/email processes, complaints about admin burden |
| **Capacity constraints** | Can't scale production to meet demand | Waitlists, production timelines, facility expansion announcements |

**For brands/retailers, investigate:**

| Pain category | What to look for |
|---|---|
| **Supply chain transparency** | Don't know environmental impact of materials used |
| **Regulatory pressure** | CSRD Scope 3, ESPR, Digital Product Passport deadlines |
| **Greenwashing risk** | Need credible, verified sustainability data for claims |
| **Supplier discovery** | Can't find innovative/sustainable material sources at scale |
| **Cost pressures** | Sustainable materials cost more — need to justify to procurement |

**Output format for each pain point:**
```
Pain Point: [Clear, specific statement]
Evidence: [Quote, data point, or recent action that proves this pain exists]
Source: [URL + date]
Severity: [Critical / High / Medium — based on how urgently it affects their business]
```

### Phase 4: Strategic Positioning

Synthesize research into actionable approach:

1. **Opening hook:** What recent event or achievement gives you permission to reach out? (Specific — not generic congratulations)
2. **Primary value prop:** Which pain point can you solve most directly? Lead with this.
3. **Secondary angles:** What else can you address once the conversation opens?
4. **Proof points:** What evidence do you have that your solution works for companies like them?
5. **Likely objections:** What will they push back on? (Map to their specific situation, not generic objections)
6. **Key stakeholders:** Who to contact, their role, their likely perspective

---

## Phase 5: Carbonfact Value Mapping (Optional — use when in BD context)

When the research is being used to prepare outreach via the `bd-carbonfact-suppliers` skill, add this layer:

### Pain → Carbonfact Solution Mapping

For each pain point identified in Phase 3, map to a specific Carbonfact for Suppliers capability:

| Supplier pain | Carbonfact solution | Proof point |
|---|---|---|
| Discovery/visibility | Profile discoverable inside eco-design tools used by 200+ brands | Brands compare materials in real-time simulations |
| Data sharing anxiety | Brands see verified data + system boundary only — never the raw LCA document. Brand-by-brand access control, revocable anytime | Access control dashboard, NDA available |
| Repetitive data requests | One verified profile replaces per-brand PDF/NDA/email cycles | "Organize, don't duplicate" — Angle A |
| Credibility gaps | Free LCA verification by Carbonfact Science team (PEF-aligned, ISO 14040/44) | Verification at no cost, comparable methodology |
| Price premium justification | Verified environmental data lets brands quantify the impact advantage vs conventional | Eco-design simulations show the delta |
| Regulatory compliance | Brands under CSRD/PEF need product-level supplier data — suppliers who provide it get priority | French Eco-Score rollout, CSRD Scope 3 deadlines |
| Volume anxiety | Visibility to 200+ brands creates inbound demand pipeline | Brand discovery → access requests → commercial conversations |

### Messaging Alignment

Map the strongest pain point to the right prospecting angle:

| If strongest pain is... | Lead with angle... | Email sequence |
|---|---|---|
| Repetitive data requests / admin burden | **A — Organize, don't duplicate** | Sequence A or B |
| Discovery / need more brand relationships | **B — Be where sourcing happens** | Sequence A or B |
| Regulatory pressure / market access | **C — Regulation is your sales pitch** | Sequence B or C |
| Credibility rebuilding (post-crisis, no LCA) | **Free verification as trust signal** | Sequence C |
| Data sharing anxiety (dominant) | **Lead with access control + NDA** in opening | Any sequence, modify opener |

### Objection Pre-Loading

Based on the pain points, predict which objections from `references/objection-handling.md` will surface:

| Pain profile | Likely objection | Pre-load response |
|---|---|---|
| Data sharing anxiety is high | "What about confidentiality?" | Objection #1 — lead with "you never share the actual LCA document" |
| Already has own platform/library | "We already manage our own data" | Custom — position as complementary layer, not replacement |
| Financial stress / post-crisis | "Why is it free?" | Objection #2 — "brands pay, not suppliers" + free verification rebuilds trust |
| Large existing client base | "We already share with our clients directly" | Objection #3 — "PDFs mean version control issues + no discoverability" |
| No LCA at all | "We don't have the data yet" | Objection #8 — "critical review not mandatory, free assessment" |
| Competitor platform in use | "We already use [competitor]" | Competitive positioning — see `references/competitive-positioning.md` |

### Bridge to BD Skill Output

When this research feeds into the BD pipeline, output a summary block that can be directly consumed:

```
## Research Summary for BD Pipeline

### Classification Inputs
- Suggested Tier: [1/2/3] — based on [LCA maturity evidence]
- Suggested Phase: [0/1/2/3] — based on [engagement signals]
- ICP Score Inputs:
  - LCA Maturity: [X/20] — [evidence]
  - Client Base Quality: [X/20] — [named clients + regulatory exposure]
  - Regulatory Exposure: [X/20] — [geography + regulations]
  - Material Innovation: [X/20] — [material type + differentiation]
  - Engagement Readiness: [X/20] — [contact quality + activity level]

### Personalization Ammunition
- Opening hook: [specific recent event/achievement]
- Brand overlap with Carbonfact clients: [which brands they work with that are also Carbonfact clients]
- Regulation angle: [most relevant regulation + deadline]
- Competitor presence: [are competitors on Carbonfact already?]
- Referral potential: [who in their network could they refer?]

### Recommended Angle: [A/B/C + custom variant if needed]
### Predicted Top Objection: [#X from objection-handling.md]
### Contact Priority: [Name, Title — why they're the right entry point]
```

---

## Output Structure

```markdown
# [COMPANY NAME] — B2B Prospect Profile

## Company Overview
- **Product/Service:** [What they make/do — be specific about materials/processes]
- **Location:** [Facilities, HQ, key markets]
- **Stage:** [Startup / Scale-up / Enterprise / Post-restructuring]
- **Production status:** [Active / Scaling / Restarting / Pilot]
- **Notable clients:** [Named brands with dates if possible]

## Current Situation (Last 3–6 Months)
- **Operational status:** [Where they are today]
- **Recent developments:** [Key news, milestones, changes — with dates]
- **Strategic focus:** [What they're prioritizing now]
- **Financial context:** [Funding, ownership, stress indicators]

## Technical Credentials
- **LCA/Carbon data:** [Specific numbers: kg CO₂e, % reduction, system boundary, methodology]
- **Certifications:** [List with issuing body]
- **Third-party verification:** [Who reviewed, when, what they found]
- **Quantified impact:** [Numbers that matter for brand conversations]
- **Data gaps:** [What environmental data is missing or unverified]

## Pain Points (Ranked by Severity)

### 1. [Most Critical Pain] — Severity: Critical
- **Evidence:** [Specific source/quote/data point]
- **Source:** [URL + date]
- **Business impact:** [What happens if unresolved]
- **Carbonfact solution:** [How the platform addresses this — if in BD context]

### 2. [Second Pain] — Severity: High
[Same structure]

### 3. [Third Pain] — Severity: Medium
[Same structure]

## Key Stakeholders
| Name | Title | Why they matter | Approach |
|---|---|---|---|
| [Name] | [Title] | [Decision-maker / influencer / champion] | [Email / LinkedIn / Referral] |

## Approach Strategy

### Opening (30 sec)
[Specific hook based on recent news — not generic]

### Key Questions to Ask
1. [Discovery question that surfaces Pain #1]
2. [Discovery question that surfaces Pain #2]
3. [Validation question about their current priorities]
4. [Question that reveals how they currently share environmental data]

### Value Prop Angles (ordered by fit)
1. **[Primary angle]:** [Why this resonates with their #1 pain]
2. **[Secondary angle]:** [Supporting angle]
3. **[Tertiary angle]:** [Long-term value]

### Likely Objections
1. **[Objection]** → [Counter-response tailored to their situation]
2. **[Objection]** → [Counter-response]

## Key Facts to Memorize (for the call)
- [Specific number + context]
- [Specific date + what happened]
- [Specific client name + relevance]
- [Specific regulation + deadline affecting them]

## Research Summary for BD Pipeline
[Include this section when feeding into bd-carbonfact-suppliers — see Phase 5]

## Sources
- [URL] — [Key finding + date accessed]
- [URL] — [Key finding + date accessed]
- [URL] — [Key finding + date accessed]
```

## Quality Checks

Before delivering the profile:

1. **Source verification:** Every claim must have a traceable source (URL + date). No invented pain points.
2. **Recency check:** Flag if most information is >12 months old. Prioritize last 3 months.
3. **Number specificity:** Replace vague claims ("low carbon") with quantified data ("−2 kg CO₂e/kg") wherever possible. Flag gaps explicitly.
4. **Pain validation:** Each pain point needs evidence from a source — not assumptions from the company's industry.
5. **Actionability:** The user should be able to walk into a meeting with this profile alone and sound informed.
6. **Stakeholder mapping:** At least one named contact with title and approach recommendation.

## Critical Reminders

- **Don't invent pain points** — only include what you can evidence from sources
- **Date everything** — "Company raised $X" needs "in [month/year]"
- **Verify claims** — If a source says "negative carbon footprint", find the actual number and methodology
- **Recent news first** — Last 3 months > last 3 years for understanding current situation
- **B2B context** — Focus on business impact, not general company description
- **Competitor awareness** — Note if competitors are already on Carbonfact for Suppliers or similar platforms
- **Network value** — Flag referral potential (their supplier network, brand clients, industry contacts)
