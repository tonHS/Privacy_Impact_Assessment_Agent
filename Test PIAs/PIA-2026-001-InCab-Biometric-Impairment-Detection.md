# PRIVACY IMPACT ASSESSMENT

| Field | Value |
|---|---|
| **Initiative Name** | In-Cab Biometric Impairment Detection System |
| **PIA Reference Number** | PIA-2026-001 |
| **Date Prepared** | 2026-05-09 |
| **Prepared By** | Privacy Impact Assessment Agent (intake supported by Project Manager) |
| **Privacy Officer Reviewed** | Pending — General Counsel (acting Privacy Officer) |
| **Version** | 1.0 Draft |
| **Classification** | Confidential — Internal Only |

---

## Executive Summary

The organization, an Ontario-headquartered interprovincial and international trucking company operating a fleet of approximately 200 trucks across Canada and the United States, proposes to deploy an **In-Cab Biometric Impairment Detection System** in all fleet vehicles. The system uses continuous skin-chemistry and breath-chemistry sensors to detect alcohol impairment while a vehicle is in operation. On a positive reading, the system either (a) issues a warning followed by an automated controlled slowdown to a safe stop, or (b) locks the driver out of the vehicle. Biometric data is streamed to a U.S.-headquartered umbrella vendor for cloud processing and analytics, retained for the duration of employment or contract plus a defined period (and longer where a disciplinary or contractual matter is open), and is intended to be used as evidence in employment-discipline proceedings and in contract disputes with rental contractors. Approximately 400 drivers are affected — a mix of employees, independent contractors, and contractor sub-employees.

The initiative pursues legitimate, weighty objectives — reducing road-safety incidents, protecting drivers and the public, and limiting organizational liability. However, this PIA identifies that the program, **as currently designed and on its current pilot timeline**, presents **eleven High-rated and four Medium-rated privacy risks**, several of which require structural design changes before deployment may lawfully proceed.

The most material findings are:

1. **Quebec Law 25 obligations are imminent and unmet.** A biometric database must be declared to the Commission d'accès à l'information (CAI) at least 60 days before being put into service (*Act to establish a legal framework for information technology*, CQLR c. C-1.1, s. 45). A pilot is already imminent and Quebec drivers are within scope. A mandatory PIA under Quebec Law 25 s. 3.3 and a transfer-specific PIA under s. 17 are also required and not yet completed. **The CAI declaration is the single highest-priority pre-launch action.**
2. **Automated decision-making without a human-in-the-loop review path** is inconsistent with Quebec Law 25 s. 12.1 and is below industry best practice for decisions with significant employment effects.
3. **The current notice and consent plan — sticker plus a 1–2 week advance notice — is below the legal threshold** for meaningful consent to continuous biometric workplace surveillance under PIPEDA, Sch. 1 Principle 4.3 and s. 6.1, and below the "reasonable notice" standard required for employee monitoring under provincial private-sector statutes. Contractors are not covered by employee-monitoring statutory shortcuts and require express consent.
4. **The vendor contract is not yet executed** and key data-protection terms (cross-border, breach notification, sub-processor controls, audit, return/destruction, cooperation with rights requests) are unconfirmed. PIPEDA Sch. 1 Principle 4.1.3 requires comparable protection by contract or other means.
5. **Cross-border transfer to a U.S.-headquartered vendor with data stored largely in the U.S.** raises U.S. *CLOUD Act* exposure and U.S. state-law biometric-statute exposure (Illinois BIPA and analogues). U.S. legal advice has not been obtained.

**Overall Risk Level: HIGH.**

**Recommended Decision: Proceed with Conditions.** The initiative may proceed only after the conditions in Section 9 are met. Several conditions — most significantly the CAI declaration, vendor contract terms, the human-in-the-loop review path, and revised notice and consent — should be in place **before** the pilot expands beyond the current ~10-truck pilot footprint and **before** any data is collected from drivers actively operating in Quebec.

This Privacy Impact Assessment was prepared as a structured analysis tool using artificial intelligence. It does not constitute legal advice. The organization should obtain advice from qualified Canadian privacy counsel, U.S. counsel for state biometric-statute exposure, and should engage with the CAI as required, before proceeding with high-risk processing activities.

---

## Section 1 — Initiative Description

### 1.1 Overview
The In-Cab Biometric Impairment Detection System is a continuous, non-disableable monitoring program deployed in fleet trucks. Skin-chemistry sensors (transdermal alcohol sensing) operate as the primary modality, with breath-chemistry sensors as a secondary modality. The system computes an impairment score in real time. On a positive reading exceeding a configured threshold, the system issues a warning to the driver, then either initiates a controlled, automated slowdown to a safe stop, or locks the driver out of the vehicle.

The stated business objectives are (a) reducing road-safety incidents arising from impaired driving, (b) improving the organization's safety performance, and (c) reducing the organization's exposure to liability.

### 1.2 Status and Timeline
- Current status: design and build, with a pilot launch planned approximately six months from the date of this PIA (target: November 2026).
- Pilot scope (estimated): ~10 trucks.
- Full-fleet rollout (planned): approximately 12 months from the date of this PIA (target: May 2027), covering all ~200 trucks.
- The pilot will retain biometric data (not detection-only) so the data is available for downstream disciplinary and contractual use.

### 1.3 Scope of this PIA
**In scope:** the in-cab sensor hardware, in-cab device firmware, vehicle-control intervention logic (warning, slowdown, lockout), data transmission from the vehicle to the umbrella vendor's cloud, vendor analytics and storage, downstream company access for HR/Legal use, retention and destruction, vendor and sub-vendor relationships, data flows across the Canada–U.S. border, individual rights handling, and notice/consent design. Drivers in scope: employees, contractors, and contractor sub-employees driving company-owned trucks across Canada and the United States.

**Out of scope:** other forms of fleet monitoring (dashcams, ELD/Hours-of-Service, GPS, fatigue detection) except where they are integrated with or share data with this system. The status of those other systems is itself a gap (see Section 4).

### 1.4 Prior Reviews
None identified. This is the first formal privacy review of the initiative.

### 1.5 Regulatory and Contractual Drivers
- Internal safety and liability policy is the confirmed driver.
- An insurance-related driver may exist (e.g., insurer mandate or premium-reduction program) — **gap, to be confirmed**.
- Transport Canada / FMCSA (U.S.) status as a driver — **gap, to be confirmed**.
- No collective agreement or contractor master services agreement currently authorizes biometric monitoring.

---

## Section 2 — Stakeholders and Accountability

| Role | Name / Team | Status |
|---|---|---|
| Business Sponsor | Project Manager (specific individual TBD) | Assigned in role; individual TBD |
| Initiative Owner | Project Manager | As above |
| Privacy Officer (Accountable Individual) | General Counsel (acting) | Assigned; **publication of name and contact on the company website is required** under Quebec Law 25 s. 3.1 — gap |
| Legal / Compliance Lead | General Counsel | Assigned |
| Security / IT Lead | Not yet appointed | **Material gap — must appoint before pilot** |
| HR / Labour Lead | Not yet engaged | **Material gap — must engage before notice issuance** |
| Union Representation | Mostly non-unionized; not consulted | Engagement still recommended where applicable |
| Contractor Relationship Manager | Not yet identified | **Material gap — required for contractor consent process** |
| Vendor Relationship Owner | Likely Logistics team (TBD) | **Gap — assignment required** |
| Data Protection Officer (GDPR Art. 37) | Not appointed | Not required (no GDPR trigger identified) |

**Statutory accountability obligations engaged:**
- PIPEDA, Schedule 1, Principle 4.1 / s. 5(1) — designated individual accountable for compliance.
- Quebec Law 25, s. 3.1 — Person in Charge of the Protection of Personal Information designated; **title and contact information must be published on the website**.
- Alberta PIPA, s. 5(3) — designated individual.
- BC PIPA, s. 4 — designated individual with publicly available contact information.

---

## Section 3 — Personal Information Inventory

### 3.1 Data Elements Collected or Used

| Category | Specific Elements | Necessary? | Sensitive? |
|---|---|---|---|
| Biometric — chemistry | Transdermal alcohol (skin chemistry) signal; breath-alcohol signal | Yes (primary purpose) | **Yes — biometric & health-adjacent** |
| Biometric — derived | Computed impairment score | Yes | **Yes** |
| Biometric — derived | Pass/fail threshold flag | Yes | Yes |
| Identifiers | Vehicle ID, Driver ID | Yes | No |
| Identifiers (linked) | Driver name, employee/contractor identifier | Likely yes for accountability use | Indirectly sensitive when linked to biometric |
| Location | GPS coordinates at sensor events (assumed) | To be confirmed with vendor | Yes when combined with identity |
| Telematics | Speed, braking, vehicle state at event (assumed) | To be confirmed | Sensitive when combined with identity |
| Schedule / dispatch | Route, dispatch, schedule data | Possibly synced with system | Indirectly sensitive |
| HR / discipline / medical | Held separately by HR; integration TBD | Should remain separate | **Yes** |

**Health-data inference risk:** Skin-chemistry sensors detect transdermal alcohol but the signal can be influenced by medications, illness (e.g., diabetic ketoacidosis), hand sanitizer, and environmental factors. The signal is therefore **health-adjacent**, and false positives carry direct individual-harm consequences (lockout, discipline). Treated as sensitive personal information for the purposes of this PIA.

### 3.2 Data Subjects

| Population | Approximate Volume | Vulnerable? |
|---|---|---|
| Employee drivers | Majority of ~400 drivers | Yes — power imbalance with employer; cannot meaningfully refuse without losing employment |
| Independent contractor drivers | Minority of ~400 | Power imbalance; consent must be express and separately structured |
| Contractor sub-employees | Subset of contractor cohort | **Most acute power-imbalance risk**: not in privity with the company, but subject to its monitoring |
| Minors | None identified | N/A |

**Total data subjects: approximately 400.**

### 3.3 Data Minimization Assessment
The collection plan is **maximalist**, not minimalist:

- Continuous biometric streaming throughout engine-on time (rather than at engine-start, on threshold, or on demand).
- Both skin and breath chemistry simultaneously (rather than the minimum modality required for the safety purpose).
- Cloud retention of biometric records (rather than detect-and-discard with only flagged-event storage).
- Identifying linkage at vendor side (likely; to be confirmed).
- Open-ended downstream uses (discipline, contractor disputes, fleet analytics, insurance, vendor model training, possible law-enforcement disclosure).

The proportionality test under PIPEDA workplace-surveillance jurisprudence (see *Eastmond v. Canadian Pacific Railway*, 2004 FC 852, and OPC findings on workplace monitoring) requires assessment of **necessity, effectiveness, proportionality, and the existence of less-privacy-intrusive alternatives**. A minimization analysis (Section 8 mitigations) recommends that less-intrusive configurations be sought from the vendor before any contract is signed.

---

## Section 4 — Data Flows

### 4.1 Collection
Personal information is collected directly from the driver through in-cab sensors while the engine is on. Both local on-device processing and cloud streaming occur (assumed; to be confirmed with vendor). Notice at the point of collection is currently planned to consist of an in-cab sticker and possibly a screen prompt at engine-start. A consent or acknowledgement form is contemplated but not yet drafted.

**Statutory citations engaged:**
- PIPEDA, Sch. 1, Principle 4.2 — purposes identified at or before collection.
- PIPEDA, Sch. 1, Principle 4.3 / s. 6.1 — meaningful consent (understanding of nature, purpose, consequences); appropriate to sensitivity.
- Quebec Law 25, s. 8 — pre-collection information must include purposes, means, rights, third parties, cross-border transfer.
- Quebec Law 25, s. 12 / s. 14 — manifest, free, informed consent given for specific purposes; for sensitive PI, expressly given.
- BC PIPA, s. 10(1); Alberta PIPA, s. 13 — notice of purposes and contact at or before collection.
- Alberta PIPA, s. 15(1); BC PIPA, s. 13(2) — reasonable notice required before collecting employee personal information for an employment-related purpose.

### 4.2 Use and Purpose
**Primary use:** real-time impairment detection and automated vehicle intervention (warning, controlled slowdown, lockout).

**Secondary uses contemplated (each "potentially yes" per intake):**
- Disciplinary evidence in employment proceedings;
- Evidence in contract disputes with rental contractors;
- Aggregate fleet analytics and safety reporting;
- Insurance claims defence;
- Vendor product improvement and model training;
- Sale or sharing of de-identified data;
- Voluntary or compelled disclosure to law enforcement.

**Automated decision-making.** The slowdown/lockout decision is made fully automatically with no human in the loop in the current design. Disciplinary use is downstream of an automated event flag and currently has no defined contestation channel. **This is inconsistent with Quebec Law 25, s. 12.1**, which requires that an individual subject to an automated decision be informed and, on request, given the principal factors used in making the decision and the opportunity to submit observations to a person who can review the decision. It also creates risk under PIPEDA Sch. 1 Principle 4.3 (meaningful consent) and Principle 4.6 (accuracy).

### 4.3 Disclosure and Third-Party Sharing

| Recipient | Data Shared | Purpose | Agreement in Place? | Cross-Border? |
|---|---|---|---|---|
| Umbrella vendor (US-HQ) | Full biometric stream + identifiers + telematics | Cloud processing, analytics, storage | **No — in negotiation** | **Yes — U.S.** |
| Vendor sub-processors | Subset (TBD) | TBD | Unknown | TBD |
| Insurance carrier | Possibly — circumstance-driven | Claims defence | None confirmed | Possibly |
| Customers / shippers | Possibly — circumstance-driven | TBD | None confirmed | Possibly |
| Police / Transport Canada / FMCSA / provincial regulators | Possibly — circumstance-driven | Compliance / law-enforcement response | None confirmed | Possibly |
| Contractor management entities | Possibly — when their employee triggers event | Contractual dispute resolution | None confirmed | Possibly |

**Internal access:** HR and Legal are designated recipients today. Onward internal disclosure to be at Legal's direction. **Role-based access controls and audit logs are unconfirmed (gap).**

### 4.4 Cross-Border Transfers
Cloud processing occurs primarily in the **United States**, with possibly some Canadian processing. The umbrella vendor is U.S.-headquartered. The data crossing the border includes biometric chemistry signals, computed impairment scores, identifiers, location, and telematics — a rich profile of an identifiable individual.

**Transfer-specific risk areas:**
- **U.S. CLOUD Act** — U.S. authorities may compel a U.S.-based provider to disclose data regardless of where stored, including data of Canadian and Quebec drivers.
- **Quebec Law 25, s. 17** — communication of PI outside Quebec requires a transfer-specific PIA assessing the legal framework in the receiving jurisdiction and a written agreement. **Not yet completed — gap.**
- **PIPEDA Sch. 1 Principle 4.1.3** and **OPC *Guidelines for Processing Personal Data Across Borders*** — accountability remains with the company; comparable protection must be ensured by contractual or other means.
- **Alberta PIPA, s. 13.1** — written notice to individuals describing how PI will be handled and the foreign country to which it may be transferred, where the organization uses a foreign service provider.
- **U.S. state biometric statutes** — Illinois Biometric Information Privacy Act, Texas Capture or Use of Biometric Identifier Act, Washington's My Health My Data Act, and California CCPA/CPRA may engage where drivers transit those jurisdictions. **U.S. counsel has not been consulted — gap.**

### 4.5 Retention

| Data Category | Retention Period | Legal Basis | Disposal Method |
|---|---|---|---|
| Raw biometric sensor signal | **Not yet defined** — gap | TBD | Vendor-controlled destruction with certification (planned) |
| Computed impairment score | **Not yet defined** — gap | TBD | Vendor-controlled destruction with certification (planned) |
| Flagged-event records (positive readings) | Duration of employment / contract + a defined period; longer if disciplinary or legal matter open | Documented business need + legal-hold | Vendor-controlled destruction with certification (planned) |
| Identity and linkage records | TBD — gap | TBD | TBD |

**Statutory anchors:**
- PIPEDA Sch. 1 Principle 4.5.3 — PI used to make a decision about an individual must be retained long enough to allow access by the individual.
- Quebec Law 25, s. 23 — PI must be destroyed or anonymized once the purposes have been achieved, applying generally accepted best practices.
- BC PIPA, s. 35 / Alberta PIPA, s. 35 — retention only as long as reasonably necessary; where used to make a decision, retain at least one year.

A **documented retention schedule with separate rules for raw, derived, and flagged records is required** before pilot data collection begins.

### 4.6 Storage and Security
- Storage location: primarily United States, possibly some Canadian region.
- Vendor security posture: described as "industry-standard" — **specifics (SOC 2, ISO 27001, encryption at rest and in transit, key management, MFA, audit logging) are unconfirmed (gap)**.
- Incident-response / breach-notification process: unknown — **gap**.
- In-cab device security (firmware tamper resistance, sensor spoofing protection, physical security on lost or stolen trucks): no threat model performed — **gap**.

**Statutory safeguards obligations engaged:**
- PIPEDA Sch. 1 Principle 4.7 — physical, organizational, and technological safeguards appropriate to sensitivity.
- Quebec Law 25, s. 10 — reasonable security measures.
- Alberta PIPA, s. 34; BC PIPA, s. 34 — reasonable security arrangements.
- PIPEDA s. 10.1 and *Breach of Security Safeguards Regulations* — mandatory breach reporting to OPC and notification to individuals where there is a real risk of significant harm; 24-month breach record retention.
- Alberta PIPA, s. 34.1 — breach notification to OIPC; s. 37.1 — OIPC may direct individual notification.
- Quebec Law 25, s. 3.5 / s. 3.8 — confidentiality-incident response, notification to CAI and individuals where risk of serious injury, and incident register.

---

## Section 5 — Legal and Regulatory Compliance

### 5.1 Applicable Law(s)

| Law / Regulation | Applies? | Compliance Status (today) | Specific Provisions Engaged | Notes / Gaps |
|---|---|---|---|---|
| **PIPEDA** (SC 2000, c. 5) | **Yes — primary** | Not compliant (gaps below) | s. 4 (federal works/undertakings; cross-border processing); ss. 5, 6.1, 8, 10.1; Sch. 1 Principles 4.1–4.9, including 4.1.3 | Interprovincial/international trucking is a federal undertaking; PIPEDA applies regardless of province |
| **Quebec Law 25** (CQLR c. P-39.1) | **Yes — for Quebec drivers and Quebec operations** | Not compliant | ss. 3.1, 3.2, 3.3, 3.5, 3.8, 8, 9.1, 12, 12.1, 14, 17, 22, 23, 27, 28.1 | Mandatory PIA (s. 3.3); transfer PIA (s. 17); biometric DB declaration (Act to establish a legal framework for IT, s. 45) |
| *Act to establish a legal framework for information technology* (CQLR c. C-1.1) | **Yes — biometric DB** | Not compliant | s. 45 — declaration to CAI ≥ 60 days before service | **Highest-priority pre-launch action** |
| BC PIPA (SBC 2003, c. 63) | Generally pre-empted by PIPEDA for federal undertaking; provincial law may apply to ancillary processing | TBD | ss. 4, 5, 6, 10–11, 13(2), 23, 28–29, 33.1, 34, 35 | Confirm with counsel |
| Alberta PIPA (SA 2003, c. P-6.5) | Generally pre-empted by PIPEDA for federal undertaking; provincial law may apply to ancillary processing | TBD | ss. 5, 6, 7, 8, 11, 13, 13.1, 15, 28, 31, 34, 34.1, 35, 37.1 | Confirm with counsel |
| Ontario / PHIPA | No (no health-information custodian role) | N/A | — | — |
| GDPR | No EU presence identified | N/A | — | Re-confirm if EU drivers added |
| **Illinois BIPA** (740 ILCS 14) | Possibly — drivers transit Illinois | Not assessed | §§ 15(a)–(e) (notice, consent, retention, disclosure, security) | **Engage U.S. counsel** |
| Texas CUBI (Bus. & Com. Code § 503.001) | Possibly — drivers transit Texas | Not assessed | — | Engage U.S. counsel |
| Washington My Health My Data Act | Possibly — drivers transit Washington | Not assessed | — | Engage U.S. counsel |
| California CCPA/CPRA | Possibly — California-resident drivers TBD | Not assessed | — | Engage U.S. counsel |
| FMCSA (U.S. DOT) | Sector-specific; possible interaction | Not assessed | — | Confirm whether any FMCSA program drives this initiative |

### 5.2 Lawful Basis for Processing

| Processing Activity | Data Category | Lawful Basis (proposed) | Statutory Citation |
|---|---|---|---|
| Real-time impairment detection & automated intervention | Biometric chemistry; impairment score | **Express, informed consent** (employees) + **express written consent** (contractors); supported by reasonable employment-relationship necessity for employees | PIPEDA Sch. 1 Principle 4.3 / s. 6.1; Quebec Law 25 s. 12 / s. 14; Alberta PIPA s. 7, s. 15; BC PIPA s. 6, s. 13 |
| Disciplinary use of biometric event records | Flagged events, identifiers | Reasonable for managing the employment relationship + express consent (contractors) | Alberta PIPA s. 15, s. 18, s. 21; BC PIPA s. 13(2), s. 16(2), s. 19(2); PIPEDA Sch. 1 Principle 4.5 |
| Cross-border transfer to U.S. vendor | All categories | Accountability + comparable protection by contract; transfer-specific PIA in Quebec; written notice in Alberta | PIPEDA Sch. 1 Principle 4.1.3; Quebec Law 25 s. 17; Alberta PIPA s. 13.1 |
| Retention for legal hold | Flagged events | Documented legal/business need | PIPEDA Sch. 1 Principle 4.5.3; Quebec Law 25 s. 23; BC PIPA s. 35; Alberta PIPA s. 35 |
| Vendor model training (if pursued) | Biometric chemistry | **Not currently authorized**; would require fresh, separate consent | PIPEDA Sch. 1 Principle 4.5; Quebec Law 25 s. 12 |
| De-identified data sharing (if pursued) | De-identified records | Permissible only with robust de-identification and ongoing re-identification risk monitoring | Quebec Law 25 s. 23 (anonymization standard); PIPEDA Sch. 1 Principle 4.5 |

### 5.3 Individual Rights

| Right | Supported? | Mechanism | Statutory Basis | Notes |
|---|---|---|---|---|
| Access | Possibly (read-only via system) — to be confirmed | Vendor portal? — gap | PIPEDA s. 8 / Sch. 1 Principle 4.9 (30 days); Quebec Law 25 s. 27 (30 days); BC PIPA ss. 23, 28–29 (30 business days); Alberta PIPA s. 24, s. 28 (45 days) | Channel must be defined and timelines tracked |
| Correction | No defined channel | — | PIPEDA Sch. 1 Principle 4.9; Quebec Law 25 s. 28; BC PIPA s. 24; Alberta PIPA s. 25 | Required |
| Withdrawal of consent | Not designed (system is non-disableable) | — | PIPEDA Sch. 1 Principle 4.3.8; Quebec Law 25 s. 9; BC PIPA s. 9; Alberta PIPA s. 9 | Must be addressed; withdrawal cannot be illusory because the system cannot be disabled |
| Deletion | Not defined | — | Quebec Law 25 s. 28.1 | Required |
| Portability | Not defined | — | Quebec Law 25 s. 27 | Required for Quebec data subjects |
| **Objection to / human review of automated decision** | **No** | — | Quebec Law 25 s. 12.1; OPC ADM guidance | **Must be implemented** |

### 5.4 Privacy Notice / Policy
A general company privacy policy exists and mentions employees, but does not address biometric or in-cab monitoring. The current employee privacy notice has not been updated. **Both must be updated and published before pilot launch** (PIPEDA Sch. 1 Principle 4.8; Quebec Law 25 s. 3.2; Alberta PIPA s. 6; BC PIPA s. 5). The Privacy Officer's title and contact must be published on the website (Quebec Law 25 s. 3.1).

### 5.5 Vendor Agreements
Not yet executed. Confidentiality is likely to be included; cross-border restrictions, breach-notification timelines, audit rights, sub-processor controls, return/destruction, cooperation with rights requests are unconfirmed. **Comparable-protection obligation under PIPEDA Sch. 1 Principle 4.1.3 is not yet met. The contract must include the data-protection schedule outlined in Section 8.**

### 5.6 Mandatory PIA / DPIA Requirement
- **Quebec Law 25, s. 3.3** — mandatory PIA is triggered (acquisition/development of an information system involving sensitive PI).
- **Quebec Law 25, s. 17** — separate transfer-specific PIA for cross-border processing is required.
- **Act to establish a legal framework for information technology, s. 45** — biometric database declaration to the CAI required ≥ 60 days before deployment.
- **GDPR Art. 35** DPIA — not engaged (no GDPR trigger).
- **U.S. counsel** should advise whether any U.S. state biometric statutes require a written policy, retention schedule, or notice (e.g., Illinois BIPA § 15(a)).

### 5.7 Relevant Enforcement Decisions and Guidance (illustrative — not exhaustive; further legal research required)
- *Eastmond v. Canadian Pacific Railway*, 2004 FC 852 — workplace surveillance proportionality (necessity, effectiveness, proportionality, less-intrusive means).
- OPC PIPEDA Findings and joint investigations on workplace monitoring, GPS tracking, and biometric collection.
- OPC *Guidelines for Processing Personal Data Across Borders*.
- OPC *Guidance on inappropriate data practices: Interpretation and application of subsection 5(3)*.
- OIPC BC and OIPC AB orders on workplace surveillance, biometric collection, and cross-border transfers (further review recommended).
- Quebec CAI guidance on biometric databases and on s. 17 cross-border transfers.
- Illinois BIPA litigation (e.g., *Rosenbach v. Six Flags Entertainment Corp.*, 2019 IL 123186; *Cothron v. White Castle*, 2023 IL 128004) — high statutory damages exposure per scan.

**Action: obtain a focused legal-research memo on each of the above, scoped to fleet/transportation biometric monitoring.**

---

## Section 6 — Privacy by Design Assessment

| PbD Principle | Met? | Evidence / Notes |
|---|---|---|
| Proactive — privacy considered from the start | **No** | First formal review; pilot already imminent |
| Privacy by Default — most protective settings are default | **No** | Defaults not specified; required under Quebec Law 25 s. 9.1 for tech products/services offered to the public, and best practice elsewhere |
| Data Minimization | **No** | Continuous streaming, dual-modality, cloud retention, identifying linkage, expansive secondary use |
| Accuracy | **Partial / unknown** | False-positive risk from skin chemistry not yet addressed; vendor accuracy testing not reviewed |
| Access Controls | **Unknown** | Internal HR/Legal access stated; role-based controls and audit logs unconfirmed |
| Individual Rights | **Partial** | Possible read-only access; no correction, deletion, withdrawal, ADM-review channel |
| Accountability | **Partial** | Privacy Officer designated (acting); audit logs and breach response unconfirmed; vendor accountability unconfirmed |

**Overall Privacy by Design Rating: Inadequate (today).** Salvageable because design and build are still under way. Most items can be substantially addressed through the mitigations in Section 8 if acted upon now.

---

## Section 7 — Risk Register

Likelihood scale: 1 = Unlikely · 2 = Possible · 3 = Likely.
Impact scale: 1 = Minor inconvenience · 2 = Significant harm · 3 = Severe harm.
Risk Score = L × I. Risk Level: 1–2 Low · 3–4 Medium · 6–9 High.

| # | Risk Description | Category | L | I | Score | Level |
|---|---|---|---|---|---|---|
| R1 | Unlawful biometric collection in Quebec — pilot proceeds without CAI declaration (IT Framework Act, s. 45) and without transfer-specific PIA (Law 25, s. 17) | Regulatory | 3 | 3 | 9 | High |
| R2 | Failure of meaningful consent / proportionality for continuous workplace biometric surveillance — current notice plan (sticker + 1–2 weeks) is below the threshold under PIPEDA s. 6.1 / Sch. 1 Principle 4.3 and Alberta PIPA s. 15 / BC PIPA s. 13 | Regulatory / Individual | 3 | 3 | 9 | High |
| R3 | No human-in-the-loop review of automated decisions — inconsistent with Quebec Law 25 s. 12.1; risk of incorrect lockout/discipline with no redress | Individual / Regulatory | 3 | 3 | 9 | High |
| R4 | False positives from skin-chemistry sensor — medication, illness, sanitizer, environmental factors trigger lockout or discipline | Individual harm | 3 | 2 | 6 | High |
| R5 | U.S. CLOUD Act / cross-border exposure — U.S. vendor compelled to disclose Canadian driver biometric data to U.S. authorities | Regulatory / Individual | 2 | 3 | 6 | High |
| R6 | Unbounded secondary use — vendor model training, data sharing, insurance/police disclosure not disclosed to drivers | Regulatory | 3 | 2 | 6 | High |
| R7 | Inadequate vendor contract — sub-processor controls, breach-notification timelines, audit rights, return/destruction not confirmed | Regulatory / Operational | 3 | 2 | 6 | High |
| R8 | No defined retention rule for raw biometric data — open-ended retention violates PIPEDA Sch. 1 Principle 4.5 and Quebec Law 25 s. 23 | Regulatory | 3 | 2 | 6 | High |
| R9 | Contractor consent gap — contractors and contractor sub-employees not covered by employee-monitoring statutory shortcuts | Regulatory | 3 | 2 | 6 | High |
| R10 | Data breach at vendor or in transit — biometric data is a high-value target; no confirmed safeguards | Security / Individual | 2 | 3 | 6 | High |
| R11 | Re-identification / linkage risk from combined biometric + GPS + telematics + identity profile | Individual | 2 | 2 | 4 | Medium |
| R12 | Driver chilling effect / labour dispute — non-unionized employees may experience monitoring overreach | Reputational / Operational | 2 | 2 | 4 | Medium |
| R13 | U.S. state biometric statute exposure — Illinois BIPA, Texas CUBI, Washington MyHealth claims by drivers transiting those states | Regulatory / Litigation | 2 | 3 | 6 | High |
| R14 | Sensor tampering / spoofing — driver bypasses sensor; system integrity compromised | Security / Safety | 2 | 2 | 4 | Medium |
| R15 | Health-data inference — skin chemistry can reveal medication use, diabetic state, etc.; health PI processed without disclosure | Regulatory / Individual | 2 | 3 | 6 | High |

**Inherent (pre-mitigation) profile: 11 High, 4 Medium, 0 Low.**

---

## Section 8 — Mitigations and Residual Risk

| Risk # | Mitigation Measure | Owner | Target Date | Residual L | Residual I | Residual Score | Residual Level | Risk Accepted By |
|---|---|---|---|---|---|---|---|---|
| R1 | (a) File biometric-database declaration with CAI ≥ 60 days before any Quebec-driver data is captured; (b) complete Quebec Law 25 s. 3.3 mandatory PIA (this document satisfies in part); (c) complete Quebec Law 25 s. 17 transfer-specific PIA before any Quebec data leaves Quebec | General Counsel | Before any Quebec driver in pilot | 1 | 3 | 3 | Medium | General Counsel |
| R2 | (a) Replace 1–2 week notice with 30–60 day pre-deployment notice and consultation; (b) draft a layered privacy notice covering purposes, modalities, retention, recipients, cross-border, rights; (c) require an express acknowledgement signed by each employee driver and an express, separate consent from each contractor and contractor sub-employee; (d) document the proportionality analysis (necessity, effectiveness, proportionality, less-intrusive alternatives) per *Eastmond* | General Counsel + HR | Before pilot launch | 1 | 2 | 2 | Low | Privacy Officer |
| R3 | Implement a documented human-in-the-loop review path: (a) automated safety intervention (slowdown/lockout) may remain automatic; (b) any disciplinary or contractual use must require prior human review by a designated reviewer; (c) provide drivers a contestation channel with a defined response timeline (≤ 30 days); (d) publish ADM disclosure per Quebec Law 25 s. 12.1 | General Counsel + HR + Project Manager | Before pilot launch | 1 | 2 | 2 | Low | Privacy Officer |
| R4 | (a) Require vendor-published false-positive rates and validation methodology; (b) build a calibration / contestation protocol that does not impose discipline on the basis of a single positive reading absent corroborating evidence; (c) establish a medical-exception process (medications, conditions); (d) allow second-modality confirmation before lockout | Project Manager + Medical / HR Lead | Before pilot launch | 2 | 2 | 4 | Medium | Privacy Officer + Business Sponsor |
| R5 | (a) Encryption-at-rest with company-held keys where feasible (BYOK); (b) contract terms requiring vendor to challenge U.S. legal-process orders to the maximum extent permitted, and to notify the company unless legally barred; (c) disclose CLOUD Act exposure in the privacy notice | General Counsel + Vendor Owner | Before contract execution | 2 | 2 | 4 | Medium | Privacy Officer |
| R6 | (a) Lock down a closed list of permitted secondary uses; (b) prohibit vendor model training using the company's data unless separately and expressly consented; (c) prohibit sale or non-de-identified sharing; (d) define the law-enforcement-disclosure decision process (lawful authority, legal review) | General Counsel | Before contract execution | 1 | 2 | 2 | Low | Privacy Officer |
| R7 | Vendor contract must include a data-protection schedule covering: scope and purpose of processing; confidentiality; security measures (encryption, access controls, MFA, logging, SOC 2/ISO 27001 evidence); sub-processor list and pre-approval; cross-border restrictions; breach-notification within 24–48 hours; audit rights; return/destruction at end of term with certification; cooperation with data-subject rights requests; restriction on further use | General Counsel + Vendor Owner | Before contract execution | 1 | 2 | 2 | Low | Privacy Officer |
| R8 | Adopt a documented retention schedule: (a) raw chemistry signal retained for the shortest period needed to validate a reading (proposal: 24–72 hours unless an event is flagged); (b) computed scores retained for a defined period (proposal: 12 months unless an event is flagged); (c) flagged-event records retained per documented legal-hold policy; (d) automatic deletion verified by vendor certification | General Counsel + Project Manager | Before pilot launch | 1 | 2 | 2 | Low | Privacy Officer |
| R9 | (a) Build a separate contractor consent process distinct from the employee notice; (b) ensure contractor master services agreements include a flow-down obligation requiring contractors to obtain written consent from their own employees; (c) document refusal pathways (e.g., the contractor declines and is not engaged on company trucks) | General Counsel + Contractor Relationship Manager | Before pilot launch | 2 | 2 | 4 | Medium | Privacy Officer |
| R10 | Vendor must demonstrate a current SOC 2 Type II or ISO 27001 certification, encryption at rest and in transit, key management, MFA, audit logging, vulnerability management, and a documented incident-response plan; require breach notification to the company within 24 hours of detection | Security/IT Lead (to appoint) + Vendor Owner | Before pilot launch | 1 | 3 | 3 | Medium | Privacy Officer + Executive Sponsor |
| R11 | (a) Limit vendor-side identifiability to event flags; identifiable linkage held company-side only where possible; (b) review vendor data model for re-id risk; (c) restrict combined exports of biometric + GPS + telematics + identity to Legal-approved circumstances | Security/IT Lead + Vendor Owner | Before pilot launch | 1 | 2 | 2 | Low | Privacy Officer |
| R12 | (a) HR engagement and communication plan; (b) Q&A and an independent driver feedback channel; (c) commit to no monitoring data being used for non-safety performance management; (d) periodic program review with driver representatives | HR | Before pilot launch | 1 | 2 | 2 | Low | HR Lead |
| R13 | Engage U.S. counsel to assess Illinois BIPA, Texas CUBI, Washington My Health My Data Act, California CCPA/CPRA exposure; implement BIPA-style written policy, retention schedule, written informed consent, no-sale/no-disclosure, security obligations as a baseline across the U.S. footprint | General Counsel + U.S. Counsel | Before any U.S. driver data handling | 1 | 3 | 3 | Medium | General Counsel |
| R14 | (a) Vendor anti-tamper and anti-spoof controls described and tested; (b) in-cab device firmware integrity and secure update; (c) physical security on lost/stolen trucks; (d) sensor-bypass attempt logging and review | Security/IT Lead + Vendor Owner | Before pilot launch | 1 | 2 | 2 | Low | Security/IT Lead |
| R15 | (a) Disclose health-data inference risk in the privacy notice; (b) prohibit any use of the chemistry signal for non-impairment purposes; (c) build a medical-exception process; (d) ensure the data is treated as sensitive in all storage, access, and retention decisions | General Counsel + Medical / HR Lead | Before pilot launch | 1 | 2 | 2 | Low | Privacy Officer |

**Residual profile after mitigations are implemented as designed: 0 High, 5 Medium, 10 Low.**

**Unmitigated risks (if any):** None identified, provided the conditions in Section 9 are met. If the human-in-the-loop review path (R3) cannot be implemented before disciplinary or contractual use, R3 remains High and the program should not proceed to that downstream use.

---

## Section 9 — Recommendations

### 9.1 Overall Risk Level
**HIGH** as currently designed and on the current pilot timeline. **Reducible to Medium-with-tolerable-residuals** with the conditions below.

### 9.2 Recommended Decision

- [ ] Proceed
- [x] **Proceed with Conditions**
- [ ] Do Not Proceed

The initiative may proceed only after the following conditions are met. Conditions marked **[Pre-Pilot]** must be in place before any biometric data is captured from a driver in the pilot. Conditions marked **[Pre-Quebec]** must be in place before any data is captured from a driver who resides in or operates in Quebec. Conditions marked **[Pre-U.S.]** must be in place before any data is captured from a driver operating in the United States. Conditions marked **[Pre-Full-Rollout]** must be in place before fleet-wide deployment.

**[Pre-Quebec] Conditions:**
1. **CAI biometric-database declaration filed** under *Act to establish a legal framework for IT*, s. 45, ≥ 60 days before any Quebec driver data is captured.
2. **Quebec Law 25 s. 17 transfer-specific PIA completed** for the U.S. vendor processing chain.
3. **ADM disclosure and human-review path** in place per Law 25 s. 12.1.

**[Pre-Pilot] Conditions:**
4. **Privacy Officer appointed and published** (name, title, contact) on the company website, per Law 25 s. 3.1 and PIPEDA Sch. 1 Principle 4.1.
5. **Security/IT Lead appointed**.
6. **HR engaged**, with a 30–60 day driver consultation and notice period planned.
7. **Layered privacy notice** drafted, reviewed, and ready for publication.
8. **Express employee acknowledgement and contractor consent forms** drafted and reviewed.
9. **Documented retention schedule** with separate rules for raw signal, computed scores, and flagged events.
10. **Vendor contract executed** with the data-protection schedule described in R7, R6, R10.
11. **Vendor security evidence reviewed** (SOC 2 Type II or ISO 27001, encryption, MFA, logging, IR plan).
12. **Human-in-the-loop review path** documented, with a defined contestation channel and ≤ 30-day response timeline.
13. **False-positive / medical-exception process** documented.
14. **Threat model and security review** of in-cab device, transmission, and cloud architecture completed.
15. **Documented proportionality analysis** under PIPEDA workplace-surveillance jurisprudence, addressing necessity, effectiveness, proportionality, and less-intrusive alternatives.

**[Pre-U.S.] Conditions:**
16. **U.S. counsel review** of Illinois BIPA, Texas CUBI, Washington My Health My Data Act, and California CCPA/CPRA exposure, with a written compliance plan implemented.

**[Pre-Full-Rollout] Conditions:**
17. **Pilot retrospective**: data from the pilot reviewed for false-positive rate, contestation outcomes, and operational issues; mitigations adjusted before scaling.
18. **All conditions above re-confirmed at fleet scale.**
19. **Privacy notice and consent forms re-confirmed for any new jurisdictions** added to the rollout.

### 9.3 Priority Actions

| Priority | Action | Owner | Due Date |
|---|---|---|---|
| **Critical** | File CAI biometric-database declaration | General Counsel | ≥ 60 days before any Quebec-driver data |
| **Critical** | Execute vendor contract with data-protection schedule | General Counsel + Vendor Owner | Before pilot launch |
| **Critical** | Implement human-in-the-loop review for disciplinary/contractual use | General Counsel + HR + Project Manager | Before pilot launch |
| **Critical** | Draft and publish privacy notice; obtain employee acknowledgement and contractor consent | General Counsel + HR | 30–60 days before pilot launch |
| **High** | Engage U.S. counsel; implement BIPA-style baseline | General Counsel + U.S. Counsel | Before any U.S.-driver data |
| **High** | Appoint Security/IT Lead and complete threat model | Executive Sponsor | Before pilot launch |
| **High** | Adopt documented retention schedule | General Counsel + Project Manager | Before pilot launch |
| **High** | Document proportionality analysis | General Counsel | Before pilot launch |
| **High** | Vendor due-diligence: SOC 2/ISO 27001, encryption, IR plan, sub-processor list | Vendor Owner + Security/IT Lead | Before contract execution |
| **High** | Build false-positive / medical-exception process | Medical / HR Lead | Before pilot launch |
| **Medium** | Update general company privacy policy and Privacy Officer publication | General Counsel | Before pilot launch |
| **Medium** | Contractor MSA flow-down clauses | Contractor Relationship Manager + General Counsel | Before any contractor sub-employee in pilot |

### 9.4 PIA Review Trigger
This PIA must be revisited if any of the following occur:
- Material change to the biometric modality, sampling rate, or sensor type;
- Change of umbrella vendor or addition/change of sub-processors;
- Expansion to a new jurisdiction not covered by this assessment;
- Expansion of secondary use beyond the closed list approved under R6;
- Any confidentiality incident affecting the system;
- A change to the in-cab decision logic (e.g., adding new automated interventions);
- Adoption of any model-training or data-monetization use of the data.
- **Scheduled review date: no later than 12 months from approval, and earlier upon any of the above triggers.**

---

## Sign-Off

| Role | Name | Signature / Approval | Date |
|---|---|---|---|
| Privacy Officer (General Counsel, acting) | | | |
| Legal Counsel | | | |
| Business Sponsor (Project Manager) | | | |
| Executive Sponsor (HIGH risk requires this sign-off) | | | |
| Data Protection Authority — Quebec CAI | | (s. 45 declaration reference) | |

---

*This Privacy Impact Assessment was prepared as a structured analysis tool using artificial intelligence. It does not constitute legal advice. The organization should obtain advice from qualified Canadian privacy counsel, U.S. counsel for state biometric-statute exposure, and should engage with the Commission d'accès à l'information (Quebec) as required, before proceeding with high-risk processing activities.*

*Document version history should be maintained. Superseded versions should be archived, not deleted.*

---

## Appendix A — Open Gaps Requiring Follow-Up

| # | Gap | Owner | Target |
|---|---|---|---|
| G1 | Confirm whether an insurance mandate or premium-reduction program drives this initiative | Project Manager | Pre-pilot |
| G2 | Confirm Transport Canada / FMCSA driver/relevance | Project Manager | Pre-pilot |
| G3 | Inventory existing fleet monitoring (dashcams, ELD, GPS, fatigue) for cumulative-monitoring proportionality analysis | Project Manager | Pre-pilot |
| G4 | Confirm exact sensor outputs stored per event (raw signal, score, threshold flag, GPS, telematics) | Vendor Owner | Pre-contract |
| G5 | Confirm whether vendor stores data identifiably or only event flags | Vendor Owner | Pre-contract |
| G6 | Confirm vendor security posture (SOC 2 / ISO 27001, encryption, MFA, logging, IR plan) | Security/IT Lead | Pre-contract |
| G7 | Define retention rules for raw signal, scores, flagged events, and identity linkage | General Counsel | Pre-pilot |
| G8 | Confirm whether vendor model training is contemplated and whether it is to be permitted at all | General Counsel + Vendor Owner | Pre-contract |
| G9 | Identify the Project Manager, Security/IT Lead, Vendor Owner, and Contractor Relationship Manager by name | Executive Sponsor | Pre-pilot |
| G10 | Confirm publication of Privacy Officer name and contact on website | General Counsel | Pre-pilot |
| G11 | Identify and assess any U.S. driver-residency in Illinois, Texas, Washington, California (drives BIPA/CUBI/MyHealth/CPRA) | HR + U.S. Counsel | Pre-U.S. |
| G12 | Identify and assess fleet operations in additional Canadian provinces requiring substantively-similar review (BC, AB ancillary applicability) | General Counsel | Pre-pilot |
| G13 | Confirm whether driver access portal is read-only, and whether it returns all categories required under PIPEDA Sch. 1 Principle 4.9 | Vendor Owner | Pre-pilot |
| G14 | Define formal incident-response and breach-notification process integrated with vendor obligations | Security/IT Lead | Pre-pilot |
| G15 | Document the proportionality analysis under *Eastmond* and OPC workplace-monitoring guidance | General Counsel | Pre-pilot |
