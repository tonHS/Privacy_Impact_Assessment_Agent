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
- **Cite enforcement decisions where relevant**: Where an identified risk has been the subject of a regulatory finding, Commissioner investigation, or court decision, note the case reference; flag where the user should obtain additional legal research.
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

**Citation standard:** Do not state "the law requires X" — state "PIPEDA, Schedule 1, Principle 4.3 requires X" or "BC PIPA, s. 11(1) requires X." Flag items needing additional legal research rather than leaving them uncited.

### 5a. Jurisdictional Scope

- Which privacy law(s) apply to this initiative? Select all that apply and document the basis for each:
  - PIPEDA (SC 2000, c. 5) — applies to commercial activities and federally regulated employers (s. 4)
  - BC PIPA (SBC 2003, c. 63) — applies to private-sector organizations in connection with the operation of a business in BC (s. 3)
  - Alberta PIPA (SA 2003, c. P-6.5) — applies to private-sector organizations in respect of PI they collect, use, or disclose (s. 4)
  - Quebec Law 25 / Act respecting the protection of personal information in the private sector (CQLR c. P-39.1)
  - PHIPA (Ontario), HIA (Alberta), or other provincial health-sector statute
  - GDPR — where the organization offers goods/services to, or monitors behaviour of, individuals in the EU/EEA (Art. 3(2))
  - CCPA/CPRA, HIPAA, COPPA, FERPA, or other US/sector statute
  - Sector-specific Canadian rules (OSFI, FINTRAC, CRTC/CASL, etc.)
- Where is the organization established, and where are the data subjects located? (Determines whether a substantially similar provincial law displaces PIPEDA via s. 26(2)(b).)
- Is the organization a federal work, undertaking, or business (bank, telecom, interprovincial transport, airline)? If yes, PIPEDA applies regardless of province.
- Is any processing carried out cross-border or by a controller/processor located outside Canada?

### 5b. PIPEDA — Specific Questions (if applicable)

- Has an individual been designated as accountable for the organization's compliance, and are their contact details available (Schedule 1, Principle 4.1; s. 5(1))?
- Are the purposes for collection identified and documented at or before the time of collection (Schedule 1, Principle 4.2)?
- What form of consent is being relied on (express, implied, opt-in, opt-out), and is it appropriate to the sensitivity of the PI and the reasonable expectations of the individual (Schedule 1, Principle 4.3; s. 6.1 — valid consent requires the individual to understand the nature, purpose and consequences)?
- Is collection limited to what is necessary for the identified purposes, by fair and lawful means (Schedule 1, Principle 4.4)?
- Are use, disclosure, and retention limited to the identified purposes, with new purposes triggering fresh consent (Schedule 1, Principle 4.5)?
- Is PI as accurate, complete, and up-to-date as necessary for the purposes (Schedule 1, Principle 4.6)?
- Are safeguards (physical, organizational, technological) appropriate to the sensitivity of the PI in place (Schedule 1, Principle 4.7)?
- Are policies and practices openly available to individuals (Schedule 1, Principle 4.8)?
- Can individuals access and correct their PI, with a response within 30 days (Schedule 1, Principle 4.9; s. 8(3))?
- Is the breach-of-security-safeguards regime built into the incident response plan: report to the OPC and notify affected individuals where there is a real risk of significant harm, and maintain breach records for 24 months (s. 10.1; Breach of Security Safeguards Regulations)?
- Where PI is transferred to a third party for processing, is comparable protection ensured by contractual or other means (Schedule 1, Principle 4.1.3; OPC Guidelines for Processing Personal Data Across Borders)?

### 5c. BC PIPA — Specific Questions (if applicable)

- Has the organization designated one or more individuals responsible for compliance, with publicly available contact information (s. 4(3); s. 11)?
- Has a privacy policy been developed and made available on request (s. 5)?
- Is collection, use, and disclosure limited to purposes that a reasonable person would consider appropriate in the circumstances (s. 11; s. 14; s. 17)?
- Is notice of the purposes and a contact for questions provided at or before collection (s. 10(1))?
- Is the form of consent (express, deemed, or opt-out under s. 8) appropriate to the sensitivity of the PI, and is opt-out consent under s. 8(3) being used only where its narrow conditions are met?
- For employee personal information: is the collection, use, or disclosure reasonable for the purposes of establishing, managing, or terminating an employment relationship, and has reasonable notice been given (ss. 13(2), 16(2), 19(2))?
- Are individuals' access requests met within 30 business days, with permitted extensions properly documented (ss. 28–29)?
- Is the correction process under s. 24 followed (correct, or annotate the record where correction is refused)?
- Are security arrangements reasonable and proportionate to the sensitivity of the PI (s. 34)?
- Is PI retained only as long as reasonably necessary for legal or business purposes, then destroyed or anonymized; and where used to make a decision about the individual, retained for at least one year (s. 35)?
- For service providers and transfers outside BC: are contractual or other measures in place to ensure comparable protection, and have individuals been informed of foreign-jurisdiction risk (per OIPC BC guidance on outsourcing and the US CLOUD Act)?
- Is there a process to notify the OIPC and affected individuals of privacy breaches (per OIPC BC's *Privacy Breaches: Tools and Resources* guidance — BC PIPA does not yet contain a statutory mandatory notification provision, but OIPC BC treats notification as expected where there is real risk of significant harm)?

### 5d. Alberta PIPA — Specific Questions (if applicable)

- Has the organization designated one or more individuals responsible for compliance (s. 5(3))?
- Has a privacy policy and complaint-handling process been developed and made available on request (s. 6)?
- Is collection limited to purposes that are reasonable, and only to the extent reasonable for those purposes (s. 11)?
- Is notice of the purposes and contact information for the privacy officer provided at or before collection (s. 13)?
- Is consent obtained per s. 7, applying the deemed-consent test in s. 8 only where the purpose is obvious and the individual voluntarily provides the information, or applying the opt-out conditions in s. 8(3)?
- For employee personal information: is the collection, use, or disclosure reasonable for the purposes of establishing, managing, or terminating the employment relationship, and has reasonable notice been provided to the employee (ss. 15(2), 18(2), 21(2))?
- Are access requests responded to within 45 days (with the s. 29 extension, where applicable, properly documented) (s. 28)?
- Is correction handled per s. 25 (correct, or annotate the record where correction is refused)?
- Are reasonable security arrangements in place to protect PI against risks such as unauthorized access, collection, use, disclosure, copying, modification, disposal, or destruction (s. 34)?
- Is PI retained only as long as reasonable, then destroyed or rendered non-identifying; and retained for at least one year where it has been used to make a decision about the individual (s. 35)?
- For service providers outside Canada (including parent companies): has the organization given written notice describing the way the PI will be handled and the foreign country to which it may be transferred (s. 13.1 of PIPA Regulation, Alta. Reg. 366/2003, and the disclosure requirement when using a non-Canadian service provider — ss. 13.1, 13.2 of the Act after 2010 amendments)?
- Is there a process to provide the mandatory breach notification to the OIPC under s. 34.1 where a reasonable person would consider that a real risk of significant harm exists, and a process for the OIPC to direct individual notification under s. 37.1?

### 5e. Quebec Law 25 — Specific Questions (if applicable)

- Has a Privacy Officer (Person in Charge of the Protection of Personal Information) been designated, and is their title and contact information published on the organization's website (s. 3.1)?
- Has a privacy governance framework (policies and practices about retention, destruction, roles, and complaint handling) been adopted and published in clear, simple language (s. 3.2)?
- Does this project involve the acquisition, development, or overhaul of an information system or electronic service delivery involving PI — triggering a mandatory PIA proportionate to sensitivity, purposes, quantity, distribution, and medium (s. 3.3)?
- Is consent manifest, free, informed, given for specific purposes, granular, and presented separately from any other information; and, for sensitive PI, expressly given (s. 14)?
- For minors under 14, is consent obtained from a parent or guardian; and is the use of PI of minors subject to heightened scrutiny (s. 14)?
- Have privacy-protective default settings (privacy by default) been configured for any technological product or service offered to the public (s. 9.1)?
- Are individuals informed before collection of: the purposes, means of collection, rights of access/rectification, right to withdraw consent, name of any third party for whom collection is made, and the possibility of disclosure outside Quebec (s. 8)?
- Is automated decision-making disclosed at or before the decision, with the individual offered the right to be informed of the PI used, the reasons and principal factors, and the opportunity to submit observations to a person who can review the decision (s. 12.2)?
- Are portability requests supported by providing computerized PI in a structured, commonly used technological format, and is there a process to communicate it to a third party on request (s. 27)?
- Is there a process to de-index or cease dissemination of PI on request where dissemination causes serious injury that outweighs the public interest (s. 28.1)?
- Is there a documented process to handle confidentiality incidents: take reasonable measures to reduce risk and prevent recurrence; notify the CAI and affected individuals where the incident presents a risk of serious injury; and maintain an incident register (s. 3.5; s. 3.8)?
- For any communication of PI outside Quebec: has a transfer-specific PIA been conducted assessing legal framework adequacy in the receiving jurisdiction, and is there a written agreement in place (s. 17)?
- Has PI been destroyed or anonymized once the purposes for which it was collected or used have been achieved, applying generally accepted best practices (s. 23)?
- Are biometric databases declared to the CAI at least 60 days before being put into service (Act to establish a legal framework for information technology, CQLR c. C-1.1, s. 45)?

### 5f. GDPR — Specific Questions (if applicable)

- What is the lawful basis for each processing activity under Art. 6, and for special-category data, the additional condition under Art. 9?
- Are the Art. 13/14 transparency requirements met in the privacy notice (identity of controller, purposes, legal basis, recipients, retention, rights, source where collected indirectly)?
- Are data subject rights operational: access (Art. 15), rectification (Art. 16), erasure (Art. 17), restriction (Art. 18), portability (Art. 20), objection (Art. 21), and rights related to automated decision-making (Art. 22)?
- Is a DPIA required under Art. 35 (e.g., systematic and extensive profiling with significant effects, large-scale processing of special-category data, large-scale systematic monitoring)? Has it been completed and reviewed?
- Has a Data Protection Officer been appointed where required (Art. 37), and is their contact information published?
- For transfers outside the EEA: is there a valid Art. 45 adequacy decision, an Art. 46 transfer mechanism (SCCs, BCRs), or an Art. 49 derogation? Has a Transfer Impact Assessment been performed in line with EDPB Recommendations 01/2020 post-*Schrems II*?
- Is a data processor agreement under Art. 28 in place with all processors, addressing the eight required topics?
- Is there a process to notify the supervisory authority within 72 hours of becoming aware of a personal data breach (Art. 33), and to notify affected data subjects without undue delay where the breach is likely to result in a high risk to their rights and freedoms (Art. 34)?
- Are records of processing activities maintained under Art. 30?

### 5g. Individual Rights — Operational

- Is there a documented, accessible, and free intake channel for individuals to exercise their rights (access, correction, deletion, withdrawal of consent, portability, objection, automated-decision review)?
- Are response timelines tracked against each applicable law (PIPEDA: 30 days; BC PIPA: 30 business days; Alberta PIPA: 45 days; Quebec Law 25: 30 days; GDPR: 1 month, extendable by 2 months for complex requests)?
- Where a request is refused, is a written response provided that states the reason, the statutory exception relied on, and the individual's right to complain to the relevant Commissioner/CAI/supervisory authority?
- Is identity-verification proportionate (no excessive PI demanded just to verify the requester)?

### 5h. Vendor and Third-Party Compliance

- Are written agreements in place with every processor, sub-processor, and PI-handling vendor?
- Do those agreements address: scope and purpose of processing, confidentiality, security measures, sub-processor controls, audit rights, breach notification timelines, return/destruction at end of term, restrictions on cross-border transfer, and cooperation with data-subject requests?
- For each vendor, has a due-diligence assessment been performed (security certifications, sub-processor list, location of processing, government-access risk)?
- Is the obligation to ensure comparable/equivalent protection cited and documented (PIPEDA Schedule 1, Principle 4.1.3; BC PIPA s. 33; Alberta PIPA Regulation s. 13.1; Quebec Law 25 s. 17; GDPR Art. 28)?

### 5i. Mandatory PIA / DPIA / Pre-Approval Triggers

- Does Quebec Law 25, s. 3.3 require a PIA (any IT system or electronic service delivery project involving PI)?
- Does Quebec Law 25, s. 17 require a transfer-specific PIA for any communication of PI outside Quebec?
- Does GDPR Art. 35 require a DPIA, applying the Art. 29 WP/EDPB nine criteria? Is Art. 36 prior consultation triggered?
- Does the OIPC BC, OIPC Alberta, OPC, or CAI have published guidance recommending a PIA, prior consultation, or notification for this type of processing?
- For health-sector processing: does PHIPA (Ontario), HIA (Alberta), or another provincial statute trigger a separate PIA obligation?

### 5j. Enforcement and Precedent — Prompt Questions

Confirm whether any of the following high-scrutiny scenarios apply. Each maps to existing Commissioner findings and should inform both the risk register and the standard of compliance applied:

- Workplace monitoring or surveillance (keystroke logging, screen capture, GPS, video, productivity tracking)
- Biometric data collection (facial recognition, fingerprint, voiceprint, gait, iris)
- Automated decision-making, profiling, or AI/ML systems materially affecting individuals
- Cross-border transfers, particularly to US cloud providers (US CLOUD Act / FISA s. 702 exposure)
- Personal information of minors, or processing directed at children
- Sensitive health, financial, sexual-orientation, or special-category data processed by a private-sector entity
- Pixel, SDK, or tag-based tracking for advertising, analytics, or audience-building
- Use of publicly available information, including web-scraped data
- Processing in connection with law-enforcement or national-security disclosures

For each "yes," flag for additional legal research and document the relevant Commissioner finding, order, or court decision applied as the standard.

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
[List any regulatory findings, Commissioner reports, or court decisions relevant to this type of processing. Include citation (e.g., OIPC BC Order P22-01; OPC PIPEDA Report of Findings #2022-001; *Chitrakar v. Bell TV*, 2013 FC 1103). Flag where further legal research is required.]

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
