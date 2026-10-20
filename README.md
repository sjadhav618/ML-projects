# Clinical NLP & Regulatory Data Science Pipeline

A modular machine learning framework designed to bridge the gap between messy, unstructured clinical text and rigorous regulatory standards. This repository reflects my hands-on experience in **Clinical Data Management, Data Architecture, and Pharmacovigilance**, specifically translating clinician notes and case report forms into structured, actionable insights.

The final product has a personal health agent that extracts drug names from clinical notes and flags likely side effects and drug–drug interactions, so patients can monitor related conditions.

---

## Why I Built This
Working extensively with clinical trials and real-world medical data, I saw firsthand how much critical information gets locked away in unstructured text—from doctor's notes to patient narratives. Standardizing these inputs traditionally requires heavy manual coding or disjointed tools. 

Drawing from my professional background working with **MedDRA** (for adverse event and symptom coding; not included in this repo as it sits as separate collaborative work) and **WHO Drug** (for harmonizing disparate trade and brand names into standardized active ingredients), I wanted to build a clean, transparent, and modular pipeline. This repository demonstrates how schema-first extraction can automate clinical coding and power intelligent, patient-centric applications safely.

---

## Core Modules & Architecture

### 1. Medication Coding Engine (WHO Drug-Aligned)
* **Objective:** Detect commercial brand names, trade names, and prescription instructions from clinical free text.
* **Standardization:** Aligned with **WHO Drug** data models, mapping reported verbatim trade/brand names to standardized generic active ingredients, ensuring robust concomitant medication (`CM` domain) tracking for clinical trials.

### 2. Pharmacovigilance & Side Effect Knowledge Base
* **Objective:** Link extracted brand and generic drug names to known adverse drug reactions (ADRs) and safety profile datasets (such as openFDA labeling data and clinical trial safety summaries).

### 3. Patient-Facing Safety Agent
* **Objective:** An intelligent, guardrailed agent designed to interact with patients. Given a specific brand name medication, the agent retrieves validated side-effect profiles and presents them in accessible, patient-friendly language while reinforcing clinical safety guidelines.

---

## Tech Stack & Standards
* **Language:** Python 3.x
* **Data Validation & Schemas:** Pydantic (strict schema enforcement for LLM outputs)
* **Tabular Processing:** Pandas (exporting datasets into regulatory-ready CSV / CDISC-aligned structures)
* **Machine Learning / LLM Framework:** Prompt engineering, structured generation, and agentic retrieval patterns.

---

## Repository Structure
```text
ML-projects/
│
├── data/                    # Sample clinical notes and mock datasets
├── schemas/                 # Pydantic models for structured clinical extraction
├── extractors/              # MedDRA symptom & WHO Drug brand-matching engines
├── agent/                   # Patient-facing side-effect retrieval agent
├── outputs/                 # Exported regulatory CSV datasets (CDISC / SDTM inspired)
└── README.md                # Repository documentation
