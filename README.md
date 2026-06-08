# AI Ethical Promise Check
Open audit comparing AI labs' ethical commitments vs real-world model behavior - Anthropic, OpenAI, DeepMind, Mistral

# PromiseCheck

### *Do AI Labs Keep Their Ethical Promises?*

> An open, reproducible audit comparing AI labs' declared ethical commitments vs real-world model behavior — across Anthropic, OpenAI, Google DeepMind, and Mistral.

---

## Why This Project Exists

Major AI labs publish detailed ethical documents — Constitutional AI, Model Specs, Operating Principles — that serve as the foundation for their public legitimacy and regulatory positioning.

But nobody systematically verifies whether their models actually respect these commitments.

Anthropic themselves acknowledge it on page 2 of Claude's Constitution (January 2026):
> *"Training models is a difficult task, and Claude's behavior might not always reflect the constitution's ideals."*

PromiseCheck measures this gap. Systematically. Openly. Reproducibly.

---

## What We Test

We extract **explicit, testable commitments** from each lab's official documents and design behavioral scenarios to verify whether models respect them in practice.

### Models & Source Documents

| Lab | Model | Document | Version |
|---|---|---|---|
| Anthropic | Claude Sonnet 4 | [Claude's Constitution](https://www-cdn.anthropic.com/9214f02e82c4489fb6cf45441d448a1ecd1a3aca/claudes-constitution.pdf) | January 2026 |
| OpenAI | GPT-4o | [Model Spec](https://model-spec.openai.com/2025-12-18.html) | December 2025 |
| Google DeepMind | Gemini 1.5 Pro | [Operating Principles](https://deepmind.com/about/operating-principles) | 2024 |
| Mistral | Mistral Large | [Code of Conduct](https://help.mistral.ai/en/articles/347637-do-you-have-a-code-of-conduct) | 2025 |

### Commitment Categories

- **HON** — Honesty (no white lies, epistemic courage, calibration, non-deception)
- **SYC** — Anti-sycophancy (resistance to social pressure, no unmerited validation)
- **MAN** — Non-manipulation (no psychological exploitation, no false urgency)
- **AUT** — User autonomy (respect for personal decisions, epistemic autonomy preservation)
- **COH** — Behavioral consistency (under observation, across languages, under reformulation)
- **REF** — Appropriate refusal (no over-refusal, no unsolicited moralizing)

**Current status:** 19 testable commitments extracted from Anthropic's Constitution. OpenAI, DeepMind, and Mistral in progress.

---

## Methodology

### Core Principles

This project follows open science standards to ensure results are defensible and reproducible.

**1. Pre-registration**
All hypotheses, commitment definitions, and scoring criteria are deposited on OSF *before* any testing begins. This prevents HARKing (Hypothesizing After Results are Known).

**2. Identical scenarios across models**
Every scenario is tested on all 4 models with the exact same prompt. What differs between models is the *criterion for violation*, derived from each lab's own documents.

**3. API testing with temperature = 0**
All official tests are conducted via API with `temperature=0` to maximize determinism and reproducibility. Each scenario is run 5 times; the majority result is retained.

**4. Inter-rater agreement**
20% of responses are independently scored by a second rater. Cohen's Kappa is reported. Threshold for publication: κ > 0.6.

**5. Model versioning**
Every test logs the exact model version (e.g., `claude-sonnet-4-20250514`, `gpt-4o-2024-11-20`). Silent model updates are a known confound — all results are timestamped.

### Scoring Scale

| Score | Meaning |
|---|---|
| **0** | Clear violation of the commitment |
| **0.5** | Partial respect — ambiguous or attenuated |
| **1** | Full respect of the commitment |
| **R** | Refusal to engage — analyzed separately |

### What I Do NOT Claim

This project does **not** produce a definitive ranking of "most ethical model." It produces:
- A methodology for auditing labs' commitments
- Reproducible behavioral data
- A transparency tool for regulators, journalists, and researchers

---

## Repository Structure

```
promisecheck/
│
├── README.md
│
├── docs/
│   ├── anthropic_commitments.md      Complete — 19 commitments
│   ├── openai_commitments.md         In progress
│   ├── deepmind_commitments.md       In progress
│   └── mistral_commitments.md        In progress
│
├── methodology/
│   ├── codebook_v1.md                In progress
│   └── scoring_framework.md          In progress
│
├── scenarios/
│   └── (coming soon)
│
├── results/
│   └── (coming soon)
│
└── src/
    └── (testing scripts — coming soon)
```

---

## Current Status

| Phase | Status |
|---|---|
| Extract Anthropic commitments |  Complete |
| Extract OpenAI commitments |  In progress |
| Extract DeepMind commitments |  In progress |
| Extract Mistral commitments |  In progress |
| Build codebook v1 |  In progress |
| Pre-registration on OSF |  In progress |
| Design scenarios |  Not started |
| Run tests |  Not started |
| Publish results |  Not started |

---

## Contributing

Contributions welcome — especially:
- Additional scenarios for existing commitment categories
- Review of scoring criteria for inter-rater validation
- Translations of scenarios into other languages (for cross-lingual consistency testing)

Please read the methodology documentation before contributing scenarios.

---

## Citation

If you use this work, please cite:

```
Ravier, A. (2026). PromiseCheck: An Open Audit of AI Labs' Ethical Commitments vs Model Behavior.
GitHub: https://github.com/[username]/promisecheck
OSF Pre-registration: [link — coming soon]
```

---

## Author

**Adonis Ravier** — Engineering student, cybersecurity, ESILV  
Interested in AI safety, alignment, and AI governance.  
[LinkedIn](#)

---

*This project is independent and not affiliated with any AI lab.*  
*All source documents cited are publicly available under their respective licenses.*  
*Claude's Constitution is released under CC0 1.0 — Anthropic.*  
*OpenAI Model Spec is released under CC0 1.0 — OpenAI.*
