# 🏭 BD Skill — Carbonfact for Suppliers

A Claude AI skill for prospecting, qualifying, and onboarding suppliers onto [Carbonfact for Suppliers](https://suppliers.carbonfact.com) — a free platform where factories showcase verified environmental data to 200+ fashion brands.

## What It Does

Feed it a supplier website, LinkedIn URL, or company name — and it runs a 12-step pipeline:

```
Supplier URL → Deep Research (4 phases) → Pain Points with Evidence
→ Classify (Tier 1/2/3) → Phase (0–3) → ICP Score (0–100)
→ Intro-Call Probability → Market Opportunity Map → Angle (from pain profile)
→ Pain-Injected Email Sequence → Objection Handling → Warm Referral → Next Action
```

The research phase does the heavy lifting: it fetches the company website, searches recent news, identifies evidence-backed pain points, maps each pain to a Carbonfact solution, and feeds all of this into the email drafting step — so emails address the supplier's actual situation, not generic templates.

### Example Input

```
Prospect this supplier: https://www.circulose.com
Contact: Esther Haitink (Brand Partnership Director)
LinkedIn: https://www.linkedin.com/in/esther-haitink-02219751/
Context: They already work with GANNI, which is a Carbonfact client.
```

### Example Output

```
## Supplier Analysis: Circulose®

### Research Summary
- Product: Recycled dissolving pulp from 100% textile waste
- Stage: Post-bankruptcy restart (Altor acquisition June 2024)
- Production: Restarting Q4 2026 at Ortviken, Sweden
- Clients: H&M, Mango, M&S, Bestseller, C&A, Reformation + 5 more
- LCA: SCS 2017 study (negative carbon footprint) — data gap: no recent product-level numbers

### Pain Points Driving the Approach
- Pain #1: Credibility rebuilding post-bankruptcy → Free verification adds trust signal
- Pain #2: 60+ SKUs with zero published LCA per material → Environmental data portfolio
- Pain #3: GANNI (Carbonfact client) modeling without their real data → Bridge angle

### Email Drafts
[3 emails: opens with bankruptcy recovery, not "impressive you have an LCA"]
```

## Skill Structure

```
bd-carbonfact-suppliers/
├── SKILL.md                                  # Core logic (353 lines)
│   ├── How to Use
│   ├── 12-Step Pipeline
│   ├── Deep Research Instructions (→ references/deep-research.md)
│   ├── Supplier Segmentation (Tier 1/2/3)
│   ├── ICP Scoring Rubric (0–100)
│   ├── Phase Detection (0–3)
│   ├── Customer Pathway (Cold → Onboarded)
│   ├── Intro-Call Probability Model
│   ├── UVP Framework (Why/What/How)
│   ├── Pain-to-Email Injection Logic
│   ├── Output Template
│   └── Pointers → reference files
│
└── references/                               # Loaded on-demand
    ├── deep-research.md                      # 4-phase research methodology + pain mapping
    ├── email-sequences.md                    # Full Tier 1/2/3 email templates
    ├── objection-handling.md                 # 8 objections with scripted responses
    ├── competitive-positioning.md            # vs Vaayu, Fairly Made, consultancies
    ├── market-opportunity.md                 # EU/US regulation drivers + brand segments
    ├── linkedin-cadence.md                   # Parallel LinkedIn engagement timeline
    ├── faq.md                                # Real supplier questions + answers
    └── tracking-template.md                  # Pipeline tracker format
```

**Design principle**: Progressive disclosure. The core `SKILL.md` (353 lines) loads on every trigger. Reference files load only when needed — keeping context lean and responses fast. The `deep-research.md` file is always read first as Step 1 of the pipeline.

## Installation

### Claude.ai

1. Download the `bd-carbonfact-suppliers/` folder
2. Zip it: `zip -r bd-carbonfact-suppliers.skill bd-carbonfact-suppliers/`
3. Go to **Settings → Features → Skills**
4. Upload the `.skill` file and toggle it **on**
5. Make sure **Code execution and file creation** is enabled in **Settings → Capabilities**

### Claude Code

```bash
git clone https://github.com/nicoeos/Skills-BD-CFS.git
cp -r Skills-BD-CFS/bd-carbonfact-suppliers ~/.claude/skills/
```

## How to Use

Provide any combination of:

| Input | Example | Required? |
|---|---|---|
| **Company website** | `https://www.manteco.com` | Strongly recommended |
| **Material/process** | "recycled polyester yarn" | Helpful if not on website |
| **Contact LinkedIn** | `https://linkedin.com/in/jane-doe` | Helps personalization |
| **Company name** | "Manteco" | Minimum if no URL |
| **Additional context** | "Met them at ISPO", "A brand referred them" | Improves accuracy |

**Minimum**: a company name or website URL.

### Sample Prompts

```
"Prospect this supplier: https://www.manteco.com — they make recycled wool fabrics"
```

```
"Draft outreach for EcoFiber SRL, contact is Maria Rossi (Head of Sustainability).
They have GRS certification and sell to VF Corp."
```

```
"I met this supplier at Première Vision, here's their site: [URL].
They seem interested but worried about data privacy."
```

## Core Frameworks

### Supplier Segmentation

| Tier | Profile | Angle |
|---|---|---|
| **Tier 1** — LCA-Ready | Has LCA, sells to regulated brands, next-gen materials | "You already have the data — let it work harder for you." |
| **Tier 2** — LCA-Aware | Has env data but unstructured, mid-market brands | "Your clients are starting to ask — be ready before they demand it." |
| **Tier 3** — No LCA | No documentation, wants to enter regulated markets | "Your competitors are getting verified — don't fall behind." |

### ICP Scoring (0–100)

| Criterion | Weight |
|---|---|
| LCA Maturity | /20 |
| Client Base Quality | /20 |
| Regulatory Exposure | /20 |
| Material Innovation | /20 |
| Engagement Readiness | /20 |

### Prospecting Angles

| Angle | Premise | Best for |
|---|---|---|
| **A** — Organize, don't duplicate | One profile replaces repetitive PDF/NDA per brand | Tier 1–2 |
| **B** — Be where sourcing happens | 200+ brands compare materials on Carbonfact daily | Tier 1, 3 |
| **C** — Regulation is your sales pitch | CSRD/PEF/French Eco-Score make LCA data a requirement | Tier 2–3 |

## Multilingual Support

The skill replies in the language of your input. Email drafts are adapted to the target recipient's language and local business norms — not just translated.

## What This Skill Does NOT Do

- Brand-side prospection (separate concern)
- Negotiate pricing for paid LCA services (escalate to Carbonfact Science team)
- Provide legal advice on NDAs (redirect to Carbonfact legal)

## Key References

| Resource | URL |
|---|---|
| Carbonfact for Suppliers | https://suppliers.carbonfact.com |
| Example Supplier Profile | https://suppliers.carbonfact.com/en/processes/73908f26-333e-4934-a1e9-0c7163e6bedc |
| Carbonfact Main Platform | https://www.carbonfact.com |
| Carbonfact Customers | https://www.carbonfact.com/customers |
| Trust Center (Data Security) | https://trust.carbonfact.com |

## Contributing

1. Fork the repo
2. Edit the relevant file in `references/`
3. Open a PR with context on what changed and why

Keep `SKILL.md` under 500 lines. Move detailed content to `references/`.

## License

MIT
