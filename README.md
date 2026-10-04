# VirtualWorks-Task-5---Individual-Case-Safety-Report-ICSR-
# Task 5: Individual Case Safety Report (ICSR) Processing

## Overview
This repository contains the comprehensive documentation and applied case processing simulation for **Task 5: Individual Case Safety Report (ICSR)** as part of the Pharmacovigilance Internship Program at VirtualWorks.

This project covers the full lifecycle of ICSR processing—from triage and validity checks to data entry, MedDRA/WHODrug coding, causality assessment, severity classification, and E2B regulatory submission.

---

## 1. ICSR Processing Workflow Lifecycle

The end-to-end lifecycle of an ICSR consists of six key stages:

1. **Triage & Validity Assessment:**
   - Verify the 4 minimum criteria required for a valid ICSR:
     1. Identifiable Reporter
     2. Identifiable Patient
     3. At least one Suspect Drug
     4. At least one Adverse Event
   - Determine regulatory reporting timelines based on event seriousness (e.g., 7-day or 15-day expedited reporting).

2. **Data Entry & Case Creation:**
   - Log administrative details, patient demographics, medical history, concomitant drugs, suspect drug administration (dose, route, timing), and narrative into the safety database.

3. **Medical Coding (MedDRA & WHODrug):**
   - **MedDRA:** Standardize adverse event terms (LLT $\rightarrow$ PT $\rightarrow$ SOC).
   - **WHODrug:** Standardize trade/brand names to official active ingredients.

4. **Causality & Severity Assessment:**
   - Classify event severity (Mild, Moderate, Severe) and regulatory seriousness (Death, Hospitalization, Disability, etc.).
   - Evaluate causal linkage using validated criteria (Naranjo Algorithm or WHO-UMC scale).

5. **Quality Control (QC) & Medical Review:**
   - Perform source document verification and medical evaluation by a Drug Safety Physician/Associate.

6. **Regulatory Submission:**
   - Format and transmit standardized XML files via **E2B(R2) / E2B(R3)** standards to regulatory bodies (e.g., FDA, EMA).

---

## 2. Simulated Case Study Processing

### A. Case Background & Narrative
* **Patient:** 48-year-old male (Initials: R.K., DOB: 12-May-1978).
* **Reporter:** Attending Physician (Dr. S. Mehta, City Hospital).
* **Suspect Medication:** Ciprofloxacin 500 mg oral tablet BD (Indication: Complicated UTI; Start Date: 10-Aug-2026).
* **Concomitant Medication:** Paracetamol 650 mg PRN.
* **Adverse Reaction:** Developed severe Achilles tendon pain and swelling on 14-Aug-2026. Diagnosed with Acute Tendonitis/Tendon Rupture Risk on 15-Aug-2026. Drug discontinued immediately on 15-Aug-2026. Symptoms improved significantly by 20-Aug-2026 (Positive Dechallenge).

---

### B. Four Minimum Validity Criteria Check

| Criterion | Details Present in Case | Validation Status |
|---|---|:---:|
| **Identifiable Reporter** | Dr. S. Mehta (Physician) | **VALID** |
| **Identifiable Patient** | R.K., 48-year-old Male | **VALID** |
| **Suspect Drug** | Ciprofloxacin 500 mg | **VALID** |
| **Adverse Event** | Achilles Tendonitis / Tendon Pain | **VALID** |

* **Overall Case Status:** **Valid ICSR**

---

### C. Medical Coding

| Field Type | Reported Term | Standardized Code / Term | Coding System |
|---|---|---|---|
| **Suspect Drug** | Ciprofloxacin 500 mg | Ciprofloxacin Hydrochloride | WHODrug |
| **Adverse Event** | Achilles tendon pain & swelling | Achilles Tendonitis | MedDRA (Preferred Term) |
| **System Organ Class** | Musculoskeletal System | Musculoskeletal and connective tissue disorders | MedDRA (SOC) |

---

### D. Seriousness & Causality Evaluation

* **Seriousness Classification:** **Serious** (Medically Important Event / Risk of Disability).
* **Expectedness:** **Expected / Labeled** (Fluoroquinolone-induced tendonitis is a known black-box warning).
* **Naranjo Algorithm Evaluation:**
  * Known reaction (+1)
  * Temporal relationship (+2)
  * Positive Dechallenge (+1)
  * No alternative causes (+1)
  * **Total Score:** **7 / 10** $\rightarrow$ **Probable**
* **WHO-UMC Rating:** **Probable / Likely**

---

## 3. Standardized ICSR Case Summary Form

```text
================================================================================
                    INDIVIDUAL CASE SAFETY REPORT (ICSR)
================================================================================

[SECTION A: ADMINISTRATIVE & REPORTER DETAILS]
Safety Report ID: SR-2026-CFX-00912
Initial/Follow-up: Initial
Source: Health Professional (Physician)
Reporter Name: Dr. S. Mehta
Facility: City Hospital, Department of Nephrology

[SECTION B: PATIENT INFORMATION]
Patient ID: R.K.
Age: 48 Years
Gender: Male
Medical History: No prior history of tendon disorders or fluoroquinolone toxicity.

[SECTION C: SUSPECT DRUG DETAILS]
Drug Name: Ciprofloxacin
Dose: 500 mg
Route: Oral
Frequency: Twice Daily (BD)
Indication: Complicated Urinary Tract Infection (UTI)
Start Date: 10-Aug-2026
Stop Date: 15-Aug-2026
Action Taken: Drug Discontinued

[SECTION D: ADVERSE EVENT & OUTCOME DETAILS]
Adverse Event (Verbatim): Severe Achilles tendon pain and swelling
MedDRA PT: Achilles Tendonitis
MedDRA SOC: Musculoskeletal and connective tissue disorders
Event Onset Date: 14-Aug-2026
Seriousness: Serious (Medically Important Event)
Causality Assessment: Probable (Naranjo Score: 7)
Outcome: Recovering / Resolved (as of 20-Aug-2026)

================================================================================
