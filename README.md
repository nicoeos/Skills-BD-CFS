# Skills-BD-CFS
# 🏭 BD Skill — Carbonfact for Suppliers

A Claude AI skill for prospecting, qualifying, and onboarding suppliers onto [Carbonfact for Suppliers](https://suppliers.carbonfact.com) — a free platform where factories showcase verified environmental data to 200+ fashion brands.

## What It Does

Feed it a supplier website, LinkedIn URL, or company name — and it runs an 11-step pipeline:

```
Supplier URL → Research → Classify (Tier 1/2/3) → Phase (0–3) → ICP Score (0–100)
→ Intro-Call Probability → Market Opportunity Map → Prospecting Angle Selection
→ Personalized Email Sequence → Objection Handling → Warm Referral Strategy → Next Action
```

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

### Classification
- Tier: 1 — Next-gen recycled cellulose pulp, 60+ material SKUs, TextileGenesis traceability
- Phase: 1 — Aware but Passive (deep sustainability infra, no standardized LCA sharing)
- ICP Score: 87/100

### Intro Call Probability
- Score: 75 points → High (>70%)

### Email Drafts
[3 fully personalized emails with GANNI bridge angle...]

### Top 3 Objections & Responses
[Tailored to their existing Material Library and traceability solution...]
```

## Skill Structure

```
bd-carbonfact-suppliers/
├── SKILL.md                                  # Core logic (269 lines)
│   ├── How to Use
│   ├── 11-Step Pipeline
│   ├── Supplier Segmentation (Tier 1/2/3)
│   ├── ICP Scoring Rubric (0–100)
│   ├── Phase Detection (0–3)
│   ├── Customer Pathway (Cold → Onboarded)
│   ├── Intro-Call Probability Model
│   ├── UVP Framework (Why/What/How)
│   ├── Output Template
│   └── Pointers → reference files
│
└── references/                               # Loaded on-demand
    ├── email-sequences.md                    # Full Tier 1/2/3 email templates
    ├── objection-handling.md                 # 8 objections with scripted responses
    ├── competitive-positioning.md            # vs Vaayu, Fairly Made, consultancies
    ├── market-opportunity.md                 # EU/US regulation drivers + brand segments
    ├── linkedin-cadence.md                   # Parallel LinkedIn engagement timeline
    ├── faq.md                                # Real supplier questions + answers
    └── tracking-template.md                  # Pipeline tracker format
```

**Design principle**: Progressive disclosure. The core `SKILL.md` (269 lines) loads on every trigger. Reference files (~490 lines total) load only when needed — keeping context lean and responses fast.

## Installation

### Claude.ai (Recommended)

1. Download the `.skill` file
2. Go to **Settings → Features → Skills**
3. Upload the `.skill` file
4. Toggle it **on**
5. Make sure **Code execution and file creation** is enabled in **Settings → Capabilities**

### Claude Code

```bash
# Clone and copy to your skills directory
git clone https://github.com/nicoeos/bd-carbonfact-suppliers.git
cp -r bd-carbonfact-suppliers ~/.claude/skills/
```

### Manual

Copy the `bd-carbonfact-suppliers/` folder (with `SKILL.md` + `references/`) into your Claude skills directory.

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

```
"Compare how we should position against Vaayu when talking to this supplier."
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

Supported: English, French, Spanish, German, Italian, and any other language Claude supports.

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

Found a better objection response? A regulation update? A new prospecting angle that converts?

1. Fork the repo
2. Edit the relevant file in `references/`
3. Open a PR with context on what changed and why

Keep `SKILL.md` under 300 lines. Move detailed content to `references/`.

## License

MIT
