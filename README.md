# Privacy Impact Assessment Agent

An AI agent skill framework for conducting structured, legally-grounded Privacy Impact Assessments (PIAs) and enforcing security best practices in AI-assisted workflows.

## Overview

This repository provides two skill files designed to be loaded into an AI agent (such as Claude) to give it the knowledge and methodology to:

1. **Guide organizations through Privacy Impact Assessments** — from initial scoping to a final governance-ready document with statutory citations, risk scoring, and actionable recommendations.
2. **Apply security guardrails** — protecting against prompt injection, insecure code generation, sensitive data leakage, and unauthorized actions during AI-assisted workflows.

The framework is particularly suited for Canadian jurisdictions (federal PIPEDA, BC PIPA, Alberta PIPA, Quebec Law 25) and GDPR-regulated environments, though the methodology is adaptable to other frameworks.

---

## Repository Structure

```
Privacy_Impact_Assessment_Agent/
├── PIA_skill.md        # Full PIA methodology, question bank, risk framework, and legislative reference
└── Security_Skill.md  # Security protocols for AI agents handling sensitive data and workflows
```

---

## PIA Skill (`PIA_skill.md`)

### What It Does

When loaded into an AI agent, this skill enables the agent to conduct a complete, multi-phase Privacy Impact Assessment:

| Phase | Description |
|-------|-------------|
| **0 – Intake & Scoping** | Determine whether a PIA is required, at what depth, and which jurisdictions apply |
| **1 – Information Gathering** | Structured question bank across 8 sections covering data inventory, flows, legal basis, and privacy-by-design |
| **2 – Risk Assessment** | Score identified risks using a Likelihood × Impact matrix (1–9 scale) |
| **3 – Document Drafting** | Produce a complete PIA document with specific statutory citations |
| **4 – Recommendations** | Summarize top risks, assign mitigations, and issue a Proceed / Proceed with Conditions / Do Not Proceed decision |

### Question Bank Sections

1. Initiative description and business context
2. Stakeholder roles and accountability
3. Personal information inventory (data elements, subjects, sensitivity)
4. Data flows — collection, use, disclosure, retention, and storage
5. Legal and regulatory compliance
6. Privacy by Design assessment
7. Risk identification
8. Mitigations and residual risk acceptance

### Risk Scoring

Risks are scored using a 3×3 matrix:

```
               Impact
              Minor | Moderate | Severe
Likelihood  ───────────────────────────
Unlikely  │   1   │    2     │   3
Possible  │   2   │    4     │   6
Likely    │   3   │    6     │   9

Low: 1–2  |  Medium: 3–4  |  High: 6–9
```

### Legislative Reference

The skill includes detailed statutory provisions and key enforcement decisions for:

- **PIPEDA** (Federal) — 10 Schedule 1 principles, breach notification (s. 10.1), third-party accountability. https://laws-lois.justice.gc.ca/eng/acts/P-8.6/index.html  
- **BC PIPA** (SBC 2003, c. 63) — Consent structure, access Part 7-8. https://www.bclaws.gov.bc.ca/civix/document/id/complete/statreg/03063_01
- **Alberta PIPA** (SA 2003, c. P-6.5) — Breach notification (s. 34.1), employee-specific provisions, 45-day access rights (s.28) https://kings-printer.alberta.ca/documents/Acts/P06P5.pdf 
- **Quebec Law 25** (Bill 64) — Mandatory PIA before project launch (s. 3.3), Privacy by Default (s. 9), portability (s.27) and deletion rights (s.23), significant penalties (s.90.1, 90.12). https://www.legisquebec.gouv.qc.ca/fr/document/lc/p-39.1?langCont=en
- Parts of Europe's GDPR and America's NIST


All citations distinguish between legal requirements and best practices, and flag compliance gaps explicitly.

---

## Security Skill (`Security_Skill.md`)

A comprehensive security reference for AI agents, covering nine domains:

1. **Prompt Injection Defense** — Content isolation, instruction detection protocol, social engineering defenses
2. **Input Validation & Sanitization** — File type validation, archive safety, parameterized queries
3. **Code Generation Security** — Secure coding standards: credentials, cryptography, SQL, serialization, logging
4. **Sensitive Data Handling** — Classification rules, transmission and storage requirements, no secrets in version control
5. **Skill & Plugin Security** — Principle of Least Surprise review checklist for third-party skills
6. **Web & Browser Security** — Safe navigation, no credential entry in web forms, content restrictions
7. **Action Authorization** — Three-tier matrix: Prohibited / Requires Explicit Permission / Autonomous
8. **Environment & Infrastructure Security** — Sandbox discipline, safe git practices
9. **Document & File Processing Security** — Office document safety, macro handling

---

## Usage

### Loading the Skills into an Agent

These files are designed to be provided to an AI agent as context (e.g., via a system prompt, uploaded document, or agent skill configuration). Example trigger instruction for the PIA skill:

> "Use this skill whenever a user wants to conduct, draft, complete, or review a Privacy Impact Assessment."

For Claude Code or similar CLI tools, you can reference these files directly when starting a session.

### Running a PIA

Once the skill is loaded, initiate a PIA by asking the agent:

> "I need to conduct a Privacy Impact Assessment for [project/initiative]."

The agent will:
1. Ask scoping questions to determine jurisdiction and depth
2. Work through the information-gathering question bank
3. Score identified risks
4. Draft a structured PIA document with citations
5. Produce a recommendation and sign-off block

### Output Format

The final PIA document includes:

- Executive Summary
- Initiative Description
- Stakeholder Roles
- Personal Information Inventory
- Data Flow Description
- Legal Basis and Compliance
- Privacy by Design Evaluation
- Risk Assessment Table
- Recommendations and Mitigations
- Sign-off Block (Privacy Officer / Legal Counsel / Business Owner)

Output is delivered in Markdown by default; Word document export is available via a compatible docx skill.

---

## Supported Jurisdictions

| Jurisdiction | Framework | Mandatory PIA Trigger |
|---|---|---|
| Canada (Federal) | PIPEDA | High-risk processing; OPC guidance |
| British Columbia | BC PIPA | Best practice; high-risk scenarios |
| Alberta | Alberta PIPA | Best practice; breach risk reduction |
| Quebec | Law 25 (Bill 64) | Required before new IT systems/services (s. 3.3) |
| European Union | GDPR | Required for high-risk processing (Art. 35) |

---

## No Installation Required

This is a documentation-only repository. There are no dependencies, build steps, or runtime requirements. Simply load the Markdown files into your agent environment.

---

## License

License not yet specified. Contact the repository owner for usage rights.
