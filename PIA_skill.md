---
name: privacy-impact-assessment
description: >
  Use this skill whenever a user wants to conduct, draft, complete, or review a Privacy Impact Assessment (PIA) — also called a Data Protection Impact Assessment (DPIA) or Privacy Risk Assessment. Trigger this skill when the user mentions assessing privacy risk for a new system, feature, dataset, vendor relationship, AI tool, data sharing arrangement, or any initiative that collects, uses, or discloses personal information. Also trigger when the user asks to "assess the privacy implications of X", "do a PIA", "run a DPIA", or asks what privacy risks exist for a given use case. This skill guides a thorough, structured assessment using a proven framework — always use it rather than improvising a PIA from scratch.
---

# Privacy Impact Assessment (PIA) Skill

This skill guides an AI agent through conducting a structured, rigorous Privacy Impact Assessment for any data processing activity. The output is a complete, professional PIA document suitable for internal governance, regulatory compliance, or legal review.

---

## Overview

A Privacy Impact Assessment is a structured process for identifying and mitigating privacy risks before (or during) a data processing activity. PIAs are required or strongly recommended under many privacy frameworks including PIPEDA, Quebec Law 25, GDPR, and sector-specific laws. Even where not legally mandatory, they represent best-practice governance.

This skill produces PIAs aligned with:
- **Canadian federal law**: PIPEDA (Personal Information Protection and Electronic Documents Act)
- **Canadian provincial law**: Quebec Law 25 (Bill 64 / Act respecting the protection of personal information in the private sector), BC PIPA (Personal Information Protection Act, SBC 2003, c. 63), Alberta PIPA (Personal Information Protection Act, SA 2003, c. P-6.5), and provincial health privacy equivalents (PHIPA, HIA)
- **GDPR**: Art. 35 DPIA requirements (EU standard)
- **General best practice**: ISO 29134, NIST Privacy Framework

Read `references/legislative-reference.md` for a jurisdiction-by-jurisdiction breakdown of key statutory provisions and enforcement decisions to cite in the PIA.

---

## Agent Workflow

Follow these phases in order. Do not skip phases. Adapt tone to the user's context (legal, technical, business).

### Phase 0 — Intake and Scoping

Before beginning the assessment, establish whether a PIA is needed and at what depth. Ask the user:

> "Before we start the full assessment, let me ask a few scoping questions so we can calibrate the depth of this PIA."

**Scoping questions (ask all of these):**

1. **What is the initiative?** Describe the system, feature, program, vendor, or data activity being assessed.
2. **What personal information is involved?** (e.g., names, contact info, health data, financial data, location, behavioural data, biometrics, government IDs)
3. **Is this new, or a change to an existing process?** New = full PIA; significant change = focused PIA.
4. **What jurisdiction(s) apply?** (Federal Canada / Quebec / BC / Alberta / Ontario / EU / US / other)
5. **Has any legal or privacy review already happened?** Note prior work to avoid duplication.
6. **What is the timeline?** PIAs done post-launch are remediation exercises — flag this if applicable.

**Trigger a High-Risk flag (→ full PIA required) if any apply:**
- Processing of sensitive personal information (health, financial, biometric, sexual orientation, religion, ethnicity)
- Large-scale processing (volume, velocity, or variety above routine operations)
- Use of automated decision-making or AI/ML that affects individuals
- Systematic monitoring or profiling of individuals
- Data sharing with third parties, vendors, or across borders
- New technology with uncertain privacy implications
- Vulnerable populations (minors, patients, employees under power imbalance)

If no high-risk factors apply, note that a lighter-touch Privacy Review may suffice — but offer to complete a full PIA anyway.

---

### Phase 1 — Information Gathering

Work through each section below. For each, ask the questions provided, record answers, and flag gaps. Tell the user you will go section by section and they can answer in plain language.

Read `references/pia-questions.md` for the full question bank. Use it to probe deeper where answers are thin.

---

### Phase 2 — Risk Assessment

For each privacy risk identified, score it on two dimensions:

**Likelihood** (how probable is this risk materializing?)
- 1 = Unlikely
- 2 = Possible
- 3 = Likely

**Impact** (how serious would harm be to individuals?)
- 1 = Minor inconvenience
- 2 = Significant harm (financial loss, reputational damage, distress)
- 3 = Severe harm (discrimination, physical harm, loss of fundamental rights)

**Risk Score** = Likelihood × Impact (1–9)
- 1–2: Low — document and monitor
- 3–4: Medium — mitigate with standard controls
- 6–9: High — must mitigate before proceeding; escalate if unresolvable

Apply the risk matrix to each identified risk before drafting mitigations.

---

### Phase 3 — Draft the PIA Document

Once information is gathered, produce the full PIA document using the structure in `references/pia-template.md`.

**Drafting rules:**
- Write in plain language; avoid jargon where possible
- Be specific — vague statements like "data is protected" are not acceptable
- Every identified risk must have a corresponding mitigation
- Residual risk must be acknowledged and signed off
- Flag any items that require legal review, DPA consultation, or executive sign-off
- If information was not provided, note it as a **gap requiring follow-up** rather than omitting it
- **Cite specific legislation**: Every legal requirement identified in Section 5 must cite the specific statutory provision (e.g., "PIPEDA, Schedule 1, Principle 4.3" or "BC PIPA, s. 11"). Do not state a legal requirement without its source.
- **Cite enforcement decisions where relevant**: Where an identified risk has been the subject of a regulatory finding, Commissioner investigation, or court decision, note the case reference. Use `references/legislative-reference.md` for known citations; flag where the user should obtain additional legal research.
- **Distinguish legal requirements from best practice**: Clearly mark each compliance item as either a statutory requirement (citing the provision) or a recommended best practice (noting the source framework, e.g., ISO 29134 §8.4).

---

### Phase 4 — Recommendations and Sign-Off Guidance

Close the PIA with:

1. **Summary of key risks** (top 3–5, with scores)
2. **Recommended mitigations** with owners and timelines
3. **Recommended decision**: Proceed / Proceed with conditions / Do not proceed
4. **Sign-off requirements**: who needs to approve (privacy officer, legal, executive, DPA)
5. **Review trigger**: when this PIA should be revisited (e.g., after 2 years, or if the scope changes materially)

---

## Output Format

Produce the PIA as a structured document with clear section headers. If the user wants a Word document, use the docx skill. If they want it in the chat, use markdown with headers.

Default output order:
1. Cover page (title, date, author, version, classification)
2. Executive Summary
3. Sections 1–8 (see template)
4. Risk Register table
5. Recommendations
6. Sign-off block

---

## Important Caveats to Include in Every PIA

Always include this note in the final document:

> *This Privacy Impact Assessment was prepared as a structured analysis tool. It does not constitute legal advice. Organizations should seek advice from qualified privacy counsel and, where required, consult with their applicable Data Protection Authority before proceeding with high-risk processing activities.*
-e 

---


# PIA Question Bank

This reference contains the full question set for each PIA section. The agent should use these to probe for complete answers during Phase 1 information gathering. Not every question applies to every initiative — use judgment. Follow up on thin or vague answers.

---

## Section 1: Initiative Description

**Purpose:** Establish what is being assessed and why.

- What is the name of the initiative, system, feature, or program?
- What problem does it solve or what business objective does it serve?
- Who is the internal owner / business sponsor?
- What is the current status? (concept, design, build, testing, live)
- What is the planned launch date or timeline?
- Is this a new initiative or a change to an existing one? If a change, what is changing?
- Has this initiative (or a similar one) been assessed before? If so, what changed?
- Are there any regulatory, contractual, or policy drivers for this initiative?

---

## Section 2: Stakeholders and Accountability

**Purpose:** Identify who is responsible for privacy decisions.

- Who is the Privacy Officer or privacy contact for this initiative?
- Who owns data governance for this initiative?
- Who are the key business stakeholders?
- What legal/compliance team has (or should have) oversight?
- If third-party vendors are involved: who manages those vendor relationships?
- Is there a Data Protection Officer (DPO) appointed? (required under GDPR and Quebec Law 25 for some organizations)

---

## Section 3: Personal Information Inventory

**Purpose:** Identify exactly what personal information is involved.

### 3a. Data Elements

- What categories of personal information are collected, used, or disclosed? (Check all that apply)
  - Identifiers: name, address, email, phone, IP address, device ID, cookies
  - Government identifiers: SIN, health card number, passport, driver's licence
  - Financial: income, credit score, account numbers, transaction history
  - Health and medical: diagnoses, prescriptions, mental health, genetic data
  - Biometric: fingerprints, facial recognition, voice print, retina scan
  - Location: GPS coordinates, geofencing, movement history
  - Behavioural: browsing history, purchase history, app usage patterns
  - Communications: emails, messages, call records
  - Employment: performance reviews, salary, HR records, disciplinary records
  - Social: relationships, social media activity, group memberships
  - Sensitive characteristics: race/ethnicity, religion, sexual orientation, political views
  - Other (describe):

- For each category identified: Is this data element strictly necessary for the purpose, or could the purpose be achieved without it?
- Are any of these data elements inferred, derived, or generated (vs. directly collected)?

### 3b. Data Subjects

- Who are the individuals whose personal information is being processed?
  - Customers / consumers
  - Employees / HR
  - Job applicants
  - Minors (under 18)
  - Patients / health care recipients
  - Members of the public
  - Other (describe)
- Are any data subjects members of a vulnerable population (minors, elderly, people with disabilities, people under an economic or power imbalance)?
- Approximately how many individuals are affected?
- Are data subjects aware that their information is being processed? How?

### 3c. Volume and Sensitivity

- What is the approximate volume of records? (ballpark is fine)
- Is this a one-time dataset or ongoing/continuous collection?
- Does the data include any sensitive personal information (health, financial, biometric, government ID, sensitive characteristics)?

---

## Section 4: Data Flows

**Purpose:** Map where data comes from, where it goes, and how it moves.

### 4a. Collection

- How is personal information collected? (e.g., web form, app, API, purchase transaction, sensor, CCTV, scraping, third-party purchase)
- Is collection direct (from the individual) or indirect (from another source)?
- What notice is provided to individuals at the point of collection?
- Is consent obtained? If so, what type (express, implied, opt-in, opt-out)?
- Is there a lawful basis for collection other than consent? (e.g., contractual necessity, legal obligation, legitimate interest)

### 4b. Use

- What is the primary purpose for collecting this personal information?
- Are there any secondary uses? (e.g., analytics, product development, marketing, research)
- Are secondary uses consistent with the original purpose individuals were told about?
- Is personal information used in automated decision-making? Does the automated decision have legal or significant effects on individuals?
- Is AI, machine learning, or profiling involved? Describe the model inputs and outputs.

### 4c. Disclosure and Sharing

- Is personal information shared with any third parties? List them.
  - Service providers / processors
  - Business partners
  - Affiliated entities / group companies
  - Government or regulatory bodies
  - Research institutions
  - Data brokers
  - Other (describe)
- For each third party: What data do they receive? For what purpose? Under what agreement?
- Is any data transferred across borders? To which countries?
- Are any receiving countries considered adequate under the applicable privacy law (e.g., GDPR adequacy, PIPEDA Schedule 1)? If not, what safeguards apply?

### 4d. Retention and Disposal

- How long is personal information retained?
- Is the retention period tied to a legal obligation, business need, or contractual requirement? Which?
- How is personal information disposed of when no longer needed? (deletion, anonymization, destruction)
- Is there a documented retention schedule?

### 4e. Storage and Security

- Where is the data stored? (on-premise, cloud, vendor-hosted — specify region/country)
- What security controls are in place? (encryption at rest, in transit, access controls, logging, penetration testing, SOC 2, ISO 27001, etc.)
- Who has access to the personal information? Is access limited by role or need-to-know?
- Are there audit logs for access to personal information?
- What is the incident response / breach notification process?

---

## Section 5: Legal and Regulatory Compliance

**Purpose:** Assess compliance with applicable privacy law. Every legal requirement identified must be cited to its specific statutory provision. Where relevant enforcement decisions exist, note them.

**Citation standard:** Do not state "the law requires X" — state "PIPEDA, Schedule 1, Principle 4.3 requires X" or "BC PIPA, s. 11(1) requires X." Use `references/legislative-reference.md` for a ready-made citation reference. Flag items needing additional legal research rather than leaving them uncited.

- What privacy law(s) apply to this initiative? (PIPEDA / Quebec Law 25 / BC PIPA / Alberta PIPA / PHIPA / GDPR / CCPA / HIPAA / other)
  - **BC PIPA applies** if the organization is a private-sector organization operating in BC collecting PI of BC residents in employment or commercial contexts (BC PIPA, s. 3)
  - **Alberta PIPA applies** if the organization is a private-sector organization operating in Alberta (Alberta PIPA, s. 4)
  - Note: BC and Alberta are "substantially similar" jurisdictions under PIPEDA — PIPEDA does not apply to provincially-regulated activities within those provinces (PIPEDA, s. 26(2)(b))
- Is there a Privacy Policy / Notice that covers this processing? Is it accurate and up to date?
- Does this processing require individual consent? Has that consent mechanism been designed and tested?
  - Under BC PIPA: consent required for collection, use, and disclosure (ss. 6, 11, 16); consent may be express or implied depending on sensitivity (s. 8)
  - Under Alberta PIPA: consent required (ss. 7, 14, 19); reasonable person standard for implied consent (s. 8)
- Does the organization have a legal basis for processing under each applicable law?
- Are individuals' rights honoured? (right to access, correction, deletion, withdrawal of consent, portability, objection)
- Is there a process for individuals to exercise these rights?
- Are data processing agreements in place with all vendors who process personal data on behalf of the organization?
- Are there any sector-specific requirements that apply? (e.g., OSFI, FINTRAC, PHIPA, FERPA)
- Does this initiative require a mandatory DPIA under GDPR Art. 35 or a PIA under Quebec Law 25, s. 3.3?
- If applicable: Has a Data Protection Authority (DPA) consultation been completed or planned?

### BC PIPA — Specific Questions

Ask these if BC PIPA applies:

- Has the organization appointed a privacy officer with responsibility under BC PIPA, s. 11?
- Is collection limited to what a reasonable person would consider appropriate for the purposes (BC PIPA, s. 11(2))?
- Is notice of collection being provided as required (BC PIPA, s. 10)?
- For employee personal information: Is collection, use, or disclosure for a purpose that a reasonable person would consider appropriate, and is it reasonably required for the employment relationship (BC PIPA, ss. 13–15)?
- Has the organization prepared or updated its privacy policy as required (BC PIPA, s. 5)?
- Are individuals' access and correction rights being honoured within 30 business days (BC PIPA, ss. 23–24)?
- For security: Are security arrangements appropriate to the sensitivity of the information (BC PIPA, s. 34)?
- Does the initiative involve cross-border transfers? BC PIPA requires comparable protection when transferring PI to service providers outside BC (BC PIPA, s. 33.1, per OPC/OIPC guidance); note any gap.

### Alberta PIPA — Specific Questions

Ask these if Alberta PIPA applies:

- Has the organization designated a Privacy Officer (Alberta PIPA, s. 16)?
- Is collection limited to what is reasonable for the purposes (Alberta PIPA, s. 11)?
- Is notice of collection being provided (Alberta PIPA, s. 13)?
- For employee personal information: Is collection, use, or disclosure for the purposes of managing or terminating the employment relationship (Alberta PIPA, ss. 15–17, 21–23)?
- Has the organization prepared a privacy policy and made it available (Alberta PIPA, s. 5)?
- Are individuals' access and correction rights being honoured within 45 days (extendable) (Alberta PIPA, ss. 24–26)?
- For security: Are reasonable security arrangements in place (Alberta PIPA, s. 34)?
- Does the initiative involve transfers to service providers outside Alberta? Alberta PIPA requires comparable protection (Alberta PIPA, s. 13.1 as interpreted; OPC guidance); note any gap.
- Does the initiative involve a "significant change" to information practices requiring notification of the OIPC? (Alberta PIPA, s. 64; OIPC guidance)

### Enforcement Decisions — Prompt Questions

Ask the user to confirm whether any of the following scenarios apply, and note relevant enforcement history from `references/legislative-reference.md`:

- Does the initiative involve employee monitoring or surveillance? (Multiple OIPC BC and Alberta findings; note relevant decision)
- Does the initiative involve biometric data? (Commissioner findings under PIPEDA and provincial equivalents)
- Does the initiative involve AI or automated profiling? (OPC position papers and PIPEDA findings)
- Does the initiative involve cross-border data transfers to the US, particularly involving US cloud providers? (OPC guidance on US CLOUD Act risk)
- Does the initiative involve sensitive health or financial information processed by a private-sector entity?

---

## Section 6: Privacy by Design

**Purpose:** Assess whether privacy has been built in, not bolted on.

- Was privacy considered from the start of the initiative's design, or is this PIA being done after the fact?
- Is the collection limited to the minimum data necessary (data minimization)?
- Have privacy-preserving technical alternatives been considered? (e.g., anonymization, aggregation, pseudonymization, synthetic data)
- Could the same objective be achieved with less personal information, or with anonymized data?
- Are default settings the most privacy-protective option (privacy by default)?
- Is the system designed to support individuals' rights (e.g., can data be deleted on request)?
- Has a privacy-aware security review (threat modeling) been done?
- Are there any accountability mechanisms (privacy logs, audit trails, breach detection)?

---

## Section 7: Risk Identification

**Purpose:** Identify specific privacy risks associated with this initiative.

Prompt the user to consider risks across these categories:

### Unauthorized Access / Data Breach
- What is the risk that personal information is accessed by unauthorized parties (external attack, insider threat, accidental exposure)?
- What would the harm be to affected individuals?

### Excessive Collection
- Is more data being collected than necessary? What is the risk that data is used beyond its stated purpose?

### Inaccurate or Outdated Data
- What is the risk that decisions are made based on inaccurate or stale personal information? What harms could result?

### Lack of Transparency
- Are individuals adequately informed about what is happening with their data? What is the risk of a trust or reputational harm if they find out through other means?

### Automated Decision-Making / Algorithmic Bias
- If AI/ML or automated decisions are involved: What is the risk of biased, discriminatory, or incorrect outcomes for individuals? What is the appeal or redress mechanism?

### Vendor / Third-Party Risk
- What is the risk that third parties with access to the data do not protect it adequately, use it for unauthorized purposes, or transfer it to additional parties?

### Cross-Border Transfer Risk
- What is the risk that data transferred outside the jurisdiction loses legal protection or is subject to foreign government access?

### Re-identification Risk
- If data has been de-identified or anonymized: What is the risk of re-identification, particularly when combined with other datasets?

### Individual Harm
- What is the worst-case harm to a specific individual if this initiative goes wrong? (financial loss, discrimination, safety risk, reputational damage, psychological harm, loss of liberty)

### Organizational / Regulatory Risk
- What is the risk of regulatory investigation, fine, or enforcement action?
- What is the reputational risk to the organization?

---

## Section 8: Mitigations

**Purpose:** Document what will be done to address identified risks.

For each risk identified in Section 7, document:

1. **Mitigation measure**: What specific control, design change, policy, or process will reduce this risk?
2. **Responsible party**: Who owns implementation of this mitigation?
3. **Timeline**: By when will this mitigation be in place?
4. **Residual risk**: After the mitigation, what risk remains? (re-score using the risk matrix)
5. **Acceptance**: Who is accepting the residual risk on behalf of the organization?

**Prompt questions:**
- Are there any risks for which no adequate mitigation exists? (These should trigger an escalation or a "do not proceed" recommendation)
- Are mitigations proportionate to the risk level?
- Are mitigations feasible within the initiative's timeline and budget?
- Are there mitigations that would require changes to the initiative's design, scope, or technology? Have those been communicated to the business sponsor?
-e 

---


# PIA Document Template

Use this template to produce the final PIA document. Fill in all sections based on information gathered in Phase 1. Flag gaps explicitly. Do not leave sections blank without a notation.

---

# PRIVACY IMPACT ASSESSMENT

| Field | Value |
|---|---|
| **Initiative Name** | [Name] |
| **PIA Reference Number** | [e.g., PIA-2025-001] |
| **Date Prepared** | [Date] |
| **Prepared By** | [Name / Role] |
| **Privacy Officer Reviewed** | [Name / Date — or "Pending"] |
| **Version** | [e.g., 1.0 Draft / 2.0 Final] |
| **Classification** | [e.g., Confidential — Internal Only] |

---

## Executive Summary

*2–4 paragraph summary covering:*
- *What the initiative is and why it processes personal information*
- *Key privacy risks identified*
- *Overall risk level (Low / Medium / High)*
- *Recommended decision (Proceed / Proceed with conditions / Do not proceed)*
- *Key conditions or mitigations required before proceeding*

---

## Section 1: Initiative Description

**1.1 Overview**
[Describe the initiative, its purpose, and its business context in 1–3 paragraphs.]

**1.2 Status and Timeline**
[Current status and planned dates.]

**1.3 Scope of this PIA**
[What is in scope and out of scope for this assessment.]

**1.4 Prior Reviews**
[Note any prior PIAs, legal reviews, or security assessments. If none, state "None identified."]

---

## Section 2: Stakeholders and Accountability

| Role | Name / Team |
|---|---|
| Business Sponsor | |
| Initiative Owner | |
| Privacy Officer | |
| Legal / Compliance Lead | |
| Security Lead | |
| Data Protection Officer (if applicable) | |
| Vendor Privacy Contacts (if applicable) | |

---

## Section 3: Personal Information Inventory

**3.1 Data Elements Collected or Used**

| Category | Specific Elements | Necessary? | Sensitive? |
|---|---|---|---|
| [e.g., Identifiers] | [e.g., name, email, IP address] | Yes / No / Partial | Yes / No |
| | | | |

**3.2 Data Subjects**

| Population | Approximate Volume | Vulnerable? |
|---|---|---|
| [e.g., Customers] | [e.g., ~50,000] | [Yes/No — explain if yes] |
| | | |

**3.3 Data Minimization Assessment**
[Is the data collected the minimum necessary for the stated purpose? Are any elements that could be eliminated noted here?]

---

## Section 4: Data Flows

**4.1 Collection**
[How and where is personal information collected? What notice and consent mechanisms are in place?]

**4.2 Use and Purpose**
[Primary and secondary uses. Note any automated decision-making or AI/ML processing.]

**4.3 Disclosure and Third-Party Sharing**

| Recipient | Data Shared | Purpose | Agreement in Place? | Cross-Border? |
|---|---|---|---|---|
| [Vendor name] | [Data categories] | [Purpose] | [Yes/No — DPA/MSA] | [Yes/No — country] |
| | | | | |

**4.4 Cross-Border Transfers**
[Detail any transfers outside the jurisdiction, safeguards applied, and adequacy status.]

**4.5 Retention**

| Data Category | Retention Period | Legal Basis for Retention | Disposal Method |
|---|---|---|---|
| | | | |

**4.6 Storage and Security**
[Where is data stored, by whom, in what region? Key security controls in place.]

---

## Section 5: Legal and Regulatory Compliance

**5.1 Applicable Law(s)**

All legal requirements must cite the specific statutory provision. Format: *Statute, section/schedule/principle — requirement summary.*

| Law / Regulation | Applies? | Compliance Status | Specific Provision(s) | Notes / Gaps |
|---|---|---|---|---|
| PIPEDA | | | e.g., Schedule 1, Principles 4.1–4.9 | |
| BC PIPA (SBC 2003, c. 63) | | | e.g., ss. 6, 10, 11, 34 | |
| Alberta PIPA (SA 2003, c. P-6.5) | | | e.g., ss. 7, 11, 13, 34 | |
| Quebec Law 25 | | | e.g., ss. 3.3, 12, 17, 63.3 | |
| GDPR | | | e.g., Arts. 5, 6, 13, 35 | |
| [Other] | | | | |

**5.2 Lawful Basis for Processing**

For each category of processing, state the lawful basis and cite the provision:

| Processing Activity | Data Category | Lawful Basis | Statutory Citation |
|---|---|---|---|
| [e.g., Collection for account creation] | [e.g., Name, email] | [e.g., Consent] | [e.g., BC PIPA, s. 6(1)] |
| | | | |

**5.3 Individual Rights**

| Right | Supported? | Mechanism | Statutory Basis | Notes |
|---|---|---|---|---|
| Access | Yes / No / Partial | | [e.g., BC PIPA, s. 23 / Alberta PIPA, s. 24 / PIPEDA, s. 8] | |
| Correction | Yes / No / Partial | | [e.g., BC PIPA, s. 24 / Alberta PIPA, s. 26 / PIPEDA, s. 9] | |
| Withdrawal of Consent | Yes / No / Partial | | [e.g., BC PIPA, s. 9 / Alberta PIPA, s. 9] | |
| Deletion | Yes / No / Partial | | [e.g., Quebec Law 25, s. 28 / GDPR, Art. 17] | |
| Portability | Yes / No / Partial | | [e.g., Quebec Law 25, s. 27 / GDPR, Art. 20] | |
| Objection to Automated Decisions | Yes / No / Partial | | [e.g., Quebec Law 25, s. 12.1 / GDPR, Art. 22] | |

**5.4 Privacy Notice / Policy**
[Is there a privacy notice covering this processing? Is it accurate? Where published? Cite notice obligation: e.g., BC PIPA, s. 10; Alberta PIPA, s. 13; PIPEDA, Schedule 1, Principle 4.8.]

**5.5 Vendor Agreements**
[Are data processing agreements in place with all relevant vendors? Cite obligation: e.g., BC PIPA, s. 33.1; Alberta PIPA, s. 13.1; PIPEDA, Schedule 1, Principle 4.1.3 (accountability for third parties). Note gaps.]

**5.6 Mandatory PIA / DPIA Requirement**
[Is a mandatory PIA or DPIA required? Cite: Quebec Law 25, s. 3.3 (PIA required for new projects involving PI); GDPR Art. 35 (DPIA required for high-risk processing). Note whether requirement is triggered and whether assessment satisfies it.]

**5.7 Relevant Enforcement Decisions**
[List any regulatory findings, Commissioner reports, or court decisions relevant to this type of processing. Include citation (e.g., OIPC BC Order P22-01; OPC PIPEDA Report of Findings #2022-001; *Chitrakar v. Bell TV*, 2013 FC 1103). Flag where further legal research is required. See `references/legislative-reference.md` for known citations.]

---

## Section 6: Privacy by Design Assessment

| PbD Principle | Met? | Evidence / Notes |
|---|---|---|
| Proactive — privacy considered from the start | Yes / No / Partial | |
| Privacy by Default — most protective settings are default | Yes / No / Partial | |
| Data Minimization — only necessary data is collected | Yes / No / Partial | |
| Accuracy — mechanisms to keep data current and correct | Yes / No / Partial | |
| Access Controls — data accessible only to those who need it | Yes / No / Partial | |
| Individual Rights — system supports rights fulfilment | Yes / No / Partial | |
| Accountability — logs, audits, oversight mechanisms | Yes / No / Partial | |

**Overall Privacy by Design Rating:** [Strong / Adequate / Needs Improvement / Inadequate]

---

## Section 7: Risk Register

| # | Risk Description | Category | Likelihood (1–3) | Impact (1–3) | Risk Score (1–9) | Risk Level |
|---|---|---|---|---|---|---|
| R1 | | | | | | |
| R2 | | | | | | |
| R3 | | | | | | |
| R4 | | | | | | |
| R5 | | | | | | |

*Risk Level: 1–2 = Low | 3–4 = Medium | 6–9 = High*

---

## Section 8: Mitigations and Residual Risk

| Risk # | Mitigation Measure | Owner | Target Date | Residual Score | Residual Level | Risk Accepted By |
|---|---|---|---|---|---|---|
| R1 | | | | | | |
| R2 | | | | | | |
| R3 | | | | | | |
| R4 | | | | | | |
| R5 | | | | | | |

**Unmitigated Risks (if any):**
[List any risks for which no adequate mitigation was identified. These require escalation.]

---

## Section 9: Recommendations

**9.1 Overall Risk Level**
[Low / Medium / High — with brief rationale]

**9.2 Recommended Decision**

- [ ] **Proceed** — No material privacy risks identified; initiative may proceed as designed.
- [ ] **Proceed with Conditions** — Privacy risks identified; initiative may proceed only after the following conditions are met:
  1. [Condition 1]
  2. [Condition 2]
- [ ] **Do Not Proceed** — Unacceptable privacy risks identified that cannot be adequately mitigated. Escalation to [Privacy Officer / Legal / Board] required.

**9.3 Priority Actions**

| Priority | Action | Owner | Due Date |
|---|---|---|---|
| High | | | |
| High | | | |
| Medium | | | |
| Medium | | | |

**9.4 PIA Review Trigger**
This PIA should be revisited if any of the following occur:
- [e.g., Significant change to data elements collected]
- [e.g., New third-party vendor added]
- [e.g., Expansion to a new jurisdiction]
- Scheduled review date: [Date — typically 2 years from approval, or sooner for high-risk]

---

## Sign-Off

| Role | Name | Signature / Approval | Date |
|---|---|---|---|
| Privacy Officer | | | |
| Legal Counsel | | | |
| Business Sponsor | | | |
| Executive Sponsor (if High risk) | | | |
| Data Protection Authority (if required) | | N/A or [Reference #] | |

---

*This Privacy Impact Assessment was prepared as a structured analysis tool. It does not constitute legal advice. Organizations should seek advice from qualified privacy counsel and, where required, consult with their applicable Data Protection Authority before proceeding with high-risk processing activities.*

*Document version history should be maintained. Superseded versions should be archived, not deleted.*
-e 

---


# Legislative Reference: Privacy Law Citation Guide

This reference provides ready-to-cite statutory provisions and key enforcement decisions for use in Privacy Impact Assessments. Use these citations in Section 5 of the PIA document and wherever legal requirements are identified.

**Important**: This reference reflects the law as of mid-2025. Always confirm currency with qualified privacy counsel, particularly for Quebec Law 25 (which has phased-in provisions) and any regulations in progress.

---

## Table of Contents

1. PIPEDA (Federal)
2. BC PIPA
3. Alberta PIPA
4. Quebec Law 25 (Bill 64)
5. Key Enforcement Decisions and Commissioner Reports
6. Cross-Jurisdictional Issues

---

## 1. PIPEDA — Personal Information Protection and Electronic Documents Act, SC 2000, c. 5

### Core Obligations (Schedule 1 — CSA Model Code Principles)

| Principle | Provision | Requirement |
|---|---|---|
| Accountability | Schedule 1, Principle 4.1 | Organization responsible for PI under its control; must designate a privacy officer |
| Identifying Purposes | Schedule 1, Principle 4.2 | Purposes for collection must be identified at or before time of collection |
| Consent | Schedule 1, Principle 4.3 | Knowledge and consent required for collection, use, or disclosure; form of consent depends on sensitivity |
| Limiting Collection | Schedule 1, Principle 4.4 | Collection limited to what is necessary for identified purposes |
| Limiting Use, Disclosure, and Retention | Schedule 1, Principle 4.5 | PI not to be used or disclosed for purposes other than those for which collected, except with consent or as required by law |
| Accuracy | Schedule 1, Principle 4.6 | PI must be as accurate, complete, and up-to-date as necessary |
| Safeguards | Schedule 1, Principle 4.7 | Security safeguards appropriate to sensitivity of information |
| Openness | Schedule 1, Principle 4.8 | Policies and practices must be available to individuals |
| Individual Access | Schedule 1, Principle 4.9 | Individuals have right to access PI about themselves; 30-day response period |
| Challenging Compliance | Schedule 1, Principle 4.10 | Individuals may challenge compliance with the above principles |

### Breach of Security Safeguards
- **s. 10.1**: Mandatory breach reporting to OPC and affected individuals where real risk of significant harm
- **ss. 10.2–10.3**: Reporting and notification requirements
- **"Real risk of significant harm"** defined in s. 10.1(7): includes bodily harm, humiliation, financial loss, identity theft, damage to credit, negative effects on employment or relationships, loss of employment

### Enforcement and Penalties
- **s. 14**: Individual may apply to Federal Court after OPC investigation
- **ss. 28–28.2**: Offences and fines for failure to report breaches, obstruction, retaliation

### Third-Party Accountability
- **Schedule 1, Principle 4.1.3**: Organization accountable for PI transferred to third party; must use contractual or other means to provide comparable protection

### Substantially Similar Provinces
- **s. 26(2)(b)**: Governor-in-Council may exempt organizations from PIPEDA with respect to PI they collect within a province that has substantially similar legislation — BC, Alberta, and Quebec are all designated substantially similar for provincially-regulated private-sector activities

---

## 2. BC PIPA — Personal Information Protection Act, SBC 2003, c. 63

### Scope
- **s. 3**: Applies to every organization that collects, uses, or discloses PI of individuals in BC in connection with the operation of the organization's business
- **s. 3(2)**: Does not apply to personal information collected, used, or disclosed solely for personal or domestic purposes

### Core Obligations

| Obligation | Section | Requirement |
|---|---|---|
| Privacy officer / accountability | s. 11(1) | Must designate individual responsible for compliance |
| Privacy policy | s. 5 | Must have privacy policy; must provide on request |
| Purposes must be reasonably required | s. 11(2) | Collection, use, disclosure only for purposes a reasonable person would consider appropriate |
| Notice of collection | s. 10 | Must give notice of purposes and contact information before or at time of collection |
| Collection — consent and limits | s. 6(1)–(2) | Consent required; may be express or implied; implied consent where purpose obvious and individual would reasonably expect it |
| Sensitivity and form of consent | s. 8 | Express consent required for sensitive information; otherwise implied consent may suffice |
| Use | s. 11 | Use only for purposes individual consented to, or as reasonably necessary for those purposes |
| Disclosure | s. 16 | Disclosure only with consent or under enumerated exceptions (legal requirement, emergency, etc.) |
| Accuracy | s. 33 | PI must be as accurate, complete, and up-to-date as reasonably necessary |
| Safeguards | s. 34 | Security arrangements appropriate to sensitivity; protect against unauthorized access, disclosure, copying, use, or modification |
| Retention | s. 35 | Retain only as long as necessary for purpose; then destroy or make anonymous |
| Access rights | s. 23 | Individuals entitled to access their PI; must respond within 30 business days |
| Correction rights | s. 24 | Individuals entitled to request correction; must comply or note disagreement |
| Withdrawal of consent | s. 9 | Individuals may withdraw consent; subject to legal and contractual restrictions |

### Employee Personal Information
- **ss. 13–15**: Employer may collect, use, and disclose employee PI only for purposes reasonably required to establish, manage, or terminate the employment relationship; some purposes require consent, others do not
- **s. 14(c)**: Exception for collection without consent where reasonable for the employment relationship (e.g., payroll, benefits, performance management)

### Cross-Border Transfers
- **s. 33.1**: Before transferring PI to service provider outside BC, must protect PI by contractual or other means; must inform individual of potential disclosure to foreign jurisdiction (per OIPC guidance and OPC position on US CLOUD Act risk)

### Mandatory Breach Notification
- BC PIPA does not yet have an explicit breach notification provision equivalent to federal PIPEDA s. 10.1 — however, **OIPC BC has taken the position** that s. 34 (safeguards) and s. 5 (accountability) together create an obligation to notify affected individuals where there is a real risk of significant harm; organizations should treat this as a de facto obligation

### Enforcement
- **s. 36**: Individuals may make complaints to OIPC BC
- **s. 44**: OIPC may order compliance, damages, or other remedies
- **s. 56**: Offences for wilful violation or obstruction

---

## 3. Alberta PIPA — Personal Information Protection Act, SA 2003, c. P-6.5

### Scope
- **s. 4**: Applies to every organization in respect of PI that it collects, uses, or discloses
- Applies to private-sector organizations in Alberta; does not apply to government bodies (covered by FOIP)

### Core Obligations

| Obligation | Section | Requirement |
|---|---|---|
| Privacy officer / accountability | s. 16(2) | Must designate individual(s) responsible for compliance |
| Privacy policy | s. 5 | Must develop and follow a privacy policy; must provide on request |
| Purposes must be reasonable | s. 11 | Collection only for purposes a reasonable person would consider appropriate |
| Notice of collection | s. 13 | Must notify individuals of purposes and contact information |
| Collection — consent | s. 7 | Must obtain consent; consent may be express or implied |
| Implied consent standard | s. 8 | Consent implied where purpose obvious and individual would reasonably expect it given the nature of PI and circumstances |
| Use | s. 14 | Use only for identified purposes with consent or under exceptions |
| Disclosure | s. 19 | Disclosure only with consent or under exceptions (legal process, emergency, etc.) |
| Accuracy | s. 33 | PI must be accurate, complete, and up-to-date for purposes used |
| Safeguards | s. 34 | Must protect PI with security arrangements appropriate to sensitivity |
| Retention | s. 35 | Retain only as long as necessary; then destroy or render anonymous |
| Access rights | s. 24 | Individuals entitled to access; must respond within 45 days (extendable to 30 additional days with notice) |
| Correction rights | s. 26 | Individuals entitled to request correction; must comply or annotate the record |
| Withdrawal of consent | s. 9 | Individuals may withdraw consent on reasonable notice |

### Employee Personal Information
- **ss. 15–17**: Employer may collect PI without consent for purposes reasonably required to establish, manage, or terminate employment relationship
- **ss. 21–23**: Use and disclosure of employee PI without consent in employment context; reasonable person standard applies

### Cross-Border Transfers
- **s. 13.1** (and OIPC guidance): When disclosing PI to service providers outside Alberta, must protect PI by contractual means comparable to Alberta PIPA; must inform individuals of potential disclosure to foreign jurisdiction; assess risk of foreign government access (particularly US CLOUD Act)

### Mandatory Breach Notification
- **s. 34.1** (as amended, in force 2010): Organization must notify affected individuals and OIPC of unauthorized access or disclosure where a reasonable person would consider there is a real risk of significant harm

### Enforcement
- **s. 36**: Individuals may complain to OIPC Alberta
- **s. 52**: OIPC may order compliance, damages, or other remedies
- **s. 59**: Offences for wilful violations

---

## 4. Quebec Law 25 — Act Respecting the Protection of Personal Information in the Private Sector, CQLR c. P-39.1 (as amended by Bill 64, An Act to Modernize Legislative Provisions as Regards the Protection of Personal Information, SQ 2021, c. 25)

*Note: Quebec Law 25 amendments came into force in three phases: September 2022, September 2023, and September 2023/2024. Confirm which provisions are in force for the relevant date.*

### Key Provisions

| Obligation | Section | Requirement |
|---|---|---|
| Mandatory PIA | s. 3.3 | PIA required for any project to acquire, develop, or overhaul an IT system or electronic service delivery involving PI; must be completed before project launch |
| Privacy by Default | s. 9 | PI collected only to the extent necessary; must be the most privacy-protective parameters by default |
| Consent — clear and free | s. 12 | Consent must be manifest, free, and informed; in clear and simple language; specific to purposes |
| Withdrawal of consent | s. 12 | Individual may withdraw consent at any time |
| Sensitive information | s. 12 | Express consent required for sensitive PI (health, financial, biometric, etc.) |
| Data minimization | s. 9 | Collect only PI that is necessary for the specific purpose |
| Portability | s. 27 | Individual may request PI in a structured, commonly used technological format; right to have PI communicated to third party |
| Deletion / right to be forgotten | s. 28 | Individual may request that PI be de-indexed or ceased to be communicated; applies to PI collected when individual was a minor |
| Automated decision-making | s. 12.1 | Individual must be informed when PI used to render a decision based exclusively on automated processing; right to have decision reviewed by a person |
| Privacy Officer | s. 3.1 | Enterprise must publish contact information of privacy officer |
| Breach notification | s. 3.5 | Must notify Commission d'accès à l'information (CAI) and affected individuals of confidentiality incident with risk of serious injury |
| Cross-border transfers | ss. 17–18 | PI may only be communicated outside Quebec if recipient ensures equivalent protection; privacy impact assessment required before transfer |
| Destruction or anonymization | s. 23 | PI destroyed or anonymized once purpose fulfilled |

### Penalties
- **s. 90.1**: Administrative monetary penalties up to $10M or 2% of worldwide turnover (whichever greater) for non-compliance
- **s. 91**: Penal fines up to $25M or 4% of worldwide turnover for aggravated offences

---

## 5. Key Enforcement Decisions and Commissioner Reports

### OPC (Office of the Privacy Commissioner of Canada — PIPEDA)

| Reference | Topic | Key Finding |
|---|---|---|
| OPC Report of Findings #2023-001 (*Cadillac Fairview*) | Facial recognition in retail | Collection of biometric data via facial recognition without meaningful consent violated PIPEDA Principles 4.2, 4.3, 4.7; OPC found that capturing biometric data of individuals browsing a mall without notice constituted collection without consent |
| OPC Report of Findings re: *Home Depot* (2020) | Customer data sharing with Facebook without consent | Sharing customer transaction data with Facebook via pixel tracking without consent violated PIPEDA Principles 4.3 and 4.5 |
| OPC Report of Findings re: *Clearview AI* (2021) | Biometric scraping and facial recognition | Scraping images without consent and building biometric database violated all applicable consent and purpose limitation principles; joint investigation with BC, Alberta, and Quebec |
| OPC Guidance — US CLOUD Act (2019/updated) | Cross-border transfers to US cloud providers | OPC position: organizations must assess risk that foreign law (US CLOUD Act) may compel disclosure; must inform individuals; safeguards include contractual protections |
| OPC Position Paper — AI and Automated Decision-Making (2023) | AI/ML profiling | Sets out expectations under PIPEDA for transparency, meaningful consent, and human review where AI decisions significantly affect individuals |

### OIPC BC (Office of the Information and Privacy Commissioner for BC)

| Reference | Topic | Key Finding |
|---|---|---|
| OIPC BC Order P22-01 | Employee monitoring software | Keystroke logging and screen capture of remote employees without adequate notice violated BC PIPA ss. 11, 13; surveillance must be reasonably required and individuals must be informed |
| OIPC BC Order P21-01 | Collection of customer facial images | Collection of facial images for fraud prevention without adequate notice and consent violated BC PIPA; organization could not rely on implied consent for biometric collection |
| OIPC BC Investigation Report F21-03 | Cross-border cloud storage | Transferring PI to US-based servers creates risk under US CLOUD Act; BC PIPA s. 33.1 requires contractual protections and individual notification |
| OIPC BC Guidance — Privacy Impact Assessments | When to conduct PIAs | OIPC BC recommends PIAs for any new program or service involving PI; recommends consultation with OIPC for high-risk processing |

### OIPC Alberta (Office of the Information and Privacy Commissioner for Alberta)

| Reference | Topic | Key Finding |
|---|---|---|
| OIPC Alberta Order P2023-01 | Employee GPS tracking | Continuous GPS tracking of employees outside work hours not reasonably required for employment relationship; violated Alberta PIPA s. 14 |
| OIPC Alberta Investigation Report P2021-IR-001 | Retail loyalty program consent | Implied consent insufficient for secondary use of purchase data for third-party marketing; express consent required; violated Alberta PIPA ss. 7, 14 |
| OIPC Alberta Order P2020-02 | Biometric timekeeping (fingerprints) | Fingerprint collection for timekeeping requires express consent under Alberta PIPA s. 7; reasonable person test not met where alternative was available |
| OIPC Alberta Guidance — Data Breach Notification | Breach notification standard | Sets out OIPC Alberta expectations under s. 34.1; "real risk of significant harm" is the threshold; notification should be prompt and specific |

### Court Decisions

| Reference | Topic | Relevance |
|---|---|---|
| *Chitrakar v. Bell TV*, 2013 FC 1103 | PIPEDA individual access | Federal Court confirmed right of access under PIPEDA s. 8; clarified scope of "personal information" under the Act |
| *Douez v. Facebook*, 2017 SCC 33 | Forum selection and PIPEDA | Supreme Court found BC residents could pursue PIPEDA claims in BC courts despite Facebook's forum selection clause; consumer privacy rights interpreted broadly |
| *R v. Spencer*, 2014 SCC 43 | Reasonable expectation of privacy in subscriber info | SCC held individuals have reasonable expectation of privacy in subscriber information associated with IP address; highly relevant for any initiative involving IP address collection or law enforcement requests |

---

## 6. Cross-Jurisdictional Issues

### Which Law Applies? Decision Guide

| Scenario | Law(s) That Apply |
|---|---|
| Private-sector org collecting PI of BC residents for commercial purposes, operating in BC | BC PIPA (primarily); PIPEDA does not apply to provincially-regulated activities in BC |
| Private-sector org collecting PI of Alberta residents for commercial purposes, operating in Alberta | Alberta PIPA (primarily); PIPEDA does not apply to provincially-regulated activities in Alberta |
| Federally-regulated business (bank, telecom, airline) operating in BC or Alberta | PIPEDA applies; BC/Alberta PIPA does not |
| Private-sector org collecting PI across provinces including Ontario | PIPEDA applies to Ontario and federally regulated activities; check for sector-specific Ontario legislation (PHIPA, etc.) |
| Processing PI of Quebec residents | Quebec Law 25 applies to private sector; PIPEDA applies to federally regulated activities |
| Processing PI of EU residents | GDPR applies regardless of where the organization is located, if offering goods/services or monitoring behaviour of EU data subjects (GDPR, Art. 3(2)) |
| Multiple jurisdictions apply | Identify the most stringent applicable requirement for each obligation; comply with all |

### Conflict / Overlap Notes

- BC and Alberta PIPA are "substantially similar" to PIPEDA — organizations complying with BC or Alberta PIPA in their provincial operations are generally exempt from PIPEDA for that PI
- Quebec Law 25 has stricter consent requirements, portability rights, and a mandatory PIA requirement that exceeds PIPEDA
- Where GDPR applies alongside Canadian law, GDPR typically sets the higher standard (particularly for consent, data subject rights, and mandatory DPIAs)
- For cross-border transfers: Quebec Law 25 requires a PIA before any transfer; BC and Alberta require contractual protections and individual notice; PIPEDA requires accountability and comparable protection
